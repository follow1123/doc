import CodeBlock from '@theme/CodeBlock';

# 锁/InnoDB引擎

* 锁是计算机协调多个进程或线程并发访问某一资源的机制
* 在数据库中，除传统的计算资源（CPU、RAM、I/O）的争用以外，数据也是一种供许多用户共享的资源
* 如何保证数据并发访问的一致性、有效性是所有数据库必须解决的一个问题，锁冲突也是影响数据库并发访问性能的一个重要因素
* MySQL中的锁，按照锁的粒度分，分为以下三类：
    * **全局锁** - 锁定数据库中的所有表
    * **表级锁** - 每次操作锁住整张表
    * **行级锁** - 每次操作锁住对应的行数据

## 测试数据account表

```sql
create table account(
    id int auto_increment primary key comment '主键',
    name varchar(10) comment '姓名',
    money int comment '余额'
) comment '账户表';

insert into account values (null, 'zhangsan', 2000), (null, 'lisi', 2000);
```

## 全局锁

* 全局锁就是对整个数据库实例加锁，加锁后整个实例就处于只读状态，后续的DML的写语句，DDL语句，
以及更新操作的事务提交语句都将被阻塞
* 其典型的使用场景是做全库的逻辑备份，对所有的表进行锁定，从而获取一致性视图，保证数据的完整性

### 测试使用全局锁后备份

* 打开两个命令行窗口
* 左边是使用`mysql -uusername -p`登录的session
* 右边是命令行终端

<div class="v-codeblock-root">
    <CodeBlock className="v-codeblock-left" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 以下操作按左右框内的序号执行

-- 1. 开启全局锁
flush tables with read lock;

-- 3. 释放锁
unlock tables;`
        }</CodeBlock>
    <CodeBlock className="v-codeblock-right" language="bash">{
`# 2. 使用mysqldump备份数据库，如果是备份远程的MySQL仓库，则加上-h参数指定ip
mysqldump -uusername -ppassword databasename > filename.sql`
        }</CodeBlock>
</div>

* 在不加锁的情况下完成备份可以使用`mysqldump`命令时添加`--single-transaction`参数

```sql
mysqldump --single-transaction -uusername -ppassword databasename > filename.sql
```

### 全局锁问题

* 如果在主库上备份，那么在备份期间都不能执行更新，业务基本上就得停摆
* 如果在从库上备份，那么在备份期间从库不能执行主库同步过来的二进制日志（binlog） ，会导致主从延迟

## 表级锁

* 表级锁，每次操作锁住整张表。锁定粒度大，发生锁冲突的概率最高，并发度最低
* 应用在MyISAM、InnoDB、BDB等存储引擎中
* 表级锁主要分为三类：**表锁**、**元数据锁（meta data lock，MDL）**、**意向锁**

### 表锁

* 表锁分为：**表共享读锁（read lock）** **表独占写锁（write lock）**

```sql
-- 加锁
lock tables 表名... read/write;

-- 释放锁，可以执行以下SQL或客户端断开连接
unlock tables;
```

#### 表共享读锁

* 打开两个命令行窗口，使用`mysql -uusername -p`分别登录两个session
* 使用[测试数据account表](#测试数据account表)

<div class="v-codeblock-root">
    <CodeBlock className="v-codeblock-left" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 给account表添加readlock
lock tables account read;

-- 执行查询操作，可以正常查询
select * from account where id = 1;

-- 执行修改操作，报错ERROR 1099 (HY000): Table 'account' was locked with a READ lock and can't be updated
update account set money = 1000 where id = 1;`
        }</CodeBlock>
    <CodeBlock className="v-codeblock-right" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 执行查询操作，可以正常查询
select * from account where id = 1;

-- 执行修改操作，阻塞，直到account的表锁被释放后执行
update account set money = 2000 where id = 1;`
        }</CodeBlock>
</div>

* 测试发现给account表添加**表共享读锁**的session和其他session都只能对account表进行查询操作，无法进行修改操作

#### 表独占写锁

* 打开两个命令行窗口，使用`mysql -uusername -p`分别登录两个session
* 使用[测试数据account表](#测试数据account表)

<div class="v-codeblock-root">
    <CodeBlock className="v-codeblock-left" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 给account表添加writelock
lock tables account write;

-- 执行查询操作，可以正常查询
select * from account where id = 1;

-- 执行修改操作，可以正常修改
update account set money = 1000 where id = 1;`
        }</CodeBlock>
    <CodeBlock className="v-codeblock-right" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 执行查询操作，阻塞，直到account的表锁被释放后执行
select * from account where id = 1;

-- 执行修改操作，阻塞，直到account的表锁被释放后执行
update account set money = 2000 where id = 1;`
        }</CodeBlock>
</div>

* 测试发现给account表添加**表独占写锁**的session可以对account表进行读写操作，其他session不能对account表进行读写操作

### 元数据锁

* MDL加锁过程是系统自动控制，无需显式使用，在访问一张表的时候会自动加上
* MDL锁主要作用是维护表元数据的数据一致性，在表上有活动事务的时候，不可以对元数据进行写入操作，为了避免DML与DDL冲突，保证读写的正确性
* 在MySQL5.5中引入了MDL, 当对一张表进行增删改查的时候，加MDL读锁（共享）；当对表结构进行变更操作的时候，加 MDL 写锁（排他）。

| SQL    | 锁类型    | 说明    |
|---------------- | --------------- | --------------- |
| `lock tables xxx read/write`    | SHARED_READ_ONLY/SHARED_NO_READ_WRITE    |     |
| `select、select .. lock in share mode`    | SHARED_READ   | 与SHARED_READ、SHARED_WRITE兼容，与EXCLUSIVE互斥    |
| `insert、update、delete、select ... for update` | SHARED_WRITE   | 与SHARED_READ、SHARED_WRITE兼容，与EXCLUSIVE互斥    |
| `alter table ...` | EXCLUSIVE | 与其他的MDL都互斥 |

* 查看元数据加锁情况：`select object_type, object_schema, object_name, lock_type, lock_duration from performance_schema.metadata_locks;`

#### 测试

* 使用[测试数据account表](#测试数据account表)

<div class="v-codeblock-root">
    <CodeBlock className="v-codeblock-left" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 以下操作按左右框内的序号执行

-- 1. 开启事务
begin;

-- 2. 查询account表
select * from account;

-- 4. 提交事务
commit;`
        }</CodeBlock>
    <CodeBlock className="v-codeblock-right" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 3. 添加字段
-- 此时由于account表的元数据在前面的事务内添加了共享锁，与排他锁互斥
-- 等待事务提交后才会执行
alter table account add age int;

-- 5. 此时查询表，字段添加成功
select * from account;`
        }</CodeBlock>
</div>

### 意向锁

* 在事务内执行更新操作时，会对更新的数据行加上行锁，此时如果需要给这种表加锁就需要判断一行一行判断里面的数据是否有加锁，
这种情况下效率较低
* 为了避免DML在执行时，加的行锁与表锁的冲突，在InnoDB中引入了意向锁，使得表锁不用检查每行数据是否加锁，使用意向锁来减少表锁的检查
* 意向锁分为以下两种：
    * **意向共享锁（IS）** - 由语句`select ... lock in share mode`添加，与表锁共享锁（read）兼容，与表锁排他锁（write）互斥
    * **意向排他锁（IX）** - 由`insert、update、delete、select ... for update`添加，与表锁的共享锁和排他锁都互斥，意向锁之间不会互斥
* 查看**意向锁**和**行锁**加锁情况：`select object_schema, object_name, index_name, lock_type, lock_mode, lock_data from performance_schema.data_locks;`
* 使用[测试数据account表](#测试数据account表)

<div class="v-codeblock-root">
    <CodeBlock className="v-codeblock-left" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 以下操作按左右框内的序号执行

-- 1. 开启事务，测试意向共享锁
begin;

-- 2. 查询account表，手动添加意向共享锁
select * from account where id = 1 lock in share mode;

-- 4. 提交事务
commit;

-- 6. 开启事务，测试意向排他锁
begin;

-- 7. 修改account表id为1的数据，此时会自动加上共享排他锁
update account set money = 500 where id = 1;

-- 提交事务
commit;`
        }</CodeBlock>
    <CodeBlock className="v-codeblock-right" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 3. 给account表添加read锁
-- 由于account表id为1的数据添加了行锁，这个表也添加了意向共享锁
-- 而意向共享锁与表共享锁兼容，所以SQL正常执行
lock table account read;

-- 3.1. 如果是给account表添加write锁
-- 由于account表id为1的数据添加了行锁，这个表也添加了意向共享锁
-- 而意向共享锁与表排他锁互斥，所以SQL会阻塞，直到之前的事务提交
lock table account write;

-- 5. 释放表锁
unlock tables;

-- 8. 由于account表添加的是意向排他锁，意向排他锁与表共享锁和排他锁都互斥
-- 所以现在无论加表共享锁还是排他锁都会阻塞
lock table account read;

-- 释放表锁
unlock tables;`
        }</CodeBlock>
</div>

## 行级锁

* 行级锁，每次操作锁住对应的行数据。锁定粒度最小，发生锁冲突的概率最低并发度最高，应用在InnoDB存储引擎中
* InnoDB的数据是基于索引组织的，行锁是通过对索引上的索引顶加锁来实现的，而不是对记录加的锁。主要分为以下三类：
    * **行锁（Record Lock ）** - 锁定单个行记录的锁，防止其他事务对此行进行update和delete，在RC、RR隔离级别下都支持
    * **间隙锁（Gap Lock）** - 锁定索引记录间隙〈不含该记录），确保索引记录间隙不变，防止其他事务在这个间隙进行insert，产生幻读，在RR隔离级别下都支持
    * **临键锁（Next-Key Lock）** - 行锁和隙锁组合，同时锁住数据，并锁住数据前面的间隙Gap，在RR隔离级别下支持

### 行锁

* InnoDB实现了以下两种类型的行锁：
    * **共享锁（S）** - 允许一个事务去读一行，阻止其他事务获得相同数据集的排它锁
    * **排他锁（x）**- 允许获取排他锁的事务更新数据，阻止其他事务获得相同数据集的共享锁和排他锁
* 两个事务要给同一行加锁的情况下，只有两个事务加的都是**共享锁**才能执行成功，如果其中任意一个事务加的是**排他锁**，另一个事务都会阻塞
    * 可以将**共享锁**理解为`true`，**排他锁**理解为`false`，两个事务之间的关系是**与**

| SQL    | 行锁类型    | 说明    |
|---------------- | --------------- | --------------- |
| `INSERT ...`    | 排他锁    | 自动加锁    |
| `UPDATE ...`    | 排他锁    | 自动加锁    |
| `DELETE ...`    | 排他锁    | 自动加锁    |
| `SELECT ...`    | 不加任何锁    |     |
| `SELECT ... LOCK IN SHARE MODE`    | 共享锁    | 需要手动在SELECT之后加LOCK IN SHARE MODE    |
| `SELECT ... FOR UPDATE`    | 排他锁    | 需要手动在SELECT之后加FOR UPDATE |

* 默认情况下，InnoDB在REPEATABLE READ事务隔离级别运行，InnoDB使用next-key锁进行搜索和索引扫描，以防止读
* 针对唯一索引进行检索时，对已存在的记录进行等值匹配时，将会自动优化为行锁
* InnoDB的行锁是针对于索引加的锁，不通过索引条件检索数据，那么InnoDB将对表中的所有记录加锁，此时就会**升级为表锁**
* 查看**意向锁**和**行锁**加锁情况：`select object_schema, object_name, index_name, lock_type, lock_mode, lock_data from performance_schema.data_locks;`

#### 测试行锁兼容情况

* 两个事务对同一行数据添加共享锁情况
* 使用[测试数据account表](#测试数据account表)

<div class="v-codeblock-root">
    <CodeBlock className="v-codeblock-left" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 以下操作按左右框内的序号执行

-- 1. 开启事务，测试意向共享锁
begin;

-- 2. 查询account表，手动添加共享锁
select * from account where id = 1 lock in share mode;

-- 提交事务
commit;`
        }</CodeBlock>
    <CodeBlock className="v-codeblock-right" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 3. 开启事务
begin;

-- 4. 查询account表，手动添加共享锁
-- 由于两个事务对id为1的数据添加的都是共享锁
-- 所以都正常执行
select * from account where id = 1 lock in share mode;

-- 提交事务
commit;`
        }</CodeBlock>
</div>

* 一个事务添加共享锁，一个事务添加排他锁情况
* 使用[测试数据account表](#测试数据account表)

<div class="v-codeblock-root">
    <CodeBlock className="v-codeblock-left" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 以下操作按左右框内的序号执行

-- 1. 开启事务，测试意向共享锁
begin;

-- 2. 查询account表，手动添加共享锁
select * from account where id = 1 lock in share mode;

-- 提交事务
commit;`
        }</CodeBlock>
    <CodeBlock className="v-codeblock-right" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 3. 开启事务
begin;

-- 4. 修改id为1的数据，此时会自动添加排他锁
-- 由于之前的事务已经添加了共享锁，共享锁和排他锁不兼容
-- 所以会阻塞
update account set money = 1000 where id = 1;

-- 提交事务
commit;`
        }</CodeBlock>
</div>


#### 测试行锁升级为表锁的情况

* 需要保证测试表处主键索引之外没有其他索引
* 使用[测试数据account表](#测试数据account表)
* 这个情况需要对检索数据的字段添加索引解决

<div class="v-codeblock-root">
        <CodeBlock className="v-codeblock-left" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 以下操作按左右框内的序号执行

-- 1. 开启事务，测试意向共享锁
begin;

-- 2. 查询account表，由于修改时没有使用到索引，所以行锁升级为了表锁
update account set name = 'zs' where name = 'zhangsan';

-- 提交事务
commit;`
        }</CodeBlock>
    <CodeBlock className="v-codeblock-right" language="sql">{
`-- 使用指定的数据库
use db_name;

-- 3. 开启事务
begin;

-- 4. 由于上面的事务修改时将行锁升级为了表锁，此时更新其他id的数据也会阻塞
update account set name = 'ls' where id = 2;

-- 提交事务
commit;`
        }</CodeBlock>
</div>
