# Java基础

> [官方文档](https://docs.oracle.com/javase/tutorial/reallybigindex.html)</br>
> [详细代码地址](https://github.com/follow1123/java-basics)

## 目录
1. <a href="#comments">注释</a>
2. <a href="#variables">变量</a>
    1. <a href="#variables-data-type">数据类型</a>
        1. <a href="#variables-auto-type-promotion">基本数据类型的自动类型提升</a>
        2. <a href="#variables-type-conversion">基本数据类型的强制类型转换</a>
        3. <a href="#data-type-float">Float</a>
        4. <a href="#data-type-string">String</a>
3. <a href="#base">进制</a>
    1. <a href="#base-conversion-table">进制之间的换算</a>
    2. <a href="#base-conversion">二进制转换</a>
        1. <a href="#binary-to-decimal">二进制转十进制</a>
        2. <a href="#decimal-to-binary">十进制转二进制</a>
        3. <a href="#binary-octal-and-hexadecimal">二进制与八进制、十六进制之间的转换</a>
4. <a href="#operators">运算符</a>
    1. <a href="#arithmetic-operators">算数运算符</a>
    2. <a href="#assignment-operators">赋值运算符</a>
    3. <a href="#comparison-operators">比较（关系）运算符</a>
    4. <a href="#logical-operators">逻辑运算符</a>
    5. <a href="#bitwise-operators">位运算符</a>
        1. <a href="#left-shift">左移</a>
        2. <a href="#right-shift">右移</a>
        3. <a href="#unsigned-right-shift">无符号右移</a>
        4. <a href="#and-or-xor-not">与、或、异或、取反</a>
    6. <a href="#conditional-operators">条件运算符（三元运算符）</a>
5. <a href="#control-flow">流程控制</a>
    1. <a href="#if-else">if...else</a>
    2. <a href="#switch-case">switch-case</a>
    3. <a href="#loop-structure">循环结构</a>
        1. <a href="#for-loop">for循环</a>
        2. <a href="#while-loop">while循环</a>
        3. <a href="#do-while-loop">do-while循环</a>
        4. <a href="#infinite-loop">无限循环</a>
        5. <a href="#break-and-contiune">break和continue关键字</a>
6. <a href="#arrays">数组</a>
    1. <a href="#one-dimensional-array">一维数组</a>
    2. <a href="#two-dimensional-array">二维数组</a>
    3. <a href="#array-related-operations">数组相关操作</a>
        1. <a href="#array-max">最大值</a>
        2. <a href="#array-minimum">最小值</a>
        3. <a href="#array-sum">求和</a>
        4. <a href="#array-average">平均数</a>
        5. <a href="#array-pascal-triangle">杨辉三角</a>
        6. <a href="#array-number-of-loops">回形数</a>
        7. <a href="#array-reverse">数组翻转</a>
        8. <a href="#array-scaling">数组扩容</a>
    4. <a href="#array-algorithm">数组相关算法</a>
        1. <a href="#array-linear-search">线性查找</a>
        2. <a href="#array-binary-search">二分查找</a>
        3. <a href="#array-bubble-sort">冒泡排序</a>
        4. <a href="#array-quick-sort">快速排序</a>
    5. <a href="#array-utils">Arrsys工具类</a>
7. <a href="#object-oriented">面向对象</a>
    1. <a href="#oop-field">属性（成员变量）和局部变量</a>
        1. <a href="#oop-member-variables-and-local-variables">成员变量和局部变量的区别</a>
    2. <a href="#oop-method">方法（Method）</a>
        1. <a href="#oop-return-keyword">return关键字</a>
        2. <a href="#oop-variable-parameters">可变个数形参的方法(jdk5)</a>
        3. <a href="#oop-method-value-passing-mechanism">方法的值传递机制</a>
        4. <a href="#oop-recursive-methods">递归方法</a>
    3. <a href="#oop-package-and-import">package和import</a>
    4. <a href="#oop-encapsulation">封装性（Encapsulation）</a>
        1. <a href="#oop-permission-modifiers">权限修饰符</a>
        2. <a href="#oop-constructor">构造器（constructor）</a>
        3. <a href="#oop-assignment-process">类中属性赋值过程</a>
        4. <a href="#oop-java-bean">JavaBean</a>
        5. <a href="#oop-this-keyword">this关键字</a>
    9. <a href="#oop-inheritance">继承（inheritance）</a>
        1. <a href="#oop-methods-override">方法的重写（override）</a>
        2. <a href="#oop-super-keyword">super关键字</a>
    10. <a href="#oop-polymorphism">多态性（Polymorphism）</a>
        1. <a href="#oop-upward-and-downward-transformation">向上转型和向下转型</a>
    11. <a href="#oop-object-class">Object类</a>
        1. <a href="#oop-object-equals">equals()方法</a>
        2. <a href="#oop-object-tostring">toString()方法</a>
        3. <a href="#oop-object-clone-finalize">clone()和finalize()方法</a>
    12. <a href="#oop-static-keyword">static关键字</a>
        1. <a href="#oop-static-field">static修饰属性</a>
        2. <a href="#oop-static-method">static修饰方法</a>
    13. <a href="#oop-code-block">代码块</a>
    14. <a href="#oop-final-keyword">final关键字</a>
    15. <a href="#oop-abstract-keyword">abstract关键字（抽象类或抽象方法）</a>
    16. <a href="#oop-interface">interface（接口）</a>
        1. <a href="#oop-interface-features">接口新特性</a>
    17. <a href="#oop-inner-class">内部类（InnerClass）</a>
    18. <a href="#oop-enum-class">枚举类</a>
    19. <a href="#oop-annotation">注解（Annotation）</a>
        1. <a href="#oop-meta-annotation">元注解</a>
    20. <a href="#oop-wrapper">包装类</a>
        1. <a href="#oop-basic-data-and-wrapper-class">基本数据类型与包装类型之间的转换</a>
            1. <a href="#oop-basic-data-to-wrapper-class">基本数据类型转包装类</a>
            2. <a href="#oop-wrapper-class-to-basic-data">包装类转基本数据类型</a>
            3. <a href="#oop-auto-boxing-unboxing">自动装箱和拆箱（jdk5）</a>
        2. <a href="#oop-string-to-basic-data-and-wrapper-class">String与基本数据类型和包装类型之间的转换</a>
        3. <a href="#oop-auto-boxing-issues">自动装箱相关问题</a>
            1. <a href="#oop-wrapper-cache-object">包装类缓存对象</a>
8. <a href="#exceptions">异常处理</a>
    1. <a href="#compile-time-and-runtime-exception">编译时异常和运行时异常</a>
    2. <a href="#java-exception-handing">Java异常的处理</a>
        1. <a href="#try-catch-finally">捕获异常（try-catch-finally）</a>
        2. <a href="#throws">抛出异常（throws）</a>
        3. <a href="#exceptions-choice">两种异常处理方式的选择</a>
    3. <a href="#throwing-exception-manually">手动抛出异常</a>
    4. <a href="#custom-exception">自定义异常</a>

## JDK和JRE

* **JDK**(Java Development Kit)：是Java程序开发工具包，包含JRE和开发人员使用工具
* **JRE**(Java Runtime Environment)：是Java程序的运行时环境，包含JVM和运行时所下需要的核心库
* java长期支持版本8、11、17、21
* 使用包管理器或压缩包安装

## Hello World

* 找一个目录，新建一个`HelloWorld.java`文件
* 使用`javac HelloWorld.java`命令编译文件生成`HelloWorld.class`文件
* 使用`java HelloWorld`命令执行

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```
<a id="comments"></a>
## 注释

* 使用`javadoc -encoding UTF-8 -author -version -d comment Comments.java`生成对应文档

```java
/**
 * 文档注释
 * @author a
 * @version 1.0
 */
public class Comments {

    /*
    多行注释
    多行注释
    多行注释
    */
    public static void main(String[] args) {
        // 单行注释
        System.out.println("Hello World!");
    }
}
```

<a id="variables"></a>
## 变量

<a id="variables-data-type"></a>
### 数据类型

| 数据类型    | 默认值    | 范围    | 占用存储空间 |
|---------------- | --------------- | --------------- | --- |
| byte    | 0    | -128~127    | 1字节=8bit |
| short    | 0    | -32,768~32,767    | 2字节 |
| int    | 0    | -2^31~2^31-1    | 4字节 |
| long    | 0L    | -2^63~2^63-1    | 8字节 |
| <a href="#data-type-float">float</a> | 0.0f    | -3.403E38~3.403E38(3.403E38表示3.403x10^38)    | 4字节 |
| double    | 0.0d    | -1.798E308~1.798E308 | 8字节 |
| char    | '\u0000'    | '\u0000'~'\uffff'| 2字节 |
| boolean    | false    | true/false | 根据JVM规范 |

* 代码示例

```java
boolean result = true;

char c1 = 'C';
char c2 = 65; // 等同于A
char c3 = '\u221a'; // 等同于√
char c4 = '\t'; // 制表符

byte b = 100;
short s = 10000;
int i = 100000;

// 数值较大可以使用下划线分割
long creditCardNumber = 1234_5678_9012_3456L;
long socialSecurityNumber = 999_99_9999L;
float pi =  3.14_15F;
long hexBytes = 0xFF_EC_DE_5E; // 十六进制表示
long hexWords = 0xCAFE_BABE;
long maxLong = 0x7fff_ffff_ffff_ffffL;
byte nybbles = 0b0010_0101; // 二进制表示
long bytes = 0b11010010_01101001_10010100_10010010;
double d = 1.797E308; // 科学计数法表示
```

<a id="variables-auto-type-promotion"></a>
#### 基本数据类型的自动类型提升

```mermaid
flowchart LR
a(byte,short,char) --> b(int)
b --> c(long)
c --> d(float)
d --> e(double)
```

* 范围小的数据类型默认可以赋值给范围大的数据类型
* 其中byte,short,char之间相互操作后的结果默认是int类型，由于这三个数据类型的范围太小，
相互操作很可能超出范围
* 整型字面量默认是int类型，浮点型字面量默认是double类型

```java
int i1 = 100;
long l1 = i1;
float f1 = l1;
double d1 = f1;


byte b1 = 1;
// byte b2 = b1 + 1; // 编译不通过
int i2 = b1 + 1;

short s1 = 434;
short s2 = 4543;
// short s3 = s1 + s2; // 编译不通过

char c1 = 'a';
int i3 = c1 + 1; // 98
```

<a id="variables-type-conversion"></a>
#### 基本数据类型的强制类型转换

* 浮点型强转为整型小数部分会丢失
* 范围大的数据类型强转为范围小的数据类型时，正数可能变为负数，负数可能变为正数

```java
long l1 = 34;
// int i1 = l1; // 编译不通过
int i1 = (int) l1;

float f1 = 1.9F;
int i2 = (int) f1; // 1

long l2 = 128;
byte b1 = (byte) l2; // -128

long l3 = -130;
byte b2 = (byte) l3; // 126
```

<a id="data-type-float"></a>
#### Float

##### 精度说明

* 并不是所有的小数都可能精确的用二进制浮点数表示。二进制浮点数不能精确的表示
0.1、0.01、0.001这样10的负次幂。
* 浮点类型float、double的数据不适合在**不容许舍入误**差的金融计算领域。如果需要**精确**
数字计算或保留指定位数的精度，需要使用`BigDecimal`类

##### 问题测试

```java
System.out.println(0.1 + 0.2); // 0.30000000000000004

float ff1 = 123123123F;
float ff2 = ff1 + 1;
System.out.println(ff1); // 1.2312312E8
System.out.println(ff1); // 1.2312312E8
System.out.println(ff1 == ff2); // true
```

<a id="data-type-string"></a>
#### String

* String是引用类型
* String和其他基本数据类型进行`+`操作结果都是String
* 多个数值类型和String相加，如果String放在最后面则前面数值类型全部相加后再拼接为字符串，
如果String放在最前面则全部数值都拼接为字符串

```java
int i1 = 234;
float f1 = 34.55F;
boolean b1 = true;
String s1 = "str";

String s2 = s1 + i1; // str234
String s3 = s1 + f1; // str34.55
String s4 = s1 + b1; // strtrue

String s5 = i1 + f1 + s1; // 268.55str

String s6 = s1 + f1 + i1; // str34.55234
```

<a id="base"></a>
## 进制

* **十进制**，0-9组成，满十进一
* **二进制**，0-1组成，满二进一，以`0b`或`0B`开头
* **八进制**，0-7组成，满八进一，以`0`开头
* **十六进制**，0-9，a-f组成，满十六进一，以`0x`或`0X`开头

```java
int n1 = 2134; // 十进制
int n2 = 0b1011; // 二进制
int n3 = 033; // 八进制
int n4 = 0xfa33; // 十六进制
```

<a id="base-conversion-table"></a>
### 进制之间的换算

| 十进制    | 二进制    | 八进制    | 十六进制    |
|---------------- | --------------- | --------------- | --------------- |
| 0    | 0    | 0    | 0    |
| 1    | 1   | 1   | 1   |
| 2   | 10   | 2   | 2   |
| 3   | 11   | 3   | 3   |
| 4   | 100   | 4   | 4   |
| 5   | 101   | 5   | 5   |
| 6   | 110   | 6   | 6   |
| 7   | 111   | 7   | 7   |
| 8   | 1000   | 10   | 8   |
| 9   | 1001   | 11   | 9   |
| 10   | 1010   | 12   | A   |
| 11   | 1011   | 13   | B   |
| 12   | 1100   | 14   | C   |
| 13   | 1101   | 15   | D   |
| 14   | 1110   | 16   | E   |
| 15   | 1111   | 17   | F   |
| 16   | 10000   | 20   | 10   |

<a id="base-conversion"></a>
### 二进制转换

* 计算机数据的存储使用二进制**补码**形式存储，并且**最高位是符号位**
    * 正数最高位是`0`，负数最高位是`1`
* 正数的补码与反码、原码一样，称为**三码合一**
* 负数的补码与反码、原码不一样
    * 负数的**原码**：把十进制转为二进制，然后最高位设置为1
    * 负数的**反码**：在原码的基础上，最高位不变，其余为取反
    * 负数的**补码**：反码+1

<a id="binary-to-decimal"></a>
#### 二进制转十进制

* 正整数：`00001011`的十进制是`11`

<table>
    <tbody>
        <tr>
            <td>二进制</td>
            <td>0(符号位)</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td>1</td>
        </tr>
        <tr>
            <td>2的次方</td>
            <td></td>
            <td>2^6</td>
            <td>2^5</td>
            <td>2^4</td>
            <td>2^3</td>
            <td>2^2</td>
            <td>2^1</td>
            <td>2^0</td>
        </tr>
        <tr>
            <td>十进制</td>
            <td></td>
            <td>64</td>
            <td>32</td>
            <td>16</td>
            <td>8</td>
            <td>4</td>
            <td>2</td>
            <td>1</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="1">结果</td>
            <td colspan="1">+</td>
            <td colspan="7" style="text-align:center">8+2+111</td>
        </tr>
    </tfoot>
</table>

* 负整数：补码`11110101`的十进制是`-11`

<table>
    <tbody>
        <tr>
            <td>补码</td>
            <td>1(符号位)</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
        </tr>
        <tr>
            <td>反码</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>0</td>
        </tr>
        <tr>
            <td>原码</td>
            <td>1</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td>1</td>
        </tr>
        <tr>
            <td>2的次方</td>
            <td></td>
            <td>2^6</td>
            <td>2^5</td>
            <td>2^4</td>
            <td>2^3</td>
            <td>2^2</td>
            <td>2^1</td>
            <td>2^0</td>
        </tr>
        <tr>
            <td>十进制</td>
            <td></td>
            <td>64</td>
            <td>32</td>
            <td>16</td>
            <td>8</td>
            <td>4</td>
            <td>2</td>
            <td>1</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="1">结果</td>
            <td colspan="1">-</td>
            <td colspan="7" style="text-align:center">8+2+1=11</td>
        </tr>
    </tfoot>
</table>

<a id="decimal-to-binary"></a>
#### 十进制转二进制

* 除2取余的逆
* `13`的二进制是`1101`

<table>
    <thead>
        <tr>
            <th>商</th>
            <th>余数</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>13/2</td>
            <td>1</td>
        </tr>
        <tr>
            <td>6/2</td>
            <td>0</td>
        </tr>
        <tr>
            <td>3/2</td>
            <td>1</td>
        </tr>
        <tr>
            <td>1/2</td>
            <td>1</td>
        </tr>
        <tr>
            <td>0</td>
            <td></td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td>结果</td>
            <td>1101</td>
        </tr>
    </tfoot>
</table>

<a id="binary-octal-and-hexadecimal"></a>
#### 二进制与八进制、十六进制之间的转换

* 八进制：十进制`233`对应的八进制是`351`


<table>
    <tbody>
        <tr>
            <td>二进制</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
        </tr>
        <tr>
            <td>每3位转十进制对应八进制</td>
            <td colspan="2" style="text-align:center">3</td>
            <td colspan="3" style="text-align:center">5</td>
            <td colspan="3" style="text-align:center">1</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="1">结果</td>
            <td colspan="8" style="text-align:center">351</td>
        </tr>
    </tfoot>
</table>

* 十六进制：十进制`233`对应的十六进制是`E9`

<table>
    <tbody>
        <tr>
            <td>二进制</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
        </tr>
        <tr>
            <td>每4位转十进制对应十六进制</td>
            <td colspan="4" style="text-align:center">E</td>
            <td colspan="4" style="text-align:center">9</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="1">结果</td>
            <td colspan="8" style="text-align:center">E9</td>
        </tr>
    </tfoot>
</table>

<a id="operators"></a>
## 运算符

| 分类   | 运算符    |
|--------------- | --------------- |
| 算术运算符（7个）   | `+` `-` `*` `/` `%` `++` `--`   |
| 赋值运算符（12个）   | `=` `+=` `-=` `*=` `/=` `%=` `>>=` `<<=` `>>>=` `&=` <code>&#124;=</code> `^=` |
| 比较（或关系）运算符（6个）   | `>` `>=` `<` `<=` `==` `!=`   |
| 逻辑运算符（6个） | `&` <code>&#124;</code> `^` `!` `&&` <code>&#124;&#124;</code> |
| 位运算符（7个）| `&` <code>&#124;</code> `^` `~` `<<` `>>` `>>>` |
| 条件运算符（1个）| (条件表达式)?结果1:结果2 |
| Lambda运算符（1个）| `->` |

<a id="arithmetic-operators"></a>
### 算数运算符


| 运算符   | 运算    |
|--------------- | --------------- |
| `+`   | 正号   |
| `-`   | 负号   |
| `+`   | 加     |
| `-`   | 减     |
| `*`   | 乘     |
| `/`   | 除     |
| `%`   | 取模（取余）     |
| `++`   | 自增（前）：先运算后取值     |
| `++`   | 自增（后）：先取值后运算     |
| `--`   | 自减（前）：先运算后取值     |
| `--`   | 自减（后）：先取值后运算     |
| `+`   | 字符串连接     |

```java
// 正号
System.out.println(+3); // 3
// 负号
int i1 = 4;
System.out.println(-i1); // -4
// 加
System.out.println(5+5); // 10
// 减
System.out.println(6-4); // 2
// 乘
System.out.println(3*4); // 12
// 除
System.out.println(5/5); // 1
// 取模（取余）
System.out.println(7%5); // 2
// 自增（前）：先运算后取值
int i2 = 2;
int i3 = ++i2;
System.out.println(i2); // 3
System.out.println(i3); // 3
// 自增（后）：先取值后运算
int i4 = 2;
int i5 = i4++;
System.out.println(i4); // 3
System.out.println(i5); // 2
// 自减（前）：先运算后取值
int i6 = 2;
int i7 = --i6;
System.out.println(i6); // 1
System.out.println(i7); // 1
// 自减（后）：先取值后运算
int i8 = 2;
int i9 = i8--;
System.out.println(i8); // 1
System.out.println(i9); // 2
// 字符串连接
System.out.println("He" + "llo"); // Hello
```

<a id="assignment-operators"></a>
### 赋值运算符

```java
// 将5赋值给变量i1
int i1 = 5;
i1 += 1; // 等同于 i1 = i1 + 1
System.out.println(i1); // 6
i1 -= 1; // 等同于 i1 = i1 - 1
System.out.println(i1); // 5
i1 *= 2; // 等同于 i1 = i1 * 2
System.out.println(i1); // 10
i1 /= 2; // 等同于 i1 = i1 / 2
System.out.println(i1); // 5
i1 %= 2; // 等同于 i1 = i1 % 2
System.out.println(i1); // 1
// 其他类似
```

<a id="comparison-operators"></a>
### 比较（关系）运算符

| 运算符   | 运算    |
|--------------- | --------------- |
| `==`   | 相等于   |
| `!=`   | 不等于   |
| `<`   | 小于   |
| `>`   | 大于   |
| `<=`   | 小于等于   |
| `>=`   | 大于等于   |
| `instanceof`   | 检查是否为类的对象   |

* 比较运算符的结果都是`boolean`类型：`true`/`false`
* `>` `<` `>=` `<=`只适用于基本数据类型（除boolean外），
`==` `!=`适用于基本数据类型和引用数据类型
* `==` `!=`在比较引用数据类型是对比的是对象的地址，如果需要比较两个对象推荐使用`equals`方法

```java
System.out.println(4==3); // false
System.out.println(4!=3); // true
System.out.println(4<3); // false
System.out.println(4>3); // true
System.out.println(4<=3); // false
System.out.println(4>=3); // true
System.out.println("Hello" instanceof String); // true
```

<a id="logical-operators"></a>
### 逻辑运算符

| a | b | a&b | a&&b | a&#124;b | a&#124;&#124;b | !a | a^b |
| --- | --- | --- | --- | --- | --- | --- | --- |
| true | true | true | true | true | true | false | false |
| true | false | false | false | true | true | false | true |
| false | true | false | false | true | true | true | true |
| false | false | false  | false | false | false | true | false |

* `&`和`&&`表示**且**，两边都是true时，结果为true，否则为false
* <code>&#124;</code>和<code>&#124;&#124;</code>表示**或**，两边其中有一边是true，结果为true，两边都是false时，结果为false
* `!`表示**非**，结果取反
* `^`表示异或，两边结果不同时为true，两边结果相同时为false

```java
boolean a1 = true;
boolean b1 = true;
System.out.println(a1 & b1); // true
System.out.println(a1 && b1); // true
System.out.println(a1 | b1); // true
System.out.println(a1 || b1); // true
System.out.println(!a1); // false
System.out.println(a1 ^ b1); // false
System.out.println("-----------");
boolean a2 = true;
boolean b2 = false;
System.out.println(a2 & b2); // false
System.out.println(a2 && b2); // false
System.out.println(a2 | b2); // true
System.out.println(a2 || b2); // true
System.out.println(!a2); // false
System.out.println(a2 ^ b2); // true
System.out.println("-----------");
boolean a3 = false;
boolean b3 = true;
System.out.println(a3 & b3); // false
System.out.println(a3 && b3); // false
System.out.println(a3 | b3); // true
System.out.println(a3 || b3); // true
System.out.println(!a3); // true
System.out.println(a3 ^ b3); // true
System.out.println("-----------");
boolean a4 = false;
boolean b4 = false;
System.out.println(a4 & b4); // false
System.out.println(a4 && b4); // false
System.out.println(a4 | b4); // false
System.out.println(a4 || b4); // false
System.out.println(!a4); // true
System.out.println(a4 ^ b4); // false
```

#### `&`和`&&`，<code>&#124;</code>和<code>&#124;&#124;</code>之间的关系
* `&&`表示**短路且**
    * 当符号左边是true时，`&`和`&&`一样
    * 当符号左边是false时，`&`会执行符号右边的操作，而`&&`不会
* <code>&#124;&#124;</code>表示**短路或**
    * 当符号左边是false时，<code>&#124;</code>和<code>&#124;&#124;</code>一样
    * 当符号左边是true时，<code>&#124;</code>会执行符号右边的操作，而<code>&#124;&#124;</code>不会

```java
// &和&&，|和||之间的关系
int i = 3;
boolean bool = true;
if (bool & (++i > 3)){
   System.out.println();
}
System.out.println(i); // 4

i = 3;
bool = false;
if (bool && (++i > 3)){
   System.out.println();
}
System.out.println(i); // 3

i = 3;
bool = true;
if (bool | (++i > 3)){
   System.out.println();
}
System.out.println(i); // 4

i = 3;
bool = true;
if (bool || (++i > 3)){
   System.out.println();
}
System.out.println(i); // 3
```

<a id="bitwise-operators"></a>
### 位运算符

* 位运算操作可以理解为将十进制的数转换为二进制后，对二进制的相关操作

| 运算符   | 运算    |
|--------------- | --------------- |
| <<   | 左移   |
| >>   | 右移   |
| >>>   | 无符号右移   |
| &   | 与运算   |
| &#124;   | 或运算   |
| ^   | 异或运算   |
| ~   | 取反运算   |

<a id="left-shift"></a>
#### 左移

* 将左边的高位移出去后右边的空位补零
* `11`左移2位是`44`

<table>
    <tbody>
        <tr>
            <td>二进制</td>
            <td></td>
            <td></td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td>1</td>
        </tr>
        <tr>
            <td>左移两位</td>
            <td style="background-color:#db5c5c">0</td>
            <td style="background-color:#db5c5c">0</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td>1</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>高位丢弃，低位补零</td>
            <td></td>
            <td></td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td>1</td>
            <td style="background-color:#57965c">0</td>
            <td style="background-color:#57965c">0</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="1">结果</td>
            <td colspan="12" style="text-align:center">44</td>
        </tr>
    </tfoot>
</table>

```java
System.out.println(11 << 2); // 44
System.out.println(-11 << 2); // -44
```

<a id="right-shift"></a>
#### 右移

* 如果是正数，左边空位补零
* 如果是负数，左边空位补一
* `11`右移2位是`2`
<table>
    <tbody>
        <tr>
            <td>二进制</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td>1</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>右移两位</td>
            <td></td>
            <td></td>
            <td>0(符号位)</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td style="background-color:#db5c5c">1</td>
            <td style="background-color:#db5c5c">1</td>
        </tr>
        <tr>
            <td>低位丢弃，高位补零</td>
            <td style="background-color:#57965c">0</td>
            <td style="background-color:#57965c">0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="1">结果</td>
            <td colspan="12" style="text-align:center">2</td>
        </tr>
    </tfoot>
</table>

* `-11`右移2位是`-3`
<table>
    <tbody>
        <tr>
            <td>二进制</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>右移两位</td>
            <td></td>
            <td></td>
            <td>1(符号位)</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td style="background-color:#db5c5c">0</td>
            <td style="background-color:#db5c5c">1</td>
        </tr>
        <tr>
            <td>低位丢弃，高位补一</td>
            <td style="background-color:#57965c">1</td>
            <td style="background-color:#57965c">1</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>原码</td>
            <td>1</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>1</td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="1">结果</td>
            <td colspan="12" style="text-align:center">-3</td>
        </tr>
    </tfoot>
</table>

```java
System.out.println(11 >> 2); // 2
System.out.println(-11 >> 2); // -3
```

<a id="unsigned-right-shift"></a>
#### 无符号右移

* 无论是正数还是负数，被移出的高位都补零
* `-11`无符号右移2位是`61`
* 由于java内没有无符号类型，需要将`-11`的补码当作原码存入int内操作，将`-11`和`0xFF`进行**与**操作即可

<table>
    <tbody>
        <tr>
            <td>二进制</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>右移两位</td>
            <td></td>
            <td></td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td style="background-color:#db5c5c">0</td>
            <td style="background-color:#db5c5c">1</td>
        </tr>
        <tr>
            <td>低位丢弃，高位补零</td>
            <td style="background-color:#57965c">0</td>
            <td style="background-color:#57965c">0</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="1">结果</td>
            <td colspan="12" style="text-align:center">61</td>
        </tr>
    </tfoot>
</table>

```java
/*
无符号右移
                         11110101 b1 -11
                         11111111 & 0xFF
00000000 00000000 00000000 11110101 i1
00000000 00000000 00000000 00111101 61
*/
byte b1 = -11;
int i1 = b1 & 0xFF;
i1 >>>= 2;
System.out.println(i1); // 61
```

<a id="and-or-xor-not"></a>
#### 与、或、异或、取反

* 操作相同，以与为例，`11`与`19`结果为`3`

<table>
    <tbody>
        <tr>
            <td>11</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>1</td>
            <td>1</td>
        </tr>
        <tr>
            <td>19</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>1</td>
        </tr>
        <tr>
            <td>3</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td>1</td>
        </tr>
    </tbody>
</table>

```java
/*
00001011
00010011
00000011 3

00001011
00010011
00011011 27

00001011
00010011
00011000 24

00001011
11110100
10001011
10001100 -12

*/
System.out.println(11 & 19); // 3
System.out.println(11 | 19); // 27
System.out.println(11 ^ 19); // 24
System.out.println(~11); // -12
```

<a id="conditional-operators"></a>
#### 条件运算符（三元运算符）

* 格式：`(条件表达式) ? 表达式1 : 表达式2`

```java
String a = "Hello";
String b = "Wrold!";
boolean c = true;
System.out.println(c ? a : b); // Hello
```

<a id="control-flow"></a>
## 流程控制

* **顺序结构**：程序从上到下逐行执行，中间没有任何判断和跳转
* **分支结构**
    * 根据条件，选择性地执行某段代码
    * `if...else`和`switch-case`
* **循环结构**
    * 根据循环条件，重复性的执行某段代码
    * `for`、`while`、`do-while`。`foreach`（jdk5新增）遍历集合和数组

### 分支结构

<a id="if-else"></a>
#### if...else

```java
int i1 = 0;
if (i1 > 0) {
    i1--;
}
System.out.println(i1); // 0
if (i1 > 0) {
    i1--;
}else {
    i1++;
}
System.out.println(i1); // 1
if (i1 > 1) {
    i1--;
} else if (i1 == 1) {
    i1 = 0;
}
System.out.println(i1); // 0
```

<a id="switch-case"></a>
#### switch-case

* switch中的表达式只能是特定的类型：byte，short，char，int，枚举（jdk5），String（jdk7）
* switch中必须要有一个default分支用于处理未匹配到的情况
* switch中的每一对case必须对应一个break，如果忘写break则会穿透到下一个分支

```java
int week = 5;
String weekStr;
switch (week) {
    case 1:
        weekStr = "Monday";
        break;
    case 2:
        weekStr = "Tuesday";
        break;
    case 3:
        weekStr = "Wednesday";
        break;
    case 4:
        weekStr = "Thursday";
        break;
    case 5:
        weekStr = "Friday";
        break;
    case 6:
        weekStr = "Saturday";
        break;
    case 7:
        weekStr = "Sunday";
        break;
    default:
        weekStr = "error";
        break;
}
System.out.println(weekStr); // Friday

// case 5 未加上break
switch (week) {
    case 1:
        weekStr = "Monday";
        break;
    case 2:
        weekStr = "Tuesday";
        break;
    case 3:
        weekStr = "Wednesday";
        break;
    case 4:
        weekStr = "Thursday";
        break;
    case 5:
        weekStr = "Friday";
        // break;
    case 6:
        weekStr = "Saturday";
        break;
    case 7:
        weekStr = "Sunday";
        break;
    default:
        weekStr = "error";
        break;
}
System.out.println(weekStr); // Saturday
```

<a id="loop-structure"></a>
### 循环结构
* 循环结构四要素：
    * 初始化部分
    * 循环条件部分
    * 循环体部分
    * 迭代部分

<a id="for-loop"></a>
#### for循环

* 执行过程

```mermaid
flowchart LR
a(初始化) --> b(循环条件)
b --> c(循环体)
c --> d(迭代)
d --> b
```

```java
/*
 for(初始化; 循环条件; 迭代){
    循环体
 }

 依次输出1到10
 */
for (int i = 1; i <= 10; i++) {
    System.out.println(i);
}
```

<a id="while-loop"></a>
#### while循环

* 执行过程，和for循环一样

```java
/*
 初始化
 while(循环条件){
     循环体
     迭代
 }

 依次输出1到10
 */
int i = 1;
while (i <= 10) {
    System.out.println(i);
    i++;
}
```

<a id="do-while-loop"></a>
#### do-while循环

* 执行过程

```mermaid
flowchart LR
a(初始化) --> b(循环体)
b --> c(迭代)
c --> d(循环条件)
d --> b
```

* do-while循环至少执行一次循环

```java
/*
 初始化
 do {
     循环体
     迭代
 }while(循环条件)

 依次输出1到10
 */
int i = 1;
do {
    System.out.println(i);
    i++;
}while (i <= 10);

/*
 初始化
 do {
     循环体
     迭代
 }while(循环条件)

 依次输出1到10
 */
int i1 = 1;
do {
    System.out.println(i1);
    i1++;
    break;
}while (i1 <= 10);
System.out.println(i1); // 2
```

<a id="infinite-loop"></a>
#### 无限循环

* for实现：`for(;;) {}`
* while实现：`while(true) {}`

<a id="break-and-contiune"></a>
#### break和continue关键字

<table>
    <thead>
        <tr>
            <th>关键字</th>
            <th>适用范围</th>
            <th>作用</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="2" style="vertical-align: middle">break</td>
            <td>switch-case</td>
            <td>跳出分支</td>
        </tr>
        <tr>
            <td>循环结构</td>
            <td>跳出当前循环</td>
        </tr>
        <tr>
            <td>continue</td>
            <td>循环条件</td>
            <td>提前进入下一次循环</td>
        </tr>
    </tbody>
</table>

```java
// 跳出循环
for (int i = 1; i <= 10; i++) {
    if (i > 4){
        break;
    }
    System.out.println(i);
}

System.out.println("---");

// 跳过偶数
for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0){
        continue;
    }
    System.out.println(i);
}
```

<a id="arrays"></a>
## 数组

* 数组（Array），是多个相同类型数据按一定循序排列的集合，并使用一个名字命名，
通过编号的方式对这些数据进行统一管理
* 概念
    * 数组名
    * 下标（索引），从0开始
    * 元素
    * 数组的长度
* 特点
   * 数组中的元素在内存中是依次紧密排列的，有序的
   * 数组属于引用数据类型，数组中的元素可以是基本数据类型或引用数据类型
   * 数组一旦初始化完成，长度确定，不可变
   * 创建数组对象会在内存中开辟一整块**连续的空间**。占用空间的大小，
   取决于数组的长度和数组中元素的类型

<a id="one-dimensional-array"></a>
### 一维数组

#### 声明数组

```java
int[] integers;
String[] names;
```

#### 初始化

```java
int[] integers;
String[] names;
integers = new int[]{1, 2, 3, 4}; // 静态初始化
int[] integers1 = {5, 6, 7, 8}; // 类型推断
names = new String[4]; // 动态初始化
```

#### 数组元素的调用

```java
System.out.println(integers[0]); // 1
System.out.println(integers[1]); // 2
// System.out.println(integers[4]); // 报错ArrayIndexOutOfBoundsException

names[0] = "zs";
names[1] = "ls";
// names[4] = "ww"; // 报错ArrayIndexOutOfBoundsException
```

#### 数组的长度

```java
System.out.println(integers.length); // 4
System.out.println(names.length); // 4
```

#### 遍历数组

```java
for (int i = 0; i < names.length; i++) {
    System.out.println(names[i]);
}

// foreach遍历
for (int integer : integers) {
    System.out.println(integer);
}
```

#### 数组元素的默认初始化值

* 基本数据类型，参考<a href="#variables-data-type">数据类型</a>默认值
* 引用数据类型默认都是`null`

```java
// 数组默认初始化值
int[] is = new int[3];
double[] ds = new double[4];
String[] strs = new String[5];
System.out.println(is[0]); // 0
System.out.println(ds[0]); // 0.0
System.out.println(strs[1]); // null
```

#### 一维数组的内存解析

```java
int[] arr1 = new int[4];
arr1[0] = 10;
arr1[1] = 20;

String[] arr2 = new String[2];
arr2[1] = "zs";
arr2 = new String[3];
```
![内存图](./assets/Snipaste_2024-09-07_15-33-16.png)

<a id="two-dimensional-array"></a>
### 二维数组

* 二维数组就是一维数组中的元素又是一维数组

#### 二维数组的使用

```java
// 初始化，模拟班级里面分组
String[][] classroom = new String[][]{
    {"zs", "ls"},
    {"aa", "bb", "cc"},
    {"mm", "nn", "xx", "yy", "zz"}
};

// 获取
// 1组里面的第二个成员
System.out.println(classroom[0][1]); // ls
// 3组里面的第三个成员
System.out.println(classroom[2][2]); // xx
System.out.println("---");
// 长度
// 班级里面有多少个组
System.out.println(classroom.length); // 3
// 每个组里面有多少个成员
System.out.println(classroom[0].length); // 2
System.out.println(classroom[1].length); // 3
System.out.println(classroom[2].length); // 5

System.out.println("---");
// 遍历
// 模拟报数
for (int i = 0; i < classroom.length; i++) {
    System.out.println("第" + ( i + 1 ) + "组报数");
    for (int j = 0; j < classroom[i].length; j++) {
        System.out.println(classroom[i][j] + ": " + (j + 1));
    }
}
```

<a id="array-related-operations"></a>
### 数组相关操作

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/syntax/arrays/ArrayOperator.java)

<a id="array-max"></a>
* 最大值

```java
int[] array = getRandomIntegerArray(10, 59, 10);

int max = array[0];
for (int i = 0; i < array.length; i++) {
    if (max < array[i]) {
        max = array[i];
    }
}
printArray(array);
System.out.println(max);
```

<a id="array-minimum"></a>
* 最小值

```java
int[] array = getRandomIntegerArray(10, 59, 10);

int min = array[0];
for (int i = 0; i < array.length; i++) {
    if (min > array[i]) {
        min = array[i];
    }
}
printArray(array);
System.out.println(min);
```

<a id="array-sum"></a>
* 求和

```java
int[] array = getRandomIntegerArray(10, 59, 10);

int count = 0;
for (int i = 0; i < array.length; i++) {
    count += array[i];
}
printArray(array);
System.out.println(count);
```

<a id="array-average"></a>
* 平均数

```java
int[] array = getRandomIntegerArray(10, 59, 10);

int count = 0;
for (int i = 0; i < array.length; i++) {
    count += array[i];
}
printArray(array);
System.out.println(count / array.length);
```

<a id="array-pascal-triangle"></a>
* 杨辉三角

```java
int[][] arrays = new int[10][];

for (int i = 0; i < arrays.length; i++) {
    // 边框
    arrays[i] = new int[i + 1];
    arrays[i][0] = arrays[i][i] = 1;
    // 内部
    for (int j = 1; j < arrays[i].length - 1; j++) {
        arrays[i][j] = arrays[i - 1][j - 1] + arrays[i - 1][j];
    }
}

for (int i = 0; i < arrays.length; i++) {
    for (int j = 0; j < arrays[i].length; j++) {
        System.out.print(arrays[i][j] + "\t");
    }
    System.out.println();
}
```

<a id="array-number-of-loops"></a>
* 回形数

```java
Scanner scanner = new Scanner(System.in);
int num;
while ((num = scanner.nextInt()) != 0) {
    int[][] arrays = new int[num][num];

    int loopNum = num * num;
    // 1 右 2 下 3 左 4 上
    int direction = 1;

    int i = 0, j = 0;
    for (int data = 1; data <= loopNum; data++) {
        if (direction == 1) {
            if (j < num && arrays[i][j] == 0) {
                arrays[i][j++] = data;
            } else {
                direction = 2;
                i++;
                j--;
                data--;

            }
        } else if (direction == 2) {
            if (i < num && arrays[i][j] == 0) {
                arrays[i++][j] = data;
            } else {
                direction = 3;
                i--;
                j--;
                data--;
            }
        } else if (direction == 3) {
            if (j >= 0 && arrays[i][j] == 0) {
                arrays[i][j--] = data;
            } else {
                direction = 4;
                i--;
                j++;
                data--;
            }
        } else if (direction == 4) {
            if (i >= 0 && arrays[i][j] == 0) {
                arrays[i--][j] = data;
            } else {
                direction = 1;
                i++;
                j++;
                data--;
            }
        }

    }
    for (int m = 0; m < arrays.length; m++) {
        for (int n = 0; n < arrays[m].length; n++) {
            System.out.print(arrays[m][n] + "\t");
        }
        System.out.println();
    }

}
```

<a id="array-reverse"></a>
* 数组翻转

```java
int[] arr = new int[]{39, 59, 25, 51, 38, 11, 26, 47, 31, 37, 25};


int lastIdx = arr.length - 1;
int halfLen = arr.length / 2;

for (int i = 0; i < halfLen; i++) {
    // 分别将头尾的元素交换
    int tmp = arr[i];
    arr[i] = arr[lastIdx - i];
    arr[lastIdx - i] = tmp;
    // arr[i] = arr[i] ^ arr[lastIdx - i];
    // arr[lastIdx - i] = arr[i] ^ arr[lastIdx - i];
    // arr[i] = arr[i] ^ arr[lastIdx - i];
}
printArray(arr);
```

<a id="array-scaling"></a>
* 数组扩容

```java
// 38, 11, 26
int[] arr = new int[]{39, 59, 25, 51};
// 创建新数组
int[] newArr = new int[arr.length * 2];
// 将原数组内的数据添加进来
for (int i = 0; i < arr.length; i++) {
    newArr[i] = arr[i];
}
// 添加新元素
newArr[arr.length] = 38;
newArr[arr.length + 1] = 11;
newArr[arr.length + 2] = 26;

printArray(newArr);
```
<a id="array-algorithm"></a>
### 数组相关算法

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/syntax/arrays/ArrayAlgorithm.java)

<a id="array-linear-search"></a>
* 线性查找

```java
for (int i = 0; i < arr.length; i++) {
    if (arr[i] == data){
        return i;
    }
}
return -1;
```

<a id="array-binary-search"></a>
* 二分查找

```java
int head = 0;
int tail = arr.length - 1;
while (head <= tail){
    int mid = (head + tail) / 2;
    if (data == arr[mid]){
        return mid;
    } else if (data > arr[mid]) {
        head = mid + 1;
    }else {
        tail = mid - 1;
    }
}
return -1;
```

<a id="array-bubble-sort"></a>
* 冒泡排序

```java
int tmp;
for (int i = 0; i < arr.length; i++) {
    for (int j = i + 1; j < arr.length; j++) {
        if (arr[i] > arr[j]){
            tmp = arr[i];
            arr[i] = arr[j];
            arr[j] = tmp;
        }
    }
}
```

<a id="array-quick-sort"></a>
* 快速排序

```java
private void swap(int[] arr, int i, int j){
    int tmp = arr[i];
    arr[i] = arr[j];
    arr[j] = tmp;
}
private void quickSort(int[] arr, int start, int end){
    if (start < end) {
        int base = arr[start];
        int low = start;
        int high = end + 1;
        while (true){
            while (low < end && arr[++low] - base <= 0);
            while (high > start && arr[--high] - base >= 0);
            if (low < high) {
                swap(arr, low, high);
            }else {
                break;
            }
        }
        swap(arr, start, high);

        quickSort(arr, start, high - 1);
        quickSort(arr, high + 1, end);
    }
}
```

<a id="array-utils"></a>
### Arrsys工具类

```java
int[] arr = new int[]{39, 59, 25, 51, 38, 11, 26, 47, 31, 37};
int[] arr1 = new int[]{39, 59, 25, 51, 38, 11, 26, 47, 31, 37, 25};

System.out.println(Arrays.compare(arr, arr1)); // 比较 0 相同，1 左边数组大，-1左边数组小
System.out.println(Arrays.equals(arr, arr1)); // 比较， true 相同，false 不同

Arrays.sort(arr); // 排序
System.out.println(Arrays.binarySearch(arr, 11)); // 查找

int[] newArr = Arrays.copyOf(arr, arr1.length + 3); // 扩容

System.out.println(Arrays.toString(newArr)); // 打印
```

<a id="object-oriented"></a>
## 面向对象

* Java类及类的成员：属性、方法、构造器；代码块、内部类 
* 面向对象特性：封装、继承、多态、抽象
* 其他关键字使用：this、super、package、import、static、final、interface、abstract


### 类和对象

* **类**：具有相同特征的事物的抽象描述，是抽象的、概念上的定义
* **对象**：实际存在的该类事物的每个个体，是具体的，也称为**实例(instance)**

#### 类的成员

* Java中用类class来描述事务，类是一组相关**属性**和**行为**的集合，这也是类最基本的两个成员
    * **属性**：该类事物的状态。对应类中的**成员变量(属性、Method)**
    * **行为**：该类事物要做什么操作，或者基于事物的状态能做什么。对应类中的**成员方法（函数、Field）**


##### 定义一个类并且使用

* 定义

```java
public class Phone {
    // 属性
    String name;
    double price;

    // 方法
    public void call(){
        System.out.println("打电话");
    }

    public void playGame(){
        System.out.println("玩游戏");
    }
}
```

* 使用

```java
public static void main(String[] args) {
    Phone phone = new Phone();
    phone.name = "hw";
    phone.price = 6999.0;

    phone.call();
    phone.playGame();
}
```

<a id="oop-field"></a>
## 属性（成员变量）和局部变量

* 变量声明的格式相同：`数据类型 变量名 = 变量值`
* 变量都有其有效的作用域，出作用域就失效
* 变量必须先声明，后赋值，再使用

<a id="oop-member-variables-and-local-variables"></a>
### 成员变量和局部变量的区别

| 不同点 | 属性（成员变量） | 局部变量 |
| --- | --- | --- |
| **类中声明的位置** | 声明在类内，方法外 | 声明在方法、构造器内 |
| **内存中分配的位置** | 随对象的创建存储在堆空间 | 存储在栈空间 |
| **生命周期** | 随着对象创建或消亡 | 方法入栈，局部变量在栈中分配，方法出栈，局部变量消亡|
| **作用域** | 整个类内部有效 | 在声明局部变量的方法、构造器、代码块中有效 |
| **权限修饰符** | 可以 | 不可以 |
| **默认值** | 有 | 没有 | 

```java
/**
 * 员工
 */
public class Employee {
    int id;
    String name;

    public void work(String workName){
        System.out.println("员工：" + name + "正在：" + workName);

    }
}
```

<a id="oop-method"></a>
## 方法（Method）

* **方法**是类或对象行为特征的抽象，用来完成某个功能的操作。
在某些语言中也成为**函数**或**过程**
* 将功能封装为方法的目的是，可以实现代码重用，减少冗余，简化代码
* Java里的方法**不能独立存在**，所有方法必须定义在类中
* 方法内可以调用本类中的**其他**方法或属性
* 方法内不能定义方法

### 方法声明的格式说明

```java
权限修饰符 [其他修饰符] 返回值类型 方法名(形参列表) [throws 异常类型]{ // 方法头
    // 方法体
}
```
* 权限修饰符
    * 四种：private，缺省，protected，public
* 返回值类型：调用当前方法，是否需要一个结果
    * 无返回值，使用`void`
    * 有返回值，指明返回值的具体类型，可以是基本数据类型或引用数据类型
    在方法内部使用`return`+返回类型的变量
* 方法名：标识符，描述方法是干什么的
* 形参列表：属于局部变量，可以声明多个
    * 格式：`(形参1, 形参2, 形参3, 形参4, ...)`
    * 无形参直接使用`()`即可
* 方法体：方法的功能，真正执行的代码

```java
/**
 * 人
 */
public class Person {

    String name;

    public void eat(){
        System.out.println(name + "吃饭");
    }

    public void sleep(int hour){
        System.out.println("先睡" + hour + "小时");
    }

    public boolean isHappy(){
        return true;
    }

}
```
<a id="oop-return-keyword"></a>
### return关键字

* 结束一个方法
* 结束一个方法的同时可以返回数据给调用者

```java
for (int i = 0; i < 10; i++) {
    if (i == 5){
        return; // 提前返回
    }
}
System.out.println("方法结束"); // 未输出
```

### 方法调用内存解析

* 调用方法时，堆空间会新入栈一个栈帧
* 方法的形参和局部变量会保存在这个栈帧内
* 方法结束时，栈帧会弹出，对应的形参和局部变量会销毁

### 方法的重载(overload)

* **方法的重载**：在同一个类中，允许存在一个以上的同名方法，只要它们的形参列表不同即可
* **重载的特点**：与修饰符、返回值类型无关，只看参数列表，且参数列表必须不同，（参数个数或类型）
* **重载方法条用**：JVM通过方法的参数列表，调用匹配的方法
    * 先找个数、类型最匹配的
    * 再找个数和类型可以兼容的，如果同时多个方法可以兼容，将会报错

```java
/**
 * 无返回值
 */
public void add(int a, int b){
    System.out.println(a + b);
}

/**
 * 虽然返回值不同，但形参相同，编译不通过
 */
// public int add(int a, int b){
//     return a + b;
// }

/**
 * 有返回值
 */
public int add(int a, int b, int c){
    return a + b + c;
}

/**
 * 类型不同
 */
public double add(double a, double b){
    return a + b;
}

/**
 * 修饰符不同
 */
private double add(double a, double b, double c){
    return a + b + c;
}
```

<a id="oop-variable-parameters"></a>
### 可变个数形参的方法(jdk5)

* 在调用方法时，可能会出现方法形参类型确定，但个数不确定，此时，我们可以使用可变个数形参的方法
* 格式`(参数类型... 参数名)`
* 同一个类中，可变形参方法可以与相同单个类型的方法构成重载
* 同一个类中，可变形参方不能与相同类型的数组构成重载
* 可变形参必须声明在形参列表的最后面
* 可变形参在一个方法内最多声明一次

```java
/**
 * 可变形参方法
 */
public int add(int... nums){
    int count = 0;
    for (int i = 0; i < nums.length; i++) {
        count += nums[i];
    }
    return count;
}

/**
 * 可变形参方法不能与相同类型的数组的方法存在同一个类中，编译不通过
 */
// public int add(int[] nums){
//     int count = 0;
//     for (int i = 0; i < nums.length; i++) {
//         count += nums[i];
//     }
//     return count;
// }

/**
 * 可变形参必须声明在形参列表的最后面
 */
public boolean equalsAll(long a, int... nums){
    return a ==  add(nums);
}

/**
 * 可变形参在方法内只能声明一次，编译不通过
 */
// public boolean equalsAll(long... a, int... nums){
//    return add(a) == add(nums);
// }
```

<a id="oop-method-value-passing-mechanism"></a>
### 方法的值传递机制

* 对于方法内声明的局部变量来说，如果出现赋值操作
    * 基本数据类型，将变量保存的数据值传递出去
    * 引用数据类型，将变量保存的地址值传递出去

```java
public void addOne(int i){
    i = + 1;
}

/**
 * 基本数据类型
 */
@Test
public void testBasicDataType() {
    int i = 1;
    addOne(i);
    System.out.println(i); // 1
}

public void addOne(int[] arr){
    for (int i = 0; i < arr.length; i++) {
        arr[i] = arr[i] + 1;
    }
}

/**
 * 数组
 */
@Test
public void testArray(){
    int[] arr = new int[]{1, 1, 1, 1, 1};
    addOne(arr);
    System.out.println(Arrays.toString(arr)); // 2, 2, 2, 2, 2
}

public void growUp(People people){
    people.setAge(people.age + 1);
}

/**
 * 引用数据类型
 */
@Test
public void testReferenceDataType() {
    People people = new People();
    people.setName("zs");
    people.setAge(11);
    System.out.println(people.info()); // 我的名字是：zs, 11岁

    growUp(people);
    System.out.println(people.info()); // 我的名字是：zs, 12岁
}
```

<a id="oop-recursive-methods"></a>
### 递归方法

* 方法内自己调用自己的现象就成为递归
* **递归的分类**：直接递归，间距递归
* 递归方法包含了一种隐式的循环
* 递归方法一定要已知方向递归，否则这种递归就变成了无穷递归，停不下来，类似死循环，最终发生**栈溢出**
* 递归的问题
    * 递归调用会占用大量系统堆栈，内存耗用多，在递归调用层次多时速度要比循环慢，使用递归时要谨慎
    * 在要求高性能的情况下尽量避免使用递归，考虑循环迭代

#### 代码示例

* 直接递归

```java
/**
 * 直接递归
 */
public void a(){
    a();
}
```

* 间接递归

```java
/**
 * 间距递归
 */
public void b(){
    c();
}

public void c(){
    d();

}
public void d(){
    b();
}
```

* 累加数组应用

```java
/**
 * 累加数字
 */
public int getSum(int num){
    if (num == 1){
        return 1;
    }
    return num + getSum(num - 1);
}

@Test
public void testSum() {

    System.out.println(getSum(100));
}
```

<a id="oop-package-and-import"></a>
## package和import

### package(包)

* 用于指明该文件中定义的类、接口等结构所在的包
* 语法：`package 顶层包名 子包名;`
* 说明
    * 一个源文件只能有一个声明包的package语句
    * package语句作为java源文件的第一条语句出现。若缺省该语句，则指定为无名包
    * 包名，属于标识符，满足标识符命名规则和规范（全部小写）、见名知意
        * 包通常使用所在公司域名的倒置
* 作用
    * 包可以包含类和子包，划分项目层次，便于管理
    * 帮助管理大型软件系统，将功能相近的类划分到同一个包内
    * 解决类命名冲突问题
    * 控制访问权限

### import关键字

* 为了使用定义在其他包内的java类，需要使用import语句显示引入指定包下的需要的类。
相当于import语句告诉编译器到哪里去找这个类
* 语法：`import 包名.类名;`
* 说明
    * import语句声明在包的声明和类的声明之间
    * 导入多个类或接口，直接写多个import语句
    * 一次性导入某个包下的所有类或接口可以使用`import a.*;`
    * 如果导入的类或接口是java.lang包下的，或者是当前包下的，则可以省略此import语句
    * 导入`java.a`包下的某个类后，如果需要导入`java.a.b`包下的某个类仍需要导入
    * 如果有两个同名的类在不同包下，都需要使用的话，需要将其中一个使用全类名方式声明`a.b.c.People people = new a.b.c.People()`
    * `import static`组合使用可以导入指定类下的静态属性或方法

<a id="oop-encapsulation"></a>
## 封装性（Encapsulation）

* 面向对象的开发原则要遵循**高内聚**、**低耦合**
    * **高内聚**：类的内部数据操作细节自己完成，不允许外部干涉
    * **低耦合**：尽量暴露少量的方法给外部使用，尽量方便外部调用
* 封装就是把客观的事物抽象概念的类，并且类可以把自己的数据和方法只向可信的类或对象开放，向没必要开放的类或对象隐藏信息

### Java实现封装性

* 实现封装就是控制类或成员的可见性范围。需要访问控制修饰符，也称权限修饰符
* 权限修饰符：`public`、`protected`、`缺省`、`private`

<a id="oop-permission-modifiers"></a>

| 修饰符    | 本类内部    | 本包内    | 其他包的子类    | 其他包的非子类    |
|---------------- | --------------- | --------------- | --------------- | --------------- |
| private    | √    | ×    | ×    | ×   |
| 缺省   | √   | √   | ×   | ×   |
| protected   | √   | √   | √   | ×   |
| public   | √   | √   | √   | √   |

* 修饰的结构
    * 外部类只能使用`public`和`缺省`两种权限修饰符
    * 成员变量、成员方法、构造器、成员内部类可以使用所有权限修饰符

#### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/encapsulation/A.java)

* 定义一个`A`类，定义4个属性，分别有4种不同的权限修饰符

```java
/**
 * 测试权限修饰符类
 */
public class A {
    /**
     * 私有属性
     */
    private int privateField;

    /**
     * 缺省属性
     */
    int defaultField;

    /**
     * protected数字
     */
    protected int protectedField;

    /**
     * 公开属性
     */
    public int publicField;
}
```

* 在`A`类相同包下定义一个`B`类，使用main方法访问`A`类的所有属性

```java
/**
 * 和A类处在相同的包下
 */
public class B {
    public static void main(String[] args) {
        A a = new A();
        // int privateField a.privateField; // 无法访问
        int defaultField = a.defaultField;
        int protectedField = a.protectedField;
        int publicField = a.publicField;
    }
}
```

* 在`A`类的子包下定义一个`packag1.C`类，并继承`A`类，使用方法访问`A`类的所有属性

```java
/**
 * 和A类处在不同的包下，但是是A类的子类
 */
public class C extends A {
    public void cMethod(){
        // int privateField super.privateField; // 无法访问
        // int defaultField = super.defaultField; // 不在相同包内，无法访问
        int protectedField = super.protectedField;
        int publicField = super.publicField;
    }
}
```

* 在`A`类的子包下定义一个`packag2.D`类，使用main方法访问`A`类的所有属性

```java
/**
 * 和A类处在不同的包下，不是A类的子类
 */
public class D {

    public static void main(String[] args) {
        A a = new A();
        // int privateField a.privateField; // 无法访问
        // int defaultField = a.defaultField; // 不在相同包内，无法访问
        // int protectedField = a.protectedField; // 不在相同包内并且不是子类，无法访问
        int publicField = a.publicField;
    }
}
```

<a id="oop-constructor"></a>
## 构造器（constructor）

* 构造器搭配`new`关键字使用，用于创建类的对象
* 在创建对象的同时，可以给对象相关属性赋值
* 说明
    * 格式：`权限修饰符 类名(形参列表){}`
    * 创建类后，在没有显示提供任何构造器的情况下，系统会默认提供一个空参构造器，构造器权限修饰符与类声明的权限相同
    * 一旦类中显示声明了构造器，系统就不再提供默认的空参构造器
    * 一个类可以声明多个构造器，彼此之间构成重载

### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/constructor)

* 默认构造器

```java
/**
 * 默认构造器
 */
public class DefaultConstructorClass {

    public static void main(String[] args) {
        DefaultConstructorClass defaultConstructorClass = new DefaultConstructorClass();
    }
}
```

* 自定义构造器

```java
/**
 * 自定义构造器
 */
public class CustomConstructorClass {

    String name;

    int age;

    public CustomConstructorClass(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public static void main(String[] args) {
        CustomConstructorClass zs = new CustomConstructorClass("zs", 11);

        // CustomConstructorClass zs1 = new CustomConstructorClass() // 没有无参构造器，编译不通过

        // 给对象的属性赋值
        System.out.println(zs.name); // zs
        System.out.println(zs.age); // 11
    }
}
```

* 构造器重载

```java
/**
 * 构造器重载
 */
public class OverloadConstructorClass {

    String name;

    int age;

    /**
     * 只有age的构造器
     */
    public OverloadConstructorClass(int age) {
        this.age = age;
    }

    /**
     * 全部参数构造器
     */
    public OverloadConstructorClass(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public static void main(String[] args) {
        OverloadConstructorClass zs = new OverloadConstructorClass("zs", 11);
        System.out.println(zs.name); // zs
        System.out.println(zs.age); // 11
        OverloadConstructorClass zs1 = new OverloadConstructorClass(11);
        System.out.println(zs1.name); // null
        System.out.println(zs1.age); // 11
    }
}
```

<a id="oop-assignment-process"></a>
## 类中属性赋值过程

* 在类的属性中，给属性赋值的位置
    1. 默认赋值
    2. 显示赋值
    3. 构造器赋值
    4. `对象.方法`赋值
    5. `对象.属性`赋值
* 这些位置赋值的顺序：1，2，3，4/5
* 这些位置的执行次数
    * 1、2、3只能执行一次
    * 4、5可以执行多次

### 代码示例

```java
/**
 * 测试属性赋值顺序
 */
public class AssignmentOrder {

    // int integer; // 默认赋值
    int integer = 1; // 显示赋值

    public AssignmentOrder(){}

    public AssignmentOrder(int i){
        integer = i;
    }

    /**
     * 方法赋值
     */
    public void setInteger(int i){
        integer = i;
    }

    public static void main(String[] args) {
        AssignmentOrder assignmentOrder = new AssignmentOrder();
        // 打开默认赋值代码注释
        // System.out.println(assignmentOrder.integer); // 0

        // 打开显示赋值注释
        System.out.println(assignmentOrder.integer); // 1

        // 构造器赋值
        AssignmentOrder ao2 = new AssignmentOrder(2);
        System.out.println(ao2.integer); // 2

        // 对象.属性赋值可以赋值多次
        ao2.integer = 3;
        ao2.integer = 4;
        System.out.println(ao2.integer); // 4

        // 对象.方法赋值可以赋值多次
        ao2.setInteger(5);
        ao2.setInteger(6);
        System.out.println(ao2.integer); // 6
    }
}
```

<a id="oop-java-bean"></a>
## JavaBean

* JavaBean是一种java语言写的可重用组件
* 符合以下标准的类
    * 类是公共的
    * 有一个无参的公共构造器
    * 有属性，且有对应的get，set方法

<a id="oop-this-keyword"></a>
## this关键字

* 在方法中（非static方法）内部使用，表示调用该方法的对象
* 在构造器中，表示该构造器正在初始化的对象
* 使用`this(形参列表)`可以调用构造器
    * 使用这种方式调用构造器必须声明在构造器的首行

```java
/**
 * 测试this调用构造器
 */
public class ThisClass {

    private String name;

    private int age;

    public ThisClass(){
        System.out.println("初始化代码执行");
    }

    public ThisClass(String name) {
        this();
        this.name = name;
    }

    public ThisClass(String name, int age) {
        this();
        this.name = name;
        this.age = age;
    }

    public static void main(String[] args) {
        // 下面三行都会输出 初始化代码执行
        ThisClass thisClass = new ThisClass();
        ThisClass thisClass1 = new ThisClass("zs");
        ThisClass thisClass2 = new ThisClass("zs", 11);
    }
}
```

<a id="oop-inheritance"></a>
## 继承（inheritance）

* 在定义类时发现要定义的类与之前的类有相似点，可以考虑继承之前的类，或将相同点抽象出来一个类并继承
* 继承的好处
    * 继承的出现减少了代码的冗余，提高了代码的复用性
    * 继承的出现有利于功能的扩展
    * 继承的出现让类和类之间产生了`is-a`的关系，为多态的使用提供了前提。
        * 描述事物之间的所属关系，这种关系是`is-a`的关系，父类更通用，子类更具体

### 语法

* 通过`extends`关键字实现
* 描述
    * 类A：父类、superClass、超类、基类
    * 类B：子类、subClass、派生类

```java
[修饰符] class 类A {
    ...
}

[修饰符] class 类B extends 类A {
    ...
}
```

### 继承的功能

* 子类可以获取到父类中的属性和方法（受封装性影响）
* 子类继承父类之后，可以扩展自己特有的功能（添加属性或方法）

### Java继承体系

* Java中声明的类，如果没有显式的声明其父类时，默认继承与`java.lang.Object`
* 一个类可以同时拥有多个子类
* 一个类不可以同时继承多个父类（Java只支持单继承，不支持多继承）

### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/inheritance/InheritanceTest.java)

* 定义一个父类

```java
/**
 * 人
 */
public class Person {

    String name;

    int age;

    public void eat(){
        System.out.println("吃饭");
    }
}
```

* 定义一个子类

```java
/**
 * 学生
 */
public class Student extends Person{

    public Student() {
    }

    public Student(String name, int age){
        this.name = name;
        this.age = age;
    }


    public void study(){
        System.out.println("学习");
    }
}
```

* 测试

```java
Student student = new Student("zs", 11);

// 调用父类中的属性
System.out.println(student.name);
System.out.println(student.age);

// 调用父类中的方法
student.eat();
// 调用自己的方法
student.study();
```

<a id="oop-methods-override"></a>
## 方法的重写（override）

* 子类对父类继承过来的方法进行覆写的操作，就称为方法的重写

### 方法重写的规则

* 子类重写父类的方法，方法的命令，形参列表必须相同
* 权限不能小于父类方法的修饰符
* 返回值
    * 父类的返回值时void，子类也必须是void
    * 返回值是基本数据类型，子类必须相同
    * 返回值是引用数据类型，子类可以相同，或是其子类
* 异常：子类重写方法抛出的异常必须和父类方法抛出的异常相同或则是其子类
* 方法体没有要求

### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/override/OverrideTest.java)

* 定义父类

```java
/**
 * 人
 */
public class Person {

    String name;

    int age;

    public void eat(){
        System.out.println("吃饭");
    }

    public void read(String word){
        System.out.println("说话：" + word);
    }

    public void sleep(int hour){
        System.out.println("先睡" + hour + "小时");
    }

    public String info(){
        return name + ":" + age;
    }

}
```

* 定义子类

```java
/**
 * 学生
 */
public class Student extends Person {

    public Student() {
    }

    public Student(String name, int age){
        this.name = name;
        this.age = age;
    }


    @Override
    public void eat() {
        System.out.println(name + "正在吃饭");
    }

    @Override
    public void read(String word) {
        System.out.println(name + "读" + word);
    }

    @Override
    public void sleep(int hour) {
        System.out.println(name + "准备睡" + hour + "小时");
    }

    @Override
    public String info() {
        return "姓名：" + name + "\t年龄" + age + "岁";
    }

    public void study(){
        System.out.println("学习");
    }
}
```

* 测试

```java
// 调用父类的方法
Person person = new Person();
person.name = "人";
person.age = 11;
person.eat();
person.read("123");
person.sleep(21);
System.out.println(person.info());

System.out.println("---");
// 调用子类重写后的方法
Student student = new Student("sz", 12);
student.eat();
student.read("书");
student.sleep(6);
System.out.println(student.info());
```

<a id="oop-super-keyword"></a>
## super关键字

* 子类继承父类后重写了父类的某个方法，但是需要调用这个被重写的方法，可以使用`super.方法`
* 子类继承父类后，定义了一个与父类重名的属性，需要使用父类的这个属性，可以使用`super.属性`
    * 子类出现父类相同的属性是不会覆盖父类的属性，两个属性同时存在
* 子类继承父类后，在初始化该对象时需要调用父类的构造器，可以使用`super(形参列表)`
    * `super(形参列表)`必须声明在构造器的首行
    * `super(形参列表)`和`this(形参列表)`只能二选一
    * 如果首行没有显示调用this或super构造器，则默认调用`super()`空参构造器

### super调用属性、方法

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/keywords/super_keyword/SuperTest.java)

* 定义父类

```java
/**
 * 人
 */
public class Person {

    int id;

    String name;

    int age;

    public Person() {
        System.out.println("初始化Person");
    }

    public Person(int id, String name, int age) {
        this.id = id;
        this.name = name;
        this.age = age;
    }

    public void eat(){
        System.out.println("吃饭");
    }

}
```

* 定义子类

```java
/**
 * 学生
 */
public class Student extends Person {

    int id;

    public Student() {
    }

    public Student(int id, String name, int age) {
        super(id, name, age);
        this.id = id + 1;
    }

    public void showId(){
        System.out.println(this.id);
        System.out.println(super.id);
    }

    @Override
    public void eat() {
        System.out.println(name + "正在吃饭");
        super.eat();
    }


    public void study(){
        System.out.println("学习");
    }
}
```

* 测试

```java
Student zs = new Student(1, "zs", 11);

// 子类重写方法后调用父类的方法
zs.eat();

// 子类打印属性后打印父类的同名属性
zs.showId();
```

### super调用构造器

* 测试（父类子类代码和上面一样）

```java
// 调用子类无参构造器会默认调用父类无参构造器，打印里面的信息
Student student = new Student();


// 使用super(形参列表)会初始化父类里面的属性
Student zs = new Student(1, "zs", 11);
// 由于Student有一个同名的属性，只初始化了父类的属性，两个id属性的值不同
zs.showId();
```

<a id="oop-polymorphism"></a>
## 多态性（Polymorphism）

* 对象的多态性：父类的引用指向子类对象
* 格式：`父类类型 变量名 = 子类对象`
* 前提
    * 要有类的继承关系
    * 要有方法的重写
* 多态只适用于方法，不适用于属性
* 好处：极大的减少了代码的冗余，不需要定义多个重载的方法
* 弊端：在多态的场景下，创建了子类的对象，也加载了子类特有的方法和属性，
由于声明的是父类的引用，无法直接调用子类的特有方法

### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/polymorphism/PolymorphismTest.java)

* 定义一个父类

```java
/**
 * 人
 */
public class Person {

    int id = 1;

    public void eat() {
        System.out.println("吃饭");
    }

    public void doWork() {
        System.out.println("工作");
    }
}
```

* 定义一个子类

```java
/**
 * 男人
 */
public class Man extends Person{

    int id = 2;
    @Override
    public void eat() {
        System.out.println("吃一大碗");
    }

    @Override
    public void doWork() {
        super.doWork();
    }

    /**
     * 模拟子类特殊操作
     */
    public void a(){
        System.out.println("a");
    }
}
```
* 另一个子类

```java
/**
 * 女人
 */
public class Woman extends Person {
    int id = 3;
    @Override
    public void eat() {
        System.out.println("吃一碗");
    }


    @Override
    public void doWork() {
        super.doWork();
    }
}
```

* 测试

```java
public class PolymorphismTest {

    @Test
    public void testPolymorphism1() {
        Person person = new Person();

        Person woman = new Woman();

        Person man = new Man();


        person.eat();

        // 多态，实际调用子类方法，这种方式称为虚方法
        woman.eat();
        man.eat();

        // 属性不适用与多态

        System.out.println(person.id); // 1
        System.out.println(woman.id); // 1
        System.out.println(man.id); // 1
    }


    /**
     * 模拟招聘
     */
    private void recruitment(Person person){
        person.doWork();
    }

    /**
     * 多态的好处
     */
    @Test
    public void testPolymorphism2() {
        // 男人女人都能用
        recruitment(new Woman());
        recruitment(new Man());
    }

    /**
     * 多态的弊端
     */
    @Test
    public void testPolymorphism3() {
        Person man = new Man();
        // man.a(); // 无法调用子类的特殊操作
    }

}
```

<a id="oop-upward-and-downward-transformation"></a>
### 向上转型和向下转型

* instanceof关键字：在类型强转前判断甚至是其子类，增加程序的健壮性

```java
@Test
public void testClassCast() {

    Person man = new Man();

    // 使用强转操作调用子类的特殊方法
    Man m = (Man) man;
    m.a();
}

@Test
public void testInstanceof() {
    Person man = new Man();

    // 错误的强转会报错
    Woman woman = (Woman) man;

    // 使用instanceof判断
    if (man instanceof Man){
        Man m = (Man) man;
    }

}
```

<a id="oop-object-class"></a>
## Object类

* 类`java.lang.Object`是类层次结构的根类，即所有其他类的父类。每个类都使用`Object`作为超类
* Object类型的变量与除Object以外的任意引用数据类型的对象都存在多态引用

### Object类的方法

<a id="oop-object-equals"></a>
#### equals()方法

* 自定义类在没有重写Object的equals()方法的情况下，调用的就是Object类中声明的equals()方法，
比较两个对象的引用地址是否相同
* 在需要判断自定义类内的多个属性是否相同的情况下可以使用

##### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/object/equals/EqualsTest.java)

* 定义一个类

```java
public class User {

    private String name;

    private int age;

    public User(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (obj instanceof User){
            User user = (User) obj;
            return this.age == user.age && this.name.equals(user.name);
        }
        return false;
    }
}
```

* 测试

```java
User user1 = new User("zs", 11);
User user2 = new User("zs", 11);

// 重写equals方法前，比较对象地址
System.out.println(user1.equals(user2)); // false

// 重写equals方法前后，比较对象内的属性
System.out.println(user1.equals(user2)); // true
```

<a id="oop-object-tostring"></a>
#### toString()方法

* toString()方法默认返回当前对象的类名加地址
* `System.out.println()`方法就是使用`toString()`打印
* 用于自定义输出类里面的信息

##### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/object/tostring/ToStringTest.java)

* 定义一个类

```java
public class User {

    String name;

    int age;

    public User(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return "User{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```

* 测试

```java
User zs = new User("zs", 11);
System.out.println(zs);
```

<a id="oop-object-clone-finalize"></a>
#### clone()和finalize()方法

* clone()

* 定义一个类，实现Cloneable接口

```java
public class Person implements Cloneable{

    private String name;

    public Person(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    protected Object clone() throws CloneNotSupportedException {
        return super.clone();
    }
}
```

* 测试

```java
Person zs = new Person("zs");
Person zsCopy = (Person) zs.clone();

// 克隆后两个对象并不是同一个
System.out.println(zs == zsCopy);

// 克隆后修改原始对象内的基本数据类型的属性，不会改变克隆对象内的基本数据类型属性
zs.setName("zhangsan");
System.out.println(zs.getName());
System.out.println(zsCopy.getName());
```
* finalize()

```java
/**
 * 测试finalize方法，（jdk9被废弃了，不推荐使用）
 */
@Test
public void testFinalize() {
    Person zs = new Person("zs");
    zs = null; // 将引用指向为null表示这个对象是垃圾了，等待被回收，但时间不确定

    System.gc(); // 强制释放空间

}
```

<a id="oop-static-keyword"></a>
## static关键字

* 如果想让一个成员变量被类的所有实例所共享，就用`static`修饰即可，称为类变量（或类属性）

<a id="oop-static-field"></a>
### static修饰属性

* 使用static修饰的成员变量也叫静态变量或类变量
* 静态变量和实例变量的对比

|     | 静态变量    | 实例变量    |
|---------------- | --------------- | --------------- |
| **个数**    | 内存空间中只有一份，被多个对象共享    | 类的每一个实例都保存这自己的实例变量    |
| **内存位置**   | jdk6及之前存在方法区，jdk7及之后存在堆空间    | 存在堆空间的对象实体中    |
| **加载时机** | 随着类的加载而加载，由于类只会加载一次，所有静态变量只有一份 | 随着对象的创建而加载，每个对象拥有一份实例变量 |
| **调用者** | 可以被类之间调用，也可以被对象调用 | 只能被对象调用 |
| **消亡时机** | 随着类的卸载而消亡 | 随着对象的消亡而消亡 |

#### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/keywords/static_keyword/StaticTest.java)

* 定义类

```java
public class Chinese {
    String name;

    int age;

    public static String nation = "中国";

    public Chinese(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void eat(){
        System.out.println("吃饭");
    }

    public static void show_nation(){
        System.out.println("我的国际是：" + nation);

        // eat(); // 无法调用实例方法，编译不通过
    }

    public void show_info(){
        System.out.println("我的名字是：" + name);
        show_nation(); // 可以调用静态方法
    }

}
```

* 测试

```java
// 在对象创建之前就可以使用
System.out.println(Chinese.nation);

Chinese zs = new Chinese("zs", 11);
Chinese ls = new Chinese("ls", 12);

// 一个对象修改了实例变量，所有对象都生效
zs.nation = "china";
System.out.println(zs.nation); // china
System.out.println(ls.nation); // china
```

<a id="oop-static-method"></a>
### static修饰方法

* static修饰的方法也叫静态方法或类方法
* 静态方法内不用调用对象的实例方法，但实例方法可以调用静态方法
* 静态方法内不能使用`this`或`super`关键字，因为静态方法调用时，对象可能没创建

```java
Chinese.show_nation();

Chinese zs = new Chinese("zs", 11);

// 实例方法内调用静态方法
zs.show_info();
```

<a id="oop-code-block"></a>
## 代码块

* 用来初始化类或对象的成员变量
* 代码块又分为静态代码块和非静态代码块
    * 静态代码块随着类的加载而执行，只会执行一次
    * 非静态代码块随着对象的创建而执行，执行时机是在构造器的前面
    * 多个静态代码块或非静态代码块之间的执行顺序是根据代码块声明的位置而定
    * 静态代码块和非静态代码块调用属性和方法的规则与成员方法和静态方法规则相同
* 父类的代码块加载时机永远在子类之前

### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/block/BlockTest.java)

* 定义父类

```java
public class Person {
    String name;

    static String info = "123";

    public Person(String name) {
        System.out.println("构造器执行");
        this.name = name;
    }

    public void eat(){
        System.out.println("吃饭");
    }

    {
        System.out.println("代码块执行2");
    }
    {
        System.out.println("代码块执行1");
    }

    static {
        System.out.println("静态代码块执行1");
    }
    static {
        System.out.println("静态代码块执行2");
    }
}
```

* 定义子类

```java
public class Man extends Person{

    {
        System.out.println("2 代码块执行");
    }

    static {
        System.out.println("2 静态代码块执行");
    }

    static int a;
    public Man(String name) {
        super(name);
    }
}
```

* 测试

```java
public class BlockTest {
    @Test
    public void testBlock() {
        System.out.println(Person.info);

        Person zs = new Person("zs");
    }

    @Test
    public void testBlockWithExtends() {
        // 加载子类，会先执行父类的静态代码块再执行子类的静态代码块
        System.out.println(Man.a);

        System.out.println("---");

        // 创建子类会先执行父类的代码块，再执行父类构造方法，最后执行子类代码块
        Man zs = new Man("zs");

    }
}
```

<a id="oop-final-keyword"></a>
## final关键字

* `final`可以用来修饰：**类**、**方法**、**变量**
* 用`final`修饰**类**表示类不能被继承
* 用`final`修饰**方法**表示方法不能被重写
* 用`final`修饰变量
    * 可以修饰**成员变量**，**局部变量**，**形参**
    * 修饰这些变量之后都表示变量不能被修改了，也称为常量
    * `final`配合`static`修饰**成员变量**后称为全局常量

<a id="oop-abstract-keyword"></a>
## abstract关键字（抽象类或抽象方法）

* 我们声明的一些几何图形类中：圆、矩形，三角形等，这些类之间都有共同特征，求面积、周长等，
这些共同的特征可以抽取到一个公共的父类中，但这些方法在父类中**无法给出具体的实现**，
而是交给子类各自自己实现。那么父类在声明这些方法时，**就只有方法签名，没有方法体**，
我们把没有方法体的方法称为**抽象方法**，Java语法规定，包含抽象方法的类必须时**抽象类**
* 格式
    * **抽象类**：被`abstract`修饰的类
    * **抽象方法**：被`abstract`修饰没有方法体的方法

```java
public abstract class AbstractClass {
    abstract void abstractMethod();
}
```
* 抽象类
    * 抽象类不能实例化
    * 抽象类可以没有抽象方法，但抽象方法声明所在的类必须是抽象类
* 抽象方法
    * 抽象方法只有方法声明，没有方法体
    * 子类继承抽象类后必须重写父类的所有抽象方法，否则子类也必须要使用`abstract`修饰（编译器会检查）
* `abstract`不能修饰属性、构造器、代码块等
* `abstract`不能与私有方法、静态方法、final方法、final类共用
    * 私有方法不能被子类访问到所以不能共用
    * 避免静态类调用静态方法，静态方法未实现
    * final方法不能被重写
    * final类不能被继承

### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/abstract_class/AbstractTest.java)

* 定义几何图形抽象类

```java
/**
 * 几何图形类
 */
public abstract class Geometry {
    /**
     * 获取几何图形的面积
     */
    abstract double getArea();
}
```

* 定义圆形

```java
/**
 * 圆形
 */
public class Circle extends Geometry{
    int radius;
    @Override
    double getArea() {
        return Math.PI * (radius * radius);
    }
}
```

* 定义正方形

```java
/**
 * 正方形
 */
public class Square extends Geometry{
    int side;
    @Override
    double getArea() {
       return side * side;
    }
}
```

* 测试

```java
Circle circle = new Circle();
circle.radius = 5;
System.out.println(circle.getArea());

Square square = new Square();
square.side = 5;
System.out.println(square.getArea());
```

<a id="oop-interface"></a>
## interface（接口）

* 接口就是规范，定义的是一组规则，**继承**是一个“是不是”的`is-a`关系，而接口实现则是“能不能”的`has-a`关系
* 格式：
```java
public interface Interface{
    void abstractMethod();
}
```
* 接口结构说明：
    * 可以声明属性，但必须使用`public static final`修饰
    * 方法：
        * jdk8前只能声明抽象方法
        * jdk8后可以声明**静态方法**和**默认方法**
        * jdk9可以声明**私有方法**
    * 接口内不能又构造器、代码块等
* 接口与类的关系
    * B类继承A类，那么B为A类的子类
    * B类实现A类，那么B为A类的实现类
* 类可以实现多个接口
* 类必实现接口后必须将接口内的所有抽象方法都重写
* 接口与接口之间的关系：继承关系，接口之间可以多继承

### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/interface_test/InterfaceTest.java)

* 测试

```java
public class InterfaceTest {
    @Test
    public void testInterface() {
        Plane plane = new Plane();
        plane.fly();
        plane.attack();

        Kite kite = new Kite();
        kite.fly();
    }

    @Test
    public void testInterfaceExtends() {

        Gunship gunship = new Gunship();
        // Gunship未实现Flyable接口，也可以调用fly方法，因为Hovering接口继承了Flyable接口
        gunship.fly();
        gunship.hover();
        gunship.attack();
    }

    private void fly(Flyable flyable){
        flyable.fly();
    }
    
    @Test
    public void testAnonymousInterface() {
       fly(new Kite());

        Flyable flyable = new Flyable() {
            @Override
            public void fly() {
                System.out.println("飞");
            }
        };

        fly(flyable);
    }
}
```

<a id="oop-interface-features"></a>
### 接口新特性

* **静态方法**（jdk8）
    * 实现类无法调用接口的静态方法
* **默认方法**（jdk8）
    * 如果一个**类**实现的两个**接口**都有**同名同参**的**默认方法**，那么这个实现类必须重写这个方法
        * 重写后想要调用其中一个接口的同名方法的话使用`接口名.super.方法`调用
    * 如果一个类**继承了一个父类**并**实现了一个接口**，这个**父类**和**接口**内都有同名同参的方法，
    则默认调用父类的同名同参方法，**类优先原则**
* **私有方法**（jdk9）
    * 供接口内的默认方法使用，抽出接口内默认方法内的公共逻辑


### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/interface_test/new_methods/InterfaceTest.java)

* 测试静态方法默认方法

```java
/**
 * 测试接口
 *      静态方法默认方法（jdk8添加）
 *      私有方法（jkd9添加）
 */
public class InterfaceTest {

    /**
     * 测试静态方法
     */
    @Test
    public void testStaticMethod() {
        A.a1();
        // B.a1(); // 实现类无法调用接口的静态方法，编译不通过
    }

    /**
     * 测试默认方法
     */
    @Test
    public void testDefaultMethod() {

        B b = new B();
        b.a2(); // 调用A接口内的默认方法


        // B类实现了两个接口A、C，这两个接口都实现了同名同参的默认方法common1，实现类必须重写这个方法，否则会报错
        b.common1();

        // 子类或实现类继承了父类并实现类了接口，父类和接口内都声明了同名同参的方法，子类没重写这个方法的情况下默认调用的是父类的方法，类有优先则
        b.common2();
    }
}
```

* 测试调用多个接口内的同名同参方法

```java
public class B extends D implements A, C{

    public void b1(){
        System.out.println("b3");
    }

    @Override
    public void common1() {
        System.out.println("common1 in b");
    }


    public void b2(){
        common1(); // 调用自己的方法

        super.common2(); // 调用父类的同名同参方法

        common1(); // 调用自己类中的同名同参方法
        A.super.common1(); // 调用接口A的同名同参方法
        C.super.common1(); // 调用接口C的同名同参方法
    }

}
```

<a id="oop-inner-class"></a>
## 内部类（InnerClass）

* 将A类定义在B类里面，里面的A类就称为**内部类（InnerClass）**，类B则称为**外部类（OutClass）**
* 当事物A的内部，还有一个部分需要一个完整的结构B进行描述，而这个内部的完整的结构B又只为外部事物A提供服务，
不在其他地方单独使用，那么整个内部的完整结构B最好使用内部类
* 例子：
    * `Thread`内的`State`表示线程的生命周期
    * `HashMap`内的`Node`表示每个键值对的节点
* 内部类分类（和变量分类类似）
    * 成员内部类：静态成员内部类，非静态成员内部类
    * 局部内部类（声明在方法、构造器、代码块内部）：匿名局部内部类，非匿名局部内部类

### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/innerclass/InnerClassTest.java)

* 定义一个类

```java
public class Person {

    String name = "person";
    int age;

    static class Dog{

    }

    class Bird{

        String name = "bird";
        
        public void show(String name){
            System.out.println("age = " + age); // 调用外部内的属性
            System.out.println("name = " + name); // 调用形参
            System.out.println("this.name = " + this.name); // 调用内部类的成员变量
            System.out.println("Person.this.name = " + Person.this.name); // 调用外部类的成员变量

        }

    }

    public void method(){
        class InnerClass1{

        }
    }

    public Person(){
        class InnerClass1{

        }
    }

    {
        class InnerClass1{

        }
    }
}
```

* 测试

```java
public class InnerClassTest {
    @Test
    public void testInnerClass() {

        // 创建静态成员内部类
        Person.Dog dog = new Person.Dog();

        // 创建非静态成员内部类
        Person.Bird bird = new Person().new Bird();
        // 或
        Person person = new Person();
        Person.Bird bird1 = person.new Bird();
    }

    /**
     * 测试内部内调用外部类属性
     */
    @Test
    public void testInnerClassFields() {
        Person.Bird bird = new Person().new Bird();
        bird.show("new bird");
    }

    @Test
    public void testLocalInnerClass() {
        class Task implements Runnable{
            @Override
            public void run() {
                System.out.println("run");
            }
        }

        Task task = new Task();
        task.run();
    }
}
```

<a id="oop-enum-class"></a>
## 枚举类

* 枚举类本质上也是一种对象，只不过这个类的对象是有限的、固定的几个，不能随意创建
* 比如**星期（7个）**，**月份（12个）**
* 在jdk5之后使用`enum`关键字定义枚举类
* 如果枚举类的实现只有一个，则可以看作单例的实现方式
* 使用`enum`关键字定义的枚举类默认父类是`java.lang.Enum`
    * Enum父类中的常用方法：`toString()`, `static values()`, `static valueOf()`, `name()`, `ordinal()`
* 枚举类可以继承接口，继承接口后所以实例共用定义时重写的方法，如果需要每个实例单独重写方法的逻辑，
则可以在定义枚举实例时重写


### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/oop/enum_class/EnumTest.java)

* jdk5前定义枚举类的方式

```java
public class SeasonBefore {

    private final String seasonName;

    private SeasonBefore(String seasonName){
        this.seasonName = seasonName;
    }

    public String getSeasonName() {
        return seasonName;
    }

    public static final SeasonBefore SPRING = new SeasonBefore("春天");
    public static final SeasonBefore SUMMER = new SeasonBefore("夏天");
    public static final SeasonBefore AUTUMN = new SeasonBefore("秋天");
    public static final SeasonBefore WINTER = new SeasonBefore("冬天");

    @Override
    public String toString() {
        return "SeasonBefore{" +
                "seasonName='" + seasonName + '\'' +
                '}';
    }
}
```

* jdk5后定义枚举的方式

```java
public enum Season {
    SPRING("春天"),
    SUMMER("夏天"),
    AUTUMN("秋天"),
    WINTER("冬天");


    private final String seasonName;

    private Season(String seasonName){
        this.seasonName = seasonName;
    }

    public String getSeasonName() {
        return seasonName;
    }

    @Override
    public String toString() {
        return "Season{" +
                "seasonName='" + seasonName + '\'' +
                '}';
    }
}
```

* 枚举类定义接口操作

```java
public enum SeasonWithInterface implements Runnable{
    // 枚举实例自己实现对应的逻辑
    SPRING("春天"){
        @Override
        public void run() {
            System.out.println("春天 run");
        }
    },
    SUMMER("夏天"),
    AUTUMN("秋天"){
        @Override
        public void run() {
            System.out.println("秋天 run");
        }
    },
    WINTER("冬天");


    private final String seasonName;

    private SeasonWithInterface(String seasonName){
        this.seasonName = seasonName;
    }

    public String getSeasonName() {
        return seasonName;
    }

    @Override
    public String toString() {
        return "Season{" +
                "seasonName='" + seasonName + '\'' +
                '}';
    }

    @Override
    public void run() {
        System.out.println("季节");
    }
}
```

* 测试

```java
public class EnumTest {

    @Test
    public void testEnumBefore() {
        System.out.println(SeasonBefore.SPRING);
        System.out.println(SeasonBefore.SUMMER);
        System.out.println(SeasonBefore.AUTUMN);
        System.out.println(SeasonBefore.WINTER);
    }

    @Test
    public void testEnum() {
        // 由于* 使用`enum`关键字定义的枚举类默认父类是`java.lang.Enum`，toString方法默认会输出实例对象的命令
        System.out.println(Season.SPRING);
        System.out.println(Season.SUMMER);
        System.out.println(Season.AUTUMN);
        System.out.println(Season.WINTER);

        System.out.println("--");
        // Enum父类中的常用方法
        // name() 返回实例的名称
        System.out.println(Season.WINTER.name());

        // 静态方法values
        Season[] values = Season.values();
        for (int i = 0; i < values.length; i++) {
            System.out.println(values[i]);
        }

        // 静态方法valueOf
        System.out.println(Season.valueOf("SPRING")); // 根据命令获取枚举实例
        // System.out.println(Season.valueOf("SPRING1")); // 命令写错则会报错，IllegalArgumentException

        // ordinal返回当前枚举实例在枚举类中的位置索引
        System.out.println(Season.WINTER.ordinal());
    }

    @Test
    public void testEnumWithInterface() {
        // 继承至Runnable接口实现run方法
        // 未主动重写run方法，使用类重写的run方法
        SeasonWithInterface.SUMMER.run();
        SeasonWithInterface.WINTER.run();

        // 定义时重写自己的run方法
        SeasonWithInterface.SPRING.run();
        SeasonWithInterface.AUTUMN.run();
    }
}
```

<a id="oop-annotation"></a>
## 注解（Annotation）

* 注解是jdk5引入，以`@注解名`存在与代码中
* Annotation可以像修饰符一样使用，可以用于修饰包、类、构造器、方法、成员变量、参数、局部变量的声明
* 注解可以在类编译、运行时进行加载，体现不同的功能
* 注解与注释的区别
    * **注释**主要是给程序员看的
    * **注解**可以给程序员看，可以被编译器读取，实现一些特定的功能
* java基础常见的注解：
    * `@Override`：限定重写父类的方法，该注解只能用于方法
    * `@Deprecated`：表示修饰的元素（类、方法等）以过时，不推荐使用或有更好的选择
    * `@SuppressWarnings`：抑制编译器警告

### 注解的定义

```java
public @interface MyAnnotation {
    String value() default "123";
}
```

<a id="oop-meta-annotation"></a>
### 元注解

* 对现有注解进行解释说明的注解
* 说明：
    * `@Target`：用于描述注解的使用范围，可以通过枚举类`ElementType`的对象来指定
    * `@Retention`：用于描述注解的声明周期，通过枚举类`RetentionPolicy`的对象来指定
        * `SOURCE`、`CLASS`、`RUNTIME`
        * 只用`RUNTIME`阶段才能被反射读取
    * `@Documented`：表示这个注解应该被`javadoc`工具记录
    * `@Inherited`：运行子类继承父类的注解

<a id="oop-wrapper"></a>
## 包装类

* Java对八种基本数据类型定义了对应的引用类型，**包装类**
* 基本数据类型中，数值类型的父类都是`Number`

| 基本数据类型   | 包装类    |
|--------------- | --------------- |
| byte   | Byte   |
| short   | Short   |
| int   | Integer   |
| long   | Long   |
| float   | Float   |
| double   | Double   |
| boolean   | Boolean   |
| char   | Character   |

<a id="oop-basic-data-and-wrapper-class"></a>
### 基本数据类型与包装类型之间的转换

<a id="oop-basic-data-to-wrapper-class"></a>
* 基本数据类型转包装类，**成员变量定义为包装类后默认值会变为null**

```java
int i = 1;
Integer integer = Integer.valueOf(i);

float f = 1.1F;
Float float_value = Float.valueOf(f);

boolean b = true;
Boolean.valueOf(b);
```

<a id="oop-wrapper-class-to-basic-data"></a>
* 包装类转基本数据类型

```java
Integer i = Integer.valueOf(1);
int int_value = i.intValue();

Double d = Double.valueOf(1.1);
double double_value = d.doubleValue();

Boolean b = Boolean.valueOf(true);
boolean bool = b.booleanValue();
```

<a id="oop-auto-boxing-unboxing"></a>
* 自动装箱和拆箱（jdk5）

```java
Integer i = 1;
Double d = 2.2;
Boolean b = false;

int i1 = i;
double d1 = d;
boolean b1 = b;
```

<a id="oop-string-to-basic-data-and-wrapper-class"></a>
### String与基本数据类型和包装类型之间的转换

* 基本数据类型、包装类转String，**调用String.valueOf()及其重载方法**
 
```java
// 调用String.valueOf()方法
int i = 1;
String s1 = String.valueOf(i);

double d = 2.2;
String s2 = String.valueOf(d);

boolean b = true;
String s3 = String.valueOf(b);

// 或直接拼接空串
String s4 = i + "";
String s5 = d + "";
String s6 = b + "";
```

* String转基本数据类型、包装类，**调用各个包装类的parseXXX方法**

```java
String s1 = "132";
int i1 = Integer.parseInt(s1);
String s2 = "132abc";
// int i2 = Integer.parseInt(s2); // 不是数值无法转换，报错NumberFormatException

String s3 = "true";
Boolean b1 = Boolean.valueOf(s3);

String s4 = "TrUe";
Boolean b2 = Boolean.valueOf(s4); // boolean转换时可以无视大小写
```

<a id="oop-auto-boxing-issues"></a>
### 自动装箱相关问题

* 以下两处自动装箱为什么结果不一样
* 因为自动装箱底层调用的是valueOf方法，而方法内对应-128~127之间的数直接会在内部缓存中取，
而超过这个范围后会直接new一个新对象，所以下面一对比较时为false
* 因为实际开开发时使用的这个范围的数据很多，所以直接存放在缓存内

```java
Integer i1 = 1;
Integer i2 = 1;
System.out.println(i1 == i2); // true

Integer i3 = 128;
Integer i4 = 128;
System.out.println(i3 == i4); // false
```

<a id="oop-wrapper-cache-object"></a>
#### 包装类缓存对象

| 包装类   | 缓存对象    |
|--------------- | --------------- |
| Byte   | -128~127   |
| Short   | -128~127   |
| Integer   | -128~127   |
| Long   | -128~127   |
| Float   | 没有   |
| Double   | 没有  |
| Character| 0~127  |
| Boolean   | true和false  |


<a id="exceptions"></a>
## 异常处理

* 在使用计算机语言进行项目开发的过程中，即使程序员把代码写的尽善尽美，
在系统运行过程中任然会遇到一些问题，因为很多问题不是能靠代码避免的，比如：客户输入的数据格式问题、
读取文件是否存在，网络是否通畅等
* **异常**：指的是程序在运行的过程中，出现了非正常的情况，如果不处理最终会导致JVM的非正常停止
* Java中异常的抛出机制
    * java中把不同的异常用不同的类表示，一旦发生某种异常，就创建该类异常类型的对象，并且抛出（throw）。
    然后程序员可以捕获（catch）到这个异常类，并处理；如果没有捕获（catch）这个异常类，
    那么这个异常对象会导致程序终止

### Java异常体系

#### Throwable

* `java.lang.Throwable`类是java程序执行过程中发生的异常事件对应的类的根父类。
* Throwable中的常用方法：
    * `printStackTrace()`：打印异常的详细信息
    * `getMessage()`：获取发生异常的原因

#### Error和Exception

* Throwable可以分为两类：Error和Exception。分别对应`java.lang.Error`和`java.lang.Exception`两个类
* **Error**：java虚拟机无法解决的严重问题。如：JVM系统内部错误、资源耗尽等严重情况。一般不编写针对性的代码进行处理
    * 例如：`StackOverflowError`（栈内存溢出）和`OutOfMemoryError`（堆内存溢出，简称OOM）
* **Exception**：其他因编程错误或偶然的外在因素导致的一般性问题，需要使用针对性代码进行处理，
使程序继续运行，否则一旦出现异常，程序也会挂掉。例如：
    * 空指针访问，试图读取不存在的文件，网络连接中断等

##### Error

* 模拟错误

```java
public static void main(String[] args) {
    // 模拟StackOverflowError错误
    // main(args);

    // 模拟OutOfMemoryError错误
    int[] ints = new int[100000000 * 100000000];
}
```

##### Exception

<a id="compile-time-and-runtime-exception"></a>
###### 编译时异常和运行时异常

* java程序的执行分为编译时过程和运行时过程。有的错误只有在运行时才会发生。

```mermaid
flowchart LR
a(Java源程序) --javac--> b(字节码文件)
b --java--> c(在内存中加载或运行类)
```

* 根据异常可能出现的阶段分为：
    * **编译时异常**（即checked异常、受检异常）：在代码编译阶段，
    编译器就能明确警示当前代码可能发生（不一定发生）xx异常，并明确督促程序员提前编写处理它的代码。
    如果程序员没有编写对应的异常处理代码，则编译器就会直接判定编译失败，从而不能生成字节码文件
    * **运行时异常**（即runtime异常、unchecked异常、非受检异常）：在代码的编译阶段，编译器完全不做任何检查，
    无论该异常是否会发生，编译器都不给出任何提示。只有等代码运行起来并确实发生了xx异常，它才能被发现。
    通常这类异常时程序员编写代码不当引起，只要编写时判断就可以大部分避免
        * 在java中`java.lang.RuntimeException`类及它的子类都是运行时异常

###### 代码示例

* 运行时异常

```java
/**
 * 测试ArrayIndexOutOfBoundsException
 */
@Test
public void testArrayIndexOutOfBoundsException() {
    int[] ints = new int[4];
    System.out.println(ints[4]);
}

/**
 * 测试NullPointerException
 */
@Test
public void testNullPointerException() {
    String name = "zs";
    name = null;
    System.out.println(name.length());
}

/**
 * 测试ClassCastException
 */
@Test
public void testClassCastException() {
    Object o = new Object();
    Date date = (Date) o;
    System.out.println(date);
}

/**
 * 测试NumberFormatException
 */
@Test
public void testNumberFormatException() {
    String number = "132abc";
    Integer integer = Integer.valueOf(number);
    System.out.println(integer);
}

/**
 * 测试ArithmeticException
 */
@Test
public void testArithmeticException() {
    System.out.println(10 / 0);
}
```

* 编译时异常

```java
/**
 * 测试ClassNotFoundException编译时异常
 */
@Test
public void testClassNotFoundException() {
    // Class.forName("a.b.c").var
}

/**
 * 测试FileNotFoundException和IOException编译时异常
 */
@Test
public void testFileNotFoundExceptionAndIOException() {
    // FileNotFoundException
    // FileInputStream fis = new FileInputStream("a.txt");
    // IOException
    // fis.close();
}
```

<a id="java-exception-handing"></a>
### Java异常的处理

* java采用的异常处理机制，是将异常处理和程序代码集中在一起，与正常的程序代码分开，时程序简洁、易于维护
* java异常处理的方式
    * `try-catch-finally`
    * `throws+异常类型`

<a id="try-catch-finally"></a>
#### 捕获异常（try-catch-finally）

* 基本结构：

```java
try{
    // 可能产生异常的代码
}catch(异常类型1 e){
    // 当产生异常类型1时的处理措施
}catch(异常类型2 e){
    // 当产生异常类型2时的处理措施
}finally{
    // 无论是否发生异常，都无条件执行的语句
}
```
* finally语句和catch语句是可选的，但finally不能单独使用
* 如果声明了多个catch结构，不同异常类型在不存在父子类关系的情况下，声明的顺序无所谓，
如果多个异常满足父子类关系，则子类catch必须声明在父类的上面，否则报错
* catch中异常处理的方式：
    * 自己编写输出语句
    * 使用printStackTrace打印信息
    * 使用getMessage获取异常的原因

* 对应运行时异常不进行显示的处理，对应编译时异常一定要处理，否则编译不通过

##### 代码示例

```java
public class TryCatchFinallyTest {
    
    @Test
    public void testTryCatch() {
        String s = "123abc";
        try {
            Integer integer = Integer.valueOf(s);
            System.out.println(integer);
        }catch (NumberFormatException e){
            System.out.println("程序出错");
        }catch (NullPointerException e){ // NumberFormatException与NullPointerException异常是并列关系，所以捕获的顺序无所谓
            System.out.println("程序出错");
        }catch (RuntimeException e){ // RuntimeException是上面两个异常的父类，必须放在最后，如果放在第一个，则表示把子类异常一起捕获了
            System.out.println("运行时异常");
        }
        System.out.println("程序结束");
    }

    @Test
    public void testTryCatchAndPrintStackTrace() {
        String s = "123abc";
        try {
            Integer integer = Integer.valueOf(s);
            System.out.println(integer);
        }catch (NumberFormatException e){
            e.printStackTrace();
        }
        System.out.println("程序结束");
    }

    private int strToInt(String str){
        try {
            Integer integer = Integer.valueOf(str);
            return integer;
        }catch (NumberFormatException e){
            return -1;
        }finally {
            System.out.println("程序执行完成");
        }
    }

    @Test
    public void testTryCatchFinally() {
        System.out.println(strToInt("123abc"));
    }
}
```

<a id="throws"></a>
#### 抛出异常（throws）

* 格式：

```java
public void method() throws 异常1, 异常2 {
    // 可能有移除的代码
}
```
* 使用throws并不是真正处理了异常，对**使用者**来说是没有异常了，但是对于**调用者**来说还是要处理异常

##### 代码示例

```java
public class ThrowsTest {

    public void method() throws IOException {
        FileInputStream fis = new FileInputStream("a.txt");
        fis.close();
    }

    @Test
    public void testThrows() {
        try {
            method();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

<a id="exceptions-choice"></a>
#### 两种异常处理方式的选择

* 如果程序代码中，涉及到资源的调用（流、数据库连接、网络连接等），
则必须考虑使用`try-catch-finally`来处理，保证不出现内存泄露
* 如果父类被重写的方法没有`throws`异常类型，子类重写的方法内出现了异常，只能使用`try-catch-finally`进行处理
* 如果方法a是使用者，方法b、c是被使用者，那边如果方法b、c方法内如果出现了异常可以使用`throws`方式，
方法a内的异常可以使用`try-catch-finally`处理

<a id="throwing-exception-manually"></a>
### 手动抛出异常

* 格式：`throw 异常对象`
* 在实际开发中，如果出现不满足具体场景的代码问题，我们就可以手动抛出异常
* `throw`和`throws`的区别
    * `throws`用于声明方法可能抛出的异常，而`throw`是直接抛出具体的异常

#### 代码示例

```java
public class ThrowTest {

    public void setAge(int age){
        if (age < 0){
            throw new RuntimeException("年龄不能为负数");
        }
        System.out.println(age);
    }

    /**
     * 测试手动抛出运行时异常
     */
    @Test
    public void testThrowRuntimeException() {
        setAge(10);

        setAge(-10); // 报错
    }

    public void setPhone(String phone) throws Exception {
        if (phone.length() != 11){
            throw new Exception("电话号码必须为11位");
        }
        System.out.println(phone);
    }

    /**
     * 测试手动抛出编译时异常
     */
    @Test
    public void testThrowException() {
        try {
            setPhone("12345678901");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

<a id="custom-exception"></a>
### 自定义异常

* 自定义异常类步骤
    1. 继承现有的异常体系，`RuntimeException`或`Exception`
    2. 提供几个重载的构造器
    3. 提供一个全局常量，声明为：`static final long serialVersionUID`
* 自定义异常类要做到**见名知意**，程序运行过程中出现异常后可以根据异常的命名快速定位问题

#### 代码示例

> [详细代码](https://github.com/follow1123/java-basics/blob/main/src/main/java/cn/y/java/exceptions/custom_exception/CustomExceptionTest.java)

* 定义异常

```java
/**
 * 错误年龄异常
 */
public class WrongAgeException extends RuntimeException{

    @java.io.Serial
    private static final long serialVersionUID = -7034897290745766939L;

    public WrongAgeException(String message) {
        super(message);
    }

    public WrongAgeException(String message, Throwable cause) {
        super(message, cause);
    }
}
```

* 定义另一个异常

```java
/**
 * 错误手机号异常
 */
public class WrongPhoneNumberException extends RuntimeException{

    @java.io.Serial
    private static final long serialVersionUID = -7034997290745766939L;

    public WrongPhoneNumberException(String message) {
        super(message);
    }

    public WrongPhoneNumberException(String message, Throwable cause) {
        super(message, cause);
    }
}
```

* 测试

```java
public class CustomExceptionTest {

    public void setAge(int age) {
        if (age < 0) {
            throw new WrongAgeException("年龄不能为负数");
        }
        System.out.println(age);
    }

    /**
     * 测试手动抛出自定义WrongAgeException运行时异常
     */
    @Test
    public void testThrowRuntimeException() {
        setAge(10);

        setAge(-10); // 报错
    }

    public void setPhone(String phone) throws WrongPhoneNumberException {
        if (phone.length() != 11) {
            throw new WrongPhoneNumberException("电话号码必须为11位");
        }
        System.out.println(phone);
    }

    /**
     * 测试手动抛出WrongPhoneNumberException编译时异常
     */
    @Test
    public void testThrowException() {
        try {
            setPhone("123456789011");
        } catch (WrongPhoneNumberException e) {
            e.printStackTrace();
        }
    }
}
```
