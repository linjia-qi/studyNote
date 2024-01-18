# Day01 Java概述

## 1.1 JDK

1. 什么是jdk？

   JDK 是 Java Development ToolKit 的简称，也就是 Java 开发工具包。JDK 是整个 Java 的核心，包括 Java 运行环境（Java Runtime Envirnment，简称 JRE），Java 工具（比如 javac、java、javap 等等），以及 Java 基础类库（比如 rt.jar）。

   最主流的 JDK 是 Oracle 公司发布的 JDK，除了 Oracle JDK（商业化，更稳定）之外，还有很多公司和组织开发了属于自己的 JDK，比较有名的有 IBM JDK（更适合 IBM） 和 OpenJDK（开源的）。每个 JDK 都有自己的优缺点，我们开发者只需要掌握 Oracle JDK 就好了。

2. 开发Java程序，需要使用JDK提供的开发工具（比如javac.exe、java.exe等命令），而这些工具在JDK的安装目录的bin目录下，如果不配置环境变量，那么这些命令只可以在bin目录下使用，而我们想要在任意目录下都能使用，所以就要配置环境变量。

注意：现在最新从官网上下载的JDK安装时会自动配置javac、java命令的路径到Path环境变量中去 ，所以javac、java可以直接使用。

## 1.2 Java的三大平台

​	JavaSE、JavaME、JavaEE

### 1.2.1 JavaSE

​	是其他两个版本的基础。

### 1.2.2 JavaME

​	Java语言的小型版，用于嵌入式消费类电子设备或者小型移动设备的开发。

​	其中最为主要的还是小型移动设备的开发（手机）。渐渐的没落了，已经被安卓和IOS给替代了。

​	但是，安卓也是可以用Java来开发的。

### 1.2.3 JavaEE

​	用于Web方向的网站开发。（主要从事后台服务器的开发）

​	在服务器领域，Java是当之无愧的龙头老大。

## 1.3 Java的主要特性

- 面向对象
- 安全性
- 多线程
- 简单易用
- 开源
- 跨平台

### 1.3.1 Java语言跨平台的原理

- 操作系统本身其实是不认识Java语言的。
- 但是针对于不同的操作系统，Java提供了不同的虚拟机。

虚拟机会把Java语言翻译成操作系统能看得懂的语言。

![image-20210923091350952](D:\studyNote\java\github_studyNote_repo\Java\assets\image-20210923091350952-1705572959988-2.png)

## 1.4 JRE和JDK

![image-20210923091544110](D:\studyNote\java\github_studyNote_repo\Java\assets\image-20210923091544110.png)

JVM（Java Virtual Machine），Java虚拟机

JRE（Java Runtime Environment），Java运行环境，包含了JVM和Java的核心类库（Java API）

JDK（Java Development Kit）称为Java开发工具，**包含了JRE和开发工具**

![image](D:\studyNote\java\github_studyNote_repo\Java\assets\Snipaste_2023-12-07_22-43-32.png)

总结：我们只需安装JDK即可，它包含了java的运行环境和虚拟机。



# Day02 Java基础语法

## 1. 关键字

### 1.1 概念

​	被Java赋予了**特定含义**的英文单词。

注意：关键字很多，不用刻意去记。

| **abstract**   | **assert**       | **boolean**   | **break**      | **byte**   |
| -------------- | ---------------- | ------------- | -------------- | ---------- |
| **case**       | **catch**        | **char**      | **class**      | **const**  |
| **continue**   | **default**      | **do**        | **double**     | **else**   |
| **enum**       | **extends**      | **final**     | **finally**    | **float**  |
| **for**        | **goto**         | **if**        | **implements** | **import** |
| **instanceof** | **int**          | **interface** | **long**       | **native** |
| **new**        | **package**      | **private**   | **protected**  | **public** |
| **return**     | **strictfp**     | **short**     | **static**     | **super**  |
| **switch**     | **synchronized** | **this**      | **throw**      | **throws** |
| **transient**  | **try**          | **void**      | **volatile**   | **while**  |

### 1.2 第一个关键字class

​	表示定义一个类。创建一个类。

类：Java项目最基本的组成单元，一个完整的Java项目有可能会有成千上万个类来组成的。

class后面跟随的就是这个类的名字，简称：类名。

在类名后面会有一对大括号，表示这个类的内容。

举例：

```java
public class HelloWorld{
    
   
}
```

解释：class表示定义类。

​	类名：HelloWorld

​	HelloWorld后面的大括号表示这个类的范围。

## 2. 字面量

作用：告诉程序员，数据在程序中的书写格式。

| **字面量类型** | **说明**                                  | **程序中的写法**           |
| -------------- | ----------------------------------------- | -------------------------- |
| 整数           | 不带小数的数字                            | 666，-88                   |
| 小数           | 带小数的数字                              | 13.14，-5.21               |
| 字符           | 必须使用单引号，有且仅能一个字符          | ‘A’，‘0’，   ‘我’          |
| 字符串         | 必须使用双引号，内容可有可无              | “HelloWorld”，“黑马程序员” |
| 布尔值         | 布尔值，表示真假，只有两个值：true，false | true 、false               |
| 空值           | 一个特殊的值，空值                        | 值是：null                 |

~~~java
public class Demo {
    public static void main(String[] args) {
        System.out.println(10); // 输出一个整数
        System.out.println(5.5); // 输出一个小数
        System.out.println('a'); // 输出一个字符
        System.out.println(true); // 输出boolean值true
        System.out.println("欢迎来到黑马程序员"); // 输出字符串
    }
}
~~~

### 区分技巧

1. 不带小数点的数字都是整数类型的字面量。
2. 只要带了小数点，那么就是小数类型的字面量。
3. 只要用双引号引起来的，不管里面的内容是什么，不管里面有没有内容，都是字符串类型的字面量。
4. 字符类型的字面量必须用单引号引起来，不管内容是什么，但是个数有且只能有一个。
5. 字符类型的字面量只有两个值，true、false。
6. 空类型的字面量只有一个值，null。

### 扩展

1. \t 制表符：在打印的时候，把前面字符串的长度补齐到8，或者8的倍数。**最少补1个空格，最多补8个空格。**

## 3. 变量

### 3.1 什么是变量？

​	变量就在程序中临时存储数据的容器。但是这个容器中只能存一个值。

### 3.2 变量的定义格式

​	数据类型 变量名 = 数据值；

#### 3.2.1 格式详解

​	数据类型：限定了变量当中能存储什么类型的数据。

​			   如果要存10，那么数据类型就需要写整数类型。

​			   如果要存10.0，那么数据类型就需要写小数类型。

​	变量名：其实就是这个容器的名字。

​			当以后想要使用变量里面的数据时，直接使用变量名就可以了。

​	数据值：真正存储在容器中的数据。

​	分号：表示语句的结束，就跟以前写作文时候的句号是一样的。

#### 3.2.2 常用的数据类型

​	整数：int

​	小数：（浮点数）double

​	其他数据类型稍后讲解

举例：

```java
public class VariableDemo{
	public static void main(String[] args){
		//定义一个整数类型的变量
		//数据类型 变量名 = 数据值;
		int a = 16;
		System.out.println(a);//16
		
		//定义一个小数类型的变量
		double b = 10.1;
		System.out.println(b);//10.1
	}
}
```

#### 3.2.3 变量的注意事项

- 变量名不能重复
- 在一条语句中，可以定义多个变量。但是这种方式影响代码的阅读，所以了解一下即可。
- 变量在使用之前必须要赋值。**建议：定义变量的时候直接赋值，不要把定义和赋值分开写。**

案例：

```java
public class VariableDemo2{
	public static void main(String[] args){
		//1.变量名不允许重复
		//int a = 10;
		//int a = 20;
		//System.out.println(a); 会报错：重定义
		
		//2.一条语句可以定义多个变量
		//了解。
		//int a = 10, b = 20, c = 20,d = 20;
		//System.out.println(a);//?
		//System.out.println(b);//?
		
		
		//3.变量在使用之前必须要赋值
		int a = 30;
		System.out.println(a);
	}
}
```


## 4. 计算机数据存储规则

### 4.1 数据类型3种

* Text文本
* Image图片
* Sound声音。（视频=图片＋声音）

### 4.2 在计算机中，任意数据都是用二进制方式存储的。

#### 4.2.1 不同进制在代码中的表现形式

   ![进制](D:\studyNote\java\github_studyNote_repo\Java\assets\进制.png)

* 问：计算机为什么使用二进制

* 答：二进制只有两个状态，便于表示和区分。

   以前，用纸带的无孔和有孔分别表示0和1；现在，用电路板上通过电流的高压（>3.3V / 5V）和低压(<3.3V / 5V)分别表示1和0。

#### 4.2.2 任意进制转十进制

![进制转换](D:\studyNote\java\github_studyNote_repo\Java\assets\进制转换.png)

#### 4.2.3 二进制转十进制快速转换法：8421快速转换法。

![8421](D:\studyNote\java\github_studyNote_repo\Java\assets\8421.png)

#### 4.2.4 任意进制转十进制：除基取余法。

![进制转换](D:\studyNote\java\github_studyNote_repo\Java\assets\除基.png)

#### 4.2.5 进制转换总结

![总结](D:\studyNote\java\github_studyNote_repo\Java\assets\总结.png)

### 4.3 计算机存储规则：ASCII码表。

#### 4.3.1 文本数据

* 对于字母'a'，先查找码表，找到对应数字97，再转换成二进制存储。

![](D:\studyNote\java\github_studyNote_repo\Java\assets\ascii.png)

* 中文怎么存储？——编码规则的发布。 先查找码表找到对应的数字，再转换成二进制存储在计算机中。

![](D:\studyNote\java\github_studyNote_repo\Java\assets\中文.png)



#### 4.3.2 图片数据

* ——灰度图 用0~255表示灰度数据

![](D:\studyNote\java\github_studyNote_repo\Java\assets\灰度图.png)

* 彩色图——计算机中的三原色：红绿蓝

![](D:\studyNote\java\github_studyNote_repo\Java\assets\三原色.png)图为计算机的像素点放大后的效果。

* **三原色总结**：

![](D:\studyNote\java\github_studyNote_repo\Java\assets\三原色小结.png)

#### 4.3.3 声音数据：

* 对声波进行采样，每一个点都有对应的数字。

![](D:\studyNote\java\github_studyNote_repo\Java\assets\声音数据.png)

举例：氪金：采样点密集，声音质量高；不氪金：采样点稀疏 ，音质差。

![](D:\studyNote\java\github_studyNote_repo\Java\assets\声音.png)

### 4.4 总结：在计算机中，任意数据都是以二进制形式存储的。

![](D:\studyNote\java\github_studyNote_repo\Java\assets\总结图.png)

## 5. 数据类型

### 5.1 Java语言数据类型的分类

- 基本数据类型
- 引用数据类型（面向对象的时候再深入学习）

### 5.2 基本数据类型的四类八种

| 数据类型 | 关键字  | 内存占用 |                 取值范围                  |
| :------: | :-----: | :------: | :---------------------------------------: |
|   整数   |  byte   |    1     |    负的2的7次方 ~ 2的7次方-1(-128~127)    |
|          |  short  |    2     | 负的2的15次方 ~ 2的15次方-1(-32768~32767) |
|          |   int   |    4     |    负的2的31次方 ~ 2的31次方-1(10位数)    |
|          |  long   |    8     |   负的2的63次方 ~ 2的63次方-1（19位数）   |
|  浮点数  |  float  |    4     |        1.401298e-45 ~ 3.402823e+38        |
|          | double  |    8     |      4.9000000e-324 ~ 1.797693e+308       |
|   字符   |  char   |    2     |                  0-65535                  |
|   布尔   | boolean |    1     |                true，false                |

#### 说明

​	e+38表示是乘以10的38次方，同样，e-45表示乘以10的负45次方。

​	在java中整数默认是int类型，浮点数默认是double类型。

#### 需要记忆以下几点

byte类型的取值范围：

​	-128 ~ 127

int类型的大概取值范围：

​	-21亿多  ~ 21亿多

整数类型和小数类型的取值范围大小关系：

​	double > float > long > int > short > byte

最为常用的数据类型选择：

- 在定义变量的时候，要根据实际的情况来选择不同类型的变量。

  比如：人的年龄，可以选择byte类型。

  比如：地球的年龄，可以选择long类型。

- 如果整数类型中，不太确定范围，那么默认使用int类型。

- 如果小数类型中，不太确定范围，那么默认使用double类型。

- 如果要定义字符类型的变量，那么使用char

- 如果要定义布尔类型的变量，那么使用boolean

### 5.3 定义8种基本数据类型变量

```java
public class VariableDemo3{
    public static void main(String[] args){
        //1.定义byte类型的变量
        //数据类型 变量名 = 数据值;
        byte a = 10;
        System.out.println(a);

        //2.定义short类型的变量
        short b = 20;
        System.out.println(b);

        //3.定义int类型的变量
        int c = 30;
        System.out.println(c);

        //4.定义long类型的变量
        long d = 123456789123456789L;
        System.out.println(d);

        //5.定义float类型的变量
        float e = 10.1F;
        System.out.println(e);

        //6.定义double类型的变量
        double f = 20.3;
        System.out.println(f);

        //7.定义char类型的变量
        char g = 'a';
        System.out.println(g);

        //8.定义boolean类型的变量
        boolean h = true;
        System.out.println(h);

    }
}
```

#### **注意点**

- 如果要定义 一个整数类型的变量，不知道选择哪种数据类型了，默认使用int。
- 如果要定义 一个小数类型的变量，不知道选择哪种数据类型了，默认使用double。
- 如果要定义一个long类型的变量，那么在数据值的后面**需要加上L后缀**。（大小写都可以，**建议大写**。）
- 如果要定义一个float类型的变量，那么在数据值的后面需要加上F后缀。（大小写都可以） 

#### 总结

![](D:\studyNote\java\github_studyNote_repo\Java\assets\数据类型.png)



## 6. 标识符

业内大多数程序员都在遵守阿里巴巴的命名规则。

在day02的资料文件夹中有。 

### 6.1 硬性要求：

​	必须要这么做，否则代码会报错。

- 必须由数字、字母、下划线_、美元符号$组成。
- 数字不能开头
- 不能是关键字
- 区分大小写的。

### 6.2 软性建议：

​	如果不这么做，代码不会报错，但是会让代码显得比较low。

### 6.2.1 小驼峰命名法

适用于变量名和方法名

* 如果是一个单词，那么全部小写，比如：name

* 如果是多个单词，那么从第二个单词开始，首字母大写，比如：firstName、maxAge

### 6.2.2 大驼峰命名法

适用于类名

* 如果是一个单词，那么首字母大写。比如：Demo、Test。

* 如果是多个单词，那么每一个单词首字母都需要大写。比如：HelloWorld

不管起什么名字，都要做到见名知意。

### 阿里巴巴命名规范细节：

1. 尽量不要用拼音。但是一些国际通用的拼音可视为英文单词。

   正确：alibaba、hangzhou、nanjing

   错误：jiage、dazhe

2. 平时在给变量名、方法名、类名起名字的时候，不要使用下划线或美元符号。

   错误：_name

   正确：name

## 7. 键盘录入

​	**键盘录入**的实际功能Java已经帮我们写好了，不需要我们自己再实现了，而Java写好的功能都放在了**Scanner**这个类中，所以，我们只要直接使用Scanner这个类就可以了。

使用步骤：

第一步：

​	导包：其实就是表示先找到Scanner这个类在哪。

第二步：

​	创建对象：其实就表示申明一下，我准备开始用Scanner这个类了。

第三步：

​	接收数据：也是真正干活的代码。

代码示例：

```java
//导包，其实就是先找到Scanner这个类在哪
import java.util.Scanner;
public class ScannerDemo1{
	public static void main(String[] args){
		//2.创建对象，其实就是申明一下，我准备开始用Scanner这个类了。
		Scanner sc = new Scanner(System.in);
		//3.接收数据
		//当程序运行之后，我们在键盘输入的数据就会被变量i给接收了
		System.out.println("请输入一个数字");
		int i = sc.nextInt();
		System.out.println(i);
	}
}
```

# Day03 运算符和表达式

## 1.1 概览

#### 1.1.1 运算符：

​	就是对常量或者变量进行操作的符号。

​	比如： +  -  *  / 

#### 1.1.2 表达式：

​	用运算符把常量或者变量连接起来的，符合Java语法的式子就是表达式。

​	比如：a + b 这个整体就是表达式。

​	而其中+是算术运算符的一种，所以这个表达式也称之为算术表达式。

#### 1.1.3 运算符六种类型

<img src="D:\studyNote\java\github_studyNote_repo\Java\assets\运算符.png" style="zoom:50%;" />

## 1.2 算术运算符

#### 1.2.1 分类：

```java
+ - * / %  //5种算数运算符
```

#### 1.2.2 运算特点：

```java
+ - * :跟小学数学中一模一样没有任何区别.
```

```java
/：
1.整数相除结果只能得到整除，如果结果想要是小数，必须要有小数参数。
2.小数直接参与运算，得到的结果有可能是不精确的。
案例：
System.out.println( 10 / 3);//3
System.out.println(10.0 / 3);//3.3333333333333335
```

```java
%：取模、取余。
   他做的也是除法运算，只不过获取的是余数而已。
案例：
System.out.println(10 % 2);//0
System.out.println(10 % 3);//1
应用场景：
//可以利用取模来判断一个数是奇数还是偶数
System.out.println(15 % 2);//1  奇数
```

### 练习：数值拆分

需求：键盘录入一个三位数，将其拆分为个位、十位、百位后，打印在控制台

代码示例：

```java
//1.键盘录入一个三位数
//导包 --- 创建对象 --- 接收数据
Scanner sc = new Scanner(System.in);
System.out.println("请输入一个三位数");
int number = sc.nextInt();//123

//2.获取这个三位数的个位、十位、百位并打印出来
//公式：
//针对于任意的一个数而言
//个位： 数字 % 10
int ones = number % 10;
//十位： 数字 / 10 % 10
int tens = number / 10 % 10;
//百位： 数字 / 100 % 10
int hundreds = number / 100  % 10;

//输出结果
System.out.println(ones);
System.out.println(tens);
System.out.println(hundreds);
```

公式：

​	获取任意一个数上每一位数。

个位：数字 % 10

十位：数字 / 10 % 10

百位：数字 / 100 % 10

千位：数字 / 1000 % 10

。。。以此类推。。。

### 1.2.1 隐式转换

#### 1.3.1 概念：

​	也叫自动类型提升。

​	就是把一个**取值范围小的数据或者变量，赋值给另一个取值范围大的变量**。此时不需要我们额外写代码单独实现，是程序自动帮我们完成的。

#### 1.3.2 简单记忆：

​	就是小的给大的，可以直接给。

#### 1.3.3 存储层面：在数据前面补零，如图所示。

<img src="D:\studyNote\java\github_studyNote_repo\Java\assets\隐式转换.png" style="zoom:50%;" />



#### 1.3.4 两种提升规则：

* 取值范围小的，和取值范围大的进行运算，小的会先提升为大的，再进行运算。
* byte、short、char三种类型的数据在运算的时候，都会直接先提升为int，然后再进行运算。

#### 1.3.5 取值范围从小到大的关系：

​	byte short int long float double

### 1.2.2 隐式转换的练习

请看下面案例是否有误，如果有问题，请说出原因，如果没有问题，请说出运算过程和运算结果

#### 案例一：

```java
double d = 10;
System.out.println(d);//10.0
```

解释：

​	10是整数，整数默认是int类型的。

​	而在取值范围的顺序中：byte short int long float double

​	在赋值的时候把一个int类型的赋值给了一个double类型的。把一个小的赋值给一个大的是可以直接给的。

#### 案例二：

```java
byte b = 100;
int i = b;//可以成功赋值
```

解释：

​	因为byte的取值范围是小的，int的取值范围是大的，在底层进行了隐式转换，不需要我们额外写代码单独实现，是可以直接赋值。

#### 案例三：

```java
int i = 10;
long n = 20L;
??? result = i + n;
问变量result是什么类型的？
```

解释：

​	变量i是int类型的，变量n是long类型的。

​	而在取值范围的顺序中：byte short int long float double

​	变量i里面的值会自动提升为long类型的，最终的结果其实就是两个long相加，那么最终的result是long类型的。

#### 案例四：

```java
int i = 10;
long n = 100L;
double d = 20.0;
??? result = i + n + d;
问变量result是什么类型的？
```

解释：

​	变量i是int类型，变量n是long类型，变量d是double类型。

​	而在取值范围的顺序中：byte short int long float double

​	所以变量i和变量n里面的值在参与运算的时候，都会进行类型提升，变成double。

​	最终其实就是三个double进行相加，那么最终的结果就是double类型的。

#### 案例五：

```java
byte b1 = 10;
byte b2 = 20;
??? result = b1 + b2;//int
问变量result是什么类型的？
```

解释：

​	因为b1和b2都是byte类型的。所以在参与计算的时候，变量b1和变量b2里面的值都会自动提升为int类型的。最终其实就是两个i  nt类型的相加，最终结果也是int类型的。

#### 案例六：

```java
byte b = 10;
short s = 20;
long n = 100L;
??? result = b + s + n;
问变量result是什么类型的？long
```

解释：

​	变量b是byte类型的，变量s是short类型的，变量n是long类型的。

​	**byte，short，char类型的变量在参与运算的时候，变量里面的值会直接先提升为int**。

第一步：变量b和变量s里面的值会先提升为int参与运算。

​		int + int + long 

第二步：而long类型的取值范围是大于int的取值范围的。

​		所以变量b和变量s里面的值会再次提升为long。

​		long + long + long。

所以最终结果是long类型的。

### 1.2.3 强制转换

#### 1. 概念：

​	如果要把一个**取值范围大的数据或者变量赋值给另一个取值范围小的变量**。是不允许直接操作。

​	如果一定要这么干，就需要**加入强制转换**。

#### 2. 书写格式：

​	目标数据类型 变量名 = （目标数据类型）被强转的数据；

简单理解：

​	要转成什么类型的，那么就在小括号中写什么类型就可以了。

案例：

```java
public class OperatorDemo2 {
    public static void main(String[] args) {
        double a = 12.3;
        int b = (int) a;
        System.out.println(b);//12
    }
}
```

* 注意点：

 1. 强制转换有可能会导致数据发生错误。（数据的精度丢失）

 2. 强制转换是通过去掉前面的字节来实现的，如图。int 类型的300转换为byte类型变成44；而int 类型的200转换为byte类型变成-56。

    <img src="D:\studyNote\java\github_studyNote_repo\Java\assets\强制转换.png" style="zoom:50%;" />

    

###  1.2.4 字符串的+操作

#### 1. 核心技巧：

* 当+操作中出现字符串时，**此时就是字符串的连接符，会将前后的数据进行拼接，并产生一个新的字符串**。
* 当连续进行+操作时，从左到右逐个执行的。

#### 2. 字符串相加的练习：

案例1：

```java
1 + "abc" + 1
```

结果："1abc1"

解释：

​	第一步： 1 + "abc"。在这个过程中，有字符串参与的，所以做的是拼接操作，产生一个新的字符串"1abc"

​	第二步：  "1abc" + 1。这个过程中，有字符串参与的，所以做的也是拼接操作，产生一个新的字符串"1abc1"



案例2：

```java
1 + 2 + "abc" + 2 + 1
```

结果：“3abc21”

解释：

​	第一步：1 + 2 。在这个过程中，没有字符串参与的，所以做的是加法运算，结果为3。

​	第二步：3 + "abc"。在这个过程中，有字符串参与的，所以做的是拼接操作，产生一个新的字符串"3abc"。

​	第三步："3abc" + 2。在这个过程中，有字符串参与的，所以做的是拼接操作，产生一个新的字符串"3abc2"。

​	第四步："3abc2" + 1。在这个过程中，有字符串参与的，所以做的是拼接操作，产生一个新的字符串“3abc21”



案例3：

```java
String name = "黑默丁格";
System.out.println("我的名字是" + name);
```

结果： 我的名字是黑默丁格

解释：当字符串跟变量相加的时候，实际上是跟变量里面的值进行拼接。

### 1.2.5 字符的+操作

#### 1. 规则：

​	当+操作中出现了字符，会拿着字符到计算机内置的ASCII码表中去查对应的数字，然后再进行计算(直接变数字相加)。

#### 2. 案例：

```java
char c = 'a';
int result = c + 0;
System.out.println(result);//97
```

ASCII码表中：

​	'a'   -----    97

​	'A'   -----    65

### 1.2.6 算术运算符的总结

分类：

```java
+ - * / %  这些操作跟小学数学几乎是一模一样的。
```

注意点：

* / 和 % 的区别：他们两个都是做除法运算，/取结果的商。% 取结果的余数。
* 整数操作只能得到整数，如果想要得到小数，必须有浮点数参与运算。

算术运算符的高级用法：

是以+为例进行的讲解，其余减法，乘法，除法的运算规则也是一样的。

特例：**字符串只有+操作，没有其他操作**。

* 整数操作只能得到整数，要想得到小数，必须有浮点数参与运算。

## 1.3 自增自减运算符

### 1.3.1 分类：

```java
++  自增运算符
--  自减运算符
```

++：就是把变量里面的值+1

--：就是把变量里面的值-1

### 1.3.2 使用方式：

* 放在变量的前面，我们叫做先++。 比如：++a
* 放在变量的后面，我们叫做后++。 比如：a++

### 1.3.3 注意点：

​	不管是先++，还是后++。单独写在一行的时候，运算结果是一模一样的。

### 1.3.4 案例：

```java
//++
int a = 10;
a++;//就是让变量a里面的值 + 1
System.out.println(a);//11
++a;//就是让变量a里面的值 + 1
System.out.println(a);//12
```

### 1.3.5 自增自减运算符的应用场景：

某些情况下，变量需要进行加1或者减1的时候使用。

比如：过生日多一岁，就用到了自增运算符。

比如：购物商场中，选择商品数量，也用到了自增或者自减运算符。

比如：统计很多数据中，有多少个数据满足要求，也用到了自增运算符。

## 1.4 赋值运算符

最为常用的：	=

运算过程：就是把等号右边的结果赋值给左边的变量

案例：

```java
public class OperatorDemo6 {
    public static void main(String[] args) {
        //1.最为简单的赋值运算符用法
        int a = 10;//就是把10赋值给变量a
        System.out.println(a);

        //2.如果等号右边需要进行计算。
        int b = 20;
        int c = a + b;//先计算等号右边的，把计算的结果赋值给左边的变量
        System.out.println(c);

        //3.特殊的用法
        a = a + 10;//先计算等号右边的，把计算的结果赋值给左边的变量
        System.out.println(a);//20
    }
}
```

### 1.4.1 扩展赋值运算符

#### 1. 分类：

​	+=、-=、*=、/=、%=

#### 2. 运算规则：

​	就是把左边跟右边进行运算，把最终的结果赋值给左边，对右边没有任何影响。

#### 3. 案例：

```java
public class OperatorDemo7 {
    public static void main(String[] args) {
        //扩展赋值运算符
        int a = 10;
        int b = 20;
        a += b;//把左边和右边相加，再把最终的结果赋值给左边，对右边没有任何影响
        // 相当于 a = a + b;
        System.out.println(a);//30
        System.out.println(b);//20
    }
}
```

#### 4. 注意点：

​	**扩展的赋值运算符中隐层还包含了一个强制转换 **

以+=为例。

a += b ;实际上相当于 a = (byte)(a + b);

```java
public class OperatorDemo8 {
    public static void main(String[] args) {
        byte a = 10;
        byte b = 20;
        //a += b;
        a = (byte)(a + b);
        System.out.println(a);//30
    }
}
```

## 1.5 关系运算符

又叫比较运算符，其实就是拿着左边跟右边进行了判断而已。

### 1.5.1 分类：

| 符号 | 解释                                                         |
| ---- | ------------------------------------------------------------ |
| ==   | 就是判断左边跟右边是否相等，如果成立就是true，如果不成立就是false |
| !=   | 就是判断左边跟右边是否不相等，如果成立就是true，如果不成立就是false |
| >    | 就是判断左边是否大于右边，如果成立就是true，如果不成立就是false |
| >=   | 就是判断左边是否大于等于右边，如果成立就是true，如果不成立就是false |
| <    | 就是判断左边是否小于右边，如果成立就是true，如果不成立就是false |
| <=   | 就是判断左边是否小于等于右边，如果成立就是true，如果不成立就是false |

### 1.5.2 注意点：

* 关系运算符最终的结果一定是布尔类型的。要么是true，要么是false
* 在写==的时候，千万不要写成=

## 1.6 逻辑运算符

### 1.6.1 & 和 | 的使用：

* &：逻辑与（而且）

​	两边都为真，结果才是真，只要有一个为假，那么结果就是假。

* |：逻辑或（或者）

​	两边都为假，结果才是假，只要有一个为真，那么结果就是真。

* 代码示例：

```java
// &  //两边都是真，结果才是真。
System.out.println(true & true);//true
System.out.println(false & false);//false
System.out.println(true & false);//false
System.out.println(false & true);//false

System.out.println("===================================");

// | 或  //两边都是假，结果才是假，如果有一个为真，那么结果就是真。
System.out.println(true | true);//true
System.out.println(false | false);//false
System.out.println(true | false);//true
System.out.println(false | true);//true
```

#### 使用场景：

​	根据固定的场景，来选择使用&还是使用|

* 用户登录。

  用户名输入正确  & 密码输入正确

  因为只有用户名和密码同时都正确了，那么才能成功登录，只要有一个失败了都不行。

  使用技巧：

  ​	当我们需要同时满足左边和右边两种情况时，可以使用且

* 丈母娘选女婿

  丈母娘：女婿啊，你要么买个房子，要么买辆车。就可以把我的小棉袄穿走了。

  买个房子 | 买辆车

  两个条件中，只要满足其中一个，就可以穿走小棉袄了。

  使用技巧：

  ​	当两种条件只要满足其中一个的时候，可以使用或

### 1.6.2 ^（异或）的使用：

​	在以后用的不多，了解一下即可。

计算规则：如果两边相同，结果为false，如果两边不同，结果为true

代码示例：

```java
//^   //左右不相同，结果才是true，左右相同结果就是false
System.out.println(true ^ true);//false
System.out.println(false ^ false);//false
System.out.println(true ^ false);//true
System.out.println(false ^ true);//true
```

### 1.6.3 !（取反）的使用：

​	是取反，也叫做非。

计算规则：false取反就是true，true取反就是false

温馨提示：**取反最多只用一个。**

代码示例：

```java
System.out.println(!false);//true
System.out.println(!true);//false

System.out.println(!!false);//注意点：取反最多只用一个。
```

### 1.6.4 短路逻辑运算符

分类：  &&   ||

#### 1. &&：

​	运算结果跟&是一模一样的，只不过具有短路效果。

#### 2. ||：

​	运算结果跟|是一模一样的。只不过具有短路效果。

#### 3. 逻辑核心：

​	当左边不能确定整个表达式的结果，右边才会执行。

​	当左边能确定整个表达式的结果，那么右边就不会执行了。从而提高了代码的运行效率。

#### 4. 举例：

* 用户登录案例

  用户名正确  & 密码正确

  如果使用一个&，不管用户名是否正确都会去验证密码。

思考：

​	如果用户名输入正确了，那么我们再判断密码是否正确，是符合业务逻辑的。

​	但是如果用户名输入错误了，那么现在还有必要去比较密码吗？没有不要了。

​	如果使用一个&，那么左边和右边不管什么情况下，都会执行。



​	用户名正确  &&  密码正确

​	如果用户名输入正确了，那么才会验证密码是否输入正确。

​	如果用户名输入错误了，那么就不会再去验证密码是否正确，最终的结果直接为false。从而提高了程序运行的效率。

* 丈母娘选女婿

  有房 |  有车

  首先先看看有没有房，发现有，然后再去看看有没有车。

思考：

​	既然都有房子，干嘛还要去看车呢？多此一举。

​	有房 ||  有车

​	首先先看看有没有房，如果有，那么右边就不执行了。最终的结果直接为true。

​	如果没有房子，才会去看右边有没有车。

### 1.6.5 总结：短路逻辑运算符可以提高运行效率

​	&& 和 & 、||和|的运行结果都是一模一样的。

​	但是短路逻辑运算符可以提高程序的运行效率。

### 1.6.6 建议：最常用&&、||、！

​	**最为常用： &&、   ||、   ！** 

## 1.7 三元运算符

又叫做：三元表达式或者问号冒号表达式。

### 1. 格式：

​	关系表达式 ？ 表达式1 ：表达式2 ；

### 2. 计算规则：

* 计算关系表达式的值。
* 如果关系表达式的值为真，那么执行表达式1。
* 如果关系表达式的值为假，那么执行表达式2。

### 3. 注意点：

​	三元运算符的**最终结果一定要被使用**，要么赋值给一个变量，要么直接打印出来。

### 4. 案例：

```java
public class OperatorDemo12 {
    public static void main(String[] args) {
        //需求：求两个数的较大值
        int a = 10;
        int b = 20;

        //格式：关系表达式 ？ 表达式1 ： 表达式2 ；
        //注意点：
        //三元运算符的最终结果一定要被使用。
        //要么赋值给一个变量，要么直接输出。
       int max =  a > b ? a : b ;
        System.out.println(max);


        System.out.println(a > b ? a : b);
    }
}
```

#### 练习1-两只老虎

需求：

​	动物园里有两只老虎，两只老虎的体重分别为通过键盘录入获得，

​	请用程序实现判断两只老虎的体重是否相同。

代码示例：

```java
//1.获取两只老虎的体重
Scanner sc = new Scanner(System.in);
System.out.println("请输入第一只老虎的体重");
int weight1 = sc.nextInt();
System.out.println("请输入第二只老虎的体重");
int weight2 = sc.nextInt();

//2.利用三元运算符求出最终结果
String result = weight1 == weight2 ? "相同" : "不相同";
System.out.println(result);
```

#### 练习2-求三个数的最大值

需求：

​	一座寺庙里住着三个和尚，已知他们的身高分别为150cm、210cm、165cm。

​	请用程序实现获取这三个和尚的最高身高。

代码示例：

```java
//1.定义三个变量记录和尚的身高
int height1 = 150;
int height2 = 210;
int height3 = 165;

//2.利用三元运算符求出两个数中的较大值。
int temp = height1 > height2 ? height1 : height2;

//3.求出最终的结果
int max = temp > height3 ? temp : height3;

System.out.println(max);
```

## 1.8 运算符的优先级

在Java中涉及了很多的运算符，每一种运算符都有各自的优先级。但是这些优先级不需要记忆。

咱们只要知道其中一点：

​	**小括号优先于所有**。



##  2.1 补充知识：原码、反码、补码

### 1. 原码和反码 

一个字节（8个bit）为单位，最左边的一位是符号位；反码：为了解决原码不能计算负数的问题而出现。<img src="D:\studyNote\java\github_studyNote_repo\Java\assets\原码反码.png" style="zoom: 33%;" />

### 2. 补码：

* 为了解决反码中0有两种表现形式、出现了两次的问题。（导致每次计算跨0时，结果有1的误差）而出现。

<img src="D:\studyNote\java\github_studyNote_repo\Java\assets\反码.png" style="zoom:40%;" />

* 补码：反码错开一位（去掉了反码中0的负数表现形式，只保留了0的一种表现形式）；负数的补码 = 负数的反码 + 1；

<img src="D:\studyNote\java\github_studyNote_repo\Java\assets\补码.png" style="zoom:40%;" />

### 3. 注意：正数的原码、反码、补码都是相同的。

以上，可知补码完美解决了不能计算负数、存在重复0导致不能跨0计算的问题。

所以**现在计算机都采用补码存储和表示数字**。



### 4. -128？

   反码＋1得补码，1000000多了出来没有对应的结果，所以**把10000000规定为-128**。

   注意：-128只有补码形式，没有对应的原码和反码形式。
 <img src="D:\studyNote\java\github_studyNote_repo\Java\assets\-128.png" style="zoom:40%;" />




## 2.2 字节层面理解运算符

   <img src="D:\studyNote\java\github_studyNote_repo\Java\assets\与或非.png" style="zoom:50%;" />

### 1. 两个数字“逻辑与”操作

   <img src="D:\studyNote\java\github_studyNote_repo\Java\assets\数字与.png" style="zoom:33%;" />

### 2. 两个数字“逻辑或”操作

   <img src="D:\studyNote\java\github_studyNote_repo\Java\assets\数字或.png" style="zoom:50%;" />

### 3. 左移运算符（左移1位相当于×2，左移2位相当于×4）

   a << 2  代表将左移两位，低位补0即可。

   <img src="D:\studyNote\java\github_studyNote_repo\Java\assets\左移.png" style="zoom:40%;" />

   

### 4. 右移（右移1位相当于除2，右移2位相当于除4）

   a >> 2 代表右移两位，高位补0或补1。

   如果原来是正数，高位补0；如果原来是负数，高位补1。

   <img src="D:\studyNote\java\github_studyNote_repo\Java\assets\右移.png" style="zoom:40%;" />

### 5. 无符号右移

   向右移动，高位补0。

   <img src="D:\studyNote\java\github_studyNote_repo\Java\assets\无符号.png" style="zoom:50%;" />

# Day04 流程控制语句

##  1 流程控制语句概览

在一个程序执行的过程中，各条语句的执行顺序对程序的结果是有直接影响的。所以，我们必须清楚每条语句的执行流程。而且，很多时候要通过控制语句的执行顺序来实现我们想要的功能。

### 1.1 流程控制语句分类

* 顺序结构
* 判断和选择结构(if, switch)
* 循环结构(for, while, do…while)

### 1.2 顺序结构

顺序结构是程序中最简单最基本的流程控制，没有特定的语法结构，按照代码的先后顺序，依次执行，程序中大多数的代码都是这样执行的。

顺序结构执行流程图：

![1545615769372](D:\studyNote\java\github_studyNote_repo\Java\assets\1545615769372.png)

## 2 判断语句：if语句

### 2.1 if语句格式1

```java
格式：
if (关系表达式) {
    语句体;	
}
```

执行流程：

①首先计算关系表达式的值

②如果关系表达式的值为true就执行语句体

③如果关系表达式的值为false就不执行语句体

④继续执行后面的语句内容

![1545616039363](D:\studyNote\java\github_studyNote_repo\Java\assets\1545616039363.png)

示例：

```java
public class IfDemo {
	public static void main(String[] args) {
		System.out.println("开始");	
		//定义两个变量
		int a = 10;
		int b = 20;	
		//需求：判断a和b的值是否相等，如果相等，就在控制台输出：a等于b
		if(a == b) {
			System.out.println("a等于b");
		}		
		//需求：判断a和c的值是否相等，如果相等，就在控制台输出：a等于c
		int c = 10;
		if(a == c) {
			System.out.println("a等于c");
		}		
		System.out.println("结束");
	}
}
```

#### 练习1：老丈人选女婿

需求：

​	键盘录入女婿的酒量，如果大于2斤，老丈人给出回应，否则没有任何回应

代码示例：

```java
//分析：
//1.键盘录入女婿的酒量
Scanner sc = new Scanner(System.in);
System.out.println("请输入女婿的酒量");
int wine = sc.nextInt();//5
//2.对酒量进行一个判断即可
if(wine > 2) {
    System.out.println("不错哟，小伙子！");
}
```

#### 练习2：考试奖励

需求：

​	键盘录入一个整数，表示小明的考试名次，如果名次为1，小红可以当小明的女朋有了。

代码示例：

```java
//分析：
//1.键盘录入一个整数，表示小明的考试名次
Scanner sc = new Scanner(System.in);
System.out.println("请输入小明的名次");
int rank = sc.nextInt();
//2.对小明的考试成绩进行判断即可
if(rank == 1){
    System.out.println("小红成为了小明的女朋友");
}
```

#### 第一种格式的细节：

1. 如果我们要对一个布尔类型的变量进行判断，不要写==，直接把变量写在小括号中即可。

2. 如果大括号中的语句体只有一条，那么大括号可以省略不写

   如果大括号省略了，那么if只能控制距离他最近的那一条语句。

   **建议：**自己不要去写，如果别人这么写了，你要能看懂即可。

### 2.2 if语句格式2

```java
格式：
if (关系表达式) {
    语句体1;	
} else {
    语句体2;	
}
```

执行流程：

①首先计算关系表达式的值

②如果关系表达式的值为true就执行语句体1

③如果关系表达式的值为false就执行语句体2

④继续执行后面的语句内容

![1545616221283](D:\studyNote\java\github_studyNote_repo\Java\assets\1545616221283.png)

示例：

```java
public class IfDemo02 {
	public static void main(String[] args) {
		System.out.println("开始");		
		//定义两个变量
		int a = 10;
		int b = 20;
		//需求：判断a是否大于b，如果是，在控制台输出：a的值大于b，否则，在控制台输出：a的值不大于b
		if(a > b) {
			System.out.println("a的值大于b");
		} else {
			System.out.println("a的值不大于b");
		}		
		System.out.println("结束");
	}
}
```

#### 练习1：吃饭

需求：

​	    键盘录入一个整数，表示身上的钱。

​            如果大于等于100块，就是网红餐厅。

​            否则，就吃经济实惠的沙县小吃。

代码示例：

```java
//分析：
//1.键盘录入一个整数。表示身上的钱。
Scanner sc = new Scanner(System.in);
System.out.println("请输入一个整数表示身上的钱");
int money = sc.nextInt();
//2.对钱进行判断
if(money >= 100){
    System.out.println("吃网红餐厅");
}else{
    System.out.println("福建大酒店");
}
```

#### 练习2：影院选座

需求：

​	在实际开发中，电影院选座也会使用到if判断。

​	假设某影院售卖了100张票，票的序号为1~100。

​	其中奇数票号坐左侧，偶数票号坐右侧。

​	键盘录入一个整数表示电影票的票号。

​	根据不同情况，给出不同的提示：

​		如果票号为奇数，那么打印坐左边。

​		如果票号为偶数，那么打印坐右边。

代码示例：

```java
//分析：
//1.键盘录入票号
Scanner sc = new Scanner(System.in);
System.out.println("请输入票号");
int ticket = sc.nextInt();
if(ticket >= 1 && ticket <= 100){
    //合法
    //2.对票号进行判断
    if (ticket % 2 == 0) {
        //偶数
        System.out.println("坐右边");
    } else {
        //奇数
        System.out.println("坐左边");
    }
}else{
    //票号不合法
    System.out.println("票号不合法");
}
```

### 2.3 if语句格式3

```java
格式：
if (关系表达式1) {
    语句体1;	
} else if (关系表达式2) {
    语句体2;	
} 
…
else {
    语句体n+1;
}
```

执行流程：

①首先计算关系表达式1的值

②如果值为true就执行语句体1；如果值为false就计算关系表达式2的值

③如果值为true就执行语句体2；如果值为false就计算关系表达式3的值

④…

⑤如果没有任何关系表达式为true，就执行语句体n+1。

![1545616667104](D:\studyNote\java\github_studyNote_repo\Java\assets\1545616667104.png)

#### 练习1：考试奖励

需求：

​	小明快要期末考试了，小明爸爸对他说，会根据他不同的考试成绩，送他不同的礼物，

假如你可以控制小明的得分，请用程序实现小明到底该获得什么样的礼物，并在控制台输出。

分析：

​	①小明的考试成绩未知，可以使用键盘录入的方式获取值

​	②由于奖励种类较多，属于多种判断，采用if...else...if格式实现

​	③为每种判断设置对应的条件

​	④为每种判断设置对应的奖励

代码示例：

```java
//95~100 自行车一辆
//90~94   游乐场玩一天
//80 ~ 89 变形金刚一个
//80 以下  胖揍一顿

//1.键盘录入一个值表示小明的分数
Scanner sc = new Scanner(System.in);
System.out.println("请输入小明的成绩");
int score = sc.nextInt();
//2.对分数的有效性进行判断
if(score >= 0 && score <= 100){
    //有效的分数
    //3.对小明的分数进行判断，不同情况执行不同的代码
    if(score >= 95 && score <= 100){
        System.out.println("送自行车一辆");
    }else if(score >= 90 && score <= 94){
        System.out.println("游乐场玩一天");
    }else if(score >= 80 && score <= 89){
        System.out.println("变形金刚一个");
    }else{
        System.out.println("胖揍一顿");
    }
}else{
    //无效的分数
    System.out.println("分数不合法");
}
```

## 3 switch语句

### 3.1 格式

```java
switch (表达式) {
	case 1:
		语句体1;
		break;
	case 2:
		语句体2;
		break;
	...
	default:
		语句体n+1;
		break;
}
```

### 3.2 **执行流程：**

- 首先计算出表达式的值 
- 其次，和case依次比较，一旦有对应的值，就会执行相应的语句，在执行的过程中，遇到break就会结 束。 
- 最后，如果所有的case都和表达式的值不匹配，就会执行default语句体部分，然后程序结束掉。 

#### 练习：运动计划

- 需求：键盘录入星期数，显示今天的减肥活动。

  周一：跑步  

  周二：游泳  

  周三：慢走  

  周四：动感单车

  周五：拳击  

  周六：爬山  

  周日：好好吃一顿

- 代码示例：

```java
package a01switch选择语句;

import java.util.Scanner;

public class SwitchDemo2 {
    public static void main(String[] args) {
        //1.键盘录入一个整数表示星期
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个整数表示星期");
        int week = sc.nextInt();

        //2.书写一个switch语句去跟week进行匹配
        switch (week){
            case 1:
                System.out.println("跑步");
                break;
            case 2:
                System.out.println("游泳");
                break;
            case 3:
                System.out.println("慢走");
                break;
            case 4:
                System.out.println("动感单车");
                break;
            case 5:
                System.out.println("拳击");
                break;
            case 6:
                System.out.println("爬山");
                break;
            case 7:
                System.out.println("好好吃一顿");
                break;
            default:
                System.out.println("输入错误，没有这个星期");
                break;
        }
    }
}
```

### 3.3 switch的扩展知识：

- default的位置和省略情况

  default可以放在任意位置，也可以省略

- case穿透

  不写break会引发case穿透现象，case匹配上之后如果有重复的代码，可以用case穿透（不写break）, 这样多个case可以穿透到最后一个case的相同的代码中，进行简化。

  ```java
   //case穿透写法: 有重复的代码可以用case穿透
          switch (weekday){
              case 1:
              case 2:
              case 3:
              case 4:
              case 5:
                  System.out.println("工作日");
                  break;
              case 6:
              case 7:
                  System.out.println("休息日");
                  break;
              default:
                  System.out.println("没有这个星期数");
                  break;
          }
  ```

  

- switch在JDK12的新特性

```java
int number = 10;
switch (number) {
    case 1 -> System.out.println("一");
    case 2 -> System.out.println("二");
    case 3 -> System.out.println("三");
    default -> System.out.println("其他");
}
```

- switch和if第三种格式各自的使用场景

当我们需要对一个范围进行判断的时候，用if的第三种格式

当我们把有限个数据列举出来，选择其中一个执行的时候，用switch语句

比如：

​	小明的考试成绩，如果用switch，那么需要写100个case，太麻烦了，所以用if简单。

​	如果是星期，月份，客服电话中0~9的功能选择就可以用switch

#### 练习：休息日和工作日

需求：键盘录入星期数，输出工作日、休息日。

(1-5) 工作日，(6-7)休息日。

代码示例：

```java
//分析：
//1.键盘录入星期数
Scanner sc = new Scanner(System.in);
System.out.println("请输入星期");
int week = sc.nextInt();//3
//2.利用switch进行匹配
----------------------------------------------------
利用case穿透简化代码
switch (week){
    case 1:
    case 2:
    case 3:
    case 4:
    case 5:
        System.out.println("工作日");
        break;
    case 6:
    case 7:
        System.out.println("休息日");
        break;
    default:
        System.out.println("没有这个星期");
        break;
}
----------------------------------------------------
利用JDK12简化代码书写
switch (week) {
    case 1, 2, 3, 4, 5 -> System.out.println("工作日");
    case 6, 7 -> System.out.println("休息日");
    default -> System.out.println("没有这个星期");
}
```

### 3.4 Switch 和 if条件判断(v3)选哪个？

* switch: 把有限个数据一一列举出来，选择其中一个进行匹配（匹配不上进入default）
* if的第三种格式（if……else if……else……）：一般用于对范围的判断

## 4 循环结构

### 4.1 for循环结构（掌握）

​	循环语句可以在满足循环条件的情况下，反复执行某一段代码，这段被重复执行的代码被称为循环体语句，当反复 执行这个循环体时，需要在合适的时候把循环判断条件修改为false，从而结束循环，否则循环将一直执行下去，形 成死循环。 

#### 4.1.1 for循环格式：

```java
for (初始化语句;条件判断语句;条件控制语句) {
	循环体语句;
}
```

**格式解释：**

- 初始化语句：  用于表示循环开启时的起始状态，简单说就是循环开始的时候什么样
- 条件判断语句：用于表示循环反复执行的条件，简单说就是判断循环是否能一直执行下去
- 循环体语句：  用于表示循环反复执行的内容，简单说就是循环反复执行的事情
- 条件控制语句：用于表示循环执行中每次变化的内容，简单说就是控制循环是否能执行下去

**执行流程：**

①执行初始化语句

②执行条件判断语句，看其结果是true还是false

​             如果是false，循环结束

​             如果是true，继续执行

③执行循环体语句

④执行条件控制语句

⑤回到②继续

**for循环书写技巧：**

- 确定循环的开始条件
- 确定循环的结束条件
- 确定循环要重复执行的代码

代码示例：

```java
//1.确定循环的开始条件
//2.确定循环的结束条件
//3.确定要重复执行的代码

//需求：打印5次HelloWorld
//开始条件：1
//结束条件：5
//重复代码：打印语句

for (int i = 1; i <= 5; i++) {
    System.out.println("HelloWorld");
}
```

##### for循环练习-输出数据

- 需求：在控制台输出1-5和5-1的数据 
- 示例代码：

```java
public class ForTest01 {
    public static void main(String[] args) {
		//需求：输出数据1-5
        for(int i=1; i<=5; i++) {
			System.out.println(i);
		}
		System.out.println("--------");
		//需求：输出数据5-1
		for(int i=5; i>=1; i--) {
			System.out.println(i);
		}
    }
}
```



##### for循环练习-求和

- 需求：求1-5之间的数据和，并把求和结果在控制台输出  
- 示例代码：

```java
public class ForTest02 {
    public static void main(String[] args) {
		//求和的最终结果必须保存起来，需要定义一个变量，用于保存求和的结果，初始值为0
		int sum = 0;
		//从1开始到5结束的数据，使用循环结构完成
		for(int i=1; i<=5; i++) {
			//将反复进行的事情写入循环结构内部
             // 此处反复进行的事情是将数据 i 加到用于保存最终求和的变量 sum 中
			sum = sum + i;
			/*
				sum += i;	sum = sum + i;
				第一次：sum = sum + i = 0 + 1 = 1;
				第二次：sum = sum + i = 1 + 2 = 3;
				第三次：sum = sum + i = 3 + 3 = 6;
				第四次：sum = sum + i = 6 + 4 = 10;
				第五次：sum = sum + i = 10 + 5 = 15;
			*/
		}
		//当循环执行完毕时，将最终数据打印出来
		System.out.println("1-5之间的数据和是：" + sum);
    }
}
```

- 本题要点：
  - 今后遇到的需求中，如果带有求和二字，请立即联想到求和变量
  - 求和变量的定义位置，必须在循环外部，如果在循环内部则计算出的数据将是错误的

##### for循环练习-求偶数和

- 需求：求1-100之间的偶数和，并把求和结果在控制台输出 }
- 示例代码：

```java
public class ForTest03 {
    public static void main(String[] args) {
		//求和的最终结果必须保存起来，需要定义一个变量，用于保存求和的结果，初始值为0
		int sum = 0;
		//对1-100的数据求和与1-5的数据求和几乎完全一样，仅仅是结束条件不同
		for(int i=1; i<=100; i++) {
			//对1-100的偶数求和，需要对求和操作添加限制条件，判断是否是偶数
			if(i%2 == 0) {
                //sum += i；
				sum = sum + i;
			}
		}
		//当循环执行完毕时，将最终数据打印出来
		System.out.println("1-100之间的偶数和是：" + sum);
    }
}
```

##### for循环练习-统计次数

需求：

​	  键盘录入两个数字，表示一个范围。

​           统计这个范围中。

​           既能被3整除，又能被5整除数字有多少个？

代码示例：

```java

```

### 4.2 while循环

#### 4.2.1 格式：

```java
初始化语句;
while(条件判断语句){
	循环体;
	条件控制语句;
}
```

##### 练习1：打印5次HelloWorld

```java
int i = 1;
while(i <= 5){
    System.out.println("HelloWorld");
    i++;
}
System.out.println(i);
```

##### 练习2：珠穆朗玛峰

```java
//1.定义一个变量表示珠穆朗玛峰的高度
int height = 8844430;
//2.定义一个变量表示纸张的厚度
double paper = 0.1;

//定义一个计数器（变量），用来统计折叠的次数
int count = 0;

//3.循环折叠纸张
//只有纸张的厚度 < 穆朗玛峰的高度 循环才继续，否则循环就停止
//坑：只有判断为真，循环才会继续
while(paper < height){
    //折叠纸张
    paper = paper * 2;
    count++;
}

//4.打印一下纸张的厚度
System.out.println(count);//27
```

### 4.3 do...while循环

本知识点了解即可

格式：

```java
初始化语句;
do{
    循环体;
    条件控制语句;
}while(条件判断语句);
```

特点：

​	先执行，再判断。

### 4.4 三种格式的区别：

​	for和while循环，是先判断，再执行。

​	do...while是先执行，再判断。

​	当知道循环次数或者循环范围的时候，用for循环。

​	当不知道循环次数，也不知道循环范围，但是知道循环的结束条件时，用while循环。

### 4.5 循环跳转控制语句

* continue： 跳过本次循环，继续执行下次循环。
* break：结束在整个循环。



# Day05 循环高级和数组

## 1.无限循环

### 概念：

​	又叫死循环。循环一直停不下来。

### for格式：

```java
for(;;){
    System.out.println("循环执行一直在打印内容");
}
```

解释：

初始化语句可以空着不写，表示循环之前不定义任何的控制变量。

条件判断语句可以空着不写，如果不写，默认表示true，循环一直进行。

条件控制语句可以空着不写，表示每次循环体执行完毕后，控制变量不做任何变化。

### while格式：

```java
while(true){
    System.out.println("循环执行一直在打印内容");
}
```

解释：

​	小括号里面就不能省略了，true一定要写出来，否则代码会报错。

### do...while格式：

```java
do{
    System.out.println("循环执行一直在打印内容");
}while(true);
```

解释：

​	小括号里面就不能省略了，true一定要写出来，否则代码会报错。

### 无限循环的注意事项：

* 最为常用的格式：while
* 无限循环下面不能再写其他代码了，因为永远执行不到。

## 2.条件控制语句

* break
* continue

### break:

​	不能单独存在的。可以用在switch和循环中，表示结束，跳出的意思。

代码示例：

```java
//1.吃1~5号包子
for (int i = 1; i <= 5; i++) {
    System.out.println("在吃第" + i + "个包子");
    //2.吃完第三个的时候就不吃了
    if(i == 3){
        break;//结束整个循环。
    }
}
```

### continue:

​	不能单独存在的。只能存在于循环当中。

​	表示：跳过本次循环，继续执行下次循环。

代码示例：

```java
//1.吃1~5号包子
for (int i = 1; i <= 5; i++) {
    //2.第3个包子有虫子就跳过，继续吃下面的包子
    if(i == 3){
        //跳过本次循环（本次循环中，下面的代码就不执行了），继续执行下次循环。
        continue;
    }
    System.out.println("在吃第" + i + "个包子");
}
```

## 3. Random

Random跟Scanner一样，也是Java提前写好的类，我们不需要关心是如何实现的，只要直接使用就可以了。

### 使用步骤：

1. 导包

```java
import java.util.Random;
导包的动作必须出现在类定义的上边。
```

2. 创建对象

```java
Random r = new Random ();
上面这个格式里面，只有r是变量名，可以变，其他的都不允许变。
```

3. 生成随机数

```java
int number = r.nextInt(随机数的范围);
上面这个格式里面，只有number是变量名，可以变，其他的都不允许变。
随机数范围的特点：从0开始，不包含指定值。比如：参数为10，生成的范围[0,10)
```

代码示例：

```java
//1.导包
import java.util.Random;

public class RandomDemo1 {
    public static void main(String[] args) {
        //2.创建对象
        Random r = new Random();
        //3.生成随机数
        int number = r.nextInt(100);//包左不包右，包头不包尾
        //0 ~ 99
        System.out.println(number);

    }
}
```

## 4. 逢七过

需求：

​	朋友聚会的时候可能会玩一个游戏：逢7过 

​	游戏规则：从任意一个数字开始报数，当你要报的数字是包含7或者是7的倍数时都要说过：过

​	使用程序在控制台打印出1-100之间的满足逢七必过规则的数据 

举例：

​	1 2 3 4 5 6 过 8 9 10 11 12 13 过 15 16 过 18 ...

代码示例：

```java
/*朋友聚会的时候可能会玩一个游戏：逢7过
        游戏规则：从任意一个数字开始报数，当你要报的数字是包含7或者是7的倍数时都要说过：过
        需求：使用程序在控制台打印出1-100之间的满足逢七必过规则的数据*/
//分析：
//个位7  十位7   7倍数
//1 2 3 4 5 6 过 8 9 10 11 12 13 过 15 16 过 18 19 20 过....
//69 过 过 过 过 过 过... 80
//1.得到1~100之间的每一个数字
//开始：1
//结束：100
for (int i = 1; i <= 100; i++) {
    //2.判断每一个数字，如果符合规则，就打印过，如果不符合规则就打印真实的数字
    if(i % 10 == 7 || i / 10 % 10 == 7  ||  i % 7 == 0){
        System.out.println("过");
        continue;
    }
    System.out.println(i);
}
```

## 5. 平方根

需求：

​	键盘录入一个大于等于2的整数 x ，计算并返回 x 的 平方根 。结果只保留整数部分 ，小数部分将被舍去 。

代码示例：

```java
/*需求：键盘录入一个大于等于2的整数 x ，计算并返回 x 的 平方根 。
        结果只保留整数部分 ，小数部分将被舍去 。*/


//分析：
//平方根   16的平方根4
//         4的平方根2


// 10
// 1 * 1 = 1 < 10
// 2 * 2 = 4 < 10
// 3 * 3 = 9 < 10
// 4 * 4 = 16 > 10
//推断：10的平方根是在3~4之间。


// 20
// 1 * 1 = 1 < 20
// 2 * 2 = 4 < 20
// 3 * 3 = 9 < 20
// 4 * 4 = 16 < 20
// 5 * 5 = 25 > 20
//推断：20的平方根是在4~5之间。


//在代码当中
//从1开始循环，拿着数字的平方跟原来的数字进行比较
//如果小于的，那么继续往后判断
//如果相等，那么当前数字就是平方根
//如果大于的，那么前一个数字就是平方跟的整数部分


//1.键盘录入一个整数
Scanner sc = new Scanner(System.in);
System.out.println("请输入一个整数");
int number = sc.nextInt();
//2.从1开始循环判断
//开始：1 结束: number
for (int i = 1; i <= number; i++) {
    //用i * i 再跟number进行比较
    if(i * i == number){
        System.out.println(i + "就是" + number + "的平方根");
        //一旦找到了，循环就可以停止了，后面的数字就不需要再找了，提高代码的运行效率。
        break;
    }else if(i * i > number){
        System.out.println((i - 1) + "就是" + number + "平方根的整数部分");
        break;
    }
}
```

## 6.判断是否为质数

需求：

​	键盘录入一个正整数 x ，判断该整数是否为一个质数。 (**使用boolean变量，体现”标记思想“。**)

代码示例：

```java
//需求：键盘录入一个正整数 x ，判断该整数是否为一个质数。

//质数：
//如果一个整数只能被1和本身整除，那么这个数就是质数。否则这个数叫做合数
//7 = 1 * 7 质数
//8 = 1 * 8  2 * 4 合数


//分析：
//1.键盘录入一个正整数
//number
Scanner sc = new Scanner(System.in);
System.out.println("请输入一个正整数");
int number = sc.nextInt();//9

//定义一个变量，表示标记
//标记着number是否为一个质数
//true： 是一个质数
//false : 不是一个质数

//表示最初就认为number是一个质数
boolean flag = true;


//2.判断
//写一个循环，从2开始判断，一直判断到number-1为止
//看这个范围之内，有没有数字可以被number整除
for (int i = 2; i < number; i++) {
    //i 依次表示这个范围之内的每一个数字
    //看number是否能被i整除就可以了
    if(number % i == 0){// 9 % 2 = 1
        flag = false;
        //System.out.println(number + "不是一个质数");
        break;
    }/*else{
                System.out.println(number + "是一个质数");
            }*/
}

//只有当这个循环结束了，表示这个范围之内所有的数字都判断完毕了
//此时才能断定number是一个质数
if(flag){
    System.out.println(number + "是一个质数");
}else{
    System.out.println(number + "不是一个质数");
}
```

## 7. 猜数字小游戏

需求：

​	程序自动生成一个1-100之间的随机数，在代码中使用键盘录入去猜出这个数字是多少？

要求：

​	使用循环猜，一直猜中为止。

思路分析：

1. 生成一个1-100之间的随机数
2. 使用键盘录入去猜出这个数字是多少
3. 把反复猜的代码写在循环中

代码示例：注意**无限循环**的用法，当满足条件就退出。

```java
//1.生成一个1-100之间的随机数
Random r = new Random();
int number = r.nextInt(100) + 1;// 0 ~ 99 + 1 --- 1 ~ 100
System.out.println(number);

//2.使用键盘录入去猜出这个数字是多少？
Scanner sc = new Scanner(System.in);
while(true){  
    System.out.println("请输入一个整数");
    int guessNumber = sc.nextInt();
    //3.比较
    if(guessNumber > number){
        System.out.println("您猜的数字大了");
    }else if(guessNumber < number){
        System.out.println("您猜的数字小了");
    }else{
        System.out.println("恭喜你，猜中了");
        break;
    }
}
```

# Day06 数组

## 1.数组

### 概念：

​	指的是一种容器，可以同来存储同种数据类型的多个值。

​	但是数组容器在存储数据的时候，需要结合隐式转换考虑。

比如：

​	定义了一个int类型的数组。那么boolean。double类型的数据是不能存到这个数组中的，

​	但是byte类型，short类型，int类型的数据是可以存到这个数组里面的。

建议：

​	容器的类，和存储的数据类型保持一致。

举例：

​	整数1 2 3 4 56 就可以使用int类型的数组来存储。

​	小数1.1 1.2 1.3 1.4 就可以使用double类型的数组来存储。

​	字符串"aaa"  "bbb"  "ccc" 就可以使用String类型的数组来存储。

## 2.数组的定义

### 格式一：

​	数据类型 [] 数组名

比如：int [] array

### 格式二：

​	数据类型  数组名 []

比如： int array []

### 详解：

数据类型：限定了数组以后能存什么类型的数据。

方括号：表示现在定义的是一个数组。

数组名：就是一个名字而已，方便以后使用。

### 注意点：

​	方法括号跟数组名，谁写在前面，谁写在后面都是一样的。

​	平时习惯性使用第一种方式。

## 3.数组的静态初始化

### 完整格式：

​	数据类型[] 数组名 = new 数据类型[]{元素1，元素2，元素3，元素4...};

比如：

​	int[] arr = new int[]{11,22,33};

​	double[] arr = new double[]{1.1,1.2,1.3};

### 格式详解：

​	数据类型：限定了数组以后能存什么类型的数据。

​	方括号：表示现在定义的是一个数组。

​	数组名：其实就是名字而已，方便以后使用，在起名字的时候遵循小驼峰命名法。

​			arr   namesArr

​	new：就是给数组在内存中开辟了一个空间。

​	数据类型：限定了数组以后能存什么类型的数据。

​			  前面和后面的数据类型一定要保持一致。

​			int[] arr = new double[]{11,22,33};//错误写法

​	方括号：表示现在定义的是一个数组。

​	大括号：表示数组里面的元素。元素也就是存入到数组中的数据。

​			多个元素之间，一定要用逗号隔开。

### 注意点：

* 等号前后的数据类型必须保持一致。
* 数组一旦创建之后，长度不能发生变化。

### 简化格式:

​	数据类型[] 数组名 = {元素1，元素2，元素3，元素4...};

比如：

​	int[] array = {1,2,3,4,5};

​	double[] array = {1.1,1.2,1.3};

### 练习1：

定义数组存储5个学生的年龄。

```java
1.给数组限定什么类型？ int
2.利用静态初始化完成创建并添加元素
int[] agesArr = new int[]{18,19,20,21,22};
int[] agesArr = {18,19,20,21,22};
```

### 练习2：

定义数组存储3个学生的姓名。

```java
1.给数组限定什么类型？ String
2.利用静态初始化完成创建并添加元素
String[] namesArr = new String[]{"zhangsan","lisi","wangwu"};
String[] namesArr = {"zhangsan","lisi","wangwu"};
```

### 练习3：

定义数组存储4个学生的身高。

```java
1.给数组限定什么类型？ double
2.利用静态初始化完成创建并添加元素
double[] heightsArr = new double[]{1.85,1.82,1.78,1.65};
double[] heightsArr = {1.85,1.82,1.78,1.65};
```

## 4.地址值

```java
int[] arr = {1,2,3,4,5};
System.out.println(arr);//[I@6d03e736

double[] arr2 = {1.1,2.2,3.3};
System.out.println(arr2);//[D@568db2f2
```

打印数组的时候，实际出现的是数组的地址值。

数组的地址值：就表示数组在内存中的位置。

以[I@6d03e736为例：

[ ：表示现在打印的是一个数组。

I：表示现在打印的数组是int类型的。

@：仅仅是一个间隔符号而已。

6d03e736：就是数组在内存中真正的地址值。（十六进制的）

但是，我们习惯性会把[I@6d03e736这个整体称之为数组的地址值。

地址值对于我们来京，作用不大，简单了解。

## 5.数组元素访问

### 格式：

​	数组名[索引];

### 作用：

* 获取数组中对应索引上的值

* 修改数组中对应索引上的值

  一旦修改之后，原来的值就会被覆盖了。

### 代码示例：

```java
public class ArrDemo2 {
    /*

        数组中元素访问的格式：
                数组名[索引];

         作用：
            1.获取指定索引上对应的元素
            2.修改指定索引上对应的元素


    */
    public static void main(String[] args) {
       int[] arr = {1,2,3,4,5};
       //需求1：获取arr数组中，3索引上的值
        int number = arr[3];
        System.out.println(number);
        System.out.println(arr[3]);

       //需求2：将arr数组中，3索引上的值修改为10
            arr[3] = 10;
        System.out.println("修改之后为:" + arr[3]);

    }
}
```

## 6.索引

​	也叫角标、下标

​	就是数组容器中每一个小格子对应的编号。

### 索引的特点：

* 索引一定是从0开始的。
* 连续不间断。
* 逐个+1增长。

## 7.数组的遍历

遍历：就是把数组里面所有的内容一个一个全部取出来。

数组的长度：数组名.length;

通用代码：

```java
for(int i = 0; i < arr.length; i++){
    //在循环的过程中，i依次表示数组中的每一个索引
    sout(arr[i]);//就可以把数组里面的每一个元素都获取出来，并打印在控制台上了。
}
```

## 8.数组的动态初始化

### 格式：

​	数据类型[] 数组名 = new 数据类型[数组的长度];

### 举例：

```java
//1.定义一个数组，存3个人的年龄，年龄未知
int[] agesArr = new int[3];


//2.定义一个数组，存班级10名学生的考试成绩，考试成绩暂时未知，考完才知道。
int[] scoresArr = new int[10];
```

### 数组的默认初始化值：

整数类型：0

小数类型：0.0

布尔类型：false

字符类型：'\u0000'

引用类型：null

## 9.数组两种初始化方式的区别

静态初始化：int[] arr = {1,2,3,4,5};

动态初始化：int[] arr = new int[3];

静态初始化：手动指定数组的元素，系统会根据元素的个数，计算出数组的长度。

动态初始化：手动指定数组长度，由系统给出默认初始化值。

### 使用场景：

只明确元素个数，但是不明确具体的数据，推荐使用动态初始化。

已经明确了要操作的所有数据，推荐使用静态初始化。

### 举例：

* 使用数组来存储键盘录入的5个整数。

  int[] arr = new int[5];

* 将全班的学生成绩存入数组中，已知学生成绩为：66,77,88,99,100

  int[] arr = new int[5];

  arr[0] = 66;

  arr[1] = 77;

  ... 虽然可以实现，但是太麻烦了。

  建议使用静态初始化：int[] arr = {66,77,88,99,100};

## 10.数组常见问题

当访问了数组中不存在的索引，就会引发索引越界异常。

避免：

​	针对于任意一个数组，索引的范围：
   	最小索引：0
   	最大索引：数组的长度 - 1
​           		    数组名.length - 1

```java
public class ArrDemo6 {
    public static void main(String[] args) {
       int[] arr = {1,2,3,4,5,5,5,5,5};
        //用索引来访问数组中的元素
        System.out.println(arr[1]);
        System.out.println(arr[10]);//ArrayIndexOutOfBoundsException

    }
}
```

## 11.数组的练习

### 练习1：求和

需求：定义一个数组，存储1,2,3,4,5

遍历数组得到每一个元素，求数组里面所有的数据和

代码示例：

```java
/*定义一个数组，存储1,2,3,4,5
        遍历数组得到每一个元素，求数组里面所有的数据和*/


//分析：
//1.定义一个数组，并添加数据1,2,3,4,5
int[] arr = {1,2,3,4,5};

//求和变量
int sum = 0;
//2.遍历数组得到每一个数据，累加求和
for (int i = 0; i < arr.length; i++) {
    //i 依次表示数组里面的每一个索引
    //arr[i] 依次表示数组里面的每一个元素
    sum = sum + arr[i];
}

//当循环结束之后，sum的值就是累加之后的结果
System.out.println(sum);
```

### 练习2：统计个数

需求：定义一个数组，存储1,2,3,4,5,6,7,8,9,10

遍历数组得到每一个元素，统计数组里面一共有多少个能被3整除的数字

代码示例：

```java
//分析：
//1.定义一个数组 存储1,2,3,4,5,6,7,8,9,10
int[] arr = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
//定义一个变量，用来统计次数
int count = 0;
//2.遍历数组得到每一个元素
for (int i = 0; i < arr.length; i++) {
    //i 表示数组里面的每一个索引
    //arr[i] 表示数组里面的每一个元素
    //3.判断当前的元素是否为3的倍数，如果是那么统计变量就需要自增一次。
    if(arr[i] % 3 == 0){
        // System.out.println(arr[i]);
        count++;
    }
}
//当循环结束之后，就表示数组里面所有的数字都判断完毕了，直接打印count即可
System.out.println("数组中能被3整除的数字有" + count + "个");
```

### 练习3：变化数据

需求：

定义一个数组，存储1,2,3,4,5,6,7,8,9,10

遍历数组得到每一个元素。

要求：

1，如果是奇数，则将当前数字扩大两倍

2，如果是偶数，则将当前数字变成二分之一

代码示例：

```java
//分析：
//1.定义一个数组，存1,2,3,4,5,6,7,8,9,10
int[] arr = {1,2,3,4,5,6,7,8,9,10};
//2.遍历数组得到每一个元素
for (int i = 0; i < arr.length; i++) {
    //i 依次表示数组里面的每一个索引
    //arr[i] 依次表示数组里面的每一个元素
    //3.对每一个元素进行判断
    if(arr[i] % 2 == 0){
        //偶数 变成二分之一
        arr[i] = arr[i] / 2;
    }else{
        //奇数 扩大两倍
        arr[i] = arr[i] * 2;
    }
}

//遍历数组
//一个循环尽量只做一件事情。
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

### 练习4：求最值

需求：求数组中的最大值

代码示例：

```java
//定义数组求最大值：33,5,22,44,55

//扩展问题：
//1.根据求最大值的思路，自己改写一下求最小智
//2.为什么max要记录为arr[0],默认值不能为0吗？
//不能写0
//max的初始化值一定要是数组中的值。
//3.循环中开始条件一定是0吗？
//循环的开始条件如果为0，那么第一次循环的时候是自己跟自己比了一下，对结果没有任何影响，但是效率偏低
//为了提高效率，减少一次循环的次数，循环开始条件可以写1.


//1.定义数组用来存储5个值
int[] arr = {33,5,22,44,55};
//2.定义一个变量max用来存储最大值
//临时认为0索引的数据是最大的
int max = arr[0];
//3.循环获取数组中的每一个元素
//拿着每一个元素跟max进行比较
for (int i = 1; i < arr.length; i++) {
    //i 索引  arr[i] 元素
    if(arr[i] > max){
        max = arr[i];
    }
}
//4.当循环结束之后，max记录的就是数组中的最大值
System.out.println(max);//55
```

### 练习5：统计个数

需求：生成10个1~100之间的随机数存入数组。

1）求出所有数据的和

2）求所有数据的平均数

3）统计有多少个数据比平均值小

代码示例：

```java
//分析：
//1.定义数组
int[] arr = new int[10];
//2.把随机数存入到数组当中
Random r = new Random();

for (int i = 0; i < arr.length; i++) {
    //每循环一次，就会生成一个新的随机数
    int number = r.nextInt(100) + 1;
    //把生成的随机数添加的数组当中
    //数组名[索引] = 数据;
    arr[i] = number;
}


// 1）求出所有数据的和
//定义求和变量
int sum = 0;
for (int i = 0; i < arr.length; i++) {
    //循环得到每一个元素
    //并把元素累加到sum当中
    sum = sum + arr[i];
}
System.out.println("数组中所有数据的和为：" + sum);


//2）求所有数据的平均数
int avg = sum / arr.length;
System.out.println("数组中平均数为：" + avg);



//3）统计有多少个数据比平均值小
int count = 0;
for (int i = 0; i < arr.length; i++) {
    if(arr[i] < avg){
        count++;
    }
}

//当循环结束之后，就表示我已经找到了所有的比平均数小的数据
System.out.println("在数组中，一共有" + count + "个数据，比平均数小");



//遍历数组，验证答案
for (int i = 0; i < arr.length; i++) {
    System.out.print(arr[i] + " ");
}
```

### 练习6：交换数据

需求：定义一个数组，存入1,2,3,4,5。按照要求交换索引对应的元素。

交换前：1,2,3,4,5

交换后：5,2,3,4,1

代码示例：

```java
//1.定义数组存储数据
int[] arr = {1,2,3,4,5};
//2.利用循环去交换数据
for(int i = 0,j = arr.length - 1; i < j; i++,j--){
    //交换变量i和变量j指向的元素
    int temp = arr[i];
    arr[i] = arr[j];
    arr[j] = temp;
}
//当循环结束之后，那么数组中的数据就实现了头尾交换
for (int i = 0; i < arr.length; i++) {
    System.out.print(arr[i] + " ");
}
```

### 练习7：打乱数据 

需求：定义一个数组，存入1~5。要求打乱数组中所有数据的顺序。

代码示例：

```java
//1.定义数组存储1~5
int[] arr = {1, 2, 3, 4, 5};
//2.循环遍历数组，从0索引开始打乱数据的顺序
Random r = new Random();
for (int i = 0; i < arr.length; i++) {
    //生成一个随机索引
    int randomIndex = r.nextInt(arr.length);
    //拿着随机索引指向的元素 跟 i 指向的元素进行交换
    int temp = arr[i];
    arr[i] = arr[randomIndex];
    arr[randomIndex] = temp;
}
//当循环结束之后，那么数组中所有的数据已经打乱顺序了
for (int i = 0; i < arr.length; i++) {
    System.out.print(arr[i] + " ");
}
```

