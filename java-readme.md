# 目录
- [IDEA的使用](#idea的使用)
- [一、Java语言开发环境](#一Java语言开发环境)
- [二、入门程序](#二入门程序)
- [三、常量](#三常量)
- [四、变量和数据类型](#四变量和数据类型)
- [五、数据类型转换](#五数据类型转换)
- [六、运算符](#六运算符)
- [七、方法](#七方法)
- [八、jshell](#八jshell)
- [九、编译器优化](#九编译器优化)
- [十、流程控制](#十流程控制)
- [十一、数组](#十一数组)
- [十二、面向对象](#十二面向对象)
- [十三、API](#十三-api)
- [十四、static关键字](#十四static关键字)
- [十五、工具类](#十五工具类)
- [十六、继承](#十六继承)
- [十七、接口](#十七接口)
- [十八、多态](#十八多态)
- [十九、内部类](#十九内部类)

## IDEA的使用
![image-20200807004404269](https://tva1.sinaimg.cn/large/007S8ZIlly1ghhkk09a5gj318u0u0jwb.jpg)

```
IDEA的使用
先创建一个空项目project，然后在增加一个module,在module的src里创建一个Package
命名为 `a.b.c.e`如`com.gmm.day01.demo01`，域名的倒着写，日期，数目
这样是在src里创建了一个com文件夹，里面有个gmm-z文件夹，再接着有day01,demo01文件夹。

注意package的名称除了英文句点和英文、数字,其他的不要加。

opt + /      代码提示（在keymap里的main menu的code的	
			 completion的第一个basic更改）
			 
opt + enter  错误修复
cmd + d      复制当前行到下一行
opt+cmd+l    jetbrains软件格式化代码
shift+opt+f  vscode格式化代码
cmd + /      单行注释
shift+cmd+/  多行注释
shift+opt+↑↓ 移动当前代码行
opt+↑↓       选中代码，按上，选中代码逐渐增多，下，选中代码减少
cmd+n或者ctrl+enter  自动生成代码，toString,get,set等方法

shift+cmd+enter  表示光标定位到下一行
opt+cmd+t    在代码外加if，for等语句

main+enter    自动生成public static void main(String[]   
              args){}
sout+enter    自动生成System.out.println();
5.fori        自动生成 for (int i = 0; i < 5; i++) {}
              还可以换标识符
array.fori    自动生成遍历数组的for循环
list.fori     自动生成遍历ArrayList的for循环
变量.var       自动生成接收变量
.forr         与.fori相反

通用：
cmd + delete 删除一行
fn  + delete 删除光标后一个字符
opt + delete 删除光标前一个单词（English）
cmd + c      复制一行
cmd + x      剪切一行
cmd + v      粘贴一行

在命令行中
使用
ctrl+u/w/q 删除光标前的内容    ctrl+e 光标定位到行末
ctrl+k 删除光标后的内容    ctrl+a 光标定位到行首
也可以 ctrl+c 直接取消当前命令，进入新命令

```

```
文本编辑
* cmd+ →    到行末
* cmd+ ←    到行首
* cmd+ ↑    到文本开头
* cmd+ ↓    到文本末尾
* opt+ →    向右一个单词或一句连续的话
* opt+ ←    向左一个单词或一句连续的话
* 鼠标双击：选中一个单词
* 鼠标三击：选中一行
* 以上按键加shift , 即可以快速选中
* cmd + c   快速复制一行
* cmd + x   快速剪切一行
* cmd + enter 跳出代码块
```

## 一、Java语言开发环境

### Java虚拟机——JVM

- **JVM**（Java Virtual Machine）：Java虚拟机，简称JVM，是运行所有Java程序的假想计算机，是java程序的运行环境，是Java最具吸引力的特性之一。我们编写的Java代码，都运行在JVM上。
- **跨平台性**：java编写的软件可以运行在任何的操作系统上，这个特性称为Java语言的跨平台特性。该特性由JVM实现，我们编写的程序运行在JVM上，而JVM在每个运行系统上都有对应版本的JVM即win版本的JVM，Linux版本的JVM。

### JRE和JDK

- **JRE**( Java Runtime Environment)：是Java程序的运行时环境，包含`JVM`和运行时所需要的`核心类库`
- **JDK**( Java Development Kit)：是Java程序开发工具包，包含`JRE`和开发人员使用的工具。



运行Java程序，只要安装`JRE`

开发Java程序，必须安装`JDK`

关系

![image-20200806160949960](https://tva1.sinaimg.cn/large/007S8ZIlly1ghh5oz4eidj30ks0baabm.jpg)

## 二、入门程序

### java程序开发步骤

三部：编写、编译、运行

```
`.java` 源代码，经过`javac.exe`的编译器产生java字节码文件`.class`，然后用`java.exe`解释器在JVM里运行`.class`.
```

具体步骤

```
编写 HelloWorld.java,这里使得类名和文件名相同，注意大小写

----
public class HelloWorld {
	public static void main(String[] args){
		System.out.println("Hello world!");
	}
}
----

然后 javac HelloWorld.java,产生HelloWorld.class

-------
$ javac HelloWorld.java
-------

然后用java.exe执行HelloWorld,不写后缀

----
$ java HelloWorld
Hello world!
----
```

### 注释

```
//单行注释

/*
  多行注释（区块注释）
 */
```

```
//第一行的第三个单词必须和所在的文件名称完全一样，包括大小写
//public class代表定义一个类的名称
//类是Java当中所有源代码的基本组织单位
public class HelloWorld {
	//第二行的内容是不变的固定写法，代表main方法
	//是程序执行的起点
	public static void main(String[] args){
		//System.out.println是打印输出语句
		//屏幕展示
		//System.out.print不加换行,ln加换行
		System.out.println("Hello world!");
	}
}
```

### 关键字

```
关键字是有特殊含义的、被保留的不能随意使用的字符
常用的有:static,public,private,protected,class,void
特点:
1.小写字母
2.在特殊编辑器中有特殊颜色
```

### 标识符

#### 标识符定义

​		标识符是指在程序中，我们自己定义的内容比如类的名字，方法的名字和变量的名字。

```
`HelloWorld`就是一个标识符，类名
```


#### 命名规则：硬性

1. 标识符可以包括26英文字母（区分大小写）、0-9、`$`和`_`
2. 不能以数字开头
3. 不能是关键字

#### 命名规范：软性

1. 类名规范：首字母大写，后面每个单词首字母大写（大驼峰式）
2. 变量名规范：首字母小写，后面每个单词首字母大写（小驼峰式）
3. 方法名规范：同变量名

## 三、常量

### 概念

在程序运行期间，固定不变了量

### 分类

1. 字符串常量：凡是用双引号引起来的部分，叫做字符串常量. “ab”
2. 整数常量：直接写上的数字，没有小数点，100
3. 浮点数常量：有小数点的数字， 1.1，0.0
4. 字符常量：凡是单引号引起来的单个字符，’A’, ’9’, 包括’中’，’文’

5. 布尔常量：true, false 两种取值
6. 空常量：null ，代表没有任何数据

```
System.out.println()，里面可以直接加数字、字符常量。字符常量保证不为空，``，必须有一个字符。
```

## 四、变量和数据类型

### 数据类型

数据类型包括`基本数据类型`和`引用数据类型`

**基本数据类型**包括

```
整数型  byte(字节型、1字节) short(短整型、2字节) int(整型、4)  
       long(长整型、8)
浮点型  float(单精度浮点数、4) double(双精度浮点数、8)
字符型  char(字符型、2)，(范围0-65535)可以用来表示中文
布尔型  boolean(布尔类型、1)

默认类型：
浮点类型是double，如果要硬使用float，需要这样 3.14F，后面加个F
整数的默认类型是int，如果要使用long，加L后缀，100L。
```

**引用数据类型**包括

```
字符串、数组、类、接口、Lambda,enum
```

### 变量

定义：程序运行期间，内容可以发生改变的量。

```
public class Demo {
	public static void main(String[] args){
		int num1;
		num1 = 10;
		System.out.println(num1);
	}
}

1.注意：
	boolean var1 = true;
	SYstem.out.println(var1);
	结果为 true

2.注意：
	使用float和long类型，字母后缀F和L不能丢掉
3.byte和short类型变量，赋值不能超过其范围
4.变量的使用不能超过作用域的范围。
  （从定义变量的一行开始，一直到直接所属的大括号结束为止）
```

## 五、数据类型转换

```
自动类型转换（隐式）
	1.自动完成
	2.规则，数据范围从小到大 int-->long，long-->float
强制类型转换（显式）
	1.不能自动完成
	2. 范围小的类型 = （范围小的类型）范围大的数据
		int num = (int) 100L;
		
注意：
1.byte/short/char 这三种类型都可以发生数学运算，例如发生加法。
	char chr = 'A';
	System.out.println( chr + 1 );
2.在运算的时候，byte/short/char都会被首先提升为int类型，再进行计算。
比如 byte + byte ==> 先变成 int + int 
结果是一个 int .

而int + long ==> long + long 结果是long

3.boolean类型不能发生数据类型转换
```

```
ASCII编码表
如何查看char类型所代表的的数字

char chr = 'A';
System.out.println(chr + 0);
或者
int i = 'A';
System.out.println(i);



数字和字符的对照关系表（编码表）：

ASCII码表，American Standard Code for Information Interchange 美国信息交换标准代码
Unicode码表，万国码，也是数字和符号的对照关系，开头0-127部分和ASCII完全一样，但是从128开始包含有更多字符。

48 - '0'
65 - 'A'
97 - 'a'
```

## 六、运算符

```
1.如果运算中有不同类型的数据，那么结果就是变成数据类型范围大的那种
2.在运算的时候，byte/short/char都会被首先提升为int类型，再进行计算。结果也是int。
```

```
对于字符串 String（不是关键字）,加号代表字符串连接操作

任何数据类型和字符串进行连接的时候，结果都会变成字符串

String str = "HELLO";
System.out.println(str + 20 + 30);
结果是
HELLO2030

```

```
自增自减 ++ , --

+=自动进行强制类型转换
byte num = 30;
num += 5 ; 意思是 num = num + 5; 是byte + int
而我们自己不需要进行转换，该运算符自动进行强制类型转换
byte = (byte) (byte + int)
```

```
比较运算符

结果为布尔类型boolean，true,false

~表示按位取反,是位运算符,运算对象是2进制。1变0，0变1。 
&表示按位与，两位同时为1才为1
^表示按位异或，两位不同才为1
|表示按位或   两位至少有一个1，才为1
https://blog.csdn.net/Marccco/article/details/88709481

!  表示逻辑非,是逻辑运算符,运算对象是真或假。
&& 表示逻辑与
|| 表示逻辑或

&&和|| 具有短路效果，如果左边已经可以判断了，就不再执行后半句。
```

```
一元运算符：!,++,--,
二元运算符：+,-,*,/,=
三元运算符，需要三个数据才可以进行操作的运算符
int a = 10, b = 20;
int c = a > b ? a : b; (取最大值)

注意：
1.必须同时保证表达式a和表达式b都符合左侧数据类型的要求。
2.三元运算符的结果必须被使用。
```

## 七、方法

### 1. 方法概述

将一个功能抽取出来，把代码单独定义在一个大括号里，形成一个单独的功能。解决复用性，冗余性。

若干语句的功能集合

### 2. 格式

```
public static void 方法名称(){
	方法体
}
方法名称的命名规则和变量一样，小驼峰式
(首字母小写，后面每个单词首字母大写)

1.在main方法里 写 方法名称(); 即可，不需要声明
2.方法定义的先后顺序无所谓
3.方法的定义不能产生嵌套包含关系

```

### 3. 参数、返回值

```
定义方法的完整格式
修饰符 返回值类型 方法名称(参数类型 参数名称，……){
	方法体;
	return 返回值;
}


---
修饰符，现阶段的固定方法，public static

public static int sum (int a, int b){
	return a+b;
}
```

### 4.调用方法

```
1. 单独， 方法名称(参数);
2. 打印调用 System.out.println(方法名称(参数));
3. 赋值调用 int num = 方法名称(参数);

```

### 5. 方法重载 overload

```java
多个方法的名称相同，但是参数列表不一样
public static int sum(int a, int b){}
public static int sum(int a, int b, int c){}

参数列表不一样
1.个数不同
2.类型不同
3.多类型顺序不同(如果全是int，那么顺序不同也没有用)

方法重载无关因素
1.参数的名称
2.返回值
3.修饰符 (public static)
```

子类可以对父类的方法重载

## 八、JShell

```
在命令提示符里输入jshell,只能用于极其简单的程序。

jshell> System.out.println("hello world");
hello world

不用输入其他东西
退出 写 /exit

ps:print输出多个可以用`+`，例如
 System.out.println("输出为" + a );

```

## 九、编译器优化

1. 对于byte/short/char ，如果右侧赋值的数字没有超过范围，那么javac编译器就会自动隐含地位我们补上一个(byte/**)；如果超范围了，就会报错

2. 在给变量进行赋值的时候，如果右侧的表达式当中全是常量，没有任何变量，那么编译器javac将直接把若干个常量表达式计算得到结果，编译后的.class字节码文件已经把常量计算自动算完了，是否报错参加第一条。

3. 如果表达式右边有变量，那么就不会像2那样优化了

    ```
    byte a = 10 ;
    byte b = a + 10; 是会报错的
    ```

## 十、流程控制

### 1. 顺序结构 Sequence

### 2. 判断语句

1. 1-if
2. if…else
3. if…else if …else if…

### 3. switch语句

```
switch (){
	case 1:
		语句;
		break;
	case 2:
		语句;
		break;
	default:
		语句;
		break;
}
```

注意

1. case后面的值不能相同
2. switch后面的小括号当中只能是以下数据类型
    1. 基本数据类型：byte/short/char/int
    2. 引用数据类型：String字符串，enum枚举
3. swich语句可以很灵活，前后顺序可以颠倒，而且break可以省略。匹配哪一个case，就从那个地方往下执行。

### 4. 循环语句

四部分

1. 初始化语句，在循环开始最初执行，只做唯一一次
2. 条件判断，如果成立，则继续，不成立，循环退出
3. 循环体，重复要做的事情内容
4. 步进语句，每次循环之后都要进行的扫尾工作。

#### for

```
for (初始化表达式; 布尔表达式;步进表达式){
	循环体;
}
```

#### while

```
初始化语句
while (条件判断){
	循环体;
	步进语句;
}
```

#### do-while

```
初始化语句
do {
	循环体;
	步进语句;	
} while (布尔表达式);
```

#### 三种循环的区别

1. do-while至少执行一次，while和for最少执行0次

2. for循环的变量在小括号内定义，只有在循环内部才可以使用。while和do-while在外定义变量，可以在外使用。

#### break

打断switch和最近的循环

#### continue

跳过当次循环剩余内容，直接进入下一次循环

### 5. 死循环

标准格式

```
while (true){
	循环体;
}
```

如果前面是一个死循环，在死循环后面写一些语句，那么会报错，说无法访问。



## 十一、数组

```
数组是一种容器，可以同时存放多个数据值

特点:
1.数组是一种引用数据类型
2.数组当中的多个数据，类型必须统一
3.数组的长度在程序运行期间不可改变。
```

### 数组的初始化

```
初始化方式：
1.动态初始化（指定长度）
2.静态初始化 (指定内容)

动态初始化数组的格式:
数据类型[] 数组名 = new 数据类型[数组长度];
注意：`[]`中括号代表是一个数组
  	 new是创建数组的动作
  	 右侧的数据类型必须和左边的数据类型保持一致。
  	 数组长度，是int
  	 
int[] array = new int[300];
String[] array = new String[300];


静态初始化数组,自动推算长度。
基本格式
数据类型[] 数组名 = new 数据类型[]{元素1，元素2};
int[] array = new int[]{5,15,25};
String[] array = new String[]{"Hello","World"};


静态初始化数组的省略格式
数据类型[] 数组名称 = {10,20,30};
int[] array = {1,2,3};

注意:
1.静态初始化没有指定长度，但是仍然会自动推算得到长度
2.静态初始化标准格式可以拆分成两个步骤
	int[] array;
	array = new int[]{1,2,3};
3.动态初始化也可以拆分
	int[] array;
	array = new int[5];
4.省略格式不可以拆分❗️
	int[] array;
	array = {1,2};是不可以的
```

### 使用数组

```
直接打印数组名称，得到的是数组对应的，内存地址哈希值

访问数组的格式
数组名[索引值index],index从0到数字长度-1.

动态初始化数组的时候，其中的元素会自动拥有一个默认值
规则
1.如果是整数类型，默认为0，
2.如果是浮点类型，默认为0.0
3.如果是字符类型，默认为`\u0000`,u值Unicode,0000是十六进制位
4.如果是布尔类型，默认为false.
5.如果是引用类型，默认为null.

注意，静态初始化也有默认值，但是系统马上将默认值替换为了具体数值。
```

### 内存的划分

Java的内存需要划分成为5个部分

1. 栈(stack):存放的都是方法中的局部变量，**方法的运行在栈中**
    1. 局部变量：方法的参数，或者是方法{}内部的变量
    2. 作用域：一旦超出作用域，立刻从栈内存中消失
2. 堆(heap):**凡是new出来的东西，都是在堆中**
    1. 堆内存里的东西都有一个地址值：16进制
    2. 堆内存里面的数据，都有默认值。
    3. 默认值，整数为0，浮点数为0.0, 字符默认为’\u0000’,布尔为false,引用类型为null.
3. 方法区(Method Area)，存储`.class`相关信息，包含方法的信息
4. 本地方法栈(Native Method Stack):与操作系统相关
5. 寄存器 (pc Register): 与CPU相关

### 数组的内存图

![1](https://tva1.sinaimg.cn/large/007S8ZIlly1ghibpo2ycpj319u0jmql2.jpg)



如果数组索引越界

会提示

```
ArrayIndexOutOfBoundsExecption
```

所有的引用类型变量，都可以赋值为一个null值，但是代表什么都没有

如果此时访问，会异常

```
NullPointerException
```

### 数组的长度

```
int[] array = {10,20,30,20,20,……};
int len = array.length;

注意：
int[] array1 = new int[3];
System.out.println(array1.length); 输出3
array1 = new int [5];
则array1.length 值为 5.

即array1存储的地址哈希值可以改变


遍历
for (int i = 0; i < array.length; i++) {
            
}

快捷键
array.fori 再enter 自动生成for循环
```

### 数组元素的翻转

```
for(int i = 0,j = array.length - 1;i<j;i++,j--){
	int temp = array[i];
	array[i] = array[j];
	array[j] = temp;
}
```

### 数组作为参数，返回值

```
printArray(array);
	public static void printArray(int[] array){

}

avg = average

	public static int[] calculate(int a,int b){
		int[] array = new int[2];
		array[0] = a+b;
		array[1] = (a+b)/2;
	
		或者
		int[] array = new int[]{a+b,(a+b)/2};
		
		return array;
	}
那么怎么接受呢
int[] result = calculate(1,2);

注意
任何数据类型都能作为方法的参数，或者返回类型
数组作为方法的参数，传递的是数组的地址值。
数组作为方法的返回值，传回的是数组的地址值。
```

## 十二、面向对象

```
面向过程：当需要实现一个功能的时候，每一个具体的步骤都要亲力亲为，详细处理每一个细节
面向对象：当需要实现一个功能的时候，不关心具体的步骤，而是找一个已经具有该功能的人，来帮我做。

举例：要求输出数组元素，格式[1, 2, 3]
int[] array = {1,2,3};
-----------------------
面向过程：
System.out.print("(");
for(int i = 0;i<array.length;i++){
	if(i == array.length - 1){
		System.out.println(array[i]+"]");
	}else {
		System.out.println(array[i]+", ");
	}
}
面向对象
System.out.println(Arrays.toString(array));
(在文件首部自动添加 import java.util.Arrays;)
__________________________
```

面向对象思想特点，它是一种更加符合我们思考习惯的思想，它可以将复杂的事情简单化，并将我们从执行者变成了指挥者，面向对象的语言中，包含了三大基本特性，即封装，继承和多态。

### 类和对象的关系

类：是一组相关属性和行为的集合，可以看成是一类事物的模板，使用事物的属性特征和行为特征来描述该类事物。

猫🐱属性：名字，年龄，体重；行为：走、跑、叫。

对象：是一类事物的具体体现。对象是类的一个实例，必然具备该类事物的属性和行为。

对象，一只真实的猫。

(ΩДΩ)\(^o^)/~

类是对一类事物的描述，是抽象的。

对象是一类事物的实例，是具体的

类是对象的模板，对象是类的实体。

### 类的定义

事物与类的对比

现实世界的一类事物：

​	属性：事物的状态信息

​	行为：事物能够做什么

Java中用class描述事物也是如此：	

​	成员变量：对应事物的属性

​	成员方法：对应事物的行为

```
类定义的格式
public class ClassName{
	//成员变量
	//成员方法
	String name;
	int age;
	
	public void study(){
		
	}
}

注意：
1.普通方法有static，成员方法没有static关键字
2.成员变量直接定义在类当中，在方法的外部。

```

### 类的使用

通常情况下，类并不能直接使用，需要根据类创建一个对象，才能使用

1. 导包

2. 创建
3. 使用

```
1.导包(package)，指出需要使用的类，在什么位置
import 包名称.类名称;
import com.gmm.Demo;
如果要使用的目标类，和当前类在同一个包下，则可以省略导包语句不写。
```

```
2.创建
类名称 对象名 = new 类名称();
```

```
3.使用
使用成员变量，对象名.成员变量名;
使用成员方法，对象名.成员方法名(参数);

在不赋值直接使用成员变量，值为默认值。规则和数组一样
1.如果是整数类型，默认为0，
2.如果是浮点类型，默认为0.0
3.如果是字符类型，默认为`\u0000`,u值Unicode,0000是十六进制位
4.如果是布尔类型，默认为false.
5.如果是引用类型，默认为null.

String类型可以被这样赋值
String name;
name = "你的名字";
```

### 对象的内存图

![image-20200809003822402](https://tva1.sinaimg.cn/large/007S8ZIlly1ghjvmr7268j319g0imh8t.jpg)

```
对象存储的实际是一个地址值，通过这个地址访问堆区的内容。

new Phone()在堆区创建了一个对象，该对象里，有成员变量，成员变量实际存储在堆区，还有成员方法，实际存储的是一个地址，指向方法区的成员方法。

Phone one 创建一个对象，实际存储的是堆区的地址。

在调用函数时，将函数入栈，在栈内创建新数据类型。
```

### 两个引用指向同一对象

```
类名称 对象名 = 另一个对象名;
表示将内存地址赋值给左边的。指向同一块堆内存

对象类型作为方法的参数，实际传递的是该对象存储的地址
```

### 成员变量和局部变量的区别

1. 定义位置不同
    写在方法中的是局部变量（包括main方法）,直接写在类中的是成员变量（在方法外部）

2. 作用范围不一样

    局部变量：只有方法中才可以使用，出了方法就不能再用

    成员变量：整个类全都可以通用

    ```
    public class Demo01{
    	String name;
    	public void method1{
    		System.out.println(name);
    	}
    	public static void method2{
    		System.out.println(name);
    		//这样会报错，java无法从静态上下文中引用非静态变量name。
    		//如果要用，需要这样 static String name;
    	}
    }
    ```

3. 默认值不一样

    局部变量，没有默认值，如果要使用，必须手动赋值

    成员变量，有默认值，规则和数组一样

    ```
    1.如果是整数类型，默认为0，
    2.如果是浮点类型，默认为0.0
    3.如果是字符类型，默认为`\u0000`,u值Unicode,0000是十六进制位
    4.如果是布尔类型，默认为false.
    5.如果是引用类型，默认为null.
    ```

4. 内存的位置不一样

    ```
    局部变量，存储在栈中
    成员变量，存储在堆内存中（new出来的）
    ```

5. 生命周期不一样

    ```
    局部变量，随着方法进栈而诞生，随着方法出栈而消失。
    成员变量，随着对象创建而诞生，随着对象被垃圾回收而消失。
    ```

**注意：**

1. 方法的参数就是局部变量
2. 都可以在定义的时候赋值
3. 成员变量的作用域默认是friendly 就是同一个包内的类可以不用导入直接访问该成员变量，而且他包的类必须导入后才能访问。

### 三大特性之封装特性

面向对象三大特性：封装，继承，多态

封装在java当中的体现

1. 方法
2. 关键字private

封装就是将一些细节信息隐藏起来，对于外界不可见

#### private

```
自定义类中，定义的成员变量，无法阻止不合理的赋值，所以
要 private int age;
private关键字表示，只有在本类中才可以随意访问，但是超出本类的范围就不能直接访问了。（包括输出，赋值）

（private首先阻隔了直接对类里的成员变量访问，使访问必须经过成员函数，成员函数起一些限定或是判断之类的作用）

如需修改
需要在定义类中写
public void setAge(int num){
	age = num;
}
public int getAge(){
	return age;
}

间接访问private成员变量，就是定义一对儿Getter/Setter方法
注意
必须叫setXXX,或者是getXXX命名规则
对于Getter，不能有参数，返回值类型和成员变量对应
对于Setter，不能有返回值，参数类型和成员变量对应

可以使用ctrl+enter自动创建。
```

```
特殊情况
boolean类型数据
在Getter方法里，需要写成isXXX的形式

private boolean male;

public void setMale(boolean b){
	male = b;
}
public boolean isMale{
	return male;
}
```

#### this关键字

```
当自定义类的成员方法里的局部变量（参数）和成员变量重名的时候，根据就近原则，优先使用局部变量

如果要访问本类中的成员变量，需要使用
this.成员变量

通过谁调用的方法，this就是谁（this必须在成员方法里使用）。

```

#### 构造方法

构造方法就是专门用来创建对象的方法，当我们通过关键字new来创建对象时，其实就是在调用构造方法。

```
格式
public 类名(参数类型 参数名){
	方法体
}

在 new Person(); 时 就是调用了构造方法。

注意事项：
1.构造方法的名称必须和所在类名完全一样，包括大小写，特殊！
2.构造方法没有返回值，也不写void。
3.构造方法不能return一个具体的返回值
4.如果没有编写构造方法，那么编译器自动添加空的构造方法。
5.一旦编写了至少一个构造方法，那么编译器将不再编写其他构造方法。
	举例，就是如果自己编写了带有参数的构造方法， 则自己还需编写没有参数的构造方法。
6.构造方法可以重载，方法名相同，而参数列表不同。

public Person(int age){
	System.out.println(构造方法执行了);
	this.age = age;
}
Person person = new Person(10);
```

```
标准的类

1.所有成员变量都要使用private关键字修饰
2.为每一个成员变量编写一对儿Getter/Setter方法
3.编写一个无参数的构造方法
4.编写一个全参数的构造方法

这样标准的类也叫做 Java Bean
```

## 十三、 API

### 概述

API（Application Programming Interface） 应用程序编程接口。java API是一本程序员的`字典`，是JDK中提供给我们使用类的说明文档，这些类将底层的代码实现封装了起来，不需要关心具体如何实现，只需要学习这些类是如何使用即可。所以我们可以通过查询API的方式，来学习java提供的类。

### Scanner类

scanner类可以实现键盘输入数据

scanner是一个引用类型

引用类型使用步骤

1. 导包

    ```
    import 包路径.类名称;
    （在package后，在public class之前写）
    如果要使用的目标类，和当前类在同一个包下，则可省略导包语句。
    
    另外，在 java.lang包下的内容也不需要导包，其他的需要导包
    ```

2. 创建

    ```
    类名称 对象名 = new 类名称();
    ```

3. 使用

    ```
    对象名.成员方法名();
    ```

Scanner的使用

```
在package后，在public class之前写
import java.util.Scanner;

方法内部：
Scanner sc = new Scanner(System.in);
`System.in`表明从键盘输入

使用
1.输入int数字：int num = sc.nextInt();
2.输入字符串:  String str = sc.next();
```

### 匿名对象

```
new 类名称();
匿名对象只能使用唯一一次，下次再用不得不在创建一个新对象。
使用建议：如果确定有个对象只使用唯一一次，就可以使用匿名对象。
```

```
匿名对象作为方法参数和返回值

int num = new Scanner(System.in).nexInt();

作为参数
method(new Scanner(System.in));

作为返回值
public static Scanner method(){
	return new Scanner(System.in);
}
```

### Random类

```
1.导包， import java.util.Random;
2.创建,  Random r = new Random();
3.使用,  获取一个随机的int数字（范围是int所有范围）
		int num = r.nextInt();
		
	获取一个范围内的随机数
	int num = r.nextInt(3);表示左闭右开区间[0,3)，就是0-2;
	
	获取1-n的随机数字[1,n];
	int n = new Scanner(System.in).nextInt();
	int result = r.nextInt(n)+1;
```

### 对象数组

```
Person类
Person[] array = new Person[3];
其中由于Person类是引用类型，所以Person[0]默认值为null.

赋值
Person one = new Person("name",age);
array[0] = one;(将地址赋值给数组的0号元素)

数组的缺点，长度不可以改变
所以对象数组（集合类）解决了这个问题ArrayList
```

```
ArrayList类
import java.util.ArrayList 是大小可变的数组的实现，存储在内数据成为元素，ArrayList可不断天界新元素，其大小也自动增长。
```

```
使用方法
查看JDK的API文档，类ArrayList<E> ，有个<E>，叫做泛型，泛型，也就是装在集合当中的所有元素，全都是统一的什么类型。泛型只能是引用类型，不能是基本类型

ArrayList<String> list = new ArrayList<>();
从JDK 1.7+开始，右侧的尖括号内部可以不写内容，但是<>还是要写

此时
System.out.println(list);
输出为 []
即如果list为空，输出为空的方/中括号,[]
 
添加数据
list.add("c++");
list.add("c");
此时输出[c++, c]   用`,`和` `方式隔开
```

```
ArrayList 当中的常用方法
public boolean add(E e), 向集合内添加元素，参数的类型和泛型一致
pubLic E get(int index), 从集合中获取元素，参数时索引编号，返回值就是对应位置的元素
public E remove(int index)，从集合中删除元素，返回值是删除的元素
public int size(),获取集合的长度，返回值是集合中的元素个数。

如何快速遍历
list.fori + enter
```

```
ArrayList存储基本类型数据，必须使用基本类型对应的包装类

基本类型的包装类是引用类型，在java.lang包下，不用导包.
基本类型    包装类
byte       Byte
short      Short
int        Integer
long	   Long
float 	   Float
double     Double
char       Character
boolean    Boolean

ArrayList<Integer> list = new ArrayList<>();
list.add(100);
int num = list.get(0);

自JDK 1.5+开始，支持自动装箱和拆箱。
装箱，基本类型-->包装类型（引用类型） int-->Integer
拆箱，包装类型-->基本类型           Integer-->int
```

### String

程序当中，所有的双引号字符串，都是String类的对象，就算没有new。

`String s `这个语句声明的是一个指向对象的引用，名为“s”。

字符串的特点

1. 字符串的内容永不可变
2. 因为字符串不可改变，所以字符串是可以共享的。
3. 字符串效果相当于`char[]`字符数组，但是底层原理是`byte[]`字节数组。

创建字符串的3+1种方式(三种构造方法，一种直接创建)

1. public String(),创建一个空白字符串，不含任何内容
	`String str1 = new String();`
2. public String(char[] array),根据字符数组的内容，来创建对应的字符串
	```
	char[] charArray = {'A','B','C'};
	String str2 = new String(charString);
	```
3. public String(byte[] array),根据字节数组的内容，来创建对应的字符串
	```
	byte[] byteArray = { 97 , 98, 99};
	String str3 = new String(byteArray);
	```
4. ```
	String str = "Hello";<==>String str = new String("Hello");等价，但是却不同
	也可以String str; <==> String str = new String();
	之后，还可以改变str的值，例如str = "123";str = "234";
	
	
	-------------------
	String str1 = "abc";
	String str2 = new String(“abc”);
	在堆区分配对象的内存然后在调用构造函数将”abc”.value的值赋值给str2对象的value
	它们是不同的对象(可以用System.out.println(str1==str2)验证为False）
	但它们的value值是相同的都是指向同一个字符串常量”abc”;
	```

字符串的常量池

```
String str1 = "abc";
String str2 = "abc";
char[] charArray = {'a','b','c'};
String str3 = new String(charArray);
则str1 与 str2存储地址一样，与str3 不一样。

并且 str1 与 "abc" 地址也一样

字符串常量池，程序当中直接写上的双引号字符串，就在字符串常量池中。
new的不在池当中

对于基本类型，==是进行数值比较，对于引用类型，==是进行地址值比较。
```

字符串常量池在堆中

![image-20200809191747040](https://tva1.sinaimg.cn/large/007S8ZIlly1ghkrzhk07zj317y0i27g3.jpg)

```
new出来的字符串对象，和常量池中的字符串对象，存储的都是地址，地址指向堆区的byte[]型数组，

这里有点问题，也就是String str1/2/3  存储的分别是存放在堆区或者字符串常量池的字符串对象的地址，不是字符串对象存放的地址。
```

字符串比较

```
1.public boolean equals(Object obj).参数可以是任何对象，只有参数时一个字符串并且内容相同的才会给true，否则为false，

可以这样  "Hello".equals(str1); 具有对称性
如果比较方一个是常量一个是变量，推荐把常量字符串写在前面。防止变量为null

任何对象都能用Object进行接收。(包括基本数据类型)

2.public boolean equalsIgnoreCase(String str), 忽略大小写
```

String字符串的获取相关方法

```
public int length() 
获取字符串当中含有的字符个数，拿到字符串长度

public String concat(String str)
将当前字符串和参数字符拼接，返回值为新的字符串
（加号也可以）

public char charAt(int index)
获取指定索引位置的单个字符(索引从0开始)

public int indexOf(String str)
查找参数字符串在本字符串当中首次出现的索引位置，如果没有，返回-1.
```

字符串截取

```
public String substring(int index)
截取从参数位置一直到字符串末尾，返回新字符串。原字符串不改变

public String substring(int begin,int end)
截取[begin,end) 之间的字符串。

注意，字符串内容不会改变，改变的是String类对象存储的地址值
```

字符串的转换相关方法

```
public char[] toCharArray();
将当前字符串拆分成为字符数组作为返回值

public byte[] getBytes();获得当前字符串底层的字节数组
例如"abc" 就是生成 byte[] xx = {97,98,99};

public String replace(CharSequence oldString,CharSequence newString);
将所有出现的老字符串替换成为新字符串，返回替换后的结果新字符串
备注：CharSequence 表示可以接受字符串类型
String str2 = str1.replace("o","a");
```

字符串的分割

```
public String[] split(String regex)
regex是指regular expression ,正则表达式
按照参数的规则，将字符串切分成为若干部分。

举例，String str = "123 456";
String[] str1 = str.split(" ");用空格切割
结果为str1[0]为"123",str1[1]为"456";

注意事项：
split方法的参数其实是一个“正则表达式”
今天注意，如果要按照英文句点`.`进行分割，必须写"\\."（俩反斜杠）
```

## 十四、static关键字
对于自定义类，创建多个对象，如果有的成员变量是共享的，相同的，那么只在类当中保存唯一一份，那所有本类对象共享同一份。

一旦使用了static关键字，那么这样的内容不再属于对象自己，而是属于类的，所以凡是本类的对象，都共享同一份数据。

使用
	
```
修饰成员变量

定义类的时候
static private String class;

在使用时只要赋值一次就好

在类中定义计数器
static private int idCounter;
```

```
修饰成员方法
一旦使用static关键字修饰成员方法，那么这就是成为了静态方法，静态方法不属于对象，而是属于类的。

对于静态方法来说，可以通过对象名进行调用，也可以直接通过类名称进行调用

Person perosn = new Person();
person.method();(不推荐，这样编译后，会被javac翻译为类名称.静态方法名)
或者直接
Person.method();
```
注意:
1. 所以无论是成员变量还是成员方法，
如果有static关键字，都推荐使用类名称进行调用

2. 对于本类当中的静态方法，可以省略类名称。（等效翻译为本类.方法()）
3. 静态方法只能直接访问静态变量，不能直接访问非静态。非静态方法可以访问非静态变量。因为在内容当中，先有静态内容，后有非静态内容。所以先人不知道后人，后人知道先人。
4. 静态方法中不能使用this关键字，因为调用时，对象被转换成为了类名称，this是存储该对象存储的地址的，所以不行。

内存图
![](https://tva1.sinaimg.cn/large/007S8ZIlly1ghliphyjesj319k0ic7mf.jpg)

静态代码块
```
public class 类名称{
	static{
		//静态代码块内容
	}
}

特点，当第一次用到本类的时候，静态代码块执行唯一一次。
静态代码块优先于构造方法

用法，用来一次性地对静态成员变量进行赋值
```

## 十五、工具类

### 数组工具类Arrays

java.util.Arrays 是一个与数组相关的工具类，里面提供了大量的静态方法，用来实现数常见的操作
```
public static String toString(数组);将参数数组变成字符串，默认格式[元素1, 元素2]

举例：
int[] intArray = {1,2,3};
String str = Arrays.toString(intArray);
则str输出后为`[1, 2, 3]`
```

```
public static void sort(数组),默认按照从小到大的顺序排序。


备注：
1.如果是数值，sort默认按照从小到大。
2.如果是字符串，默认按照字符升序
3.如果是自定义的类型，那么这个自定义的类需要有Comparable或者Comparator接口支持
```

### 数学工具类Math

import java.util.Math
```
其内部提供了很多静态方法,利用类名直接调用

public static double abs(double num);获取绝对值

public static double ceil(double num);向上取整（向正向取整，-1.2==>-1）

public static double floor(double num);向下取整

public static long round(double num);四舍五入

Math.PI 代表近似的圆周率常量
```

## 十六、继承
封装，**继承**，多态
继承是多态的前提
```
继承解决的问题是：`共性抽取`
父类：也可以成为基类，超类；
子类：也可以叫派生类

继承关系：
1.子类可以拥有父类的“内容”
2.子类还可以拥有自己专有的内容

java继承特点
1. 继承是单继承，一个类的直接父类只能有唯一一个
2. 可以多级继承。
   1. `b extends a`,`c extends b`,则也称a是c的父类，但不是直接父类。
   2. java.lang.Object是所有类的父类，它没有父类
3. 一个父类可以拥有多个子类
4. 可以通过子类的对象和子类的类名访问父类的静态变量和静态方法。
```

```
定义父类格式
public class 父类名称{

}

在新`.java`文件内写
定义子类格式
public class 子类名称 extends 父类名称{

}
```

```
如果子类和父类的成员变量重名，则
1.直接通过子类对象访问成员变量：
	等号左边是谁，就优先用谁，没有则向上找
2.简接通过成员方法访问成员变量
	方法属于谁，就优先用谁的成员变量
```

区分子类方法中重名的三种变量
```
以下在子类的方法中调用

局部变量          直接用 
本类的成员变量     this.成员变量名
父类的成员变量     super.成员变量名

super指的是该子类对象的父类对象，可以认为子类创建的对象内部创建了一个父类对象
```

```
如果子类和父类的成员方法重名，则优先调用最近的那个。
```

继承中方法的重写（覆盖、覆写） Override
概念：在继承关系中，方法的名称一样，参数列表也一样。
```
注意事项
1.必须保证父子类之间方法的名称相同，参数列表页相同。
	@Override,写在方法前面，用来检测是不是有效的正确覆盖重写。（@为annotation，注解）
2.子类方法的返回值必须小于等于父类的返回值范围。
（注意，这仅仅存在于引用类型，不包括基本类型，基本类型返回值必须一样）
	java.lang.Object类是所有类的公共最高父类（祖宗类）
	java.lang.String就是Object的子类
3.子类方法的权限必须大于等于父类方法的权限修饰符
	public > protected > (default) > private
	(default)是留空
```
覆盖重写应用场景
```
对于已经通入使用的类，尽量不要进行修改。
推荐定义一个新的类
来重复利用其中共性的内容，并且添加新改动的内容

在子类覆盖重写方法时，写上方法名，然后回车，自动添加@override和方法其他参数
```

父子类构造方法的访问

```
1. 子类构造方法当中，有一个默认隐含的"super()"调用，所以先调用父类的构造方法，再调用子类的构造方法。

	public Zi(){
		super();//父类无参构造方法，不写自动产生。
		System.out.println("子类构造方法");
	}

2. 可以通过super()调用父类的重载的构造方法。

	public Zi(){
		super(10);
	}

3. 只有子类构造方法才能调用父类构造方法super()，而且要防在子类构造方法的第一条语句，而且只能调用一次（不能即调用无参构造，又调用有参构造）
```

### super关键字
用法
1. 在子类的成员方法中，访问父类的成员变量
2. 在子类的成员方法中，访问父类的成员方法
3. 在子类的构造方法中，访问父类的构造方法。

### this关键字
用法
1. 在本类的成员方法中，访问本类的成员变量 
2. 在本类的成员方法中，访问本类的另一个成员方法 （强调作用）`this.method();`
3. 在本类的构造方法中，访问本类的另一个构造方法
	```
	public Zi(){
		this(1);
	}
	public Zi(int num){
		this.num = num;
	}
	注意，this()调用也必须是构造方法的第一个语句，唯一一个。
	super和this两种构造调用，不能同时使用。只能有一个存在
	```

### super和this关键字图解

```
下面说一个例子
public class Fu{
	int num = 10;
	public void method(){};//父
}
public class Zi extends Fu{
	int num = 20;
	@override
	public void method(){};//子
	public void show(){
		int num = 30;
		System.out.println(num);// 30
		System.out.println(this.num);// 20
		System.out.println(super.num);// 10
	}
}
```
![](https://tva1.sinaimg.cn/large/007S8ZIlly1ghmn8bzvcuj31mo0u07wh.jpg)

### 抽象方法
```
抽象方法，就是加上abstract关键字，然后去掉大括号，直到分号结束
抽象类：抽象方法所在的类，必须是抽象类才行，在clss之前写上abstract即可

public abstract class Animal{
	public abstract void eat();//抽象方法
	public void normalMethod(){}//普通成员方法
}
```

### 怎么使用抽象类和抽象方法
1. 不能直接创建new抽象类对象
	```
	Animal animal = new Animal();//错误
	```
2. 必须用一个子类来继承抽象父类
3. 子类必须覆盖重写抽象父类当中所有的抽象方法
	即去掉abstract关键字，补上实现内容。
	```
	public class cat{
		@override
		public void eat(){
			System.out.println("子类");
		}
	}
	```
4. 创建子类的对象进行使用

#### 注意事项

1. 抽象类不能创建对象。
2. 抽象类中，可以有构造方法，是供子类创建对象时，初始化父类成员使用的`super()`
3. 抽象类中，不一定包含抽象方法，但是有抽象方法一定是抽象类
4. 抽象类的子类，必须重写父类的所有抽象方法，除非子类也是抽象类。

## 十七、接口

- 接口就是多个类的公共规范
- 接口是一种引用类型，最重要的是其中的抽象方法

### 如何定义一个接口

```
新建文件时选择Interface,

public interface 接口名称{
	//接口内容
}

备注，换成了关键字interface，编译生成的字节码文件，仍然是`.java--->.class`
```

不同版本java的接口有不同内容
- java 7 接口可以有常量和抽象方法
- java 8 接口可以额外有默认方法，静态方法
- java 9 接口可以额外有私有方法


### 接口使用步骤

1. 接口不能直接使用，必须有一个“实现类”来实现该接口
	```
	public class 实现类 implements 接口名称{
	}
	```
2. 接口的实现类必须覆盖重写接口中的所有抽象方法
	```
	推荐实现类命名为`接口名Impl`
	(implement，可以翻译为实现);
	```
3. 创建实现类的对象，进行使用。
	```
	如果这个实现类没有覆盖重写接口所有的抽象方法，那么这个实现类自己也必须是抽象类
	```

### 具体实现
1. 接口内定义抽象方法
	```
	public abstract 返回值类型 方法名称(参数列表);

	注意：
	1. 接口中的抽象方法，修饰符必须是两个固定的关键字：public abstract
	2. 这两个关键字修饰符，可以选择地省略，不推荐
	3. 如果这个实现类没有覆盖重写接口所有的抽象方法，那么这个实现类自己也必须是抽象类
	```
2. 接口内默认方法定义
	```
	java8，开始接口允许定义默认方法。
	public default 返回值类型 方法名称(参数列表){
		方法体
		//public 可以省略
		//default 不可以省略
	}
	备注：接口当中的默认方法，可以解决接口升级的问题
	```

	注意：
	1. 接口的默认方法，可以通过接口实现类对象直接调用
	2. 接口的默认方法，也可以被实现类覆盖重写，但不是必要的。
	3. `public`可省略

3. 接口的静态方法定义
	```
	java8 开始，接口允许定义静态方法。
	public static 返回值类型 方法名称(参数列表){
		方法体
		//public 可以省略
	}

	通过接口名称直接访问
	接口名.静态方法();

	不能通过接口实现类的对象来调用接口当中的静态方法。
	也不能通过接口的实现类名称直接调用。
	（因为一个实现类可以实现多个接口，怕产生冲突）
	理论上编辑器应该讲实现类调换成接口名，但是如果冲突的话，就没法实现了。

	```
4. 接口的私有方法定义
	```
	java9 接口允许定义私有方法
	1. 普通私有方法，解决多个默认方法之间重复代码的问题，并且不让实现类访问。
	private 返回值类型 方法名(参数列表){
		方法体
	}
	2. 静态私有方法，解决多个静态方法之间重复代码的问题。
	private static 返回值类型 方法名(参数列表){

	}

	注意，静态方法只能调用[私有或者公有]静态方法，非静态方法可以调用所有的静态或非静态方法。
	```
5. 接口内定义成员变量（就是常量）\
 必须使用`public static final`三个关键字进行修饰
 从效果上看，这其实就是接口的[常量]。
 	```
 	public static final int NUM = 10;
 	这是一个常量，一旦赋值，无法改变。
	`final`关键字，说明不可改变
 	1. 不写`public static final`也是自动添加。
 	2. 接口的常量，必须进行初始化赋值。
 	3. 接口中的常量名称，必须完全大写，不同单词用`_`分隔。
	4. 可以通过实现类的类名直接访问,也可以通过实现类的对象访问接口内定义的常量。
 	```

### 注意事项

1. 接口是没有静态代码块或者构造方法的。
2. 一个类的直接父类是唯一的,但是一个类可以同时实现多个接口。\
	格式：
	```java
	public class MyInterfaceImpl implements MyInterfaceA,MyInterfaceB{

	}
	```
3. 如果实现类所实现的多个接口中，存在重复的抽象方法，那么只需要覆盖重写一次即可
	（重复的抽象方法指参数列表相同的）
4. 如果实现类没有覆盖重写所有接口当中的所有抽象方法，那么实现类必须是抽象类
5. 如果实现类所实现的接口中，默认方法存在重复，则必须对默认方法覆盖重写。（实现类是抽象类也是这样）
6. 一个类如果它的直接父类当中的方法，和接口当中的默认方法，产生了冲突，优先使用父类的方法。
	```java
	如何即继承又实现
	public class Son extends Father implements MyInterface{}
	```

### 接口之间的多继承

<!--2020-08-11夜，看到了第184集，记录之-->

1. 类与类之间是单继承的，直接父类只能有一个
2. 类与接口之间是多实现的，一个类可以实现多个接口
3. 接口与接口之间是多继承的。
	```java
	public interface MyInterface extends MyInterfaceA, MyInterfaceB {
	}
	注意:
	1. 子接口不需要覆盖重写父接口的抽象方法。
	2. 多个父接口当中的抽象方法如果重复，子接口不用管，只需在实现类中覆盖重写一个就行
	3. 多个父接口当中的默认方法重复，那么子接口必须覆盖重写该默认方法。
	```

## 十八、多态

面向对象三大特征，封装性，继承性，**多态性**, `extends`继承或者`implements`实现，是多态性的前提。

### 多态的格式和使用

java代码当中体现多态性：父类对象的引用指向子类对象。

```
格式：
Father father = new Son();
或者：
MyInterface obj = new InterfaceImpl();

则,
如果子类覆盖重写了父类的成员方法
father.method();执行的是子类的方法，即优先子类成员方法。
但是父类对象的引用无法访问子类的特有方法，只能访问父类方法和子类中覆盖重写父类的方法。

如果子类和父类的成员变量重名
father.variable;访问的是父类的成员变量。

即，成员方法优先访问子类，再访问父类，成员变量只能访问父类的。
```
即
1. 成员变量
   1. 父类对象的引用，只能访问父类的成员变量
   2. 不能访问子类成员变量
2. 成员方法
   1. 不能访问子类特有的成员方法。
   2. 只能访问父类的成员方法和子类中覆盖重写父类的成员方法，而且，优先访问子类覆盖重写的方法。

### 多态的好处

无论右边new的时候是哪个子类，等号左边就是父类`Father obj = new Son()`,并且调用的方法种类不改变，达到统一性(因为多态不能访问子类特有的成员方法)。

### 对象的转型

1. 对象的向上转型，就是多态的写法
   1. 格式：父类名称 对象名 = new 子类名称();
   2. 含义：右侧创建一个子类对象，把它当做父类来看待使用
   3. 注意事项：向上转型一定是安全的。从小范围转向了大范围，是安全的，类似int-->double的自动类型转换。
   4. 向上转型，编译器可以自动向上转型。
2. 对象的向下转型，其实是一个还原的动作
   1. 格式：子类名称 对象名 =(子类名称)父类对象引用;
   2. 含义：将父类对象的引用，[还原]成为本来的子类对象，可以调用子类特有的成员方法。
   3. 注意事项
      1. 必须保证还原后的子类对象与创建时new的子类对象的子类名称相同。
      2. 如果不同会报错。`ClassCastException`
   4. 编译器不可以自动向下转型。
	
### instanceof

如何才能知道一个父类引用的对象，本来是什么子类，用instanceof。

#### 格式：
`父类对象的引用 instanceof 子类名称`
返回值类型是boolean,即判断该父类对象的引用创建时new的子类是否与后面的子类名相同。

#### 使用：
```java
主要用于传参
public static void main(String[] args){
	giveMeAnAnimal(new Dog());//向上转型
		相当于 Animal animal = new Dog();
		或者{
			Dog dog = new Dog();
			Animal animal = dog; //这样也是向上转型
		}
	giveMeAnAnimal(new Cat());//向上转型
}

public static void giveMeAnAnimal(Animal animal){
	if(animal instanceof Dog){
		Dog dog = (Dog) animal;//向下转型
		dog.watchHouse();
		return;
	}
	if(animal instanceof Cat){
		Cat cat = (Cat) animal;//向下转型
		cat.catchMouse();
		return;
	}
}
```

## 十九、内部类

### final关键字

`final`关键字代表最终，不可改变的

#### 常见用法：
1. 可以用来修饰一个类
   1. 当用final修饰类的时候,此类不可被继承,即final类没有子类。
   2. 用法
		```java
		public final class 类名称{}
		```
   3. 注意：一个final类，那么所有的成员方法都无法进行覆盖重写。所以final类不能有抽象方法。
2. 可以用来修饰一个方法
   1. final方法，表示不能够被覆盖重写
   2. 用法
		```java
		修饰符 final 返回值类型 方法名称(参数列表){}
		public final void method(){}
		```
   3. 注意：对于类和方法来说，abstract关键字和final关键字不能同时使用，因为矛盾
3. 可以用来修饰一个局部变量
   1. final局部变量，变量不能进行更改，只能赋值一次。
   2. 用法
		```java
		final int num1 = 10; √

		final int num2;
		num2 = 10;          √
		两种赋值方法都可以
		```
   3. 注意，对于基本类型，不可变指的是变量当中的数据不可改变；对于引用类型，不可变说的是变量当中的地址值不可改变，而该地址指向的内容可变。
4. 可以用来修饰一个成员变量
   1. final修饰成员变量后，第一种是在创建的时候进行赋值，这样的话，构造方法和成员方法都不能对其赋值。
		```
		final String name = "123";
		```
   2. 对于final修饰的成员变量，要么使用直接赋值，要么通过构造方法赋值，通过构造方法赋值，必须创建时不赋值,必须保证所有重载的构造方法都对该final成员变量进行赋值。
		```
		final String name;
		public Person(){
			this.name = "123";
		}
		public Person(String name){
			this.name = name;
		}
		```

### 四种权限修饰符

权限：`public` > `protected` > `(default)` > `private`
注意：`(default)`并不是关键字`default`，而是不写，除了[接口内默认方法定义](#具体实现).

注意：
以下内容指的是`public`类中，成员变量的访问权限，在不同包`package`中，需要写导包语句，而且不同包的概念包括一个包在另一个包内部。

|   |`public`|`protected`|`(default)`|`private`|
|:-:|  :-:   |  :-:      |   :-:     |  :-:    |
|同一个类访问`我自己`|可以|可以|可以|可以|
|同一个包内访问`我邻居`|可以|可以|可以|不可以|
|不同包的子类访问`我儿子`|可以|可以|不可以|不可以|
|不同包非子类访问`陌生人`|可以|不可以|不可以|不可以|

### 内部类的概念与分类

一个类内部包含另一个类，一个事物包含另一个实物，例如，身体和心脏的关系

分类:
1. 成员内部类
2. 局部内部类（包含匿名内部类）

#### 成员内部类

成员内部类，直接定义在另一个类内的类。
```java
格式：
修饰符 class 外部类名称{
	修饰符 class 内部类名称{
	}
}

注意：内用外，随意访问，外用内，需要内部类对象。
```

<!-- 2020-08-16，星期日，学习至P202,很烦，妹妹在家闹呢 -->

```java
public class Body{
	public class Heart{
		public void beat(){
			System.out.println("123");
		}
	}
	public void show(){
		new Heart().beat();
	}
}
编译后，在该项目下的`./out/production`文件夹与`.java`对应位置的地方会产生`.class`文件。
此时产生的文件有 `Body.class` & `Body$Heart.class`，
`$`表示Heart类是Body类的内部类
```

**成员内部类的使用**
1. 间接方式：在外部类的方法当中，使用内部类，然后在另一个类的main方法只是调用该外部类的方法。（注意，此时的外部类和内部类，没有main方法，只是当做自定义类）
	```java
	public class Body{
		public class Heart{
			public void beat(){
				System.out.println("123");
			}
		}
		public void show(){
			new Heart().beat();
		}
	}

	public class Demo{
		public static void main(String[] args){
			Body body = new Body();
			body.show();
		}
	}
	```
2. 直接方式：公式：外部类名称.内部类名称 对象名 = new 外部类名称().new 内部类名称();
	```java
	public class Demo{
		public static void main(String[] args){
			Body.Heart heart = new Body().new Heart();
			heart.beat();
		}
	}
	```

**内部类的同名变量访问**

如果变量重名的话，内部类内的方法内，定义的局部变量，直接用变量名字访问；内部类的成员变量，用`this.变量名`访问；外部类的成员变量，用`外部类名.this.变量名`访问。
```java
public class Outer{
	int num = 10;//外部类的成员变量
	public class Inner{
		int num = 20;//内部类的成员变量
		public void method(){
			int num = 30;//内部类方法的局部变量
			num               //30 局部变量
			this.num          //20 内部类的成员变量
			Outer.this.num    //10 外部类的成员变量
		}
	}
}
```

#### 局部内部类

一个类是定义在一个方法内部，那么就是一个局部内部类，只能在所属的方法才可以使用它。
```java
public class Outer{
	public void methodOuter(){
		class Inner{ //不加public关键字修饰
			int num = 10;
			public void methodInner(){

			}
		} 
		Inner inner = new Inner();//只能这样访问
		inner.methodInner();
	}
}
```

**局部内部类的final问题**

局部内部类，如果想要访问所在方法的局部变量，那么这个局部变量必须是【有效final的】。

备注:从java8+开始，只要局部变量事实不变，那么final关键字可以省略。即，必须加final关键字修饰该方法的局部变量；如果不加final关键字，则必须保证方法的局部变量是只被赋值一次，不再改变。

```java
public class Outer{
	public void method(){
		int num = 10;
		class Inner{
			public void methodInner(){
				System.out.println(num);
			}
		}
	}
}
```

原因：
1. new出来的对象在堆内存中
2. 局部变量是跟着方法走的，在栈内存当中
3. 方法运行结束之后，立刻出栈，局部变量就会立刻消失
4. 但是new出来的对象会在堆内存当中持续存在，直到垃圾回收消失。
5. 所以当局部变量消失的时候，会在常量区创建该局部变量的副本，供堆区的对象使用。

#### 局部内部类的匿名内部类

如果接口的实现类（或者是父类的子类）只需要使用唯一的一次。
那么这种情况下就可以省略掉该类的定义，而改为使用【匿名内部类】

匿名内部类的定义格式
```java
//这样相当于多态，接口对象的引用指向了实现类的对象。
//接口名称 对象名 = new 实现类名称();
接口名称 对象名 = new 接口名称(){
	//覆盖重写所有抽象方法
};
//是不是也可以推广到抽象类和普通父类,经查阅，是可以的
父类/抽象类 对象名 = new 子类/实现类(){
	//可以覆盖重写父类/抽象类的相关方法。
};

pubic class Demo{
	public static void main(String[] args){
		MyInterface obj = new MyInterace(){
			@Override
			public void method(){

			}
		};
		obj.method();//运行的是覆盖重写后的方法。
	} 
}
```
**注意事项**
1. 对格式进行解析“new 接口名称(){……}”
   1. new代表创建对象的动作
   2. 接口名称就是匿名内部类需要实现哪个接口。
   3. {...}这才是匿名内部类的内容。
2. 匿名内部类，在创建对象的时候，只能使用唯一一次。如果希望多次创建对象，而且内容一样的话，必须定义实现类。
3. 用匿名内部类创建匿名对象，并运行方法,注意分号。
	```java
	pubic class Demo{
		public static void main(String[] args){
			new MyInterface(){
				@Override
				public void method(){

				}
			}.method();
		} 
	}
	```

### 类的权限修饰符

1. 外部类，可写 public/(default)
   1. 因为外部类的上一级是包，所以外部类的作用域有两个，同一个包或者不同包，`public`修饰符表示所有包下的类都可以访问；`(default)`修饰符表示仅在同一个包下的类可以访问。访问指的是可以`import`，即在其他的类中写导包语句和创建对象。(default)修饰外部类，其他包的类内连导包语句都没法写。
2. 成员内部类，可写 public/protected/(default)/private
3. 局部内部类，什么都不写，功能和（default）不同

成员内部类的不同权限修饰符的作用如下（类似成员变量）：

1. private: Java语言中对访问权限限制的最窄的修饰符，一般称之为“私有的”。被其修饰的类、属性以及方法只能被该类的对象访问，其子类不能访问，更不能允许跨包访问。
2. default：即不加任何访问修饰符，通常称为“默认访问模式“。该模式下，只允许在同一个包中进行访问。
3. protect: 介于public 和 private 之间的一种访问修饰符，一般称之为“保护形”。被其修饰的类、属性以及方法只能被类本身的方法及子类访问，即使子类在不同的包中也可以访问。
4. public： Java语言中访问限制最宽的修饰符，一般称之为“公共的”。被其修饰的类、属性以及方法不仅可以跨类访问，而且允许跨包（package）访问。

### 其他成员变量类型

#### 类作为成员变量类型

```java
public class Weapon{
	String name;
	public Weapon(){};
	public Weapon(String name){
		this.name = name;
	}
	public void setName(String name){
		this.name = name;
	}
	public String getName(){
		return name;
	}
}

public class Hero{
	Weapon weapon;
	public Hero(){
	}
	public Hero(Weapon weapon){
		this.weapon = weapon;
	}
	public void setWeapon(Weapon weapon){
		this.weapon = weapon;
	}
	public Weapon getWeapon(){
		return weapon;
	}
}

public class Demo{
	public static void main(String[] args){
		Hero hero = new Hero(new Weapon("多兰剑"));
	}
}
```

#### 接口作为成员变量类型

```java
public interface Skill{
	void use();
	//抽象方法，接口的抽象方法可以省略`public abstract`
}

public class InterfaceImpl implements Skill{
	@Override
	void use(){

	}
}

public class Hero{
	Skill skill;//英雄的技能
	public Hero(){}
	public Hero(Skill skill){
		this.skill = skill;
	}
}

public class Demo{
	public static void main(String[] args){
		//使用单独定义的实现类
		Hero hero= new Hero(new InterfaceImpl());
		hero.skill.use();

		//使用匿名内部类
		Skill skill = new Skill(){
			@Override
			public void use(){
			}	
		};
		Hero hero = new Hero(skill);

		//使用匿名内部类及匿名对象
		Hero hero = new Hero(new Skill(){
			@Override
			public void use(){

			}
		});
	}
}
```