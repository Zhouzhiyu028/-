01Java入门

## 一、Java发展史

### 1、Java是sun公司的产品

sun公司曾经收购了mysql

不过，sun公司被oracle收购了。

### 2、Java之父

James gosling

高司令

### 3、Java开发平台

JavaSe   java标准版开发平台

JavaEe   java企业级开发平台（javaSe+web开发组件servlet==）

JavaMe   java嵌入式开发平台

### 4、javaSe版本

jdk1.0    --   jdk1.5（java5.0）--  jdk8（主流） --jdk16



### 5、javaEe版本

servlet1.x   --  servlet2.x   --servlet3.x（主流）



## 二、jdk的安装

### 1、下载

https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html

注意：操作系统的版本和字长

### 2、安装和配置

（1）jdk安装

java开发工具，核心是编译器。

（2）jre安装

java运行环境，核心是JVM。

（3）配置jdk的环境变量

只需配置jdk的bin目录到操作系统的**Path**环境变量下。

**java_home**配置史jdk根目录。

**classpath**系统类库的路径。



classpath不配也行。



（4）检测

java  -version

检测安装是否正确

javac

检测环境变量是否正确



### 3、jdk

Java开发工具（编译器）

你在一台电脑上使用Java开发程序，必须装jdk。



### 4、jre

Java运行环境（jvm）

你在一台电脑上运行Java程序，必须装jre。



## 三、Java的开发流程

### 1、编写源代码

```java
public   class  HelloWorld{

	public   static  void  main(String[]  args){
		
		System.out.println("hello,world!");
		System.out.println("hello,hs!");
	}
}
```



注意：

Java源代码的编写结构：类{    主方法{   可执行的代码，可以有很多行，每一行以分号结束  }   }  。

严格区别大小写。

除内容外，其他字符必须是英文字符。

注意格式的优美。

类名建议和源文件名相同，包括大小写。



### 2、编译

计算机只认识二进制。

我们需要将源代码转换成字节码，这个过程叫编译。

使用jdk的javac编译器完成。



第一步，在命令行中，将当前目录切换到源文件所在的目录。

使用cd命令。

第二步，执行javac   源文件名（*.java）



结果说明：

如果没有信息提示，说明编译成功，生成：类名.class

如果报错，先解决语法错误，再次重新编译。

编译时，文件名不区别大小写。

### 3、运行

运行的是字节码文件*.class



第一步，在命令行中，将当前目录切换到字节码文件所在的目录。

使用cd命令。

第二步，执行  java  类名



首先找到类名.class文件，

然后再文件中找到这个类，

然后找到该类中的主方法，

最后执行主方法中的代码。



运行时，类名区别大小写。



## 四、安装idea

### 1、下载

https://www.jetbrains.com/idea/



### 2、安装

https://zhuanlan.zhihu.com/p/452274376



### 3、使用

（1）创建项目

new  Project

（2）界面使用介绍

![image-20220110151200383](JavaSE笔记.assets/image-20220110151200383.png)



## 五、Java的跨平台

### 1、跨平台性

一次编译，处处运行。



### 2、原因

Java代码是运行在jvm上的。

不同的操作系统存在差异。

jvm运行字节码时，会将字节码转为当前操作系统能够正确识别的机器码。



jdk为不同的操作系统提供了不同的jvm，下载时有系统版本对应。



## 六、注释

### 1、注释作用

在Java代码中添加说明文字，但是不执行。



### 2、分类

（1）单行注释       //开头

方法体内

（2）多行注释      /*    多行注释信息 */

方法体内

（3）文档注释     /**   多行文档注释信息  */

用于类前或方法前

# 02Java基础语法

## 一、标识符规范

### 1、通俗的说就是给各种事物起名字的符号。

专业的说就是有效的字符序列。

常见的标识符：文件名、项目名、类名、方法名、变量名，参数名==。



### 2、语法规范

只能使用英文字母、数字、下划线_、美元符号$构成，且不能以数字开头。

不能使用关键字和保留字。

严格区别大小写。

长度没有限制。



### 3、行业要求：

（1）望文生义

（2）驼峰命名法

如果有多个单词构成一个标识符，从第二个单词起首字母大写。

studentCount

除了类名，类名所有单词首字母大写。

Student

除了常量，所有字母都大写。

PI

### 4、判断是否合法：

this    This   class   Class    123    "1 2"    _123   $123   a1



### 3、关键字和保留字

Java是区别大小写的，关键字和保留字是清一色小写。

只要有一个字母大写，就不是关键字或保留字。

![image-20210816012306348](02基础语法插图\image-20210816012306348.png)

关键字：在语法中有特殊的用途。

保留字：还没有具体的用途，留作以后成为关键字。const，goto。



## 二、数据类型和变量

### 1、变量

（1）概念

变量是Java语言中，用于存储数据的容器。

变量中存储的数据是可以修改的。

（2）变量的声明

创建一个变量容器

语法：

数据类型   变量名;

比如：

int   a;

double  b;

char    c;

boolean   d;

String  s;



(3)变量的赋值

给变量容器中存放数据。

语法：

变量名=数据；

比如：

a=4;

b=2.5;

c='y';

d=true;

d=false;

s="abcdd";



（4）变量的使用

存的目的是，在后面的程序中使用。

直接使用变量名获取即可。

比如：

System.out.println(a+b);

System.out.println("a"+"b");



(5)简写形式

int   a=4;

int   b=4;

int   a=4,b=4;

int   a=b=4;  //错误

int  a,b=4;   //没错，只是b=4，a没有赋值。





（6）注意

代码是按照顺序执行的，从上往下，从左往右，一条一条执行。

变量必须先声明，然后才能赋值，最后才能参与各种操作或运算。



案例：

```java
		byte   a=1;
        short  b=2;
        int    c=3;
        long   d=4L;

        float   f=1.0f;
        double  g=2.0;

        char   ch='a';
        boolean   bl=true;

        String   str="abcdefg";


        System.out.println(a);
        System.out.println(b);
        System.out.println(c);
        System.out.println(d);
        System.out.println(f);
        System.out.println(g);
        System.out.println(ch);
        System.out.println(bl);
        System.out.println(str);


        b=34;
        System.out.println(b);

        b=35;
        System.out.println(b);
```



### 2、数据类型

（1）分为两大类：

基本数据类型和引用数据类型。

![QQ图片20220110164917](JavaSE笔记.assets/QQ图片20220110164917.png)

![QQ图片20220110164830](JavaSE笔记.assets/QQ图片20220110164830.png)

（2）基本数据类型

byte   字节整型，存储容量为1字节=8个二进制位bit，包含的整数范围：-128~+127。

short  短整型，存储容量为2个字节=16位，包含的整数范围：-2的（16-1）次方~2的（16-1）次方-1

int      整型，存储容量为4个字节=32位，包含的整数范围：-2的（32-1）次方~2的（32-1）次方-1

long    长整型，存储容量为8个字节=64位，包含的整数范围：-2的（64-1）次方~2的（64-1）次方-1

​			long类型的整数如果超出了int的范围，必须后面加“l”或“L”。



float      单精度浮点数，存储容量4个字节，最大能够精确小数位为7或8位。小数后面必须加“f”或“F”。

double  双精度浮点数，存储容量8个字节，最大能够精确小数位位15或16位。



char       字符类型，存储容量2个字节，有且仅能存储一个符号。数据必须使用单引号包括起来。比如'a'       '  '

boolean 布尔类型,存储容量1位，只有两个值：true和false。



（3）引用数据类型

分为：数组、类、接口。

类类型：String字符串类型，数据必须使用双引号引起来，比如“”      “abcdefg”。





### 3、二进制和十进制转换

```
二进制：
逢二进一，每一位上是0或1.

十进制：
逢十进一，每一位上是0-9.

八进制：
逢八进一，每一位上是0-7.


十六进制：
逢16进一，每一位上是0-F。

```

（1）整数部分

二进制和十进制整数部分，可以完全相等转换。

![image-20210816012413817](02基础语法插图\image-20210816012413817.png)

（2）小数部分

二进制和十进制小数部分，不一定完全相等转换。

导致丢失精度。

![image-20210816012632158](02基础语法插图\image-20210816012632158.png)

（3）解决方案

小数使用BigDecimal，解决容量和精度

整数使用BigInteger，解决容量





## 三、变量的作用范围

一个变量从声明到所在的语句组结束，称为变量的作用范围，也叫作用域。

当作用范围的代码执行完毕，变量被销毁，后面的代码就访问不到了。



```java
public class VarScope {
    public static void main(String[] args) {

        int  a=4;

        {
            int  b=5;
            System.out.println(a);
            System.out.println(b);
        }

        System.out.println(a);
        //System.out.println(b); 

    }
}

```

如果两个变量作用域有交集，不能重名！！！！！

如果两个变量的作用域没有交集，可以重名。





## 四、类型转换

变量的赋值：

​	变量名=值；

语法要求：

​	值的类型必须和变量的类型一致。



如果值的类型和变量的类型不一致，需要先转换类型才能赋值。

有两种方式：

### 1、自动类型转换

小类型的数据转为大类型的数据，系统自动完成。

必须有依据：byte、short、char自动提升成int，整数转小数，int和char之间（ascii表）。

### 2、强制类型转换

大类型的数据转为小类型的数据，需要手动完成。

语法：(你想要的类型)数据

注意：丢失精度。



### 3、类型转换的目的

保证赋值的类型语法约束要求。



```java
//        自动类型转换，系统帮我们将int的10转为了double的10.0
        double  d=10;
        float   f=10f;

        long    l=10l;
        float   f2=l;
        double  d2=l;

        byte   b=10;
        int    i2=b;

        char  c=97;
        int   i3=c;

//        强制类型转换：手动完成
//        将double的2.0转为int的2
        int   i=(int)2.0;

        long  ll=10;
        int   ii=(int)ll;
```





## 五、运算符

运算符是有优先级的，先算优先级高的，再算优先级低的，同级别从左往右算。

### 1、算术运算符

```java
+    -    *     /    %
+    -
++   --
+
```

如果参与运算全是整数，结果是整数；如果有小数，结果是小数。

```java
//        算数运算符+ - *  /  %
        int   a=10;
        int   b=4;
        System.out.println(a+b);
        System.out.println(a-b);
        System.out.println(a*b);
        System.out.println(a/b);
        System.out.println(a%b);

        double  c=4.0;
        System.out.println(a+c);
        System.out.println(a-c);
        System.out.println(a*c);
        System.out.println(a/c);
        System.out.println(a%c);

        double  d=13.5;
        System.out.println(d+c);
        System.out.println(d-c);
        System.out.println(d*c);
        System.out.println(d/c);
        System.out.println(d%c);

//        正号和负号
        System.out.println(+c);
        System.out.println(-c);

//        前++   和  后++  区别：优先级不同
        int   e=3;
        //e++;  //e=e+1;
//        ++e;    //e=e+1;
//        System.out.println(e);

//        int   f=e++;
        int  f=++e;
        System.out.println(e);
        System.out.println(f);


//      +用于字符串的拼接
        String   s1="aaaa";
        String  s2="bbbb";
        System.out.println(s1+s2);

        System.out.println(s1+a+b);
        System.out.println(a+b+s1);

//        char
        System.out.println('a'+16);
```

### 2、赋值运算符

```java
=    +=   -=   *=   /=   %=
```

```java
        int  a=10;
        int  b=20;

        a+=b;  //a=a+b;
        a-=b;  //a=a-b;
        a*=b;  //a=a*b;
        a/=b;  //a=a/b;
        a%=b;   //a=a%b;


        System.out.println(a);
        System.out.println(b);

        byte  b1=1;
//        short  s1+=b1;   //s1=s1+b1;
        short   s1=1;
//        s1+=1;   //s1=s1+1;
//        s1=s1+1;   //1是int    short+int=int
        System.out.println(s1);
```



### 3、比较运算符

用于比较大小或是否相等。

大小主要用于数字的比较，相等可以用于所有数据。

```
>    >=   <   <=     

==   !=
```

注意：比较的结果是boolean。

```
System.out.println(10>=9);        System.out.println(10<=9);        System.out.println(10==9);        System.out.println(10!=9);
```



### 4、逻辑运算符

多个boolean条件的逻辑结果。

```
&&    ||   ！
&     |
```

注意：运算结果也是boolean。

```java
//        同时为真，结果为真；否则为假。        				System.out.println( 10<=9&7<=9 );   //false&&true=false        
		System.out.println( 10<=9&&7<=9 );  //false
//       同时为假，结果为假；否则为真。        				System.out.println(10<=9|7<=9);        				System.out.println(10<=9||7<=9);
//        逻辑非，真变假，假变真        						System.out.println(!(10>=9));
//        错误的写法        
		int  m=1,n=2,k=3;
//        System.out.println(k>n>m);//k>n  = true     	  true>m  不能比较        									System.out.println(k>n&&n>m);
```



### 5、三目运算符

（boolean条件）?语句1:语句2

条件为true，执行语句1；

条件为false，执行语句2.



运算结果：可以是各种类型。

```java
  System.out.println(   (7<9)?7:9     );
```

# 03流程控制语句

## 一、程序的执行流程

### 1、顺序结构

默认，从上往下，从左往右，一条语句一条语句的执行。

### 2、选择结构（分支结构）

if语句

switch语句

### 3、循环结构

for

while

do  while



## 二、选择结构的语句

选择结构，也叫分支结构。

使用场景：

当一件事情，有多种可能发生的情况，但是每次只能发生一种情况。

到底发送哪种情况，根据条件来选择。

### 1、if语句

#### （1）单分支

一个条件，一种情况。

语法：

if(boolean条件){

​	//当条件为true时要执行的语句组。

}

执行流程：

先执行条件；

条件为true，执行语句组，然后结束if。

条件为false，直接结束if。

![image-20210720150804865](03流程控制语句.assets/image-20210720150804865.png)

```java
System.out.println("begin---");

        int   week=7;
        if(week==7){
            System.out.println("明天休息");
        }

        System.out.println("end---");
```



#### （2）双分支

一个条件，两种情况。

语法：

if(boolean条件){

​	//当条件为true时要执行的语句组1。

}else{

​	//当条件为false时要执行的语句组2。

}

执行流程：

先执行条件；

条件为true，执行语句组1，然后结束if。

条件为false，执行语句组2，然后结束if。

![image-20210720150848975](03流程控制语句.assets/image-20210720150848975.png)

```java
System.out.println("begin---");

        int   week=2;
        if(week==7){
            System.out.println("明天休息");
        }else{
            System.out.println("继续学习");
        }

        System.out.println("end---");
```





#### （3）多分支

n-1个条件，n种情况。

语法：

if(boolean条件1){

​	//当条件为true时要执行的语句组1。

}else if(条件2){

​	//当条件2为true时要执行的语句组2。

}else  if ....

....

else  if(条件n-1){

​	//当条件n-1为true时要执行的语句组n-1。

}else{

​	//当以上条件都不成立，执行语句组n。

}

执行流程：

先执行条件1；

条件1为true，执行语句组1，然后结束if。

条件1为false，执行条件2。

条件2为true，执行语句组2，然后结束if。

条件2为false，执行条件3。

.....

条件n-1为true，执行语句组n-1，然后结束if。

条件n-1为false，执行语句组n。



![image-20210720151206899](03流程控制语句.assets/image-20210720151206899.png)

```java
System.out.println("begin---");

        int   week=7;

        if(week==1){
            System.out.println("体能课");
        }else if(week==2){
            System.out.println("舞蹈课");
        }else  if(week==3){
            System.out.println("书法课");
        }else  if(week==4){
            System.out.println("美术课");
        }else  if(week==5){
            System.out.println("篮球课");
        }else  if(week==6){
            System.out.println("英语课+舞蹈课+逻辑思维课");
        }else{
            System.out.println("语言课");
        }

        System.out.println("end---");
```



### 2、switch语句

语法：

switch（表达式）{

​	case    常量表达式1：

​					语句组1；

​					[break;]

​	case    常量表达式2：

​					语句组2；

​					[break;]

​	。。。

​	case    常量表达式n-1：

​					语句组n-1；

​					[break;]



​	default:

​				语句组n;

}

强调：switch表达式只能返回byte、short、char、int、String类型。



执行流程：

​		先执行switch的表达式；

然后执行第一个case。

如果表达式的结果和常量表达式1相等，那么执行语句组1.

如果表达式的结果和常量表达式1不相等，执行下一个case。

。。。

如果以上都不匹配，执行缺省语句组。

```java
System.out.println("begin--");
        Scanner  sc=new Scanner(System.in);
        int  week=sc.nextInt();

        switch (week){
            case   1:
                System.out.println("今天星期一，我要上学");
                break;
            case   2:
                System.out.println("今天星期二，我要打游戏");
                break;
            case   3:
                System.out.println("今天星期三，我要上班");
                break;
            case   4:
                System.out.println("今天星期四，我要考试");
                break;
            case   5:
                System.out.println("今天星期五，我要按摩");
                break;
            case   6:
                System.out.println("今天星期六，我要洗脚");
                break;
            case   7:
                System.out.println("今天星期日，我要钓鱼");
                break;

            default:
                System.out.println("你输的星期对！！");
        }

        System.out.println("end----");
```



关于没有break的问题。

如果语句组中没有执行break，那么程序会向下执行下一个语句组，直到遇到break或后面的语句组全部执行完毕，结束switch。

```java
System.out.println("begin--");
        Scanner  sc=new Scanner(System.in);
        int  week=sc.nextInt();

        switch (week){
            case   1:
                System.out.println("今天星期一，我要上学");
                break;
            case   2:
                System.out.println("今天星期二，我要打游戏");
                break;
            case   3:
                System.out.println("今天星期三，我要上班");
                break;
            case   4:
                System.out.println("今天星期四，我要考试");
                //break;
            case   5:
                System.out.println("今天星期五，我要按摩");
                //break;
            case   6:
                System.out.println("今天星期六，我要洗脚");
                //break;
            case   7:
                System.out.println("今天星期日，我要钓鱼");
               // break;

            default:
                System.out.println("你输的星期对！！");
        }

        System.out.println("end----");
```



switch使用场景：

只能用于条件中的值是可以枚举的。





## 三、循环结构的语句

使用场景：

重复的操作，要执行多遍。

### 1、for

语法：

for(初始化表达式;boolean条件;迭代语句){

​	//循环体：定义重复的操作，只需定义一遍。

}



执行流程：

先执行初始化表达式；

然后执行boolean条件；

如果条件为true，执行循环体，然后执行迭代语句；

然后执行boolean条件；

如果条件为true，执行循环体，然后执行迭代语句；

。。。。

直到boolean条件为false，结束for。

![image-20210720161932315](03流程控制语句.assets/image-20210720161932315.png)



```
 System.out.println("begin---");

        for(int  i=1;i<=100;i++){
            System.out.println("我再也不迟到了"+i);
        }

        System.out.println("end----");
```





### 2、while

语法：

while（boolean条件）{

​	//循环体

}



执行流程：

先执行条件；

条件为true，执行循环体，然后在执行条件。。。。。

一直到条件为false，结束while。

![image-20210720170636087](03流程控制语句.assets/image-20210720170636087.png)

```
System.out.println("begin---");

        int  i=1;
        while(i<=100) {
            System.out.println("我再也不迟到了" + i);
            i++;
        }

        System.out.println("end----");
```



### 3、do  while

语法：

do{

​	//循环体

}while(boolean条件);



执行流程：

先执行循环体；

然后执行条件，条件为true，在执行循环体，然后在执行条件。。。。。

一直到条件为false，结束do  while。

![image-20210720172107557](03流程控制语句.assets/image-20210720172107557.png)

注意：do  while 至少执行一次。

​			如果大于0次的情况，（前提：条件和循环体相同）三种循环语句执行的结果是一样的。



```
System.out.println("begin---");

        int  i=1;

        do{
            System.out.println("我再也不迟到了" + i);
            i++;
        }
        while(i<=100);

        System.out.println("end----");
```



## 四、流程跳转语句

### 1、break

用于循环体中；还能用于switch语句中。



用于循环体中:break表示结束当前循环语句。

```java
	for(int  i=1;i<=10;i++){            
        if(i==5){                
            break;            
        }            
        System.out.println("i  like  java "+i);        		}
```



用在switch语句中，表示结束switch。

```
 		Scanner  sc=new Scanner(System.in);        			int  week=sc.nextInt();        
 		
 		switch (week){            
 		case   1:                								System.out.println("今天星期一，我要上学");               break;            
 		case   2:                								System.out.println("今天星期二，我要打游戏");             break;            
 		case   3:                								System.out.println("今天星期三，我要上班");               break;            
 		case   4:                								System.out.println("今天星期四，我要考试");               break;            
 		case   5:                								System.out.println("今天星期五，我要按摩");               break;            
 		case   6:                								System.out.println("今天星期六，我要洗脚");               break;            
 		case   7:                								System.out.println("今天星期日，我要钓鱼");               break;            
 		default:                
 			System.out.println("你输的星期不对！！");        }
```



### 2、continue

只能用于循环体中。



用于循环体中:continue表示当前循环的本次循环，然后进入下一次循环。

```
 for(int  i=1;i<=10;i++){            
 			if(i==5){                
 				continue;            
 			}            
 			System.out.println("i  like  java "+i);        	  }
```



# 04数组

## 一、数据类型

### 1、基本数据类型

byte   short  int  long 

float  double

char

boolean

### 2、引用数据类型

数组

类：String字符串，枚举

接口



## 二、数组

### 1、数组是什么？

数据类型角度：数组是一种引用数据类型。

容器角度：数组是用来保存一组数据的容器。



我们之前的变量基本上都是基本数据类型的，每个变量只能存储一个值。



### 2、数组的特点

（1）数组中的数据可以是任何类型。

（2）一组数据必须类型相同。

（3）数组的长度，固定不变。





### 3、数组的存储原理

![image-20210723104815799](04数组.assets/image-20210723104815799.png)

数组是一种存储数据的数据结构。

数组创建时，需要先确定其长度。

然后根据长度来划分元素空间。

每个元素中可以放一条数据。



元素的表示：数组名[下标]





## 三、数组的使用

![image-20220113105910094](JavaSE笔记.assets/image-20220113105910094.png)

### 1、声明数组

创建一个数组类型的变量。

语法：

元素的类型[]    数组名；

强调：数组名其实就是变量名！！



```
//        1/声明数组：创建一个数组类型的变量
//       使用数组类型声明，表示该变量中存储的是一个数组对象（容器）
        String[]   names;
```



### 2、创建数组

语法：

new    元素的类型[长度];



```
//        2、创建数组：创建一个数组类型的对象（容器）
//        下标0-4
        names=new   String[5];
```



![image-20210723110959260](04数组.assets/image-20210723110959260.png)

### 3、元素赋值

数组名[下标]=数据；

元素的下标范围：0~长度-1

```
//        3、赋值
        names[0]="张三";
        names[1]="李四";
        names[2]="王五";
        names[3]="马六";
        names[4]="路人甲";
```

![image-20210723111233051](04数组.assets/image-20210723111233051.png)

### 4、元素使用

数组名[下标]

```
//        4\使用数据
        System.out.println(names[0]);
        System.out.println(names[1]);
        System.out.println(names[2]);
        System.out.println(names[3]);
        System.out.println(names[4]);
```



### 5、数组的遍历

获取数组的长度：数组名.length



for(int  i=0;i<数据名.length;i++){

​	System.out.println(数据名[i]);

}



```
//        5、数组的遍历
        for (int i = 0; i < names.length; i++) {
            System.out.println(names[i]);
        }
```





## 三、数组元素的缺省值

### 1、基本类型

byte  short  int  long      0

float   double                  0.0

char                                  单个空白字符

boolean                           false



### 2、引用类型

所有引用类型的元素缺省值全是null





## 四、数组下标越界

### 1、下标

始终是从0开始，一直到（长度-1）



### 2、越界

```
public class ArrayDemo03 {
    public static void main(String[] args) {

        int[]  ages=new  int[5];
        ages[5]=5;
        System.out.println(ages[9]);

    }
}

```



运行时错误提示：

```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 5
	at ArrayDemo03.main(ArrayDemo03.java:5)
```





## 五、空指针问题

```
int[]   a=null;
System.out.println(a[0]);
```





运行时错误提示：

```
Exception in thread "main" java.lang.NullPointerException	
	at ArrayDemo04.main(ArrayDemo04.java:5)
```



没有new 就没有对象。



没有创建数组对象。

没有数组对象，就没有元素，没有元素就没有数据。





## 六、简写形式

```
       int[]  a;        
       a=new  int[3];        
       a[0]=0;        
       a[1]=1;        
       a[2]=2;  
       
       int[]   a2=new  int[3];        
       a2[0]=0;        
       a2[1]=1;        
       a2[2]=2;   
       
       int[]   a3=new   int[]{0,1,2};        
       
       int[]   a4={0,1,2};
```





## 七、排序

### 1、冒泡排序

相邻元素进行比较，按照排序规则排列。

![image-20210723145722325](04数组.assets/image-20210723145722325.png)



```java
public class MaoPao {


    public static void main(String[] args) {
//      由小到大
        int[]   a={3,5,4,1,2};

        //排a.length-1编
//        for (int i = 1; i < a.length; i++) {
//            //每一遍需要比较a.length-i次
//            for(int  j=0;j<a.length-i;j++){
//                //每一次比较
//                if(a[j] > a[j+1]){
//                    //交换
//                    int  temp=a[j];
//                    a[j]=a[j+1];
//                    a[j+1]=temp;
//                }
//            }
//
//        }

        //排a.length-1编
        for(int  i=0;i<a.length-1;i++){
            //一遍需要比较a.length-i-1次
            for(int  j=0;j<a.length-i-1;j++){
                //每一次比较
                if(a[j] > a[j+1]){
                    //交换
                    int  temp=a[j];
                    a[j]=a[j+1];
                    a[j+1]=temp;
                }
            }
        }


        //遍历
        for (int i = 0; i < a.length; i++) {
            System.out.println(a[i]);
        }


    }
}
```



### 2、选择排序

拿每一个元素和后面所有元素比较。

![image-20210723155413715](04数组.assets/image-20210723155413715.png)



```java
public class XuanZe {

    public static void main(String[] args) {
//       由小到大
        int[]   a={3,5,4,1,2};

        //排a.length-1遍
        for (int i = 0; i < a.length-1; i++) {
            //每一遍，比较a.length-i-1次
//            a[i]和后面的进行比较
            for(int  j=i+1;j<a.length;j++){
                //比较
                if(a[i] >  a[j]){
                    int  temp=a[i];
                    a[i]=a[j];
                    a[j]=temp;
                }
            }
        }
        
//        遍历排序结果
        for (int i = 0; i < a.length; i++) {
            System.out.println(a[i]);
        }

    }

}
```



### 3、快速排序

分治法。

选择一个基准元素，然后进行分区，左边区域中的元素都基准元素小，右边元素都比基准元素大。

然后在对每一个区进行分区。

直到区中只有一个元素。

### 4、插入排序

依次拿每一元素（第二个开始，基准元素），和前面所有元素比较，符合规则的前面元素后移，不符合规则插入基准元素。

### 5、哈希排序

### 6、堆排序

### 7、桶排序

### 8、归并排序



## 八、方法的递归使用

### 1、方法的使用

```
public class MethodDemo {

    /**
     * 程序执行的入口
     * @param args
     */
    public static void main(String[] args) {
        System.out.println("begin");
//        调用方法
        test1(10,20);
        test1(30,40);

        System.out.println("end");
    }

    /**
     * 普通方法
     * 1、方法概念
     * 有名字的语句组。
     *2、方法作用
     * 解决问题的过程。
     * 一般，一个方法解决一个问题。
     * 3、方法的定义
     * 修饰符   返回值类型    方法名([参数列表]){
     *
     *     //方法体
     * }
     *
     * 参数：类型  参数名
     * 多个参数逗号分割
     *
     * 4\方法的调用
     * 方法名([传入数据]);
     * 调用方法时，小括号不能省；
     * 调用的方法执行完毕，调用语句才结束；
     * 如果有参数必须传参，数据的数量、类型、顺序必须和参数的定义一致
     * 如果没有参数，必须不传。
     *
     * 5、建议定义static方法
     * 方便在main方法中调用；
     *
     *
     * 6、方法的返回值
     * （1）无返回值
     * void
     * （2）有返回值
     * 使用返回的数据的类型
     *
     */
    public static  void   test1(int  a,int  c){
        System.out.println(a);
        System.out.println(c);
        int  b=12;
        System.out.println(b);
        System.out.println(111);
        System.out.println(222);
        System.out.println(333);
    }

    public   static   int  test2(){
        return  2;
    }






}
```



### 2、方法的递归

```
public class DiguiDemo {

    /**
     * 方法的递归：
     * 在一个方法中，调用自己
     * @param i
     */
    public static  void  test1(int  i){
        System.out.println(i);
        if(i==1){
            return;
        }

        i--;
        test1(i);
    }

    public static void main(String[] args) {
        test1(5);


        //递归调用执行流程：
        /*
        test1(5){
            5
            test1(4){
                4
                test1(3){
                    3
                    test1(2){
                        2
                        test1(1){
                            1
                            return;
                        }
                    }
                }

            }

        }
         */


    }
}
```





### 3、快速排序

![这里写图片描述](https://img-blog.csdn.net/20150810110155861)



代码实现：

```
package lx01;

/**
 * 有一个数组，使用快速排序完成由小到大排列。
 */
public class Lx08 {

    /**
     * 快速排序：
     * 采用"分治法"进行排序。
     *
     * 5,8,9,7,1,2,6,4,3,0
     * 过程：
     * 第一遍
     *1、找一个基准值
     * 一般都是第一个元素
     * base=5
     * 2、确定高位和地位下标
     * low=0
     * height=9
     * 3、从高位下标开始查找
     * 查找比基准小的元素，找到停止。
     * 4、从低位下标开始查找
     * 查找比基准大的元素，找打停止。
     * 5、交换元素的数据
     *
     * 6、继续高位和低位查找和交换、直到重逢。
     *
     * 7、将基准值放到重逢位置
     *
     * 8、分治:递归
     * 对左边的所有元素重复1-7操作
     * 对右边的所有元素重复1-7操作
     *
     * 9、直到low=height
     *
     *
     * 5,8,9,7,1,2,6,4,3,0
     * 实操：
     * base=5
     * 0   8
     * 5  0  9  7  1  2  6  4  3  8
     * 3  9
     * 5 0 3 7 1 2 6 4 9 8
     * 4  7
     * 5 0 3 4 1 2 6 7 9 8
     * 2 重逢
     * 2 0 3 4 1 5 6 7 9 8
     *
     * 分治
     * [2 0 3 4 1 ]5[ 6 7 9 8]
     * 2 0 3 4 1
     * base=2
     * 6 7 9 8
     * base=6
     *
     */

    public static void main(String[] args) {
        int[]   a={5,8,9,7,1,2,6,4,3,0};

        quickSort(a,0,a.length-1);


        for (int a1:a){
            System.out.println(a1);
        }
    }


    public  static  void  quickSort(int[] arr,int low,int height){
        //1\结束递归
        if(low>=height){
            return;
        }

        //2\初始化
        int  i,j,base;
        i=low;
        j=height;
        base=arr[low];

        //3\查找一遍,直到重逢
        while(i<j){
            //高位查找
            while(i<j&&base<=arr[j]){
                j--;
            }

            //低位查找
            while(i<j&&base>=arr[i]){
                i++;
            }

            //交换
            if(i<j){
                int temp=arr[j];
                arr[j]=arr[i];
                arr[i]=temp;
            }

        }

        //4\交换基准数据
        arr[low]=arr[i];
        arr[i]=base;

        //5、分治
        quickSort(arr,low,i-1);
        quickSort(arr,i+1,height);

    }
}
```





## 九、二维数组

### 1、Java数组

Java没有多维数组，所有数组全是一维数组！！



### 2、二维数组

一维数组的每一个元素又是一个一维数组，我们为了和其他语言对照，习惯上称为二维数组。

![image-20210723162728368](04数组.assets/image-20210723162728368.png)

### 3、二维数组的使用

（1）声明二维数组

语法：

元素的类型[ ] [ ]      数组名;

```java
//声明数组        int[][]   aa;
```

（2）创建二维数组对象

语法：

new    元素的类型[二维数组的长度 ] [ 内部数组的长度 ];

```java
//创建数组        aa=new   int[3][4];
```

（3）赋值

数组名[二维数组的下标] [内部数组的下标]  =数据；

```java
//赋值
        aa[0][0]=100;
        aa[0][1]=101;
        aa[0][2]=102;
        aa[0][3]=103;

        aa[1][0]=110;
        aa[1][1]=111;
        aa[1][2]=112;
        aa[1][3]=113;

        aa[2][0]=120;
        aa[2][1]=121;
        aa[2][2]=122;
        aa[2][3]=123;
```





![image-20220114145053909](JavaSE笔记.assets/image-20220114145053909.png)



（4）使用

数组名[二维数组的下标] [内部数组的下标]



（5）遍历

for(int  i=0;i<二维数组名.length;i++){

​	   //二维数组名[i]

​		for(int  j=0;j<二维数组名[i].length;j++){

​				//二维数组名[i ] [j ]

​		}

}

```java
//        遍历
        System.out.println(aa.length);
        for (int i = 0; i < aa.length; i++) {
            //aa[i]又是数组
            for (int j = 0; j < aa[i].length; j++) {
                System.out.println(aa[i][j]);
            }
        }
```





## 九、内部数组长度问题（了解）

创建二维数组时，如果指定了内部数组的长度，那么每一个内部数组的长度是一样的。

如果没有指定内部数组的长度，那么每一个内部数组的长度是可以不一样。

```java
public class Array2d02 {

    public static void main(String[] args) {


        int[][]   aa;
        aa=new  int[3][];

        int[]   aa0=new  int[2];
        aa0[0]=100;
        aa0[1]=101;
        aa[0]=aa0;

        int[]   aa1=new  int[3];
        aa1[0]=110;
        aa1[1]=111;
        aa1[2]=112;
        aa[1]=aa1;

        int[]   aa2=new  int[4];
        aa2[0]=120;
        aa2[1]=121;
        aa2[2]=122;
        aa2[3]=123;
        aa[2]=aa2;



        for (int i = 0; i < aa.length; i++) {
            for (int j = 0; j < aa[i].length; j++) {
                System.out.println(aa[i][j]);
            }
        }

    }
}
```





## 十、二维数组简写形式

### 1、简写1

```java
public class Array2d03 {
    public static void main(String[] args) {

        int[][]   aa=new int[3][4];
        //赋值
        aa[0][0]=100;
        aa[0][1]=101;
        aa[0][2]=102;
        aa[0][3]=103;

        aa[1][0]=110;
        aa[1][1]=111;
        aa[1][2]=112;
        aa[1][3]=113;

        aa[2][0]=120;
        aa[2][1]=121;
        aa[2][2]=122;
        aa[2][3]=123;


    }
}
```





### 2、简写2

```java
public class Array2d04 {

    public static void main(String[] args) {
        int[][]   aa={{100,101,102,103},{110,111,112,113},{120,121,122,123}};

        for (int i = 0; i < aa.length; i++) {
            for (int j = 0; j < aa[i].length; j++) {
                System.out.println(aa[i][j]);
            }
        }
    }
}
```







## 十一、数组的执行原理

已知数组：

int[]   a={1,2,3,4,5};

获取元素的值：

a[0]

![image-20210723173039160](04数组.assets/image-20210723173039160.png)

# 05面向对象

## 一、OOP

### 1、oop

面向对象编程



### 2、oop是Java语言编程思想

这种思想指导我们程序员如何使用Java写代码。



### 3、面向对象和面向过程区别

面象过程：强调的是解决问题的步骤，直接写函数即可，直接调用函数:函数名(..)。

面向对象：强调使用对象解决问题，对象是属性和方法的综合体，使用对象名.属性名和对象名.方法名(..)。

![image-20220117094748033](JavaSE笔记.assets/image-20220117094748033.png)

### 4、oop编程

类：创建对象的模板。

对象：是类的具体化。



对象是一个独立的个体。

![image-20220117095953437](JavaSE笔记.assets/image-20220117095953437.png)

根据问题，进行分析；

通过分析，定义模板（抽象成类）；

通过类，创建对象（实例化，实例=对象）；

使用对象的属性和方法，解决问题。



### 5、oop应用

问题：

老于是一个胖子，体重200公斤。为了女朋友决定减肥，通过不懈的努力，体重将为100公斤。



分析，抽象成类：

人类{

​	属性：姓名，体重

​	方法：减肥（体重由200变成100）

}



通过类，创建对象：

new    类名（）；



通过对象，解决问题：

对象名.属性名   保存数据

对象名.方法名(..)   解决问题的过程



## 二、类的定义

### 1、语法：

[修饰符]    class   类名{

​		//定义属性:成员变量

​		[修饰符]    数据类型    属性名[=初始值];



​	  //定义方法：成员方法

​	[修饰符]   返回值类型    方法名([参数]){

​		//方法体：解决问题的过程

​	}

}



```java
//类的定义
public class Person {

//    属性的定义
    public   String  name;
    public   double  weight;

    //方法的定义
    public   void   jianfei(){
        //方法体，解决问题的过程
        weight=200;
        System.out.println(name+"开始体重为"+weight);
        weight=100;
        System.out.println("经过不懈的努力，体重减为"+weight);

    }

}

```





## 三、创建对象

### 1、语法：

类名   对象名=new  类名();

int[]   数组名=new  int[4];

```
//主方法：程序执行的入口
    public static void main(String[] args) {
        Person p=new   Person();
        Person p2=new   Person();



    }
```

每new一次，都会产生一个新对象，在堆内存中存储。



### 2、原理

jvm先加载类的信息到内存的方法区中。

在堆内存中开发空间，保存对象的信息。

然后以类为模板创建对象，类中有哪些属性和方法，就会给对象添加那些属性和方法。



![image-20210726112118822](05面向对象.assets/image-20210726112118822.png)

![image-20210726113108488](05面向对象.assets/image-20210726113108488.png)



## 四、使用对象

### 1、语法：

对象名.属性名

对象名.方法名(..)

```
		p.name="老于";
        p.weight=200;

        p.jianfei();

        p2.name="老王";
        p2.weight=300;

        p2.jianfei();
```



### 2、原理

 p.jianfei();



通过p中保存的首地址，找到对应的堆内存中的对象。

然后，找到该对象中的属性和方法；

最后执行属性和方法体。

![image-20220117105621430](JavaSE笔记.assets/image-20220117105621430.png)



## 五、基本类型和引用类型

### 1、基本数据类型

基本类型的变量存储是单一值。



### 2、引用数据类型

引用类型的变量中存储的是对象的首地址。



数组：数组对象内部分为若干元素，每个元素可以存储一条数据。

​			数组名.length，length并不是属性，length是计数器中记录数组的长度。

类：类类型的对象内部分为属性和方法。

接口：在类类型的基础上，会向上转型。



## 六、变量

### 1、变量

Java中用于存储数据的容器。

变量的特点：存储的数据是可以变化（修改）。



### 2、变量的分类

Java语言中，变量分为局部变量和成员变量（对象的属性）。



局部变量：声明在方法体内的变量。不属于任何对象。

成员变量：声明在类中，方法体外的变量。是对象的属性。



### 3、局部变量和成员变量的区别

（1）声明的位置

局部变量：声明在方法体内的变量。

成员变量：声明在类中，方法体外的变量。

（2）作用范围

局部变量：只能用于声明它的方法体内，其他方法体无法访问。

成员变量：可以作用于当前类的所有方法体内。

（3）缺省值

成员变量：有缺省值。

​				byte  short   int   long    0

​				float   double    0.0

​				char    空白字符

​				boolean   false

​				引用类型      null

局部变量：没有缺省值。



null的含义：null是一种引用类型的数据，表示没有对象的地址！！！

（4）修饰符

成员变量：可以使用任何修饰符修饰。（public   protected  private  不写）  static   final   ==

局部变量：只能使用final。

（5）重名问题

局部变量（或参数）之间如果作用范围有交集，不能重名；

成员变量之间如果作用范围有交集，不能重名；

成员变量和局部变量（或参数）是可以重名的！！



```java
public class Person2 {
    public   String  a;
    public   double  b;
    public   int     c;
    public    char   d;
    public    boolean   e;

    public static void main(String[] args) {
        Person2   pp=new Person2();
        System.out.println(pp.a);
        System.out.println(pp.b);
        System.out.println(pp.c);
        System.out.println(pp.d);
        System.out.println(pp.e);

        final int  f=10;
    }
}
```



## 七、方法参数



### 1、语法

[修饰符]   返回值类型    方法名([参数]){

​		//方法体：解决问题的过程

​	}





### 2、方法的作用和调用

（1）作用

所谓方法，就是一个有名字的语句组。

方法体，解决问题的过程。



（2）调用

我们可以通过对象名.方法名(..)调用某个方法。

调用方法，就是执行方法体中的代码。执行完毕，方法的调用语句结束。





### 3、方法的参数

（1）作用

可以根据用户的需要，每次调用方法时，都可以向方法体内传入变化的数据。



（2）参数定义

参数定义在方法名后小括号中。

一个方法，可以定义0到多个参数。

每一个参数：数据类型    参数名 ， 多个参数中间使用逗号分隔。



（3）传参

方法调用时，在小括号中给对应的参数赋值。不能使用=号符号。

调用一个方法时，方法有参数，有几个参数就必须传几个值，并且类型和顺序一致。



传入的数据：实参。

定义的参数：形参。



```
//类的定义
public class Person {

//    属性的定义
    public   String  name;
    public   double  weight;

    //方法的定义
    public   void   jianfei(){
        //方法体，解决问题的过程
        System.out.println(name+"开始体重为"+weight);
        weight=100;
        System.out.println("经过不懈的努力，体重减为"+weight);

    }

    public   void   jianfei(double   w,int  a){
        //方法体，解决问题的过程
        System.out.println(name+"开始体重为"+weight);
        weight=w;
        System.out.println("经过不懈的努力，体重减为"+weight);

    }

    //主方法：程序执行的入口
    public static void main(String[] args) {
        Person p=new   Person();
        Person p2=new   Person();

        p.name="老于";
        p.weight=200;
        p.jianfei();

        p2.name="老王";
        p2.weight=300;
        p2.jianfei();

        p2.jianfei(80,10);
        p2.jianfei(90,20);

    }

}

```

### 4、属性和参数的区别

属性：对象的数据。随对象长久存在

参数：方法体内的数据。方法调用时存在，执行完毕销毁。临时的局部变量。





## 八、方法的重载overload

### 1、定义

在同一个类中，多个方法的方法名相同但是参数必须不同的现象。



### 2、参数不同的情况：

（1）参数个数不同

（2）参数个数相同：对应顺序的类型至少有一个不同。

参数名不能作为判断的依据，因为调用时跟参数名无关！！



### 3、案例

```
public class JiSuanQi {

    public  void   jia(int  a,int  b){
        System.out.println(11);
        System.out.println(a+b);
    }

    public   void  jia(double  a,double  b){
        System.out.println(22);
        System.out.println(a+b);
    }

//    public   void  jia(double  c,double  d){
//        System.out.println(d+c);
//    }

    public   void   jia(double   a,int  b){
        System.out.println(33);
        System.out.println(a+b);
    }

    public   void   jia(int  a,double  b){
        System.out.println(44);
        System.out.println(a+b);
    }

    public   void  jia(int  a,int  b,int  c){
        System.out.println(55);
        System.out.println(a+b+c);
    }

    public  void   jian(double   a,double  b){
        System.out.println(a-b);
    }


    public static void main(String[] args) {
        JiSuanQi   jsq=new JiSuanQi();
        jsq.jia(10,20);
        jsq.jia(10.0,20.0);
        jsq.jia(10,20.0);
        jsq.jia(10.0,20);
        jsq.jia(10,20,30);

        jsq.jian(10,20);
    }
}

```



## 九、方法的返回值类型

### 1、返回值

方法调用结束时，向外输出一条数据。这条数据就叫返回值。

调用后，返回值可以在后面的程序中使用。

### 2、无返回值类型

不返回数据。

使用关键字void表示。

### 3、有返回值类型

使用具体的数据类型表示。

一旦定义了一个方法有返回值，这个方法执行结束必须返回一条该类型的数据。



返回值语句：

​	return  数据;



返回值和打印区别：

完全是没有任何交集的两个东西。

返回值作用，将方法体内的数据输出，供调用结束后，后面的程序获取和使用。

打印，将数据显示在控制台上。



### 4、return语句

（1）第一种

return   数据；

用在有返回值的方法体中。

返回一条数据，然后结束方法体。



（2）第二种

return;

用在没有返回值的方法体。

不返回数据，仅仅表示方法体执行的结束。



```java
public class JiSuanQi2 {

    public   void  jia(int  a,int  b){
        int  sum=a+b;
        System.out.println(sum);
    }

    public   int  jia2(int  a,int  b){
        int  sum=a+b;
        return   sum;
    }


    public static void main(String[] args) {
        JiSuanQi2    j2=new JiSuanQi2();
        j2.jia(10,20);
//        int  ss2=j2.jia(10,20);

        int  ss=j2.jia2(10,20);
        System.out.println(ss);

    }
}

```





## 十、构造器

### 1、类和对象的关系

类是创建对象的模板。

对象是类的具体化。



### 2、如何创建类的对象呢？

构造器是创建对象的工具。

构造器是定义在类中，每一个类必须有构造器。

如果你在类中没有定义构造器，系统会提供一个缺省的无参构造器。





### 3、构造器的定义



语法：

[修饰符]   类名([参数]){

​		//方法体：对象属性的初始化代码

}

注意：构造器的名字必须和类名相同！！

​			构造器也叫构造方法，但不是方法。

​			构造器创建对象的，方法是解决问题的过程。

```java
public class Student {

//    属性
    public   int   number;
    public   String  name;
    public   String  sex;
    public   int     score;

//    方法
    public   void   display(){
        System.out.println(number);
        System.out.println(name);
        System.out.println(sex);
        System.out.println(score);
    }


    //构造器的定义
    public  Student(){

    }

    public   Student(int  num,String nm){
        number=num;
        name=nm;
    }

    public   Student(int  num,String nm,String  s,int  sr){
        number=num;
        name=nm;
        sex=s;
        score=sr;
    }

}

```



### 4、调用构造器创建对象

类名     对象名=new   构造器名(实参);



执行过程：

```
/**
         * 通过类名在方法区中找到这个类，（如果找不到，现加载类到方法区）
         * 在堆中开辟对象空间，
         * 将类中的属性和方法，赋予堆中的对象，
         * 传参
         * 执行方法体
         * 返回对象的首地址
         */
```



### 5、构造器的重载

在同一个类中定义多个构造器的现象。

他们的参数必须不同，因为构造器的名字和类名必须相同。



构造器的方法体主要用于初始化创建的对象属性。

提供了多种初始化的方案。







## 十一、this关键字

### 1、第一种用法

当参数或局部变量，和成员变量重名时，在方法体中直接访问的是参数或局部变量，成员变量被隐藏。

我们使用this.成员变量名来访问被隐藏的属性。

```java
public class WuMingFen2 {

    public   String theMa;
    public   int quantity;
    public   boolean likeSoup;
    
    public   void   setTheMa(String theMa){
        this.theMa=theMa;
    }


    public  WuMingFen2(String  theMa,int  quantity,boolean  likeSoup){
        this.theMa=theMa;
        this.quantity=quantity;
        this.likeSoup=likeSoup;
    }
}    
```



原因：this表示的是当前对象！！！





### 2、第二种用法

this当前类的构造器！！！



通过在一个构造器中调用另外一个构造器，从而减少构造器中重复代码的编写。

调用时，使用this(实参)；

```
public  WuMingFen2(String  theMa,int  quantity,boolean  likeSoup){
        this.theMa=theMa;
        this.quantity=quantity;
        this.likeSoup=likeSoup;
    }

    public  WuMingFen2(String  theMa,int  quantity){
//        this.theMa=theMa;
//        this.quantity=quantity;
//        likeSoup=true;
		//System.out.println();
        this(theMa,quantity,true);
    }

    public  WuMingFen2(){
//        theMa="酸辣";
//        quantity=2;
//        likeSoup=true;
        this("酸辣",2,true);
    }
```

注意：this(..)语句必须时构造器方法体中的第一条语句。



## 十二、static关键字

### 1、static修饰符

static修饰的成员变量，我们叫静态变量，或者类变量。

static修饰的成员方法，我们叫静态方法，或者类方法。



没有使用static修饰的成员变量，我们叫实例变量。(实例=对象)

没有使用static修饰的成员方法，我们叫实例方法。



### 2、拥有关系

类变量和类方法属于类，实例变量和实例方法是属于对象。

类变量和类方法可以共享给所有对象。



使用类名访问类变量和类方法：类名.类变量       类名.类方法(..)

使用对象名访问实例变量和实例方法：对象名.实例变量     对象名.实例方法

使用对象名访问类变量和类方法：对象名.类变量    对象名.类方法



![image-20220118163512541](JavaSE笔记.assets/image-20220118163512541.png)



```java
public class StaticDemo {
//    实例变量
    public   int   a;
//    类变量
    public  static   int  b;

//    实例方法
    public   void   test1(){
        System.out.println(11);
    }

//    类方法（静态方法）
    public  static   void   test2(){
        System.out.println(22);
    }


//    主方法：也是一个类方法（静态方法）
    public static void main(String[] args) {
//        使用类名调用类变量和类方法
        StaticDemo.b=22;
        StaticDemo.test2();

//        使用对象名调用实例变量和实例方法
        StaticDemo   sd1=new StaticDemo();
        sd1.a=11;
        sd1.test1();

        StaticDemo   sd2=new StaticDemo();
        sd2.a=12;
        sd2.test1();

//        所有对象都可以调用类变量和类方法
        sd1.b=23;
        sd2.b=24;
        sd1.test2();
        sd2.test2();

        System.out.println(StaticDemo.b);

    }

}
```



### 3、类成员之间的访问

在实例方法中，可以直接访问所有成员（实例变量、类变量、实例方法、类方法）。

在类方法中，只能直接访问类变量和类方法；如果想要访问实例变量和方法必须指定是哪个对象的，先实例化。

```
public class StaticDemo {
//    实例变量
    public   int   a;
//    类变量
    public  static   int  b;

//    实例方法
    public   void   test1(){
        System.out.println(11);
    }

    //    实例方法
    public   void   test11(){
        System.out.println(1111);

        System.out.println(a);
        System.out.println(b);

        test1();
        test2();

    }

//    类方法（静态方法）
    public  static   void   test2(){
        System.out.println(22);
    }
    //    类方法（静态方法）
    public  static   void   test22(){
        System.out.println(2222);

//        System.out.println(a);
        System.out.println(b);

//        test1();
        test2();

//        如果想要访问实例变量和方法必须指定是哪个对象的，先实例化。
        StaticDemo  sd03=new StaticDemo();
        System.out.println(sd03.a);
        sd03.test1();
    }


//    主方法：也是一个类方法（静态方法）
    public static void main(String[] args) {
//        使用类名调用类变量和类方法
        StaticDemo.b=22;
        StaticDemo.test2();

//        使用对象名调用实例变量和实例方法
        StaticDemo   sd1=new StaticDemo();
        sd1.a=11;
        sd1.test1();

        StaticDemo   sd2=new StaticDemo();
        sd2.a=12;
        sd2.test1();

//        所有对象都可以调用类变量和类方法
        sd1.b=23;
        sd2.b=24;
        sd1.test2();
        sd2.test2();

        System.out.println(StaticDemo.b);


//        -------------------------------------------------
        StaticDemo   sd00=new StaticDemo();
        sd00.test11();

        StaticDemo   sd01=new StaticDemo();
        sd01.test11();


        StaticDemo.test22();

    }

}

```



### 4、静态块

```
/**
 * 通过类名到方法区找到类的信息（如果没有，加载类到方法区，执行静态块）
 * 在堆里开辟对象的空间
 * 将类的实例变量和实例方法赋予对象
 * 执行初始化块
 * 传参
 * 执行方法体
 * 返回首地址
 */
```

（1）初始化代码块（不用）

```java
public class StaticDemo2 {

    public   int  a=1;
    public   static  int  b=2;

    public   void  test1(){
        System.out.println(11);
    }
    public    void   test2(){
        System.out.println(22);
    }

//    初始化代码块
    {
        System.out.println("=="+a);
        System.out.println("=="+b);
        a=3;
        b=4;
        System.out.println("=="+a);
        System.out.println("=="+b);
    }


    public   StaticDemo2(){
        System.out.println("--"+a);
        System.out.println("--"+b);
        a=5;
        b=6;
        System.out.println("--"+a);
        System.out.println("--"+b);
    }


    public static void main(String[] args) {
//        实例化
        new  StaticDemo2();
    }
```



new  StaticDemo2();

执行流程：

加载类；

创建对象；

初始化属性；

初始化代码块；

构造器传参；

构造器的方法体；

返回对象。



（2）静态块（偶尔）

静态块有且仅在第一访问该类的时候执行一次，后面就不再执行。

静态块先执行！！！



new  StaticDemo2();

执行流程：

加载类；

创建对象；

初始化属性；

静态块；

初始化代码块；

构造器传参；

构造器的方法体；

返回对象。





### 5、jvm加载类的过程

![img](https://img-blog.csdnimg.cn/2019062014564165.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3poYW9jdWl0,size_16,color_FFFFFF,t_70)



类加载的三个阶段：加载，连接，初始化。

（类的使用：声明变量，创建对象，调用类变量和类方法。）

（jvm工作流程：运行程序需要打开jvm，加载类，执行代码，退出jvm（卸载类清空jvm内存），关闭jvm）

（jvm调优：扩大堆内存 ,初始堆内存 -Xms=512M、最大堆内存 -Xmx=512M）

（1）**加载阶段**

在这个阶段，JVM主要完成三件事：

1、通过一个类的全限定名（包名与类名）来获取定义此类的二进制字节流（Class文件）。而获取的方式，可以通过jar包、war包、网络中获取、JSP文件生成等方式。

2、将这个字节流所代表的静态存储结构转化为方法区的运行时数据结构。这里只是转化了数据结构，并未合并数据。（方法区就是用来存放已被加载的类信息，常量，静态变量，编译后的代码的运行时内存区域）

3、在内存中生成一个代表这个类的java.lang.Class对象，作为方法区这个类的各种数据的访问入口。这个Class对象并没有规定是在Java堆内存中，它比较特殊，虽为对象，但存放在方法区中。
![image-20220119103959416](JavaSE笔记.assets/image-20220119103959416.png)





（2）**连接阶段**

连接大致分三个阶段。

1、验证：验证被加载后的类是否有正确的结构，类数据是否会符合虚拟机的要求，确保不会危害虚拟机安全。

2、准备：为类的静态变量（static filed）在方法区分配内存，并赋默认初值（0值或null值）。如static int a = 100;

静态变量a就会在准备阶段被赋默认值0。

对于一般的成员变量是在类实例化时候，随对象一起分配在堆内存中。

另外，静态常量（static final filed）会在准备阶段赋程序设定的初值，如static final int a = 666;  静态常量a就会在准备阶段被直接赋值为666，对于静态变量，这个操作是在初始化阶段进行的。



3、解析：将类的二进制数据中的符号引用换为直接引用。

![image-20220119104651564](JavaSE笔记.assets/image-20220119104651564.png)

（3）**初始化阶段**

*\*类的初始化的主要工作\**是为静态变量赋程序设定的初值。



执行静态块和赋初始值！！！！！！（和代码顺序有关）



![image-20220119104901694](JavaSE笔记.assets/image-20220119104901694.png)



## 十三、包

### 1、包的作用

如同文件夹管理文件一样，

包是管理类和接口的形式。

开发要求：所有类和接口必须放在包下管理！！



### 2、包的声明

创建包，idea中的操作：

![image-20210727163334462](05面向对象.assets/image-20210727163334462.png)



在包下创建类，在源文件中，会生成这样一句话：

package    包名;

注意：包的声明语句必须是源文件的第一句！！

![image-20220119111512858](JavaSE笔记.assets/image-20220119111512858.png)

![image-20210727164044665](05面向对象.assets/image-20210727164044665.png)

包的作用：

（1）便于查找

（2）不同包下可以出现相同的类名。



### 3、类的导入

同包下的类，直接访问；

不同包下的类，需要先导入才能访问。



import    包名.类名;

import    包名.*;

![image-20210727164508140](05面向对象.assets/image-20210727164508140.png)



### 4、源文件

在一个源文件中，可以定义多个类。

但是最多有一个public  class，公共的类类名必须和源文件名相同。

编译，每个类对应一个字节码文件（*.class）。

![image-20210727164839605](05面向对象.assets/image-20210727164839605.png)



![image-20210727164906285](05面向对象.assets/image-20210727164906285.png)

开发规范：一个源文件中只写一个公共类public  class。



## 十四、访问修饰符

### 1、修饰符

访问修饰符：   public      protected    private

非访问修饰符：   static   abstract   final   ==



### 2、访问修饰符

（1）作用

用来控制访问权限的。



（2）可以修饰

可以修饰类

可以修饰属性、方法、构造器



### 3、修饰类

（1）只能用public，或者不写（缺省）。

（2）public和缺省的区别

public   class：公共的类可以被任何包下类访问。

缺省class：缺省的类只能被同包下的类访问。





案例：

```
package com.aa;
public class A {

}
```



```
package com.bb;
public class B {

}
```



```
package com.aa;
class C {

}
```



```
package com.bb;
class D {

}
```



```
package com.aa;

import   com.bb.*;

public class TestABCD {
    public static void main(String[] args) {

       A  a=new   A();
       C  c=new   C();

       B  b=new  B();
//        D  d=new  D();

    }
}
```



### 4、修饰属性、方法、构造器

前提是：该类可以被访问，这样才能访问类中的成员。

（1）public  protected    private   或者不写（缺省）

（2）四种权限的区别

private：只能在当前类的内部访问。

缺省：只能在同包下的类中访问。不可以被不同包下的子类继承。

protected：只能在同包下的类中访问。可以被不同包下的子类继承。

public：可以被所有包下的类访问。

![image-20210727173851026](05面向对象.assets/image-20210727173851026.png)

案例：

```
package com.aa;

public class A {

    public  int   a;
    protected   int  b;
    int  c;
    private   int  d;

    public   void   test1(){
        System.out.println(1);
    }


    protected    void   test2(){
        System.out.println(2);
    }

       void   test3(){
        System.out.println(3);
    }

    private   void   test4(){
        System.out.println(4);
    }


    public   A(){}
    protected   A(int i){}
    A(int  i,int  j){}
    private A(int  i,int  j,int  k){}


    public static void main(String[] args) {
        A  a1=new  A();
        A  a2=new  A(1);
        A  a3=new  A(1,2);
        A  a4=new  A(1,2,3);

        System.out.println(a1.a);
        System.out.println(a1.b);
        System.out.println(a1.c);
        System.out.println(a1.d);

        a1.test1();
        a1.test2();
        a1.test3();
        a1.test4();
    }

}

```



```
package com.bb;

public class B {

    public  int   a;
    protected   int  b;
    int  c;
    private   int  d;

    public   void   test1(){
        System.out.println(1);
    }


    protected    void   test2(){
        System.out.println(2);
    }

    void   test3(){
        System.out.println(3);
    }

    private   void   test4(){
        System.out.println(4);
    }


    public   B(){}
    protected   B(int i){}
    B(int  i,int  j){}
    private B(int  i,int  j,int  k){}


    public static void main(String[] args) {
        B  b1=new  B();
        B  b2=new  B(1);
        B  b3=new  B(1,2);
        B  b4=new  B(1,2,3);
        System.out.println(b1.a);
        System.out.println(b1.b);
        System.out.println(b1.c);
        System.out.println(b1.d);
        b1.test1();
        b1.test2();
        b1.test3();
        b1.test4();
    }
}

```



```
package com.aa;

import   com.bb.*;

public class TestABCD {
    public static void main(String[] args) {

//        A  a=new   A();
//        C  c=new   C();
//
//        B  b=new  B();
////        D  d=new  D();

        A  a1=new  A();
        A  a2=new  A(1);
        A  a3=new  A(1,2);
//        A  a4=new  A(1,2,3);

        System.out.println(a1.a);
        System.out.println(a1.b);
        System.out.println(a1.c);
//        System.out.println(a1.d);

        a1.test1();
        a1.test2();
        a1.test3();
//        a1.test4();



        B  b1=new  B();
//        B  b2=new  B(1);
//        B  b3=new  B(1,2);
//        B  b4=new  B(1,2,3);
        System.out.println(b1.a);
//        System.out.println(b1.b);
//        System.out.println(b1.c);
//        System.out.println(b1.d);
        b1.test1();
//        b1.test2();
//        b1.test3();
//        b1.test4();


    }
}
```

# 06面向对象的特点



## 一、面向对象的特点

### 1、封装

### 2、继承

### 3、多态



## 二、封装

### 1、封装的概念

将类中的成员（属性，方法，构造器） 设为private，只能在当前类的内部使用，外部无法访问。

### 2、企业的封装

主要用于属性的封装。

将属性设为私有的，提供公有的getter和setter方法来访问。

```java
package com.fz;

public class Student {
//  封装属性，设为private
    private   int  num;
    private   String  name;

//    设置num属性的值
    public   void  setNum(int  num){
        if(num<0){
            return;
        }
        this.num=num;
    }

//    获取num属性的值
    public   int   getNum(){
        return   num;
    }

//    设置name属性的值
    public   void   setName(String  name){
        this.name=name;
    }

//    获取name属性的值
    public  String   getName(){
        return  name;
    }


//      封装方法
//    private   void   study(){
//        System.out.println("i  like   study");
//    }
//     封装构造器
//    private   Student(){}
}
```



```java
package com.fz;

public class Test {
    public static void main(String[] args) {

        Student  s= new  Student();

//        s.name="张三";
//        s.num=1001;
        s.setNum(1001);
        s.setName("zhangsan");

        System.out.println(s.getNum());
        System.out.println(s.getName());


    }
}
```

### 3、封装的优点

保证属性中的数据完整性。

保证属性的安全性。



## 三、继承

### 1、继承的概念

子类继承父类的属性和方法。

继承之后，在子类中就不需要再定义父类中的属性和方法。



### 2、继承的好处

减少重复代码的编写，提高了代码的重用性。



使用场景：

当你发现几个类中有重复的属性和方法时，将重复的属性和方法定义到父类中，其他类继承这个父类即可。



### 3、继承的实现

(1)语法

[修饰符]   class   子类名   extends     父类名{



}



（2）案例

```java
package com.jc;

public class Animal {
    public  String  name;
    public  String  type;

    public   void   eat(){
        System.out.println("eat");
    }

    public   void   sleep(){
        System.out.println("sleep");
    }
}
```



```java
package com.jc;

public class Dog  extends  Animal{
//    public  String  name;
//    public  String  type;
//
//    public   void   eat(){
//        System.out.println("eat");
//    }
//
//    public   void   sleep(){
//        System.out.println("sleep");
//    }
}
```





```java
package com.jc;

public class Cat extends   Animal{

}
```



```java
package com.jc;

public class ManDog extends   Dog{

}
```





```java
package com.jc;

public class Test {

    public static void main(String[] args) {

//        Dog   d=new Dog();
//        d.name="旺财";
//        d.type="中华田园犬";
//        System.out.println(d.name);
//        System.out.println(d.type);
//
//        d.eat();
//        d.sleep();

//        Cat   c=new Cat();
//        c.name="tom";
//        c.type="波斯";
//        System.out.println(c.name);
//        System.out.println(c.type);
//
//        c.eat();
//        c.sleep();

        ManDog   manDog=new ManDog();
        manDog.name="来福";
        manDog.type="哈巴狗";

        System.out.println(manDog.name);
        System.out.println(manDog.type);

        manDog.eat();
        manDog.sleep();


    }
}
```

### 4、子类的扩展



子类除了继承父类的属性和方法，还可以添加自己新的属性和方法。

子类比父类功能更强大。

```java
package com.jc;

public class Dog  extends  Animal{
//    public  String  name;
//    public  String  type;
//
//    public   void   eat(){
//        System.out.println("eat");
//    }
//
//    public   void   sleep(){
//        System.out.println("sleep");
//    }

    public   void  bite(){
        System.out.println("咬人");
    }
}
```



```java
package com.jc;public class ManDog extends   Dog{    public  String  sex;}
```





```
package com.jc;

public class Test {

    public static void main(String[] args) {

//        Dog   d=new Dog();
//        d.name="旺财";
//        d.type="中华田园犬";
//        System.out.println(d.name);
//        System.out.println(d.type);
//
//        d.eat();
//        d.sleep();

//        Cat   c=new Cat();
//        c.name="tom";
//        c.type="波斯";
//        System.out.println(c.name);
//        System.out.println(c.type);
//
//        c.eat();
//        c.sleep();

        ManDog   manDog=new ManDog();
        manDog.name="来福";
        manDog.type="哈巴狗";
        manDog.sex="公";

        System.out.println(manDog.name);
        System.out.println(manDog.type);

        manDog.eat();
        manDog.sleep();
        manDog.bite();


    }
}
```





### 5、继承的特点和范围

（1）继承特点

单继承：子类只能继承一个父类。



（2）多层次继承

A继承B，B继承C

C将属性和方法传给B，B再将属性和方法传给A。



（3）继承范围

**子类**只能继承父类的属性和方法，**不能继承构造器！**！



同包下，只能继承非私有的属性和方法。（继承的受保护和缺省的属性和方法只能用在子类中。）

不同包下，只能继承公共的和受保护的属性和方法。（继承的受保护的属性和方法只能用在子类中。）



```
package com.jc.aa;

import javax.swing.*;

public class P {

    private    int   a=1;
    int   b=2;
    protected   int  c=3;
    public    int  d=4;


    private   void  test1(){
        System.out.println(11);
    }

    void   test2(){
        System.out.println(22);
    }

    protected   void   test3(){
        System.out.println(33);
    }

    public   void   test4(){
        System.out.println(44);
    }
}
```





```
package com.jc.aa;

public class CC1 extends   P{


    public static void main(String[] args) {
        CC1  c1=new CC1();
//        System.out.println(c1.a);
        System.out.println(c1.b);
        System.out.println(c1.c);
        System.out.println(c1.d);

//        c1.test1();
        c1.test2();
        c1.test3();
        c1.test4();
    }
}
```



```
package com.jc.aa;

public class Test {

    public static void main(String[] args) {
        CC1  c1=new CC1();
//        System.out.println(c1.a);
        System.out.println(c1.b);
        System.out.println(c1.c);
        System.out.println(c1.d);

//        c1.test1();
        c1.test2();
        c1.test3();
        c1.test4();

    }
}
```



```
package com.jc.bb;

import com.jc.aa.P;

public class CC2 extends P {
    public static void main(String[] args) {
        CC2   c2=new CC2();
//        System.out.println(c2.a);
//        System.out.println(c2.b);
        System.out.println(c2.c);
        System.out.println(c2.d);

//        c2.test1();
//        c2.test2();
        c2.test3();
        c2.test4();
    }
}
```



```
package com.jc.bb;

public class Test2 {
    public static void main(String[] args) {

        CC2   c2=new CC2();
//        System.out.println(c2.a);
//        System.out.println(c2.b);
//        System.out.println(c2.c);
        System.out.println(c2.d);

//        c2.test1();
//        c2.test2();
//        c2.test3();
        c2.test4();


    }
}
```

### 6、方法的重写

子类继承父类的方法，但是该方法无法满足子类的需求，我们可以重新定义该方法。这个过程叫方法的重写。



**重写的原则：**

方法名相同

参数相同（参数名无所谓）

返回值类型相同

访问修饰符>=父类的范围



重写之后，子类对象执行的重写的方法体！！！

```
package com.jc.cc;

public class Father {

    public  String  name;

    public   void  eat(){
        System.out.println(name+"  eat  food");
    }

       void  smoke(){
        System.out.println(name+" smoke sanhua");
    }
}
```



```
package com.jc.cc;

public class Son extends   Father{


    //  缺省  protected   public
    //方法的重写
    public   void  smoke(){
        System.out.println(name+" smoke zhonghua");
    }

}
```



```
package com.jc.cc;

public class Test {
    public static void main(String[] args) {

        Son   s=new Son();
        s.name="小明";

        s.eat();
        s.smoke();


    }
}
```

### 7、super关键字

### （1）super第一种用法

当子类中的属性和方法，与继承的父类的属性和方法重名了。

我们在子类中，直接访问是子类中定义的属性和重写的方法。

如果在子类中，我们想要访问父类被隐藏的属性和方法，需要使用super调用。

super.属性名

super.方法名(..)



super表示**子对象**的**super区**！！



### （2）继承的原理：

![image-20220120114247607](JavaSE笔记.assets/image-20220120114247607.png)



### （3）super第二种用法

super表示父类构造器！！！

我们创建子类对象时，new   子类构造器：

```
//      调用子类构造器创建子类的对象：
//        创建一个子类的对象；
//        系统会先调用父类的构造器，默认调用父类无参的构造器，来创建对象的super区；
//        然后调用指定的子类构造器，来创建对象的this区；
//        返回对象的this区首地址
```

如果你不想使用父类无参构造器来构建super区，那么必须需要使用：super(实参)来指定。

如果调用的是父类无参构造器，使用super();,可以省略不写。



注意：**super（..）必须是子类构造器中的第1条语句**！！！



（4）案例

```java
package com.jc.dd;

public class P {
    public String  name="张三";
    public int  age;

    public   void  eat(){
        System.out.println("eat");
    }

    public   void  smoke(){
        System.out.println("smoke   sanhua");
    }

    public   P(){
        System.out.println("我是我父类构造器");
    }

    public   P(int  i){
        age=i;
        System.out.println("我是我父类构造器:"+i);
    }
}
```





```java
package com.jc.dd;

public class C extends    P{
    public  String  name="李四";
    public   String  sex;

    @Override
    public  void  smoke(){
        System.out.println("smoke  zhonghua");
    }


    public   void  test(){
        System.out.println(name);
        smoke();

        System.out.println(super.name);
        super.smoke();
    }

    public   C(){
        //super();
        super(30);
        System.out.println("我是子类构造器");
    }


    public static void main(String[] args) {
//      调用子类构造器创建子类的对象：
//        创建一个子类的对象；
//        系统会先调用父类的构造器，默认调用父类无参的构造器，来创建对象的super区；
//        然后调用指定的子类构造器，来创建对象的this区；
//        返回对象的this区首地址
        C c=new C();
        c.test();
        c.eat();
        System.out.println(c.age);
    }

}
```



## 四、多态

### 1、向上转型和向下转型

（1）前面我们学过数据类型转换：基本数据类型转换

自动类型转换和强制类型转换。

（2）我们今天学的是：引用类型转换

向上转型和向下转型



（3）向上转型

【子类的对象】由子类型转为父类型。

该对象只能访问父类继承的属性和方法，如果该方法被重写，访问重写之后的。

子类中扩展的属性和方法不能访问。



（4）向下转型

【子类的对象】由父类型转为子类型

该对象可以访问父类继承的属性和方法，如果该方法被重写，访问重写之后的。

还可以访问子类中扩展的属性和方法。



```
package com.jc.dd;

public class P {
    public String  name="张三";
    public int  age;

    public   void  eat(){
        System.out.println("eat");
    }

    public   void  smoke(){
        System.out.println("smoke   sanhua");
    }

    public   P(){
        System.out.println("我是我父类构造器");
    }

    public   P(int  i){
        age=i;
        System.out.println("我是我父类构造器:"+i);
    }
}
```



```
package com.jc.dd;

public class C extends    P{
    public  String  name="李四";
    public   String  sex;

    @Override
    public  void  smoke(){
        System.out.println("smoke  zhonghua");
    }


    public   void  test(){
        System.out.println(name);
        smoke();

        System.out.println(super.name);
        super.smoke();
    }

    public   C(){
        //super();
        super(30);
        System.out.println("我是子类构造器");
    }

}
```

```java
package com.jc.dd;

public class Test {

    public static void main(String[] args) {
//      创建子类对象，类型是子类型C
//      如果子类对象是子类型，那么指针指向this
        C  c=new  C();

//        向上转型：子类对象由子类型转为父类型
//        如果子类对象是父类型，那么指针指向super
        P   pc=c;

        System.out.println(pc.name);
        System.out.println(pc.age);
//        System.out.println(pc.sex);

        pc.eat();
        pc.smoke();
//        pc.test();


//        向下转型：子类对象由父类型转为子类型
//        如果子类对象是子类型，那么指针指向this
        C  c2=(C)pc;
        System.out.println(c2.name);
        System.out.println(c2.age);
        System.out.println(c2.sex);
        c2.eat();
        c2.test();
        c2.smoke();

    }
}
```





（5）错误案例

```java
package com.jc.dd;

public class Test2 {
    public static void main(String[] args) {

//        1、C和C2没有继承关系
        C  c1=new C();
//        C2  c2=(C2)c1;

//        2、父类的对象，向上和向下转型的目标是子类的对象
        P   p=new  P();
        C   cp=(C)p;

    }
}
```



### 2、多态的概念

多态，顾名思义：多种形态。

一个方法在执行时，根据传入对象的不同，执行结果不同。



### 3、多态产生的条件

继承关系

方法的重写

向上转型



### 4、案例

```
package com.dt;

public class Animal {
    public  String  name;
    public  void  eat(){
        System.out.println("动物吃饭");
    }
}
```



```
package com.dt;

public class Dog extends   Animal{

    @Override
    public void eat() {
        System.out.println("小狗吃饭");
    }
}
```



```
package com.dt;

public class Cat extends    Animal{

    @Override
    public void eat() {
        System.out.println("小猫吃饭");
    }
}
```





```
package com.dt;

public class Feeder {
    Animal   a;

//    多态的呈现：通过属性传入对象
    public  void  feed(){
        a.eat();
    }

//   多态的呈现：通过参数传入对象
    public  void  feed(Animal  a){
        a.eat();
    }


}
```



```
package com.dt;

import com.jc.dd.C;

public class Test {

    public static void main(String[] args) {
        Dog  d=new Dog();
        Cat  c=new Cat();

        Feeder  f=new Feeder();
        f.a=d;
        f.feed();
        f.a=c;
        f.feed();

        f.feed(d);
        f.feed(c);
    }

}
```



### 5、多态的优点

（1）提高代码的重用性

（2）降低程序的耦合度





## 五、instanceof关键字

### 1、作用

判断一个对象是否属于某种类型



### 2、使用

对象名  instanceof   类名或接口名

返回：boolean



```
Dog  d=new  Dog();

System.out.println(d   instanceof   Dog);
System.out.println(d   instanceof   Animal);
```





# 07面向对象的扩展

## 一、抽象类



### 1、抽象方法

没有方法体的方法，我们叫抽象方法。

抽象方法没有方法体，必须使用abstract修饰。



抽象方法定义：

**[修饰符]  abstract   返回值类型   方法名([参数]);**



使用场景：

当我们没有办法实现方法的方法体时，一般建议该方法定义成抽象方法。

抽象方法不能被使用！！



### 2、抽象类

使用abstract修饰的类，我们叫抽象类。



定义：

[修饰符]   abstract  class   类名{ .. }



### 3、抽象类和抽象方法的关系

含有抽象方法的类，必须定义为抽象类。

抽象类中，可以有抽象方法，也可以没有。





### 4、抽象类的特点

不能实例化！！

原因：里面可能有抽象方法，不能使用。



### 5、抽象类作用

（1）编程约定。

（2）抽象类主要是：用来被继承的。



### 6、继承抽象类

[修饰符]    class   子类名   extends  抽象类{



}



### 7、方法的实现

我们把对抽象方法的重写，由抽象状态转为非抽象状态，也就是添加方法体。习惯称为方法的实现。



### 8、案例

```
package com.hs;

public abstract class Shape {

    private   int  a;

    public  Shape(){}

    public  void  test(){
        System.out.println(a);
    }

    public abstract   double  area();

    public abstract  double perimter();


    public static void main(String[] args) {
        //new  Shape();
    }

}
```



```
package com.hs;

public  abstract class Circle extends   Shape{


}
```



```
package com.hs;

public class Rect  extends   Shape{
    private  double  chang;
    private  double  kuan;

    public double getChang() {
        return chang;
    }

    public void setChang(double chang) {
        this.chang = chang;
    }

    public double getKuan() {
        return kuan;
    }

    public void setKuan(double kuan) {
        this.kuan = kuan;
    }

    @Override
    public double area() {
        return chang*kuan;
    }

    @Override
    public double perimter() {
        return (chang+kuan)*2;
    }
}
```



```
public class Test {

    public static void main(String[] args) {
//        new  Shape();

        new  Rect();
    }
}
```



## 二、final关键字

### 1、修饰类

final  class，该类不能被继承。

```java
package com.hs.finaltest;

public final class FinalDemo {

}
```

```java
package com.hs.finaltest;

public class FinalChild extends    FinalDemo{
}
```

### 2、修饰变量（属性和局部变量）

常量，保存的数据不可被修改。



```java
public final class FinalDemo {

    public  final   int  ABC=1;


    public static void main(String[] args) {
        final int  B=10;
//        常量，不可被修改
//        ABC=2;
//        B=20;
        
    }

}
```



### 3、修饰方法

可以被继承，但是不能被重写。



```
package com.hs.finaltest;

public class FinalMethod {

    public   final   void  test(){
        System.out.println("test");
    }
}
```



```
package com.hs.finaltest;

public class FinalMethodChild extends   FinalMethod{

//    不能被重写
    public   void  test(){

    }


    public static void main(String[] args) {
        FinalMethodChild   c=new FinalMethodChild();
        c.test();
    }
}
```





## 三、接口

### 1、接口

（1）关键字

接口interface

类class



（2）定义

[public]   interface   接口名{

​	   //属性



​	  //方法



​	   //不能定义构造器

}



(3)接口可以看作是更加抽象的抽象类

接口中主要定义常量属性和抽象方法。

从jdk1.8开始，支持缺省方法和类方法。

[public]  interface   接口名{

​		//常量属性public  static  final

​		[public  static  final]    数据类型    属性名=初始值；



​		//抽象方法

​		[public  abstract]    返回值类型   方法名([参数]);

​		

​		//缺省方法

​		public   default     返回值类型     方法名([参数]){

​					..

​		}



​		//类方法

​		public    static    返回值类型     方法名([参数]){

​					..

​		}



}





案例：

```java
package com.hs.interfaceTest;
//接口关键字：interface
public interface MyInterface {

//    常量属性
    public   static  final   double  PI=3.14;
    public   static  final   double  E=2.714;

//    抽象方法
    public   abstract  void   test();

//    缺省方法
    public  default    void  test2(){
        System.out.println(22);
    }

//    类方法
    public  static    void  test3(){
        System.out.println(33);
    }

}
```





### 2、接口的特点

本质：类似更抽象的抽象父类。

不能实例化！！





### 3、接口的作用

（1）编程约定

（2）主要是用来被类实现



### 4、接口的实现(多实现)

一个类可以同时实现多个接口。

实现：类继承接口。

语法：

[修饰符]   class   实现类   **implements**    接口名1,接口名2....    {



​		。。。

}



案例：

```java
package com.hs.interfaceTest;

public class MyClass  implements    MyInterface{

//    方法的实现：重写抽象方法，添加方法体。
    @Override
    public void test1() {
        System.out.println(11);
    }
}
```

```
package com.hs.interfaceTest;

public class Test {

    public static void main(String[] args) {
        MyClass    myClass=new MyClass();

        System.out.println(myClass.PI);
        System.out.println(myClass.E);

        myClass.test1();
        myClass.test2();
//        myClass.test3();


        System.out.println(MyClass.PI);
        System.out.println(MyClass.E);
//        MyClass.test3();


//       接口中的类方法，只能通过接口名调用，不能使用实现类的类名和对象名调用。
        System.out.println(MyInterface.PI);
        System.out.println(MyInterface.E);
        MyInterface.test3();
    }
}
```



### 5、接口的继承(多继承)

语法：

public   interface    子接口     extends   父接口1，父接口2...{

​	....

}



```
package com.hs.interfaceTest;

public interface IA {
    double   A=10;
    void   test1();
}
```

```
package com.hs.interfaceTest;

public interface IB {
    double  B=30;

    void  test2();
}
```

```
package com.hs.interfaceTest;

public interface IC extends    IA,IB{
}
```



```
package com.hs.interfaceTest;

//public class ClassAB implements IA,IB{
public class ClassAB implements IC{

    @Override
    public void test1() {
        System.out.println(11);
    }

    @Override
    public void test2() {
        System.out.println(22);
    }
}
```

**总结：**

**类和类是单继承**

**接口和接口是多继承**

**类和接口是多实现**



### 6、接口存在的原因

Java来源于c++。

c++的类之间是支持多继承的，而Java类之间是单继承。

为了弥补这个缺陷，我们创造了接口，从而间接实现多继承。



### 7、接口类型

引用类型：数组、类、接口。

接口类型会向上转型，只能访问接口中定义的属性和方法；如果该方法被实现，将访问实现之后的。

```java
package com.hs.interfaceTest;

public interface Pin {

    double  a=10;

    void   test1();
}
```



```java
package com.hs.interfaceTest;

public class Pclass implements    Pin{
    private   int  b=20;

    @Override
    public void test1() {
        System.out.println(11);
    }

    public  void  test2(){
        System.out.println(22);
    }


    public static void main(String[] args) {
        Pclass   pc=new Pclass();
        System.out.println(pc.b);
        System.out.println(pc.a);
        pc.test1();
        pc.test2();

//        使用接口声明的，使用实现类实例化。
//        向上转型
//        只能访问接口中定义的属性和方法，
//        如果方法被实现，将访问实现之后。
        Pin   pc2=new Pclass();
//        System.out.println(pc2.b);
        System.out.println(pc2.a);
        pc2.test1();
//        pc2.test2();
    }
}
```



## 四、内部类（了解）



### 1、内部类

比如B类定义在A类中，那么我们称B类为内部类，A类叫外部类。



**内部类就相当于外部类的一个成员变量。**



### 2、内部类分类

（1）成员内部类

（2）静态内部类

（3）局部内部类

（4）匿名内部类（匿名类）





### 3、成员内部类

成员内部类相当于外部类一个实例变量

```
package com.hs.inner;

public class A {

    private  int    a1;
    public   int   a2;
//    成员内部类:相当于外部类一个实例变量
    public   class  B{
        private  int  b1;
        public   int  b2;

        public   void  testb1(){
            System.out.println(b1);
            System.out.println(a1);
        }
    }


    public   void  testa1(){
        System.out.println(a1);
//        System.out.println(b1);
//        System.out.println(b2);

        B   bb=new  B();
        System.out.println(bb.b1);
        System.out.println(bb.b2);
    }

}
```

```
package com.hs.inner;

public class Test {

    public static void main(String[] args) {
        A   aa=new  A();
        A.B   bb=aa.new  B();

//        System.out.println(bb.b1);
        System.out.println(bb.b2);
    }
}
```





### 4、静态内部类

静态内部类相当于外部类的一个类变量。

```
package com.hs.inner;

public class C {
    private static  int  c1;
    public  static  int  c2;
    public static   class   D{
        private static    int  d1;
        public static  int  d2;
        public  int  d3;

        public   void  testd1(){
            System.out.println(c1);
            System.out.println(c2);
            System.out.println(d1);
            System.out.println(d2);
        }
    }


    public  void   testa1(){
        System.out.println(c1);
        System.out.println(c2);

        System.out.println(D.d1);
        System.out.println(D.d2);
    }
}
```



```
package com.hs.inner;

public class Test2 {

    public static void main(String[] args) {

        System.out.println(C.D.d2);

        C.D   dd=new  C.D();
        System.out.println(dd.d3);

    }
}
```





### 5、局部内部类

局部内部类相当于一个局部变量。

```
package com.hs.inner;

public class E {

    public   void  test(){

//        局部内部类
        class   F{
            private int  f1;
            public   int  f2;

            public  void  testf1(){
                System.out.println(f1);
            }
        }
//        使用
        F   f=new   F();
        System.out.println(f.f1);
    }


    public static void main(String[] args) {
        new  E().test();
    }
}
```



### 6、匿名内部类（重点）

匿名类，没有类名。

该类必须要继承一个父类，或实现一个接口。

定义完，需要立马实例化。

实例化时，构造器名使用父类名或接口名代替，会发生向上转型。

在匿名类中，扩展属性和方法是没有意义的，访问不到。



```
package com.hs.inner;

public interface P {

    void   testP();
}
```



```
package com.hs.inner;

public class G {

    public   static   void   main(String[]  a){
//        匿名内部类
        P  pp=new  P(){
            public  void   testP(){
                System.out.println("pp");
            }
        };

        pp.testP();
    }

}
```

# 08常用类库

## 一、系统类库

### 1、系统类库解释

JRE中已经编写好的类和接口的统称，我们叫Java的系统类库。

我们直接使用这些类和接口即可。





### 2、API文档

Application Programming Interface，应用程序接口。

类和接口的解释说明文档，或者叫使用手册。



下载：

jdk api 1.8_google.CHM（google翻译）

jdk api 1.8_baidu.CHM （百度翻译）



### 3、API文档使用

（1）主页面

![image-20210730110634156](08常用类库.assets/image-20210730110634156.png)



左上角：包

左下角：类

右边：解释说明



（2）使用

以String类为例：

第一步，选择包名：java.lang

第二步，选择类：String

第三步，查看右边String类的详细信息

![image-20210730110952872](08常用类库.assets/image-20210730110952872.png)





### 4、类的详细信息

以String类为例：

（1）类的声明

- ```
  public final class String
  extends Object
  implements Serializable, Comparable<String>, CharSequence
  ```

（2）类的功能描述

- `String`类代表字符串。Java程序中的所有字符串文字（例如`"abc"` ）都被实现为此类的实例。

  字符串不变; 它们的值在创建后不能被更改。 字符串缓冲区支持可变字符串。  因为String对象是不可变的，它们可以被共享。 例如： 

  > ```
  >   String str = "abc";
  > 
  > ```

  相当于： 

  > ```
  >   char data[] = {'a', 'b', 'c'};
  >   String str = new String(data);
  > ```



（3）属性概要介绍

- - ### Field Summary

    | Modifier and Type           | Field and Description                                        |
    | --------------------------- | ------------------------------------------------------------ |
    | `static Comparator<String>` | `CASE_INSENSITIVE_ORDER`  一个比较器，按 `compareToIgnoreCase`订购  `String`对象。 |

（4）构造方法概要描述

- - ### 构造方法摘要

    | Constructor and Description                                  |
    | ------------------------------------------------------------ |
    | `String()`  初始化新创建的 `String`对象，使其表示空字符序列。 |
    | `String(byte[] bytes)`  通过使用平台的默认字符集解码指定的字节数组来构造新的 `String` 。 |
    | `String(byte[] bytes,  Charset charset)`  构造一个新的`String`由指定用指定的字节的数组解码[charset](../../java/nio/charset/Charset.html)  。 |
    | `String(byte[] ascii,  int hibyte)`  已弃用  此方法无法将字节正确转换为字符。 从JDK 1.1开始，首选的方法是通过`String`构造函数获取[`Charset`](../../java/nio/charset/Charset.html)  ，字符集名称，或者使用平台的默认字符集。 |
    | `String(byte[] bytes,  int offset, int length)`  通过使用平台的默认字符集解码指定的字节子阵列来构造新的 `String` 。 |
    | `String(byte[] bytes,  int offset, int length, Charset charset)`  构造一个新的`String`通过使用指定的指定字节子阵列解码[charset](../../java/nio/charset/Charset.html)  。 |
    | `String(byte[] ascii,  int hibyte, int offset, int count)`  已弃用  此方法无法将字节正确转换为字符。 从JDK 1.1开始，首选的方式是通过`String`构造函数获取[`Charset`](../../java/nio/charset/Charset.html)  ，字符集名称，或使用平台的默认字符集。 |
    | `String(byte[] bytes,  int offset, int length, String charsetName)`  构造一个新的 `String`通过使用指定的字符集解码指定的字节子阵列。 |
    | `String(byte[] bytes,  String charsetName)`  构造一个新的`String`由指定用指定的字节的数组解码[charset](../../java/nio/charset/Charset.html)  。 |
    | `String(char[] value)`  分配一个新的 `String` ，以便它表示当前包含在字符数组参数中的字符序列。 |
    | `String(char[] value,  int offset, int count)`  分配一个新的 `String` ，其中包含字符数组参数的子阵列中的字符。 |
    | `String(int[] codePoints,  int offset, int count)`  分配一个新的 `String` ，其中包含 [Unicode code point](Character.html#unicode)数组参数的子阵列中的 [字符](Character.html#unicode) 。 |
    | `String(String original)`  初始化新创建的`String`对象，使其表示与参数相同的字符序列;  换句话说，新创建的字符串是参数字符串的副本。 |
    | `String(StringBuffer buffer)`  分配一个新的字符串，其中包含当前包含在字符串缓冲区参数中的字符序列。 |
    | `String(StringBuilder builder)`  分配一个新的字符串，其中包含当前包含在字符串构建器参数中的字符序列。 |



（5）方法概要描述

- ### 方法摘要

  | Modifier and Type | Method and Description                                       |
  | ----------------- | ------------------------------------------------------------ |
  | `char`            | `charAt(int index)`  返回 `char`指定索引处的值。             |
  | `int`             | `codePointAt(int index)`  返回指定索引处的字符（Unicode代码点）。 |
  | `int`             | `codePointBefore(int index)`  返回指定索引之前的字符（Unicode代码点）。 |
  | `int`             | `codePointCount(int beginIndex,  int endIndex)`  返回此 `String`指定文本范围内的Unicode代码点数。 |
  | `int`             | `compareTo(String anotherString)`  按字典顺序比较两个字符串。 |

（6）属性详细介绍

（7）构造器详细介绍

（8）方法详细介绍

- - - #### charAt

      ```
      public char charAt(int index)
      ```

      返回`char`指定索引处的值。指数范围为`0`至`length() - 1` 。该序列的第一个`char`值在索引`0` ，下一个索引为`1`  ，依此类推，与数组索引一样。

      如果`char`由索引指定的值是[surrogate](Character.html#unicode) ，则返回所述替代值。 

      - Specified by: 

        `charAt`在界面  `CharSequence` 

      - 参数 

        `index` - `char`值的指数。 

      - 结果 

        所述`char`此字符串的指定索引处的值。  第一个`char`值是索引`0` 。 

      - 异常 

        `IndexOutOfBoundsException`  - 如果 `index`参数为负数或不小于此字符串的长度。 





## 二、常用包

java.lang(此包下的类，无需导入，可以直接使用)

java.io

java.text

java.util

java.net

java.sql



## 三、Object类

### 1、包

java.lang.Object

### 2、构造器

Object()` 

无参构造器，没有啥用。

### 3、方法

- - | Modifier and Type  | Method and Description                                       |
    | ------------------ | ------------------------------------------------------------ |
    | `protected Object` | `clone()`  创建并返回此对象的副本。                          |
    | `boolean`          | `equals(Object obj)`  指示一些其他对象是否等于此。           |
    | `protected void`   | `finalize()`  当垃圾收集确定不再有对该对象的引用时，垃圾收集器在对象上调用该对象。 |
    | `类<?>`            | `getClass()`  返回此 `Object`的运行时类。                    |
    | `int`              | `hashCode()`  返回对象的哈希码值。                           |
    | `void`             | `notify()`  唤醒正在等待对象监视器的单个线程。               |
    | `void`             | `notifyAll()`  唤醒正在等待对象监视器的所有线程。            |
    | `String`           | `toString()`  返回对象的字符串表示形式。                     |
    | `void`             | `wait()`  导致当前线程等待，直到另一个线程调用该对象的 [`notify()`](../../java/lang/Object.html#notify--)方法或 [`notifyAll()`](../../java/lang/Object.html#notifyAll--)方法。 |
    | `void`             | `wait(long timeout)`  导致当前线程等待，直到另一个线程调用 [`notify()`](../../java/lang/Object.html#notify--)方法或该对象的 [`notifyAll()`](../../java/lang/Object.html#notifyAll--)方法，或者指定的时间已过。 |
    | `void`             | `wait(long timeout,  int nanos)`  导致当前线程等待，直到另一个线程调用该对象的 [`notify()`](../../java/lang/Object.html#notify--)方法或 [`notifyAll()`](../../java/lang/Object.html#notifyAll--)方法，或者某些其他线程中断当前线程，或一定量的实时时间。 |

### 4、超类

根类，基类。

所有类都直接或间接继承了Object类。

```
package com.hs.obj;

public class P {
	//p  extend  object
}
```

```
package com.hs.obj;

public class Student extends P{

    public static void main(String[] args) {
        Student  s=new Student();
        Student  s2=new Student();
        s.toString();
        s.hashCode();
        s.equals(s2);

    }
}
```



Object充分体现了面向对象继承的使用！！

我们将所有类都应该有的方法，定义到Object。



### 5、常用方法

（1）hashCode方法

每个对象在内存中存储，都一个对应的地址。

我们可以通过地址找到内存中的该对象，然后访问对象。

每个对象都一个唯一的地址。



hashCode方法作用：将对象的地址，通过哈希算法（散列算法）转换为一个int整数，这个整数我们称为哈希码。

一般情况，不同的对象对应的哈希码值不同。但是少数情况，不同的对象哈希码值可能相同。

```
 		Student  s=new Student();
        Student  s2=new Student();

        System.out.println(s.hashCode());
        System.out.println(s2.hashCode());
```



（2）toString方法

返回对象的字符串形式：类名@哈希码值

```
		Student  s=new Student();
        Student  s2=new Student();

        System.out.println(s.hashCode());
        System.out.println(s2.hashCode());

        System.out.println(s.toString());
        System.out.println(s2.toString());
```



（3）equals方法

比较两个对象是否相等：比较的是对象的首地址是否相同，如果相同返回true，如果不相同返回false。

```
Student  s=new Student();
Student  s2=new Student();

System.out.println(s.hashCode());
System.out.println(s2.hashCode());

System.out.println(s.toString());
System.out.println(s2.toString());

System.out.println( s.equals(s2));
Student  s3=s2;
System.out.println(s3.equals(s2));
```





## 四、String类

### 1、包

java.lang.String

### 2、构造器

- `String`类代表字符串。
- 每一个String对象，保存一个字符串。



4个常用的构造器：

- String()`  初始化新创建的 `String`对象，使其表示空字符序列。 
- `String(byte[] bytes)`  通过使用平台的默认字符集解码指定的字节数组来构造新的 `String` 。

- String(char[] value)`  分配一个新的 `String` ，以便它表示当前包含在字符数组参数中的字符序列。 

- String(String original)`  初始化新创建的`String`对象，使其表示与参数相同的字符序列;  换句话说，新创建的字符串是参数字符串的副本。



```java
//        构造器
//        创建一个长度为0的字符串
        String  s1="";
        String  s11=new  String();

        String  s2="abcd";
        String  s22=new  String("abcd");

        char[]  cc={'a','b','c','d'};
        String  s33=new  String(cc);

        byte[]  bb={97,98,99,100};
        String  s44=new  String(bb);

        System.out.println(s1);
        System.out.println(s11);
        System.out.println(s2);
        System.out.println(s22);
        System.out.println(s33);
```





### 3、存储结构

String  s22=new  String("abcd");



![image-20210730145154900](08常用类库.assets/image-20210730145154900.png)



### 4、常用方法

String类提供了很多操作字符串的方法。

- - | `int` | `length()`  返回此字符串的长度。 |
    | ----- | -------------------------------- |

- - | `char` | `charAt(int index)`  返回 `char`指定索引处的值。 |
    | ------ | ------------------------------------------------ |

- - | `int` | `indexOf(int ch)`  返回指定字符第一次出现的字符串内的索引。 |
    | ----- | ----------------------------------------------------------- |

- - | `int` | `lastIndexOf(int ch)`  返回指定字符的最后一次出现的字符串中的索引。 |
    | ----- | ------------------------------------------------------------ |



- - | `boolean` | `isEmpty()`  返回 `true`如果，且仅当 [`length()`](../../java/lang/String.html#length--)为  `0` 。 |
    | --------- | ------------------------------------------------------------ |

- - | `boolean` | `startsWith(String prefix)`  测试此字符串是否以指定的前缀开头。 |
    | --------- | ------------------------------------------------------------ |

- - | `boolean` | `endsWith(String suffix)`  测试此字符串是否以指定的后缀结尾。 |
    | --------- | ------------------------------------------------------------ |

- - | `boolean` | `contains(CharSequence s)`  当且仅当此字符串包含指定的char值序列时才返回true。 |
    | --------- | ------------------------------------------------------------ |





- - | `String` | `toUpperCase()`  将所有在此字符 `String`使用默认语言环境的规则大写。 |
    | -------- | ------------------------------------------------------------ |

- - | `String` | `toLowerCase()`  将所有在此字符 `String`使用默认语言环境的规则，以小写。 |
    | -------- | ------------------------------------------------------------ |

- - | `String` | `concat(String str)`  将指定的字符串连接到该字符串的末尾。 |
    | -------- | ---------------------------------------------------------- |



- - | `String` | `substring(int beginIndex)`  返回一个字符串，该字符串是此字符串的子字符串。 |
    | -------- | ------------------------------------------------------------ |
    | `String` | `substring(int beginIndex,  int endIndex)`  返回一个字符串，该字符串是此字符串的子字符串。 |

- - | `String` | `replace(char oldChar,  char newChar)`  返回从替换所有出现的导致一个字符串 `oldChar`在此字符串  `newChar` 。 |
    | -------- | ------------------------------------------------------------ |

- - | `String[]` | `split(String regex)`  将此字符串分割为给定的 [regular  expression的](../util/regex/Pattern.html#sum)匹配。 |
    | ---------- | ------------------------------------------------------------ |

- - | `String` | `trim()`  返回一个字符串，其值为此字符串，并删除任何前导和尾随空格。 |
    | -------- | ------------------------------------------------------------ |



- - | `char[]` | `toCharArray()`  将此字符串转换为新的字符数组。 |
    | -------- | ----------------------------------------------- |

- - | `byte[]` | `getBytes()`  使用平台的默认字符集将此 `String`编码为字节序列，将结果存储到新的字节数组中。 |
    | -------- | ------------------------------------------------------------ |

- - | `int` | `compareTo(String anotherString)`  按字典顺序比较两个字符串。 |
    | ----- | ------------------------------------------------------------ |
    | `int` | `compareToIgnoreCase(String str)`  按字典顺序比较两个字符串，忽略病例差异。 |

### 5、重写的方法

String  extends  Object

（1）hashCode方法

返回不是对象地址的哈希码，而是字符串内容的哈希码。

```
//      重写hashCode方法
        String   s7=new  String("abcd");
        String   s8=new  String("abcd");

        System.out.println(s7.hashCode());
        System.out.println(s8.hashCode());
```

（2）toString方法

返回不是类名@哈希码值，而是保存的字符串。

```
//        重写toString方法
        String   s7=new  String("abcd");
        String   s8=new  String("abcd");
        
        System.out.println(s7.toString());
        System.out.println(s8.toString());
```

（3）equals方法

不是比较对象的首地址，而是比较保存的字符串是否相等。

```
//        重写equals方法
		String   s7=new  String("abcd");
        String   s8=new  String("abcd");
        
        System.out.println(s7.equals(s8));
        System.out.println(s7.equalsIgnoreCase(s8));
```



### 6、字符串是常量

String对象保存的字符串是不可以被修改的。

String对象一旦创建，保存的字符串固定不变。





==和equals方法的区别：？？





### 7、特殊字符处理

**\：反斜杠表示转义字符，不占符号位。**

特殊字符需要使用\转义表示。



常见特殊字符：

回车  \r

换行   \n

缩进   \t   (相当于Tab键)

退格    \b

反斜杠    \ \

单引号   \ '

双引号   \ "

# 08常用类库02

## 一、String类

### 1、作用

存储字符串，处理字符串。



使用构造器（4个）创建String对象，用来保存字符串。

然后使用对象的方法（20个常用方法），处理字符串。



### 2、String是常量

String对象一旦创建，其保存的字符串内容是固定不变。

```java
String  s="aabbccddaabbccdd";
String  s2=s.replace("aa","99");

System.out.println(s);
System.out.println(s2);
```

![image-20210802164010502](08常用类库02.assets/image-20210802164010502.png)

```java
String  s="aabbccddaabbccdd";
String  s2=s.replace("aa","99");

System.out.println(s);
System.out.println(s2);


s="abcd";
System.out.println(s);
```

![](08常用类库02.assets/image-20210802164252042.png)

### 3、常量池

![image-20210802164742962](08常用类库02.assets/image-20210802164742962.png)

常量池创建对象的特点：

如果存储在一个对象保存相同内容，那么久不会在常量池中再创建新对象，直接返回老对象的地址。

![image-20210802165218869](08常用类库02.assets/image-20210802165218869.png)



==和equals的区别：

==既可以比较基本类型的数据，也可以用于引用类型的比较。

equals方法只能用于引用类型的比较。



==比较引用类型，始终比较的是对象的首地址。

equals可以被重写，比较规则按照重写之后的比较。



```java
String  s1="abcd";
String  s2=new  String("abcd");

String  s3="abcd";
String  s4=new  String("abcd");


System.out.println(s1==s2);//false
System.out.println(s1==s3);//true
System.out.println(s1.equals(s2));//true
System.out.println(s1.equals(s3));//true


//一共创建了几个对象：三个
String  s="abcd"+"abcd"+"abcd";
        //abcd
        //abcdabcd
        //abcdabcdabcd
```



### 4、特殊字符处理

特殊字符是java中用于特殊用途的符号。

在字符串中，需要使用反斜杠转义。

反斜杠\  ，是转义字符，不占符号位。



常见的特殊字符：

 \ ”    双引号

\ '     单引号

\n     换行

\t      缩进tab

\r      回车

\ \     反斜杠



```
String  s="\"\\\\";

System.out.println(s.length());  //3
```





## 二、StringBuffer

### 1、作用

存储字符串，处理字符串。



### 2、构造器

- - `StringBuffer(String str)`  构造一个初始化为指定字符串内容的字符串缓冲区。



### 3、常用方法

- - 不同的方法

    | `String` | `toString()`  返回表示此顺序中的数据的字符串。 |
    | -------- | ---------------------------------------------- |

- - 

    | `StringBuffer` | `append(StringBuffer sb)`  将指定 `StringBuffer`这个序列。 |
    | -------------- | ---------------------------------------------------------- |

- - | `StringBuffer` | `replace(int start,  int end, String str)`  用指定的String中的字符替换此序列的子字符串中的 `String` 。 |
    | -------------- | ------------------------------------------------------------ |

- - | `StringBuffer` | `reverse()`  导致该字符序列被序列的相反代替。 |
    | -------------- | --------------------------------------------- |

- - | `StringBuffer` | `insert(int offset,  String str)`  将字符串插入到此字符序列中。 |
    | -------------- | ------------------------------------------------------------ |

- - | `StringBuffer` | `delete(int start,  int end)`  删除此序列的子字符串中的字符。 |
    | -------------- | ------------------------------------------------------------ |



相同的方法：

- - 

    | `char` | `charAt(int index)`  返回 `char`在指定索引在这个序列值。 |
    | ------ | -------------------------------------------------------- |

- - 

    | `int` | `indexOf(String str)`  返回指定子字符串第一次出现的字符串内的索引。 |
    | ----- | ------------------------------------------------------------ |

- - 

    | `int` | `lastIndexOf(String str)`  返回指定子字符串最右边出现的字符串内的索引。 |
    | ----- | ------------------------------------------------------------ |

- - 

    | `int` | `length()`  返回长度（字符数）。 |
    | ----- | -------------------------------- |



- - | `String` | `substring(int start)`  返回一个新的 `String` ，其中包含此字符序列中当前包含的字符的子序列。 |
    | -------- | ------------------------------------------------------------ |
    | `String` | `substring(int start,  int end)`  返回一个新的 `String` ，其中包含此序列中当前包含的字符的子序列。 |





### 4、StringBuffer特点

StringBuffer对象保存的字符串是可以修改的。

![image-20210802172823053](08常用类库02.assets/image-20210802172823053.png)

## 三、StringBuilder

### 1、作用

存储字符串，处理字符串



### 2、学习

和StringBuffer一样，类似的构造器和相同的方法。



### 3、String、StringBuffer、StringBuilder区别

String对象保存的字符串是不可修改的。

StringBuffer和StringBuilder对象保存的字符串是可以修改的。



StringBuffer是线程安全的，执行效率低；StringBuilder是线程不安全，执行效率高。



## 四、八大包装类

### 1、基本数据类型

byte  short   int  long

float  double

boolean

char



### 2、包装类

java.lang:

Byte

Short

Integer

Long



Float

Double



Boolean

Character



我们将八种基本数据类型对应的类，称为包装类。



### 3、包装类的作用

（1）和基本类型一样，用于存储数据。

（2）提供了处理数据的方法：最常用的是类型转换的方法。



### 4、存储数据

![image-20210803091856956](08常用类库02.assets/image-20210803091856956.png)



### 5、构造器

- - | `Integer(int value)`  构造一个新分配的 `Integer`对象，该对象表示指定的 `int`值。 |
    | ------------------------------------------------------------ |
    | `Integer(String s)`  构造一个新分配 `Integer`对象，表示 `int`由指示值  `String`参数。 |



```java
//        1、存储数据
        int   i=9;
        Integer  in=new Integer(9);
        Integer  in2=new Integer("9");//参数必须是整数字符
```



### 6、类型转换

（1）int 、Integer、String三者之间的转换。

```java
package com.hs.demo02;

public class IntegerDemo {

    public static void main(String[] args) {

//        1、存储数据
        int   i=9;
        Integer  in=new Integer(9);
        Integer  in11=new Integer("9");

//        2、类型转转
//        （1）int-->Integer
        int   i1=9;
        Integer  in1=new Integer(i1);

//        (2)Integer-->int
        Integer   in2=new Integer(9);
        int i2 = in2.intValue();

//        (3)int-->String(常用)
        int  i3=9;
        String  s3=Integer.toString(i3);//"9"
        String  s33=i3+"";

//        (4)String-->int(最常用的)
        String  s4="9";
        int  i4=Integer.parseInt(s4);

//        (5)Integer-->String
        Integer   in5=new Integer(9);
        String    s5=in5.toString();//"9"

//        (6)String-->Integer
        String   s6="9";
        Integer  in6=new Integer(s6);


    }

}
```



（2）double、Double、String

```java
package com.hs.demo02;

public class DoubleDemo {
    public static void main(String[] args) {

        double  d1=10.0;
        Double   db1=new Double(d1);

        Double   db2=new Double(10.0);
        double   d2=db2.doubleValue();

        double   d3=10.0;
        String   s3=Double.toString(d3);
        String   s33=""+d3;

        String   s4="10.5";
        double   d4=Double.parseDouble(s4);


        String   s5="10.5";
        Double  db5=new Double(s5);

        Double   db6=new Double(10.5);
        String   s6=db6.toString();


    }
}
```

（3）boolean、Boolean、String

```java
package com.hs.demo02;

public class BooleanDemo {
    public static void main(String[] args) {

        boolean   b1=true;
        Boolean    bl1=new Boolean(b1);

        Boolean   bl2=new Boolean(true);
        boolean b = bl2.booleanValue();

        boolean   b3=true;
        String   s3=Boolean.toString(b3);
        String  s33=""+b3;

        String   s4="true";
        boolean   b4=Boolean.parseBoolean(s4);


        String   s5="true";
        Boolean  bl5=new Boolean(s5);

        Boolean   bl6=new Boolean(true);
        String s6 = bl6.toString();



    }
}
```

（4）char、Character、String

```java
package com.hs.demo02;

public class CharacterDemo {

    public static void main(String[] args) {

        char   c1='a';
        Character   ch1=new Character(c1);


        Character   ch2=new Character('a');
        char   c2=ch2.charValue();


        char   c3='a';
        String  s3=Character.toString(c3);
        String   s33=""+c3;

//        没有parseChar方法，使用String的charAt(0)方法
        String   s4="a";
        char   c4=s4.charAt(0);

//        没有字符串参数的构造器，只能间接转换
        String   s5="a";
        Character   ch5=new Character(s5.charAt(0));

        Character   ch6=new Character('a');
        String s6 = ch6.toString();

    }


}
```

### 7、装箱和拆箱

基本类型   和 包装类  之间转换，jdk1.5我们提供了装箱和拆箱技术。

（1）装箱

将一个基本类型的数据转换为包装类的对象。

（2）拆箱

将一个包装类的对象转为基本类型数据。

```java
package com.hs.demo02;

public class DemoALL {

    public static void main(String[] args) {

        int  i=9;
        Integer    in=i;//装箱
        int   i2=in;  //拆箱


        double   d=10.5;
        Double   db=d;
        double   d2=db;


        boolean   b=true;
        Boolean   bl=b;
        boolean   b2=bl;


        char   c='a';
        Character  ch=c;
        char   c2=ch;
    }

}
```





## 五、System类

系统类

### 1、属性

- - 

    | `static PrintStream` | `err`  “标准”错误输出流。 |
    | -------------------- | ------------------------- |
    | `static InputStream` | `in`  “标准”输入流。      |
    | `static PrintStream` | `out`  “标准”输出流。     |

### 2、方法

- - 

    | `static void` | `exit(int status)`  终止当前运行的Java虚拟机。 |
    | ------------- | ---------------------------------------------- |

- - 

    | `static void` | `gc()`  运行垃圾回收器。 |
    | ------------- | ------------------------ |

- - 

    | `static long` | `currentTimeMillis()`  返回当前时间（以毫秒为单位）。 |
    | ------------- | ----------------------------------------------------- |



```java
package com.hs.system;

import java.util.Scanner;

public class SystemDemo {

    public static void main(String[] args) {

//        in保存的是一个输入流对象，由系统创建和赋值
        Scanner   sc=new Scanner(System.in);

//        out保存一个标准输出流，由系统创建和赋值
        System.out.println("aaaaa");

//        err保存一个错误输出流，由系统创建和赋值
        System.err.println("aaaaa");

//       退出jvm
//        0表示正常退出
//        非0异常退出
//        System.exit(0);


//        当前jvm的系统时间
//        1970-1-1 0:0:0  0
        long   time=System.currentTimeMillis();
        System.out.println(time);
    }
}
```



## 六、Math类

与数学运算相关的。

### 1、属性

PI

E



### 2、方法

- - | `static double` | `random()`  返回值为 `double`值为正号，大于等于 `0.0` ，小于  `1.0` |
    | --------------- | ------------------------------------------------------------ |

- - | `static long` | `round(double a)`  返回参数中最接近的 `long` ，其中 `long`四舍五入为正无穷大。 |
    | ------------- | ------------------------------------------------------------ |

```java
package com.hs.system;

import com.sun.xml.internal.bind.v2.runtime.output.StAXExStreamWriterOutput;

public class MathDemo {
    public static void main(String[] args) {
        System.out.println(Math.random());
        System.out.println((int)(Math.random()*100));
        System.out.println(Math.round(Math.random()*100));
    }
}
```

# 09日期类和格式化类

## 一、Date

### 1、包

java.util

### 2、作用

存储日期，处理日期

### 3、构造器

- - `Date()`  分配一个 `Date`对象，并初始化它，以便它代表它被分配的时间，测量到最近的毫秒。 
- - `Date(long date)`  分配一个  `Date`对象，并将其初始化为表示自称为“时代”的标准基准时间以后的指定毫秒数，即1970年1月1日00:00:00 GMT

```java
//        构造器
//        当前时间
        Date   d1=new Date();
//        相对时间
//        基准时间：1970-1-1  0:0:0  0
//        格林威治时间：1970-1-1  0:0:1  0
//        东八区时间：1970-1-1  8:0:1  0
        Date   d2=new Date(1000);
        System.out.println(d1);
        System.out.println(d2);
```

### 4、方法

（1）已弃用的方法：

```java
package com.hs;

import java.util.Date;

public class DateDemo {

    public static void main(String[] args) {
//        构造器
//        当前时间
        Date   d1=new Date();
//        相对时间
//        基准时间：1970-1-1  0:0:0
//        格林威治时间：1970-1-1  0:0:1
//        东八区时间：1970-1-1  8:0:1
        Date   d2=new Date(1000);
        System.out.println(d1);
        System.out.println(d2);

//        弃用方法
        d1.setYear(122);
        d1.setMonth(10);
        d1.setDate(10);
        d1.setHours(10);
        d1.setMinutes(10);
        d1.setSeconds(10);

        int year = d1.getYear();
        int month = d1.getMonth();
        int date = d1.getDate();
        int hours = d1.getHours();
        int minutes = d1.getMinutes();
        int seconds = d1.getSeconds();
        int day = d1.getDay();

        System.out.println(year+1900);
        System.out.println(month+1);
        System.out.println(date);
        System.out.println(hours);
        System.out.println(minutes);
        System.out.println(seconds);
        System.out.println(day);
    }
}
```





（2）正常方法：

- - | `void` | `setTime(long time)`  设置此 `Date`对象以表示1970年1月1日00:00:00 GMT后的  `time`毫秒的时间点。 |
    | ------ | ------------------------------------------------------------ |

- - | `long` | `getTime()`  返回自1970年1月1日以来，由此 `Date`对象表示的00:00:00 GMT的毫秒 `数`  。 |
    | ------ | ------------------------------------------------------------ |

- - | `int` | `compareTo(Date anotherDate)`  比较两个日期进行订购。 |
    | ----- | ----------------------------------------------------- |

- - | `boolean` | `equals(Object obj)`  比较两个日期来平等。 |
    | --------- | ------------------------------------------ |

- - | `boolean` | `after(Date when)`  测试此日期是否在指定日期之后。  |
    | --------- | --------------------------------------------------- |
    | `boolean` | `before(Date when)`  测试此日期是否在指定日期之前。 |

```java
//      正常方法
//        相对基准时间过去2000ms的时间
        d1.setTime(2000);
        long   time= d1.getTime();
        System.out.println(d1);
        System.out.println(time);

        Date   a=new  Date();
        Date   b=new  Date();

        System.out.println(a.compareTo(b));
```





## 二、Calendar类

### 1、包

java.util

### 2、作用

存储日期时间，处理日期时间。

### 3、它是抽象类

不能实例化！！

实例化它的子类GregorianCalendar。

### 4、常用方法

- - | `static Calendar` | `getInstance()`  使用默认时区和区域设置获取日历。 |
    | ----------------- | ------------------------------------------------- |

- - | `void` | `set(int field,  int value)`  将给定的日历字段设置为给定的值。 |
    | ------ | ------------------------------------------------------------ |

- - | `int` | `get(int field)`  返回给定日历字段的值。 |
    | ----- | ---------------------------------------- |

- - | `int` | `compareTo(Calendar anotherCalendar)`  比较时间值（从毫秒偏移量 [Epoch](#Epoch)由两个表示）  `Calendar`对象。 |
    | ----- | ------------------------------------------------------------ |

- - | `Date` | `getTime()`  返回一个 `Date`表示此物体 `Calendar`的时间值（毫秒从偏移 [Epoch](#Epoch) “）。 |
    | ------ | ------------------------------------------------------------ |

- - | `void` | `setTime(Date date)`  使用给定的 `Date`设置此日历的时间。 |
    | ------ | --------------------------------------------------------- |



## 三、日期格式化类

### 1、SimpleDateFormat

java.text.SimpleDateFormat  extends   DateFormat

作用：

用于将Date保存的日期时间，按照指定格式输出。



### 2、构造器

- - `SimpleDateFormat(String pattern)`  使用给定模式 `SimpleDateFormat`并使用默认的 [`FORMAT`](../../java/util/Locale.Category.html#FORMAT)语言环境的默认日期格式符号。

### 3、模式定义：

- > | Letter | Date or Time Component                           | Presentation                           | Examples                                    |
  > | ------ | ------------------------------------------------ | -------------------------------------- | ------------------------------------------- |
  > | `G`    | Era designator                                   | [Text](#text)                          | `AD`                                        |
  > | `y`    | Year                                             | [Year](#year)                          | `1996`; `96`                                |
  > | `Y`    | Week year                                        | [Year](#year)                          | `2009`; `09`                                |
  > | `M`    | Month in year (context sensitive)                | [Month](#month)                        | `July`; `Jul`; `07`                         |
  > | `L`    | Month in year (standalone form)                  | [Month](#month)                        | `July`; `Jul`; `07`                         |
  > | `w`    | Week in year                                     | [Number](#number)                      | `27`                                        |
  > | `W`    | Week in month                                    | [Number](#number)                      | `2`                                         |
  > | `D`    | Day in year                                      | [Number](#number)                      | `189`                                       |
  > | `d`    | Day in month                                     | [Number](#number)                      | `10`                                        |
  > | `F`    | Day of week in month                             | [Number](#number)                      | `2`                                         |
  > | `E`    | Day name in week                                 | [Text](#text)                          | `Tuesday`; `Tue`                            |
  > | `u`    | Day number of week (1 = Monday, ..., 7 = Sunday) | [Number](#number)                      | `1`                                         |
  > | `a`    | Am/pm marker                                     | [Text](#text)                          | `PM`                                        |
  > | `H`    | Hour in day (0-23)                               | [Number](#number)                      | `0`                                         |
  > | `k`    | Hour in day (1-24)                               | [Number](#number)                      | `24`                                        |
  > | `K`    | Hour in am/pm (0-11)                             | [Number](#number)                      | `0`                                         |
  > | `h`    | Hour in am/pm (1-12)                             | [Number](#number)                      | `12`                                        |
  > | `m`    | Minute in hour                                   | [Number](#number)                      | `30`                                        |
  > | `s`    | Second in minute                                 | [Number](#number)                      | `55`                                        |
  > | `S`    | Millisecond                                      | [Number](#number)                      | `978`                                       |
  > | `z`    | Time zone                                        | [General time zone](#timezone)         | `Pacific Standard Time`; `PST`; `GMT-08:00` |
  > | `Z`    | Time zone                                        | [RFC 822 time zone](#rfc822timezone)   | `-0800`                                     |
  > | `X`    | Time zone                                        | [ISO 8601 time zone](#iso8601timezone) | `-08`; `-0800`; `-08:00`                    |

### 4、方法

- - | `String` | `format(Date date)`  将日期格式化成日期/时间字符串。 |
    | -------- | ---------------------------------------------------- |

- - | `Date` | `parse(String source)`  从给定字符串的开始解析文本以生成日期。 |
    | ------ | ------------------------------------------------------------ |



```java
package com.hs;

import java.text.SimpleDateFormat;
import java.util.Date;

public class SimpleDateFormatDemo {

    public static void main(String[] args)  throws   Exception {

        Date d=new  Date();
        System.out.println(d);

        SimpleDateFormat   sdf=new SimpleDateFormat("yyyy-MM-dd HH:mm:ss E");
        String str = sdf.format(d);
        System.out.println(str);

        String  str2="1999-10-10 10:10:10 星期三";
        Date d2 = sdf.parse(str2);
        System.out.println(d2);

    }
}
```



## 四、LocalDate/LocalTime/LocalDateTime

### 1、jdk1.8新特性

java.time包下：

LocalDate/LocalTime/LocalDateTime



### 2、LocalDate

（1）作用：存储年月日

（2）方法：

- - | `static LocalDate` | `now()`  从默认时区的系统时钟获取当前日期。 |
    | ------------------ | ------------------------------------------- |

- - | `static LocalDate` | `of(int year,  int month, int dayOfMonth)`  从一年，一个月和一天获得一个 `LocalDate`的实例。 |
    | ------------------ | ------------------------------------------------------------ |

```java
//        创建一个对象，保存当前日期
        LocalDate   d1=LocalDate.now();
        System.out.println(d1);

//        创建一个对象，保存指定日期
        LocalDate   d2=LocalDate.of(2020,10,11);
        System.out.println(d2);

//        设置的方法
        LocalDate   d11=d1.withYear(2024);
        System.out.println(d11);

//        获取的方法
        System.out.println(d1.getYear());
        System.out.println(d1.getMonth());
        System.out.println(d1.getDayOfMonth());
        System.out.println(d1.getDayOfWeek());
        System.out.println(d1.getDayOfYear());
```



### 3、LocalTime

（1）作用：

存储时分秒

（2）方法：

- - | `static LocalTime` | `now()`  从默认时区的系统时钟获取当前时间。 |
    | ------------------ | ------------------------------------------- |

- - | `static LocalTime` | `of(int hour,  int minute)`  从一小时分钟获取一个 `LocalTime`的实例。 |
    | ------------------ | ------------------------------------------------------------ |

```java
package com.hs;

import java.time.LocalTime;

public class LocalTimeDemo {
    public static void main(String[] args) {

//        创建一个对象，保存当前的时分秒
        LocalTime   t1=LocalTime.now();
        System.out.println(t1);
//        创建一个对象，保存指定的时分秒
        LocalTime   t2=LocalTime.of(10,11,12);
        System.out.println(t2);

//        获取
        int hour = t1.getHour();
        int minute = t1.getMinute();
        int second = t1.getSecond();

        System.out.println(hour);
        System.out.println(minute);
        System.out.println(second);

//        设置
        LocalTime t3 = t1.withHour(14);
        System.out.println(t3);
        System.out.println(t1);


    }
}
```



### 4、LocalDateTime

（1）作用：

存储年月日时分秒=



（2）方法

- - | `static LocalDateTime` | `now()`  从默认时区的系统时钟获取当前的日期时间。 |
    | ---------------------- | ------------------------------------------------- |

- - | `static LocalDateTime` | `of(int year,  int month, int dayOfMonth, int hour, int minute, int second)`  从年，月，日，小时，分钟和秒获得 `LocalDateTime`的实例，将纳秒设置为零。 |
    | ---------------------- | ------------------------------------------------------------ |

```java
package com.hs;

import java.time.LocalDateTime;

public class LocalDateTimeDemo {

    public static void main(String[] args) {

//        创建一个对象，保存当前日期和时间
        LocalDateTime   dt1=LocalDateTime.now();
//        创建一个对象，保存指定的日期和时间
        LocalDateTime   dt2=LocalDateTime.of(2020,2,20,2,2,2);

        System.out.println(dt1);
        System.out.println(dt2);

//        获取
        System.out.println(dt1.getYear());
        System.out.println(dt1.getMonth());
        System.out.println(dt1.getDayOfMonth());
        System.out.println(dt1.getHour());
        System.out.println(dt1.getMinute());
        System.out.println(dt1.getSecond());

//        设置
        LocalDateTime localDateTime = dt1.withMonth(12);
        System.out.println(localDateTime);
    }
}
```

# 10异常处理

## 一、异常介绍

### 1、异常的结构

程序在编译或运行时，会出现各种问题。

这些问题分为两大类：错误和异常。

![img](https://img-blog.csdn.net/20180516222429743?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RvdWppbmxvbmcx/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

错误：大问题，不可以通过程序解决。比如：jvm运行错误，jvm内存溢出等等。

异常：小问题，可以通过程序解决。比如：解析异常，空指针异常，数组下标越界，类型转换异常，算数异常等。



### 2、异常导致的问题

异常发生，会导致程序无法继续执行，退出jvm。



## 二、异常分类

### 1、运行时异常

异常发生在程序运行时。

比如：NullPointException空指针异常，ArrayIndexOutofBoundsException数组下标越界，ClassCastException类型转换异常，ArithticException算术异常等。

```java
package com.hs;

public class NullPointExceptionDemo {

    public static void main(String[] args) {

        String  s=null;
        s.charAt(0);
        System.out.println("end");
    }
}
```



```java
package com.hs;

public class ArrayIndexOutofExceptionDemo {
    public static void main(String[] args) {

        int[]   a=new  int[3];
        System.out.println(a[3]);
        System.out.println("end");

    }
}
```



```java
package com.hs;

public class ClassCastExceptionDemo {
    public static void main(String[] args) {
        String  s="111";
        Object  o=s;
        Integer  in=(Integer) o;

        System.out.println("end");
    }
}
```



```java
package com.hs;

public class ArithmeticExceptionDemo {
    public static void main(String[] args) {
        System.out.println(10/0);
        System.out.println("end");
    }
}
```



### 2、非运行时异常（编译期异常）

异常发生在编译时。

比如：ParseException，解析异常。

```java
package com.hs;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class ParseExceptionDemo {

    public static void main(String[] args) throws ParseException {
        String  s="1999/9/9";
        SimpleDateFormat   sdf=new SimpleDateFormat("yyyy-MM-dd");

        Date d = sdf.parse(s);
        System.out.println(d);

        System.out.println("end");

    }
}
```

## 三、异常处理

### 1、声明抛出异常

只能解决编译期异常（非运行时异常）

编译可以通过，但是运行时还是可能会出现该异常导致程序中止。



使用： throws    异常类名

[修饰符]    返回值类型   方法名（[参数]）    throws    异常类名{

​		调用了可能出现异常的方法或构造器；

}





```java
package com.hs;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class ParseExceptionDemo {

    public static void main(String[] args)  throws   ParseException {
        String  s="1999/9/9";
        SimpleDateFormat   sdf=new SimpleDateFormat("yyyy-MM-dd");

        Date d = sdf.parse(s);
        System.out.println(d);

        System.out.println("end");

    }
}
```



### 2、捕获异常

既可以解决编译期异常，还能解决运行时异常，程序可以继续运行。

使用：try-catch-finally

语法：

try{

​	可能出现异常的代码

}catch(可以捕获的异常类型   异常对象名){

​	异常的处理代码

}

...

catch(可以捕获的异常类型   异常对象名){

​	异常的处理代码

}finally{

​	收尾代码：不管任何情况下都会在try-catch的最后执行。

​	如果try和catch中有return语句，先执行完finally再执行return语句！！！

}



```java
package com.hs;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class ParseExceptionDemo02 {
    public static void main(String[] args) {
        String  s="1999/9/9";
        SimpleDateFormat sdf=new SimpleDateFormat("yyyy-MM-dd");

        try{
            Date d = sdf.parse(s);
            System.out.println(d);
        }catch (ParseException  e){
            //这里面一句话不写，也表示处理成功了。
            System.out.println("解析异常处理成功");
        }


        System.out.println("end");
    }
}
```



```java
package com.hs;

import javax.sound.midi.Soundbank;

public class TryDemo {

    public   static   void   test1(int  i,String  s,int[]  a){
        System.out.println("begin");

        try {
            System.out.println(10 / i);
            s.charAt(0);
            System.out.println(a[10]);
        }
        /*catch (Exception  e){
            //打印异常信息
            //e.printStackTrace();
            System.out.println("捕获和处理所有异常");
        }*/
        catch (ArithmeticException  e){
            System.out.println("捕获到算术异常，处理完毕");
        }catch (NullPointerException e){
            System.out.println("捕获到空指针异常，处理完毕");
        }catch (ArrayIndexOutOfBoundsException  e){
            System.out.println("捕获到数组下标越界异常，处理完毕");
        }
        System.out.println("end");
    }

    public   static  int  test2(int  i){
        int   k=0;

        try {
            k=10/i;
            System.out.println("try end");
            return  10;
        }catch (ArithmeticException  e){
            System.out.println("catch   success");
            return  20;
        }finally {
            System.out.println("收尾工作");
            //return  30;
        }

        //return   k;
    }

    public static void main(String[] args) {
        //test1(9,null,new  int[]{1,2,3});
        int  kk=test2(0);
        System.out.println(kk);
    }

}
```





一个try，多个catch，最多一个finally。

finally不管任何情况下，都会最后执行！！



执行流程：

先执行try。

try中没有异常，然后执行finally，结束。

try中发生异常，直接执行catch，最后执行finally，结束。







## 四、自定义异常（了解）

### 1、编写过银行账户类：取款操作。

余额不足的问题。

我们今天就写一个余额不足的异常。



### 2、继承Exception方式，自定义异常（所有类型异常）

```java
package com.hs;

public class BalanceNotEnoughException extends Exception{

    public BalanceNotEnoughException() {
        super("余额不足");
    }
}
```



```java
package com.hs;

public class Account {
    private   int  accid;
    private   String  name;
    private   String  passwd;
    private   double  balance;

    public int getAccid() {
        return accid;
    }

    public void setAccid(int accid) {
        this.accid = accid;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getPasswd() {
        return passwd;
    }

    public void setPasswd(String passwd) {
        this.passwd = passwd;
    }

    public double getBalance() {
        return balance;
    }

    public void setBalance(double balance) {
        this.balance = balance;
    }


    //取款
    public   void   deposit(double  money) throws BalanceNotEnoughException {
        if(money>balance){
            //System.out.println("余额不足");
            throw  new BalanceNotEnoughException();
        }
        balance-=money;
    }
}
```



```java
package com.hs;

public class Test {
    public static void main(String[] args)  {

        Account  acc=new Account();
        try {
            acc.deposit(1000);
        } catch (BalanceNotEnoughException e) {
            e.printStackTrace();
        }

    }
}
```



### 3、继承RuntimeException方式，自定义异常（运行时异常）

```java
package com.hs;

//public class BalanceNotEnoughException extends Exception{
public class BalanceNotEnoughException extends RuntimeException{
    public BalanceNotEnoughException() {
        super("余额不足");
    }
}
```





## 五、instanceof用法

### 1、作用

判断一个引用类型的对象是否属于某种类型。



### 2、语法

对象名   instanceof      引用类型名



### 3、案例

```java
package com.hs;

public class InstanceOfDemo {
    public static void main(String[] args) {
        Account   acc=new Account();

        System.out.println(acc  instanceof   Account);
        System.out.println(acc  instanceof   Object);

//        System.out.println(1  instanceof  int);
//        只能用于引用类型的判断，不能用于基本类型。
        Integer   in=1;
        System.out.println(in   instanceof    Integer);
    }
}
```

# 11集合

## 一、集合

### 1、集合

（1）数组

数组是用来存储一组数据的大容器。

数组的缺点：数组的长度不能改变，元素不能增加和减少！

（2）集合

集合是用来存储一组数据的大容器。

集合的好处：长度可以改变，可以添加或减少元素。

### 2、集合框架结构

![img](https://img-blog.csdnimg.cn/20190310181825411.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2Rpd2Vpa2FuZw==,size_16,color_FFFFFF,t_70)



### 3、集合分类

Collection集合和Map集合。

![image-20210804153602414](11集合.assets/image-20210804153602414.png)

Collection集合特点：每个元素可以存储一条信息，值。

Map集合特点：每个元素可以存储两条信息，键值对。



## 二、Collection集合

### 1、Collection接口

java.util.Collection

抽象方法：

- - | `boolean` | `add(E e)`  确保此集合包含指定的元素（可选操作）。 |
    | --------- | -------------------------------------------------- |

- - | `boolean` | `remove(Object o)`  从该集合中删除指定元素的单个实例（如果存在）（可选操作）。 |
    | --------- | ------------------------------------------------------------ |

- - | `int` | `size()`  返回此集合中的元素数。 |
    | ----- | -------------------------------- |

- - | `boolean` | `isEmpty()`  如果此集合不包含元素，则返回 `true` 。 |
    | --------- | --------------------------------------------------- |

- - | `void` | `clear()`  从此集合中删除所有元素（可选操作）。 |
    | ------ | ----------------------------------------------- |

- - | `boolean` | `contains(Object o)`  如果此集合包含指定的元素，则返回 `true` 。 |
    | --------- | ------------------------------------------------------------ |



- - | `Iterator<E>` | `iterator()`  返回此集合中的元素的迭代器。 |
    | ------------- | ------------------------------------------ |

    

### 2、Collection集合分类

List集合和Set集合。

List集合的特点：有序的集合，元素有下标，从0开始。可以存储重复的元素。

Set集合的特点：无序的集合。不可以存储重复的元素。



## 三、List集合

### 1、List接口

List集合：有序的集合，元素有下标，从0开始。可以存储重复的元素。



List   extends   Collection:拥有上述Collection的抽象方法。

扩展的抽象方法：

- - | `E`  | `get(int index)`  返回此列表中指定位置的元素。 |
    | ---- | ---------------------------------------------- |

- - | `E`  | `set(int index, E element)`  用指定的元素（可选操作）替换此列表中指定位置的元素。 |
    | ---- | ------------------------------------------------------------ |

- - | `E`  | `remove(int index)`  删除该列表中指定位置的元素（可选操作）。 |
    | ---- | ------------------------------------------------------------ |

    

### 2、List实现类

ArrayList、Vector、LinkedList

![image-20210804160130350](11集合.assets/image-20210804160130350.png)

区别：

ArrayList采用数组的结构存储元素，查询比较快，增删改较慢。线程不安全，效率高。

Vector采用数组的结构存储元素，查询比较快，增删改较慢。线程安全，效率低。

LinkedList采用链表结构存储元素，查询较慢，增删改较快。线程不安全，效率高。



### 3、ArrayList使用



```java
package com.hs;

import java.util.ArrayList;
import java.util.List;

public class ListDemo {


    public static void main(String[] args) {

//      创建List集合对象
        List   a=new ArrayList();

//      获取集合的长度
        System.out.println(a.size());
//      判断是否是空集合
        System.out.println(a.isEmpty());

//        添加元素
        a.add("aaa");//0
        a.add("bbb");//1
        a.add("ccc");//2
        a.add("ddd");//3
        a.add("aaa");//4
        a.add("eee");//5
        a.add("aaa");//6
        a.add("fff");//7


//      获取集合的长度
        System.out.println(a.size());

//        删除元素
//        从前面删除
        a.remove("aaa");
        a.remove(0);

//        获取元素
        Object a0 = a.get(0);
        System.out.println(a0);

        System.out.println(a.size());

//      修改元素
        a.set(0,"yyy");
        System.out.println(a.get(0));

//        判断包含元素
        boolean contains = a.contains("aaa");
        System.out.println(contains);

//        清空集合
        a.clear();
        System.out.println(a.size());
    }
}
```



### 4、List集合的遍历

```java
List a=new ArrayList();
a.add("aaa");//0
a.add("bbb");//1
a.add("ccc");//2
a.add("ddd");//3
a.add("aaa");//4
a.add("eee");//5
a.add("aaa");//6
a.add("fff");//7
```

第一种，通过下标遍历

```java
//        第一种，根据下标
        for (int i = 0; i < a.size(); i++) {
            System.out.println(a.get(i));
        }
```



第二种，使用增强for遍历

```java
//        第二种，使用增强for
        for(Object   o : a){
            System.out.println(o);
        }
```



第三种，使用Iterator遍历

```java
//        第三种，使用迭代器Iterator
        Iterator it = a.iterator();
        while(it.hasNext()){
            Object o = it.next();
            System.out.println(o);
        }
```

![image-20210806104241907](11集合.assets/image-20210806104241907.png)

第四种，Lamda表达式遍历（jdk1.8）

```java
//        第四种，使用lamda表达式
        a.forEach((o)->{
            System.out.println(o);
        });
```



## 四、Set集合

### 1、Set接口

Set集合是无序的集合，不能存储重复的元素。



Set   extends   Collection：继承上述的7个常用方法。

但是Set集合限制了add方法！！！

如果该元素存在，那么不插入，返回false。



### 2、Set实现类

HashSet、TreeSet、LinkedHashSet



实现类的区别：

![image-20210805113448669](11集合.assets/image-20210805113448669.png)

```text
HashSet
HashSet有以下特点
 不能保证元素的排列顺序，顺序有可能发生变化
 不是同步的
 集合元素可以是null,但只能放入一个null
当向HashSet结合中存入一个元素时，HashSet会调用该对象的hashCode()方法来得到该对象的hashCode值，然后根据 hashCode值来决定该对象在HashSet中存储位置。
简单的说，HashSet集合判断两个元素相等的标准是两个对象通过equals方法比较相等，并且两个对象的hashCode()方法返回值相 等
注意，如果要把一个对象放入HashSet中，重写该对象对应类的equals方法，也应该重写其hashCode()方法。其规则是如果两个对 象通过equals方法比较返回true时，其hashCode也应该相同。另外，对象中用作equals比较标准的属性，都应该用来计算 hashCode的值。

LinkedHashSet
LinkedHashSet集合同样是根据元素的hashCode值来决定元素的存储位置，但是它同时使用链表维护元素的次序。这样使得元素看起 来像是以插入顺序保存的，也就是说，当遍历该集合时候，LinkedHashSet将会以元素的添加顺序访问集合的元素。
LinkedHashSet在迭代访问Set中的全部元素时，性能比HashSet好，但是插入时性能稍微逊色于HashSet。

TreeSet类
TreeSet是SortedSet接口的唯一实现类，TreeSet可以确保集合元素处于排序状态。TreeSet支持两种排序方式，自然排序 和定制排序，其中自然排序为默认的排序方式。向TreeSet中加入的应该是同一个类的对象。
TreeSet判断两个对象不相等的方式是两个对象通过equals方法返回false，或者通过CompareTo方法比较没有返回0
```





### 3、HashSet使用

HashSet不允许插入重复的元素。



```java
package com.hs;

import java.util.HashSet;
import java.util.Set;

public class SetDemo {

    public static void main(String[] args) {
//       创建Set集合对象
        Set set=new HashSet();

//        获取元素个数
        System.out.println(set.size());
        System.out.println(set.isEmpty());

//        添加元素
        set.add("aa");
        set.add("bb");
        set.add("cc");
        set.add("aa");
        set.add("aa");
        set.add("dd");

        System.out.println(set.size());

//        删除元素
        set.remove("aa");
        System.out.println(set.size());

//        是否包含
        boolean aa = set.contains("aa");
        System.out.println(aa);

//        清空集合
        set.clear();
        System.out.println(set.size());


    }
}
```



### 4、Set集合遍历



```java
//        1\增强for
        for(Object  o:set){
            System.out.println(o);
        }
```



```java
//        2\iterator
        Iterator it = set.iterator();
        while(it.hasNext()){
            Object o = it.next();
            System.out.println(o);
        }
```



```java
//        3forEach(lambda表达式)
            set.forEach((o) -> {
                System.out.println(o);
            });
```



### 5、HashSet去重原理

元素重复，需同时满足两个条件：

（1）两个元素的hashCode()相等；

（2）两个元素使用equals(..)比较，返回true。



String重写hashCode和equals方法。

八个包装类也重写hashCode和equals方法。



普通类：需要我们自己重写hashCode和equals方法。

```java
package com.hs;

public class Student {
    public Student() {
    }

    public Student(int num, String name) {
        this.num = num;
        this.name = name;
    }

    private   int  num;
    private  String  name;

    public int getNum() {
        return num;
    }

    public void setNum(int num) {
        this.num = num;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

//    重写
    @Override
    public  int   hashCode(){
        return  num;
    }

    @Override
    public   boolean  equals(Object  o){
        Student   s=(Student)o;
        if(this.num==s.num){
            return  true;
        }
        return  false;
    }
}
```



```java
package com.hs;

import java.util.HashSet;
import java.util.Set;

public class SetDemo03 {

    public static void main(String[] args) {
        Student   s1=new Student(1001,"张三1");
        Student   s2=new Student(1002,"张三2");
        Student   s3=new Student(1003,"张三3");
        Student   s4=new Student(1004,"张三4");
        Student   s5=new Student(1001,"张三5");

        Set set=new HashSet();
        set.add(s1);
        set.add(s2);
        set.add(s3);
        set.add(s4);
        set.add(s5);

        System.out.println(set.size());
    }
}
```



## 五、Map集合

### 1、Map集合的特点

每个元素是一个键值对。

每个元素由两部分构成，一部分叫键，一部分叫值。

键是唯一的，每个元素的键不能相同，而值是可以相同的。

比如：

1001,zhangsan   

1002,lisi

1003,wangwu

1004,lisi

1005,maliu



### 2、Map接口

- - | `V`  | `put(K key, V value)`  将指定的值与该映射中的指定键相关联（可选操作）。 |
    | ---- | ------------------------------------------------------------ |

- - | `V`  | `get(Object key)`  返回到指定键所映射的值，或 `null`如果此映射包含该键的映射。 |
    | ---- | ------------------------------------------------------------ |

- - | `V`  | `remove(Object key)`  如果存在（从可选的操作），从该地图中删除一个键的映射。 |
    | ---- | ------------------------------------------------------------ |



- - | `int` | `size()`  返回此地图中键值映射的数量。 |
    | ----- | -------------------------------------- |

- - | `boolean` | `isEmpty()`  如果此地图不包含键值映射，则返回 `true` 。 |
    | --------- | ------------------------------------------------------- |



- - | `boolean`     | `containsKey(Object key)`  如果此映射包含指定键的映射，则返回 `true` 。 |
    | ------------- | ------------------------------------------------------------ |
    | **`boolean`** | **`containsValue(Object value)`  如果此地图将一个或多个键映射到指定的值，则返回 `true` 。** |



- - | `void` | `clear()`  从该地图中删除所有的映射（可选操作）。 |
    | ------ | ------------------------------------------------- |



- - | `Set<K>` | `keySet()`  返回此地图中包含的键的[`Set`](../../java/util/Set.html)视图。 |
    | -------- | ------------------------------------------------------------ |

- - | `Collection<V>` | `values()`  返回此地图中包含的值的[`Collection`](../../java/util/Collection.html)视图。 |
    | --------------- | ------------------------------------------------------------ |

- - | `Set<Map.Entry<K,V>>` | `entrySet()`  返回此地图中包含的映射的[`Set`](../../java/util/Set.html)视图。 |
    | --------------------- | ------------------------------------------------------------ |

    



### 3、Map的实现类

HashMap 、HashTable 、 TreeMap



```text
HashMap：基于哈希表的 Map 接口的实现。此实现提供所有可选的映射操作，并允许使用 null 值和 null 键。（除了非同步和允许使用 null 之外，HashMap 类与 Hashtable 大致相同。）此类不保证映射的顺序，特别是它不保证该顺序恒久不变。为了优化HashMap空间的使用，您可以调优初始容量和负载因子。
(1)HashMap(): 构造一个具有默认初始容量 (16) 和默认加载因子 (0.75) 的空 HashMap
(2)HashMap(Map m): 构造一个映射关系与指定 Map 相同的新 HashMap
(3)HashMap(int initialCapacity): 构造一个带指定初始容量和默认加载因子 (0.75) 的空 HashMap
(4)HashMap(int initialCapacity, float loadFactor): 构造一个带指定初始容量和加载因子的空 HashMap

HashTable：实现一个哈希表，该哈希表将键映射到相应的值。任何非 null 对象都可以用作键或值，即不允许null键null值。
(1)Hashtable(): 用默认的初始容量 (11) 和加载因子 (0.75) 构造一个新的空哈希表
(2)Hashtable(Map m): 构造一个与给定的 Map 具有相同映射关系的新哈希表
(3)Hashtable(int initialCapacity): 用指定初始容量和默认的加载因子 (0.75) 构造一个新的空哈希表
(4)Hashtable(int initialCapacity, float loadFactor): 指定初始容量和指定加载因子构造一个新的空哈希表

TreeMap：基于红黑树实现。TreeMap没有调优选项，因为该树总处于平衡状态。不允许null键，允许null值。
(1)TreeMap():使用键的自然顺序构造一个新的、空的树映射
(2)TreeMap(Map m): 构建一个映像树，并且添加映像m中所有元素
(3)TreeMap(Comparator c): 构建一个映像树，并且使用特定的比较器对关键字进行排序
(4)TreeMap(SortedMap s): 构建一个映像树，添加映像树s中所有映射，并且使用与有序映像s相同的比较器排序

三种常规Map性能:
HashMap：适用于在Map中插入、删除和定位元素。
HashTable：单线程环境下，性能低，适用于完全的线程安全。
Treemap：适用于按自然顺序或自定义顺序遍历键(key)。

总结：
HashMap通常比TreeMap快一点(树和哈希表的数据结构使然)，建议多使用HashMap，在需要排序的Map时候才用TreeMap，仅在你需要完全的线程安全的时候使用Hashtable。
```



### 4、HashMap



```java
package com.hs;

import java.util.HashMap;
import java.util.Map;

public class MapDemo {
    public static void main(String[] args) {

//        创建map集合
        Map map=new HashMap();

//        获取键值对数量
        System.out.println(map.size());
        System.out.println(map.isEmpty());

//      添加键值对
        map.put(1001,"zhangsan");
        map.put(1002,"lisi");
        map.put(1003,"wangwu");
        map.put(1004,"maliu");

        System.out.println(map.size());

//      获取元素
        System.out.println(map.get(1001));
        System.out.println(map.get(1002));
        System.out.println(map.get(1003));
        System.out.println(map.get(1004));

//        删除元素
        map.remove(1001);
        System.out.println(map.size());
        System.out.println(map.get(1001));

//        判断是否包含指定的键或值
        System.out.println(map.containsKey(1001));
        System.out.println(map.containsValue("lisi"));

//        清空集合
        map.clear();

    }
}
```





### 5、Map集合遍历



```java
package com.hs;

import java.util.Collection;
import java.util.HashMap;
import java.util.Map;
import java.util.Set;

public class MapDemo02 {
    public static void main(String[] args) {

//        创建map集合
        Map map=new HashMap();

//      添加键值对
        map.put(1001,"zhangsan");
        map.put(1002,"lisi");
        map.put(1003,"wangwu");
        map.put(1004,"maliu");
//        修改操作：修改键对应的值
        map.put(1001,"zhangsanfen");
        map.put(1005,"lisi");

//        System.out.println(map.size());
//        System.out.println(map.get(1001));

//        获取所有元素的键，以set集合返回
        Set ks = map.keySet();

        ks.forEach((k)->{
            System.out.println(k);
        });

//        获取所有元素的值，以Collection集合返回
        Collection vs = map.values();
        vs.forEach((v)->{
            System.out.println(v);
        });

//        获取所有的键值对，以Set集合返回
//        每个键值对使用Map.Entry类型存储
        Set set = map.entrySet();
        for(Object   o:set){
            Map.Entry   entry =(Map.Entry)o;
            System.out.println(entry.getKey()+","+entry.getValue());
        }
        
        //       等价键值对遍历
//        先找到所有元素的键，然后在根据键找值
        Set ks1 = map.keySet();
        for(Object  k:ks1){
            Object v = map.get(k);
            System.out.println(k+"="+v);
        }

    }
}
```







## 六、泛型

### 1、泛型的由来

泛型是jdk1.5才有的技术。



### 2、泛型的解释

广泛的引用数据类型

【参数化数据类型】



如同数学中的未知数，我们不知道这个数具体是多少时，是用未知数表示。

我们不能确定具体的数据类型，我们使用泛型表示。



### 3、泛型的定义

泛型一般使用26个大写字母表示。



```java
package com.hs;

public class TestFx<A,B> {

    private  A   num;
    private  B    name;

    public  void  setNum(A  num){
        this.num=num;
    }

    public  A   getNum(){
        return num;
    }

}
```



### 4、泛型的使用

```java
package com.hs;

public class Test {
    public static void main(String[] args) {

//        A=Object  B=Object
        TestFx   fx1=new TestFx();
        fx1.setNum(new Object());

//       A=Integer   B=String
        TestFx<Integer,String>   fx2=new TestFx<Integer,String>();
        fx2.setNum(1001);

//        A=String   B=String
        TestFx<String,String>   fx3=new TestFx<String,String>();
        fx3.setNum("s1001");

    }
}
```





### 5、集合中的泛型使用（必须掌握）

```java
package com.hs;

import java.util.*;

public class Test2 {
    public static void main(String[] args) {
//      list集合泛型的使用
//        指定泛型为String，所以每个元素是String类型
        List<String>    list=new ArrayList<String>();
        list.add("aa");
        list.add("bb");
        list.add("cc");

        //String s1 = list.get(0);
        for (String  s:list){
            System.out.println(s);
        }

//      set集合泛型的使用
//      指定set集合的泛型为Integer，元素就是Integer
        Set<Integer> set=new HashSet<>();
        set.add(11);
        set.add(22);
        set.add(33);

        for (Integer   i:set){
            System.out.println(i);
        }

//        map集合泛型的使用
//          键是String，值是Integer
        Map<String,Integer>   map=new HashMap<>();
        map.put("a",10);
        map.put("b",11);
        map.put("c",20);

        Set<String>   keys=map.keySet();
        for(String  k:keys){
            System.out.println(k);
        }

        Collection<Integer> values = map.values();
        for (Integer  v:values){
            System.out.println(v);
        }

        Set<Map.Entry<String, Integer>> entries = map.entrySet();
        for (Map.Entry<String, Integer>   entry:entries){
            System.out.println(entry.getKey()+" "+entry.getValue());
        }


        Set<String>   keys2=map.keySet();
        for(String  k:keys2){
            Integer v = map.get(k);
            System.out.println(k+"+"+v);
        }


    }
}
```



### 6、泛型的好处

避免了复杂的类型转换。



## 七、集合工具类

### 1、Arrays数组工具类

（1）该类包含用于操作数组的各种方法（如排序和搜索）。 



常用方法：

- - | `static <T> List<T>` | `asList(T... a)`  返回由指定数组支持的固定大小的列表。 |
    | -------------------- | ------------------------------------------------------ |

- - | `static int` | `binarySearch(int[] a,  int key)`  使用二叉搜索算法搜索指定的int数组的指定值。 |
    | ------------ | ------------------------------------------------------------ |

- - | `static void` | `sort(int[] a)`  按照数字顺序排列指定的数组。 |
    | ------------- | --------------------------------------------- |

```java
import java.util.Arrays;
import java.util.List;

public class ArraysDemo {

    public static void main(String[] args) {


//     1  将多个值转为List
        List    list= Arrays.asList(1,2,3,4,5);
        for (Object o : list) {
            System.out.println( o);
        }

//        2  排序
        int[]   arr={3,1,5,2,4};
        Arrays.sort(arr);
        for (int i : arr) {
            System.out.println(i);
        }

//        3  二分查找法
//        需要先排序：1 2 3 4 5
        int i = Arrays.binarySearch(arr, 4);
        System.out.println(i);
    }

}
```



（2）二分查找法

前提：先排序！！

![img](https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimage.bubuko.com%2Finfo%2F201805%2F20180508183939096755.png&refer=http%3A%2F%2Fimage.bubuko.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1630830183&t=fd6fe91b5dc28334a8835dc74f3500e6)



### 2、Collections集合工具类

- 它包含对集合进行操作的多态算法



常用的方法：

- - | `static <T> int` | `binarySearch(List<?  extends Comparable<? super T>> list,  T key)`  使用二叉搜索算法搜索指定对象的指定列表。 |
    | ---------------- | ------------------------------------------------------------ |

- - | `static <T extends Comparable<? super  T>>void` | `sort(List<T> list)`  根据其元素的[natural ordering](../../java/lang/Comparable.html)对指定的列表进行排序。 |
    | ----------------------------------------------- | ------------------------------------------------------------ |

- - | `static void` | `reverse(List<?> list)`  反转指定列表中元素的顺序。 |
    | ------------- | --------------------------------------------------- |

- - | `static <T extends Object & Comparable<? super  T>>T` | `max(Collection<? extends  T> coll)`  根据其元素的 *自然顺序*返回给定集合的最大元素。 |
    | ----------------------------------------------------- | ------------------------------------------------------------ |

- - | `static <T extends Object & Comparable<? super  T>>T` | `min(Collection<? extends  T> coll)`  根据其元素的 *自然顺序*返回给定集合的最小元素。 |
    | ----------------------------------------------------- | ------------------------------------------------------------ |



```java
package com.hs;

import jdk.nashorn.internal.runtime.linker.LinkerCallSite;

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class CollectionsDemo {
    public static void main(String[] args) {
        List<Integer>  list=new ArrayList<>();
        list.add(3);
        list.add(5);
        list.add(1);
        list.add(4);
        list.add(2);

        Collections.sort(list);
//        Collections.reverse(list);
        for (Integer i : list) {
            System.out.println(i);
        }

        int i = Collections.binarySearch(list, 4);
        System.out.println(i);

        Integer max = Collections.max(list);
        System.out.println(max);

        Integer min = Collections.min(list);
        System.out.println(min);
    }
}
```





## 八、BigDecimal类

### 1、遇到的问题

（1）数字的范围超出了long、double的存储范围。

（2）十进制的小数转二进制的小数时，float和double会丢失精度。

（3）小数的精度不够。double小数精度是16位，超出怎么办？

（4）金融项目对数据的精度要求非常高。



### 2、BigDecimal类

专门解决以上问题的数字类。

Java在java.math包中提供的API类BigDecimal，用来对超过16位有效位的数进行精确的运算。



### 3、构造器

BigDecimal(int)       创建一个具有参数所指定整数值的对象。 
BigDecimal(double) 创建一个具有参数所指定双精度值的对象。 //不推荐使用
BigDecimal(long)    创建一个具有参数所指定长整数值的对象。 
BigDecimal(String) 创建一个具有参数所指定以字符串表示的数值的对象。//推荐使用



### 4、常用方法

BigDecimal存储是一个对象，不能使用算数运算符计算，只能使用提供的方法来运算。



add(BigDecimal)        BigDecimal对象中的值相加，然后返回这个对象。 
subtract(BigDecimal) BigDecimal对象中的值相减，然后返回这个对象。 
multiply(BigDecimal)  BigDecimal对象中的值相乘，然后返回这个对象。 
divide(BigDecimal)     BigDecimal对象中的值相除，然后返回这个对象。 

toString()                将BigDecimal对象的数值转换成字符串。 
doubleValue()          将BigDecimal对象中的值以双精度数返回。 
floatValue()             将BigDecimal对象中的值以单精度数返回。 
longValue()             将BigDecimal对象中的值以长整数返回。 
intValue()               将BigDecimal对象中的值以整数返回。

```java
package com.hs;

import java.math.BigDecimal;

public class BigDecimalDemo {
    public static void main(String[] args) {

//        推荐使用字符串构造器
        BigDecimal    big1=new BigDecimal("123.171717161623738761873626326");
        BigDecimal    big2=new BigDecimal("123.171717161623738761873626326");

//        加减乘除运算
        BigDecimal add = big1.add(big2);
        BigDecimal subtract = big1.subtract(big2);
        BigDecimal multiply = big1.multiply(big2);
        BigDecimal divide = big1.divide(big2);

        System.out.println(add);
        System.out.println(subtract);
        System.out.println(multiply);
        System.out.println(divide);
    }
}
```



### 5、舍入模式

我们在加减乘除时，可以设置保留精度。



ROUND_CEILING    //向正无穷方向舍入
ROUND_DOWN    //向零方向舍入
ROUND_FLOOR    //向负无穷方向舍入
ROUND_HALF_DOWN    //向（距离）最近的一边舍入，除非两边（的距离）是相等,如果是这样，向下舍入, 例如1.55 保留一位小数结果为1.5
ROUND_HALF_EVEN    //向（距离）最近的一边舍入，除非两边（的距离）是相等,如果是这样，如果保留位数是奇数，使用ROUND_HALF_UP，如果是偶数，使用ROUND_HALF_DOWN
ROUND_HALF_UP    //向（距离）最近的一边舍入，除非两边（的距离）是相等,如果是这样，向上舍入, 1.55保留一位小数结果为1.6,也就是我们常说的“四舍五入”
ROUND_UNNECESSARY    //计算结果是精确的，不需要舍入模式
ROUND_UP    //向远离0的方向舍入



```java
//      舍入模式        BigDecimal divide1 = big1.divide(big2, 2, RoundingMode.HALF_UP);        System.out.println(divide1);
```





## 九、HashMap的底层实现

### 1、底层实现

HashMap底层实现：数组+链表+红黑树。



![image-20210809110551351](11集合.assets/image-20210809110551351.png)



### 2、源码分析

put方法流程

（1）根据key计算hash值（key.hashCode进行扰乱hash(key)，目的是减少重复）

（2）如果是第一次添加，会创建一个长度为16的数组，阈值12.

（3）通过hash码和(n-1)进行按位与运算，得到一个下标。

（4）插入元素：

第一种情况：当前位置为null，直接插入新元素。

第二种请况：不为null，已经有元素。

​					a、只有一个元素，且旧元素的key和新元素的key相等，将做修改操作。

​					b、元素是红黑树，将新元素添加到红黑树上。（如果红黑树中有一个元素的key和新元素的key相等，将做修改操作）。

​					c。如果是链表，将新元素插入链表尾部。（如果链表中有一个元素的key和新元素的key相等，将做修改操作）。（插入后，如果链表的长度大于8且数组的长度大于64位，将链表转为红黑树）

​	（5）扩容：

如果数组的有效元素个数大于阈值（数组的长度 * 0.75），需要进行扩容，数组的老长度 * 2。

扩容之后，需要对所有map元素进行重新排列。	





get方法流程：

（1）通过key获取hash

（2）通过hash转换成下标

（3）查找数组的元素

如果对应的数组元素为null，返回null；

如果不为null，又分为集中情况：

​						情况1：如果只有一个map元素，比较key是否相等。

​									相等，返回该元素；不相等返回null.

​						情况2：

​									如果是红黑树，通过key比较从红黑树中找，找到返回元素，否则返回null。

​						情况3：如果是链表，荣国key比较从链表中查找，找到返回元素，否则返回null。	







resize方法的流程：

（1）如果是第一次，创建长度为16的数组，阈值是12(数组16*加载因子0.75）

（2）如果数组中有效元素的个数超过了阈值，进行扩容数组的长度 * 2，阈值 * 2。

（3）扩容后，map元素需要在数组中重新排列。		





### 3、HashSet

底层是通过HashMap实现的。



# 12文件类和IO流

## 一、File类

### 1、用途

java.io.File

File对象用于表示磁盘上的文件或目录，然后使用File对象操作表示的文件或目录。

### 2、构造器

- - | `File(File parent, String child)`  从父抽象路径名和子路径名字符串创建新的 `File`实例。 |
    | ------------------------------------------------------------ |
    | `File(String pathname)`  通过将给定的路径名字符串转换为抽象路径名来创建新的 `File`实例。 |
    | `File(String parent,  String child)`  从父路径名字符串和子路径名字符串创建新的 `File`实例。 |



```java
//        创建一个File对象f1,用来表示C:\Users\lx\Desktop\JavaSe\09练习任务0803.txt文件
        File   f1=new File("C:\\Users\\lx\\Desktop\\JavaSe\\09练习任务0803.txt");
//        创建一个File对象f2,用来表示C:\Users\lx\Desktop\JavaSe目录
        File   f2=new File("C:\\Users\\lx\\Desktop\\JavaSe");

        File   f11=new File("C:\\Users\\lx\\Desktop\\JavaSe","09练习任务0803.txt");
        File   f21=new File("C:\\Users\\lx\\Desktop","JavaSe");

        File   f01=new File("C:\\Users\\lx\\Desktop\\JavaSe");
        File   f02=new File("C:\\Users\\lx\\Desktop");
        File   f12=new File(f01,"09练习任务0803.txt");
        File   f22=new File(f02,"JavaSe");
```



### 3、方法

- - | `boolean` | `exis ts()`  测试此抽象路径名表示的文件或目录是否存在。 |
    | --------- | ------------------------------------------------------- |

- - | `boolean` | `isDirectory()`  测试此抽象路径名表示的文件是否为目录。 |
    | --------- | ------------------------------------------------------- |
    | `boolean` | `isFile()`  测试此抽象路径名表示的文件是否为普通文件。  |



判断和查询方法：

```java
package com.hs;

import java.io.File;
import java.util.Date;

public class FileDemo {
    public static void main(String[] args) {

//        创建一个File对象f1,用来表示C:\Users\lx\Desktop\JavaSe\09练习任务0803.txt文件
        File   f1=new File("C:\\Users\\lx\\Desktop\\JavaSe\\09练习任务0803.txt");
//        创建一个File对象f2,用来表示C:\Users\lx\Desktop\JavaSe目录
        File   f2=new File("C:\\Users\\lx\\Desktop\\JavaSe");

        File   f11=new File("C:\\Users\\lx\\Desktop\\JavaSe","09练习任务0803.txt");
        File   f21=new File("C:\\Users\\lx\\Desktop","JavaSe");

        File   f01=new File("C:\\Users\\lx\\Desktop\\JavaSe");
        File   f02=new File("C:\\Users\\lx\\Desktop");
        File   f12=new File(f01,"09练习任务0803.txt");
        File   f22=new File(f02,"JavaSe");

//      常用方法：
//        表示的文件或目录是否真的存在？
        File   f3=new  File("C:\\Users\\lx\\Desktop\\JavaSe\\09.txt");
        File   f4=new  File("C:\\Users\\lx\\Desktop\\JavaSe02");
        System.out.println(f1.exists());
        System.out.println(f2.exists());
        System.out.println(f3.exists());
        System.out.println(f4.exists());


//        判断是否表示的是文件？
        System.out.println(f1.isFile());
        System.out.println(f2.isFile());
//        判断是否表示的是目录？
        System.out.println(f1.isDirectory());
        System.out.println(f2.isDirectory());

//        获取文件或目录信息
//        获取文件名或目录名
        System.out.println(f1.getName());
        System.out.println(f2.getName());

//        获取文件或目录的路径
        System.out.println(f1.getPath());
        System.out.println(f2.getPath());

//        获取文件或目录的可读、可写、可执行、是否是隐藏属性信息
        System.out.println(f1.canRead());
        System.out.println(f1.canWrite());
        System.out.println(f1.canExecute());
        System.out.println(f1.isHidden());

        System.out.println(f2.canRead());
        System.out.println(f2.canWrite());
        System.out.println(f2.canExecute());
        System.out.println(f2.isHidden());

//        获取最后修改时间
        System.out.println(new  Date(f1.lastModified()));
        System.out.println(new Date(f2.lastModified()));

//        获取内容的长度，单位是字节
        System.out.println(f1.length());//返回文件中的数据大小
        System.out.println(f2.length());//返回文件夹占用的空间，默认4096

    }
}
```

遍历目录：

```java
//        目录的遍历方法
//        获取当前目录包含的所有子目录名和文件名
        String[] list = f2.list();
        for (String s : list) {
            System.out.println(s);
        }

//      获取当前目录包含的所有子目录对象和文件对象
        File[] files = f2.listFiles();
        for (File file : files) {
            System.out.println(file.getName());
        }
```



创建和删除操作

```java
//        新建和删除方法
        File   f5=new File("C:\\Users\\lx\\Desktop\\1.txt");

        if(!f5.exists()){
//            在磁盘中创建这个文件
            try {
                f5.createNewFile();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }

        if(f5.exists()){
//            删除磁盘中的这个文件
            f5.delete();
        }


        File   f6=new File("C:\\Users\\lx\\Desktop\\a");
        if(!f6.exists()){
//            在磁盘上创建目录
            //f6.mkdir();
            f6.mkdirs();
        }

        if(f6.exists()){
//            删除磁盘上的目录
            f6.delete();
        }


        File   f7=new File("C:\\Users\\lx\\Desktop\\b\\c");
//        如果父目录不存在，创建失败
        //f7.mkdir();
//        如果父目录不存在，先建父目录，在建当前目录
        f7.mkdirs();
```



## 二、IO流

### 1、IO流作用

作用：数据传输。

传输过程包含：读，写。



### 2、IO流的分类

（1）从传输方向，分为输入流和输出流。

输入流：负责读取数据。

输出流：负责写入数据。



（2）从处理单位，分为字节流和字符流。

字节流：按照字节为单位进行传输。

字符流：按照字符为单位进行传输。



（3）从功能上，分为节点流和高级流。

节点流：只有读写功能。

高级流：除了读写，还有其他功能的流。



### 3、字节流

按照字节为单位进行读写。

（1）字节输入流

## InputStream

以字节为单位，读取数据

抽象类，不能实例化。

- - 已知直接子类： (读取的数据源不同)

    [AudioInputStream](../../javax/sound/sampled/AudioInputStream.html) ， [ByteArrayInputStream](../../java/io/ByteArrayInputStream.html) ， [FileInputStream](../../java/io/FileInputStream.html) ，  [FilterInputStream](../../java/io/FilterInputStream.html) ， [InputStream](../../org/omg/CORBA/portable/InputStream.html) ， [ObjectInputStream](../../java/io/ObjectInputStream.html) ， [PipedInputStream](../../java/io/PipedInputStream.html)  ， [SequenceInputStream](../../java/io/SequenceInputStream.html) ， [StringBufferInputStream](../../java/io/StringBufferInputStream.html) 



FileInputStream：从文件中读取数据。

构造器：

- - 

    | `FileInputStream(File file)`  通过打开与实际文件的连接创建一个 `FileInputStream` ，该文件由文件系统中的  `File`对象 `file`命名。 |
    | ------------------------------------------------------------ |
    | `FileInputStream(String name)`  通过打开与实际文件的连接来创建一个 `FileInputStream` ，该文件由文件系统中的路径名  `name`命名。 |

    

方法：

- - 

    | `void` | `close()`  关闭此文件输入流并释放与流相关联的任何系统资源。 |
    | ------ | ----------------------------------------------------------- |

    

- - 

    | `int` | `read()`  从该输入流读取一个字节的数据。                     |
    | ----- | ------------------------------------------------------------ |
    | `int` | `read(byte[] b)`  从该输入流读取最多 `b.length`个字节的数据为字节数组。 |
    | `int` | `read(byte[] b,  int off, int len)`  从该输入流读取最多 `len`字节的数据为字节数组。 |

    

```java
package com.hs;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;

public class FileInputStreamDemo {
    public static void main(String[] args) throws IOException {

//        1、创建一个字节输入流，指定读取的数据源
        FileInputStream  fin=new FileInputStream("C:\\Users\\lx\\Desktop\\b\\1.txt");
        FileInputStream  fin2=new        FileInputStream(new File("C:\\Users\\lx\\Desktop\\b\\1.txt"));

//        2、从数据源文件中，读取数据
//        (1)第一种:每次读取一个字节的数据，返回读取到的数据。
//        如果读到末尾，返回-1.
//        int   i=fin.read();
//        System.out.println((char)i);
//
//        int   i2=fin.read();
//        System.out.println((char)i2);
//
//        int   i3=fin.read();
//        System.out.println((char)i3);
//
//        int   i4=fin.read();
//        System.out.println((char)i4);

//        int   i=fin.read();
//        while(i!=-1){
//            System.out.println((char)i);
//            i=fin.read();
//        }

//        (2)第二种：每次读取数组长度的字节数数据
//        一次可以读取5个字节的数据，然后将数据保存在b中，最后返回实际读取到的字节数。
//        如果到达末尾，再读，返回-1.
//        byte[]   b=new  byte[5];
//        int i = fin.read(b);
//        System.out.println(new String(b));
//        System.out.println(i);

//        byte[]   b=new  byte[5];
//        int i = fin.read(b);
//        while(i!=-1){
//            System.out.println(new String(b,0,i));
//            i = fin.read(b);
//        }

//          第三种：每次读取指定长度的字节数
//        每次读取3个字节的数据，存储在b中，但是从下标为1的元素开始存储。
//        返回实际读取到的字节数
//        读到末尾，没有数据可读。返回-1.
        byte[]  b=new  byte[5];
        int i=fin.read(b,1,3);

        while(i!=-1){
            System.out.println(new  String(b,1,i));
            i=fin.read(b,1,3);
        }

//       3、 关闭流(切断对流对象的引用，让gc回收该流对象，防止内存溢出)
        fin.close();

    }
}
```



（2）字节输出流

## OutputStream

作用：按照字节写入数据。

它是抽象类，不能实例化！！



- - 已知直接子类： （写入目标不同）

    [ByteArrayOutputStream](../../java/io/ByteArrayOutputStream.html) ， [FileOutputStream](../../java/io/FileOutputStream.html)  ， [FilterOutputStream](../../java/io/FilterOutputStream.html) ， [ObjectOutputStream](../../java/io/ObjectOutputStream.html) ， [OutputStream](../../org/omg/CORBA/portable/OutputStream.html) ， [PipedOutputStream](../../java/io/PipedOutputStream.html)



FileOutputStream:将数据写入文件。

构造器：

- - | `FileOutputStream(File file)`  创建文件输出流以写入由指定的 `File`对象表示的文件。 |
    | ------------------------------------------------------------ |
    | `FileOutputStream(File file,  boolean append)`  创建文件输出流以写入由指定的 `File`对象表示的文件。 |
    | `FileOutputStream(String name)`  创建文件输出流以指定的名称写入文件。 |
    | `FileOutputStream(String name,  boolean append)`  创建文件输出流以指定的名称写入文件。 |



方法：

- - | `void` | `close()`  关闭此文件输出流并释放与此流相关联的任何系统资源。 |
    | ------ | ------------------------------------------------------------ |



- - | `void` | `write(byte[] b)`  将 `b.length`个字节从指定的字节数组写入此文件输出流。 |
    | ------ | ------------------------------------------------------------ |
    | `void` | `write(byte[] b,  int off, int len)`  将 `len`字节从位于偏移量 `off`的指定字节数组写入此文件输出流。 |
    | `void` | `write(int b)`  将指定的字节写入此文件输出流。               |



```java
package com.hs;

import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;

public interface FileOutputStreamDemo {
    public static void main(String[] args) throws IOException {

//        1\创建文件字节输出流，指定写入文件的路径
//        默认是覆盖，原来的内容被替换
//        FileOutputStream   fout1=new FileOutputStream("C:\\Users\\lx\\Desktop\\b\\2.txt");
//        如果想要追加内容，需要使用两个参数的构造器，第二个参数设置为true
        FileOutputStream   fout=new FileOutputStream("C:\\Users\\lx\\Desktop\\b\\2.txt",true);

//        2\写入数据
//        (1)第一种：一次写入一个字节数据
//        fout.write('a');
//        fout.write('b');
//        fout.write('c');
//        fout.write('d');

//        String  s="abcd我爱肖老师";
//        byte[] bytes = s.getBytes();
//        for (byte b : bytes) {
//            fout.write(b);
//        }

//        (2)第二种：一次写入数组长度的数据
        String  s="123abcd我爱肖老师";
        byte[] bytes = s.getBytes();
        fout.write(bytes);

//         （3）第三种：一次写入数组中指定部分数据。
//        String  s="123abcd我爱肖老师";
//        byte[] bytes = s.getBytes();
//        fout.write(bytes,2,5);

//        3、关闭流
        fout.close();

    }
}
```



（4）文件拷贝

先读，后写。

既要用输入流，又要用输出流。

```java
package com.hs;

import java.io.*;

public class IOCopy {
    public static void main(String[] args) throws IOException {
//        文件拷贝
//        1\创建流
        FileInputStream   in=new FileInputStream("C:\\Users\\lx\\Desktop\\b\\2.txt");
        FileOutputStream  out=new FileOutputStream("D:\\2.txt");

//        2\读和写
        byte[]  b=new byte[10];
        int  i=in.read(b);
        while(i!=-1){
            out.write(b,0,i);
            i=in.read(b);
        }

//        3、关闭流
        out.close();
        in.close();

//        4、剪切
//        删除源文件
        File  f=new File("C:\\Users\\lx\\Desktop\\b\\2.txt");
        if(f.exists()){
            f.delete();
        }

    }
}
```





### 4、字符流

以字符为单位进行读写的流。

字节byte    字符char

一个汉字是两个字节，使用字节流需要读写两次，使用字符流只需一次。



（1）字符输入流

## Reader

字符输入流的顶级父类。

以字符为单位进行读取数据。

抽象类，不能实例化。



- - 已知直接子类： （根据数据源类型不同）

    [BufferedReader](../../java/io/BufferedReader.html) ， [CharArrayReader](../../java/io/CharArrayReader.html) ，  [FilterReader](../../java/io/FilterReader.html) ， [InputStreamReader](../../java/io/InputStreamReader.html) ， [PipedReader](../../java/io/PipedReader.html) ， [StringReader](../../java/io/StringReader.html)



常用FileReader:读取文件

FileReader  extends  InputStreamReader



构造器：

- - | `FileReader(File file)`  创建一个新的 `FileReader` ，给出 `File`读取。 |
    | ------------------------------------------------------------ |
    | `FileReader(String fileName)`  创建一个新的 `FileReader` ，给定要读取的文件的名称。 |



方法：

- - | `void` | `close()`  关闭流并释放与之相关联的任何系统资源。 |
    | ------ | ------------------------------------------------- |

    

- | `int`          | `read()`  读一个字符                                         |
  | -------------- | ------------------------------------------------------------ |
  | `int`          | `read(char[] cbuf)`  将字符读入数组。                        |
  | `abstract int` | `read(char[] cbuf,  int off, int len)`  将字符读入数组的一部分。 |



```java
package com.hs;

import java.io.FileNotFoundException;
import java.io.FileReader;

public class FileReaderDemo {


    public static void main(String[] args) throws Exception {


//        1\创建字符输入流
        FileReader    reader=new FileReader("C:\\Users\\lx\\Desktop\\b\\22.txt");

//        2、读取数据
//        第一种：读取一个字符
//        int i = reader.read();
//        while(i!=-1){
//            System.out.println((char)i);
//            i = reader.read();
//        }

//        第二种：一次读取数组长度的字符数
//        char[]    cc=new char[5];
//        int  i=reader.read(cc);
//        while(i!=-1){
//            System.out.println(new  String(cc,0,i));
//            i=reader.read(cc);
//        }

//        第三种：一次读取指定长度字符，存于数组中指定位置
        char[]    cc=new char[5];
        int  i=reader.read(cc,1,3);
        while(i!=-1){
            System.out.println(new  String(cc,1,i));
            i=reader.read(cc,1,3);
        }


//        3、关闭流
            reader.close();


    }
}
```



（2）字符输出流

## Writer

字符输出流的顶级父类。

以字符为单位进行写入数据。

抽象类，不能实例化。



- - 已知直接子类： （写入目标类型的不同）

    [BufferedWriter](../../java/io/BufferedWriter.html) ， [CharArrayWriter](../../java/io/CharArrayWriter.html) ，  [FilterWriter](../../java/io/FilterWriter.html) ， [OutputStreamWriter](../../java/io/OutputStreamWriter.html) ， [PipedWriter](../../java/io/PipedWriter.html) ， [PrintWriter](../../java/io/PrintWriter.html) ， [StringWriter](../../java/io/StringWriter.html) 





常用FileWriter：写入文件

FileWriter   extends    OutputStreamReader



构造器：

- - | `FileWriter(File file)`  给一个File对象构造一个FileWriter对象。 |
    | ------------------------------------------------------------ |
    | `FileWriter(File file,  boolean append)`  给一个File对象构造一个FileWriter对象。 |
    | `FileWriter(String fileName)`  构造一个给定文件名的FileWriter对象。 |
    | `FileWriter(String fileName, boolean append)`  构造一个FileWriter对象，给出一个带有布尔值的文件名，表示是否附加写入的数据。 |



方法：

- - | `void` | `close()`  关闭流，先刷新。 |
    | ------ | --------------------------- |



- - | `void`          | `write(char[] cbuf)`  写入一个字符数组。                     |
    | --------------- | ------------------------------------------------------------ |
    | `abstract void` | `write(char[] cbuf,  int off, int len)`  写入字符数组的一部分。 |
    | `void`          | `write(int c)`  写一个字符                                   |
    | `void`          | `write(String str)`  写一个字符串                            |
    | `void`          | `write(String str,  int off, int len)`  写一个字符串的一部分。 |

- - | `void` | `flush()`  刷新流。 |
    | ------ | ------------------- |



```java
package com.hs;

import java.io.FileWriter;
import java.io.IOException;

public class FileWriterDemo {
    public static void main(String[] args) throws IOException {

//        1创建字符输出流
        FileWriter  writer=new FileWriter("C:\\Users\\lx\\Desktop\\b\\3.txt");

//        2、写
//        第一种：每次写一个字符
//        String   s="希望八月尽快过去，因为九月我就回去上课了！";
//        char[] chars = s.toCharArray();
//        for (char c : chars) {
//            writer.write(c);
//        }

//        第二种：每次写一个字符数组
//        String   s="希望八月尽快过去，因为九月我就回去上课了！22";
//        char[] chars = s.toCharArray();
//        writer.write(chars);

//        第三种：每次写字符数组的部分数据
//        String   s="希望八月尽快过去，因为九月我就回去上课了！22";
//        char[] chars = s.toCharArray();
//        writer.write(chars,0,10);

//        第四种：写一个字符串
//        String   s="希望八月尽快过去，因为九月我就回去上课了！33";
//        writer.write(s);

//        第五种：写入一个字符串的部分数据
        String   s="希望八月尽快过去，因为九月我就回去上课了！33";
        writer.write(s,0,6);

//        字符流调用write方法时，并没有写入
        writer.flush();//刷新：强制写入

//        3、关
        //writer.close();//刷新，关闭流。


    }
}
```





### 5、字节流和字符流区别

（1）字节流以字节为单位进行读写，字符流是以字符为单位进行读写。

（2）字节流写操作立即执行，字符流写操作需要调用flush或close方法时才执行。

（3）字节流可以传输任何类型的数据（文本、图片、音频、视频==），字符流只能传输字符数据（文本）。





## 三、高级流

前面讲的这些字节流和字符流都是节点流，只有基本的读写功能。

高级流不仅能够读写，还有其他增强的功能。



高级流是建立在节点流的基础上创建。

先建节点流，然后创建高级流。

### 1、转换流

将字节流转为字符流。

（1）转换输入流

将字节输入流，转为字符输入流。

InputStreamReader



```java
package com.hs;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.InputStreamReader;

public class InputStreamReaderDemo {
    public static void main(String[] args) throws IOException {

//        字节输入流
        FileInputStream   in=new FileInputStream("C:\\Users\\lx\\Desktop\\b\\22.txt");

//        转换输入流：就是一个字符流
//        首先需要一个字节输入流（节点流）
//        在此基础上转为字符输入流
        InputStreamReader   reader=new InputStreamReader(in);
        char[]  cc=new  char[10];
        int  i=reader.read(cc);
        System.out.println(new  String(cc,0,i));

//        先关输出流再关输入流
//        后打开的先关闭
        reader.close();
        in.close();
    }
}
```

（2）转换输出流

将字节输出流，转为字符输出流。

OutputStreamWriter

```java
package com.hs;

import java.io.*;

public class OutputStreamWriterDemo {


    public static void main(String[] args) throws IOException {

//        先创建一个字节输出流
        FileOutputStream   out=new FileOutputStream("C:\\Users\\lx\\Desktop\\b\\4.txt");

//        在创建转换输出流：就是一个字符流
        OutputStreamWriter   writer=new OutputStreamWriter(out);

//        写
        writer.write("希望大家都是一个快乐的人！");

//        关闭
        writer.close();
        out.close();

    }

}
```



### 2、缓冲流

默认缓冲区大小：8192字节。



使用缓冲流读写原理：

将读取的数据先临时存储在缓冲区；

当缓冲区写满了，才会将缓冲区的数据写入目的端。



使用缓冲流的优点：

提高了IO效率，同时减少了对硬盘的损耗。

![image-20210810144714607](12文件类和IO流.assets/image-20210810144714607.png)



（1）字节缓冲流

字节缓冲输入流：BufferedInputStream

字节缓冲输出流：BufferedOutputStream



```java
package com.hs;

import java.io.*;

public class BufferedDemo01 {

    public static void main(String[] args) throws IOException {

//        1、创建字节缓冲流
//        先创建字节流
        FileInputStream   in=new FileInputStream("C:\\Users\\lx\\Desktop\\b\\HelloWorld.txt");
        FileOutputStream  out=new FileOutputStream("d:\\HelloWorld.txt");

//        再创建字节缓冲流
        BufferedInputStream   bin=new BufferedInputStream(in);
        BufferedOutputStream   bout=new BufferedOutputStream(out);

//        2\使用缓冲流读写
        byte[]  b=new  byte[1024];
        int i = bin.read(b);//读取的数据放入缓冲区
        while(i!=-1){
            bout.write(b,0,i);//并没有立马写；当缓冲区满了，才会一次性写入目的端
            i = bin.read(b);//读取的数据放入缓冲区
        }

//        3\关闭流
        bout.close();
        out.close();
        bin.close();
        in.close();

    }
}
```





（2）字符缓冲流

  字符缓冲输入流：BufferedReader

  字符缓冲输出流：BufferedWriter 



```java
package com.hs;

import java.io.*;

public class BufferedDemo02 {
    public static void main(String[] args) throws IOException {

//        1、创建缓冲流
//        先建节点流
        FileReader   r=new FileReader("C:\\Users\\lx\\Desktop\\b\\HelloWorld.txt");
        FileWriter   w=new FileWriter("d:\\HelloWorld2.txt");
//        再建缓冲流
        BufferedReader  br=new BufferedReader(r);
        BufferedWriter  bw=new BufferedWriter(w);

//        2、读写
        String   line=br.readLine(); //读取的数据保存在缓冲区
        while(line!=null){
            System.out.print(line);
            bw.write(line+"\r\n");//缓冲区满了才会写
            //bw.flush();//立马写
            line=br.readLine();
        }

//        3、关闭流
        bw.close();
        w.close();
        br.close();
        r.close();


    }
}
```





### 3、序列化流

（1）对象序列化和反序列化

将对象转为字节码（二进制）的过程，我们称为对象的序列化。

将字节码转为对象的过程，我们称为对象的反序列化。

![image-20210810160221757](12文件类和IO流.assets/image-20210810160221757.png)

对象存储或者传输时，必须是二进制形式，所以要进行序列化操作。



（2）序列化流

输出流

ObjectOutputStream



**对象序列化前提：类必须实现序列化接口Serializable**

```java
package com.hs;

import java.io.Serializable;

//序列化，必须实现序列化接口！！！！！！
public class Student implements Serializable {
    public Student() {
    }

    public Student(int num, String name) {
        this.num = num;
        this.name = name;
    }

    private  int num;
    private  String  name;

    public int getNum() {
        return num;
    }

    public void setNum(int num) {
        this.num = num;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

```java
Student   s1=new Student(1001,"张三");
        Student   s2=new Student(1002,"李四");


        //1\创建序列化流
//        先建节点流
        FileOutputStream  out=new FileOutputStream("d:\\students.txt");
//        再建序列化流
        ObjectOutputStream  oos=new ObjectOutputStream(out);

//        2\写:oos先将对象进行序列化，out再写入文件中
        oos.writeObject(s1);
        oos.writeObject(s2);

//        3、关闭流
        oos.close();
        out.close();
```



（3）反序列化流

输入流

ObjectInputStream



```java
package com.hs;

import java.io.EOFException;
import java.io.FileInputStream;
import java.io.IOException;
import java.io.ObjectInputStream;

public class TestStudent02 {
    public static void main(String[] args) throws IOException, ClassNotFoundException {


//        1\创建反序列化流
        FileInputStream   in=new FileInputStream("d:\\students.txt");
        ObjectInputStream   ois=new ObjectInputStream(in);

//        2、读取：in读取二进制信息，ois将其转为Object对象
        try {
            Student s = (Student) ois.readObject();
            while (s != null) {
                System.out.println(s.getNum() + "," + s.getName());
                s = (Student) ois.readObject();
            }
        }catch (EOFException  e){
            //读到末尾，没数据了，就会发生eof异常
            System.out.println("处理了eof异常");
        }

//        3、关闭流
        ois.close();
        in.close();


    }
}
```



## 四、乱码



### 1、乱码

（1）编码和解码

计算机只能识别二进制。

我们的数据在存储和传输时，都是以二进制形式存在的。

编码：将字符转为二进制。

解码：将二进制转为字符。



（2）字符集

转换的依据：字符集。

常见的字符集：iso-8859-1（英文），gbk（英文、中文），utf-8（英文、中文、其他国家的符号）



所有字符集中都包含英文字符，且英文字符对应的编码都相同。

所有字符集中英文字符编码都是一个字节。



不是所有字符集都含有中文字符，含有中文的字符集对应的编码不相同。

gbk一个汉字编码占两个字节，utf-8一个汉字编码占三个字节。





（3）乱码解释

错乱的编码。

一个字符经过编码和解码后，和原先字符不一样，这种现象我们叫乱码。



### 2、中文乱码产生的原因

（1）情况1

使用了不支持中文的字符集。



```java
//        乱码1:采用了不支持汉字的字符集
        String   s1="我们小区有新冠病毒接触者,被带走了，我们慌！";
//        编码
        byte[]  b1=s1.getBytes("iso-8859-1");
//        解码
        String  s2=new  String(b1,"iso-8859-1");
        System.out.println(s2);
```

（2）情况2

编码和解码使用的字符集不一致。

```java
//        乱码2：编码和解码字符集不一致
        String   s3="如果你好好学习，你一定能挣钱!";
//        编码
        byte[] b3 = s3.getBytes("gbk");
//        解码：
        String  s4=new String(b3,"utf-8");
        System.out.println(s4);
```



### 3、解决乱码

```java
//        解决乱码：
//        同时满足：
//        （1）编码采用的字符集必须支持中文
//        （2）编码和解码使用的字符集一致
        String  s5="祖国万岁";
        byte[] b5 = s5.getBytes("utf-8");
        System.out.println(new  String(b5,"utf-8"));
```

# 13网络编程

## 一、计算机网络

### 1、计算机网络

使用网络设备，将不同地域的计算机连接在一起，形成一个功能强大的网络系统。



规模不同：

局域网（内网）

城域网

广域网（外网，因特网）



### 2、网络的作用

计算机之间进行数据传输，网络通信。



### 3、网络模型

（1）理想模型：

OSI：7层

![705728-20160424234824085-667046040](13网络编程.assets/705728-20160424234824085-667046040.png)

（2）实用模型：

TCP/IP：5层

![img](https://images2015.cnblogs.com/blog/705728/201604/705728-20160424234827195-1493107425.png)





## 二、网络通信

### 1、IP协议

网络为每一台计算机都提供了一个唯一的身份标识，我们叫IP协议。



两种表示法：

（1）IPv4：4段十进制数字构成，中间使用点分割。每段数字0~255 。

​					192.168.0.110

​					202.10.10.10

（2）IPv6: 8段十六进制的数字构成，中间使用冒号分割。每段数字0000-FFFF 。

​					

外网IP：202.202.10.111

局域网IP：192.168.0.110

本机IP： 127.0.0.1  或者 localhost

域名：www.baidu.com    对应[110.242.68.4]   

​			使用DNS服务器

主机名：Aery      



### 2、端口号

QQ-A          和         QQ-B    通信：

QQ-A通过B的IP，在网络中找到B，使用端口号找到QQ-B程序。



端口号：一个计算机中，应用程序接收信息的通道。每个程序都有自己唯一的端口号。

​				如果两个程序端口号相同，会出现端口号冲突，无法通信。



​				端口号是用来接收信息的，一个计算机有65536个端口号，号码：0~65535。

​				0~1023是被系统使用了，我们不能用。

​				1024以上，可以使用，前提是和已经存在的应用程序不冲突。

​				mysql:3306    oracle:1521    tomcat:8080  

![image-20210811115208273](13网络编程.assets/image-20210811115208273.png)

### 3、传输协议

这类似于日常生活中写信，把自己要表达的意思写到纸上，有兴趣的话还要把纸折叠成特殊的形状，然后放到信封里并封好口，写好收信人的地址、邮政编码和姓名，再贴上邮票，邮局的工作人员再盖上[邮戳](https://baike.baidu.com/item/邮戳)送到收信人所在邮局，邮递员按信上的地址把信交给收信人，收信人再拆信，阅读其内容。



我们通信，需要遵守的规则。如何将信息传递过去？

两种传输协议：

（1）TCP

通信前，需要先建立连接。然后才能发送消息。

它是一种可靠的传输协议，效率低。

通信完毕，断开连接。



就像我们打电话：先要拨通对方的号码，然后才能交流，交流结束后挂断。



建立连接：三次握手

![img](https://img-blog.csdn.net/20180717202520531?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM4OTUwMzE2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)



断开连接：四次挥手。

![img](https://img-blog.csdn.net/20180717204202563?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM4OTUwMzE2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)





（2）UDP

不需要建立连接，直接发送信息。

信息是以数据报的形式封装的，里面包含：对方的ip，端口号，信息==。

它是一种不可靠的传输协议，效率高。



好比发短信，不管对象是否存在，直接发出去，对方是否收到也不管，信息是否正确也不管。



（3）TCP和UDP的区别

TCP是面向连接的可靠的传输协议，效率较低。

UDP是无需连接的不可靠的传输协议，效率高。











## 三、基于TCP的网络编程

![image-20210811154315205](13网络编程.assets/image-20210811154315205.png)

### 1、客户端给服务器发送一条信息

客户端：

（1）和服务器建立连接

```java
//       创建一个套接字，向服务器发送连接请求，建立连接。
//        指定服务器的ip：localhost和服务器接收信息的端口号9999
        Socket    c=new Socket("localhost",9999);
        System.out.println("++客户端和服务器建立连接++");
```

（2）发送信息

```
//        使用Socket套接字进行通信
        OutputStream    send=c.getOutputStream();
        send.write("你好啊，服务器!".getBytes());
        send.close();

```

（3）和服务器断开连接

```java
c.close();
```



服务器：

（1）和客户端建立连接

```java
//        启动服务器,指定服务器接收信息的端口号9999
        ServerSocket   server=new ServerSocket(9999);
//        等待接收客户端的连接请求
//        如果没有没有客户端发送连接请求，将阻塞（等待）。
//        一旦接收到客户端请求，返回一个和客户端通信的套接字。
        Socket    s=server.accept();
        System.out.println("--服务器和客户端建立了连接--");
```

（2）接收信息

```java
//      使用Socket套接字通信
        InputStream recieve = s.getInputStream();
        byte[]  b=new  byte[1024];
//        read方法阻塞
        int i = recieve.read(b);
        System.out.println(new String(b,0,i));
		recieve.close();
```

（3）和客户端断开连接

```java
s.close();
server.close();
```





### 2、文件上传

客户端将一个文件发送给服务器，服务器接收文件保存在服务器上。



客户端：

（1）建立连接

（2）读取文件，发送文件

（3）断开连接

```java
package com.hs.tcp;

import java.io.FileInputStream;
import java.io.IOException;
import java.io.OutputStream;
import java.net.Socket;

/**
 * 客户端
 */
public class FileClient {
    public static void main(String[] args) throws IOException {
        //    1\建立连接
        Socket   c=new Socket("127.0.0.1",9999);

//    2、发送文件
//        读取文件
        FileInputStream   in=new FileInputStream("src/11.jpg");
        OutputStream out = c.getOutputStream();

        byte[]   b=new  byte[1024];
        int  i=in.read(b);
        while(i!=-1){
            out.write(b,0,i);
            i=in.read(b);
        }
        System.out.println("客户端发送文件完毕");

        out.close();
        in.close();

//    3、断开连接
        c.close();
    }

}
```

服务器：

（1）建立连接

（2）接收文件，保存文件

（3）断开连接

```java
package com.hs.tcp;

import com.sun.beans.editors.ByteEditor;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.ServerSocket;
import java.net.Socket;

/**
 * 服务器端
 */
public class FileServer {
    public static void main(String[] args) throws IOException {
//    1\建立连接
        ServerSocket  server=new ServerSocket(9999);
        Socket s = server.accept();

//    2、接收文件，保存文件
        InputStream in = s.getInputStream();
        FileOutputStream  out=new FileOutputStream("src/com/hs/tcp/11.jpg");

        byte[]   b=new byte[1024];
        int  i=in.read(b);
        while(i!=-1){
            out.write(b,0,i);
            i=in.read(b);
        }
        System.out.println("服务器接收文件完毕");
        out.close();
        in.close();

//    3、断开连接
        s.close();
        server.close();
    }
}
```

### 3、浏览器和tomcat

（1）浏览器

客户端程序

![image-20210811162858531](13网络编程.assets/image-20210811162858531.png)

（2）tomcat

服务器程序

![image-20210811162924069](13网络编程.assets/image-20210811162924069.png)



## 四、基于UDP的网络编程（了解）

### 1、客户端向服务器发送一条信息

客户端：

（1）发送信息

（2）关闭socket

```java
package com.hs.udp;

import java.io.IOException;
import java.net.*;

/**
 * 客户端
 */
public class UdpClient {
    public static void main(String[] args) throws IOException {
//      1、发送信息
//       （1） 创建一个套接字
        DatagramSocket   c=new DatagramSocket();

//        （2）准备一个数据报
        byte[]  b="你好啊，服务器!".getBytes();
//        服务器的地址和端口
        InetAddress   addr=InetAddress.getByName("localhost");
        DatagramPacket   p=new DatagramPacket(b,0,b.length,addr,8888);

//        （3）发送数据报
        c.send(p);

//       2、关闭socket
        c.close();
    }
}
```

服务器端：

（1）接收信息

（2）关闭socket

```java
package com.hs.udp;

import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.SocketException;

/**
 * 服务器
 */
public class UdpServer {
    public static void main(String[] args) throws IOException {
//      1、接收信息
//      （1）创建一个套接字，指定接收信息的端口是8888
        DatagramSocket    s=new DatagramSocket(8888);

//        （2）准备一个空的数据报
        byte[]   b=new  byte[1024];
        DatagramPacket    p=new DatagramPacket(b,0,b.length);

//        （3）接收信息
//        带有阻塞的方法
        s.receive(p);
        System.out.println(new  String(b));

//        2、关闭socket
        s.close();
    }
}
```



## 五、URL编程

### 1、url

统一资源定位符

url是一个地址字符串，用来标识网络资源的位置。



### 2、url格式

【通信协议】://【主机】:【端口号】/【资源的路径】



比如：

http://localhost:8080/bbs/index.html

http://www.baidu.com    -->   http://www.baidu.com:80/index.html



### 3、URL编程

通过url找到网络资源，然后获取资源的内容。

```java
package com.hs.url;

import java.io.IOException;
import java.io.InputStream;
import java.net.HttpURLConnection;
import java.net.MalformedURLException;
import java.net.URL;
import java.net.URLConnection;

public class URLDemo {
    public static void main(String[] args) throws IOException {


//        1\创建一个URL
//        URL   url=new URL("http://localhost:8080/baidu/1.txt");
//        URL   url=new URL("http://localhost:8080/baidu/index.html");
        URL   url=new URL("http://www.baidu.com");

//        2\获取一个连接对象
        HttpURLConnection conn = (HttpURLConnection)url.openConnection();

//        3\读取资源内容
        InputStream in = conn.getInputStream();

        byte[]   b=new  byte[1024];
        int  i=in.read(b);

        while(i!=-1){
            System.out.println(new  String(b,0,i));
            i=in.read(b);
        }
        in.close();

//        断开连接
        conn.disconnect();


    }
}
```

# 14多线程

## 一、程序、进程、线程

### 1、程序

使用某种计算机语言编写的，为了完成某些功能的静态代码。

![image-20210812104524333](14多线程.assets/image-20210812104524333.png)

### 2、进程

（1）程序执行的动态过程。

![image-20210812104548811](14多线程.assets/image-20210812104548811.png)



![image-20210812104638898](14多线程.assets/image-20210812104638898.png)



![image-20210812104653139](14多线程.assets/image-20210812104653139.png)

（2）关闭程序，进程结束

![image-20210812104725465](14多线程.assets/image-20210812104725465.png)

![image-20210812104736206](14多线程.assets/image-20210812104736206.png)

（3）进程生命周期：

开始运行一直到关闭或停止运行。

一个程序可以同时运行多次，每次运行都是一个进程。

### 3、线程

**一个程序可以同时运行多个任务功能**。

每一个独立运行的任务流程，我们称为一个线程。

一个进程中可以包含多个线程。



360安全卫士：

同时执行，健康检查，木马查杀，垃圾清理，优化。

QQ：

显示界面信息、发送信息、接收信息。



## 二、多线程使用场景

### 1、多线程程序特点

多个任务流程可以同时执行，互不影响。



### 2、并发和并行

所有程序都是运行在CPU上。

（1）并发

早期CPU是单核的，只能同时运行一个线程。

如果要同时运行多个线程，多个线程在CPU上交替执行。

我们将多个线程在CPU上交替执行的过程，称为并发执行。

（2）并行

我们现在的计算都是多核，可以同时运行多个线程。

每个核心上都可以运行一个线程。

我们将多个核心同时运行多个线程的过程，称为并行执行。

（3）并行和并发

我们计算机现在虽然是多核的，但是并行和并发都是存在的。

比如：

我们有16个线程同时执行，但是核心只有4个。

同时并行的是4个线程。

但是每个核心上有多个线程交替并发执行。



### 3、使用场景

当程序需要多个任务流程同时执行时。



### 4、多线程程序的优点

（1）减少了阻塞，程序的执行效率高。

（2）提高了CPU的利用率。

（3）增强了用户体验。

（4）改善了程序的结构。



## 三、线程分类

1、用户线程

我们程序的功能流程。



主线程：我们程序执行的入口，对应的就是主方法。

我们之前写的程序都是单线程的，只有一个主线程。

一个进程，有且仅有一个主线程。



2、守护线程

守护线程，也叫后台线程。

比如：

jvm的垃圾回收线程。

jvm的异常处理线程。



## 四、多线程实现（4种）

### 1、继承Thread

（1）继承java.lang.Thread类

（2）重写run方法

```java
package com.hs;

public class MyThread1 extends   Thread{

    @Override
    public void run() {
        //run方法中定义当前线程要执行的代码
        System.out.println("t1   begin");
        for (int i = 0; i < 1000; i++) {
            System.out.println("线程1："+i);
        }
        System.out.println("t1  end");
    }
}
```

（3）创建一个线程对象

（4）开启线程（运行线程代码）（start方法）

```java
package com.hs;

public class TestMain {

    //主线程
    public static void main(String[] args) {

        System.out.println("main   begin");

        //创建子线程1
        MyThread1   t1=new MyThread1();
        //开启线程:如果直接调用run，没有开启新线程；如果想要开启新线程，使用start方法。
        //开启一个新线程，去执行run方法。
        //无需等待run方法执行结束
        t1.start();

        for (int i = 0; i < 1000; i++) {
            System.out.println("main:"+i);
        }

        System.out.println("main  end");

    }
}
```



运行结果：

第一次

![image-20210812114522387](14多线程.assets/image-20210812114522387.png)



第二次

![image-20210812114543016](14多线程.assets/image-20210812114543016.png)



程序执行流程：

![image-20210812115536528](14多线程.assets/image-20210812115536528.png)





### 2、实现Runnable

（1）实现java.lang.Runnable接口

（2）实现run方法

```java
package com.hs;

public class MyThread2 implements   Runnable{
    @Override
    public void run() {
        //线程要执行的任务代码
        System.out.println("t2  begin");
        for (int i = 0; i < 1000; i++) {
            System.out.println("t2 :"+i);
        }

        System.out.println("t2   end");
    }
}
```

（3）创建线程对象

（4）开启新线程（start方法）

```java
package com.hs;

public class TestMain02 {

    //主线程
    public static void main(String[] args) {
        System.out.println("main   begin");

//        创建线程对象
		//任务代码
        MyThread2   t2=new MyThread2();
        //线程对象
        Thread    t22=new Thread(t2);

//        开启线程
        t22.start();

        for (int i = 0; i < 1000; i++) {
            System.out.println("main:"+i);
        }

        System.out.println("main   end");
    }
}
```

### 3、比较

（1）thread方式开启新线程比较方便，直接使用start方法，同时还继承了很多其他方法。

而Runnable方式，只有一个抽象的run方法。

（2）我们继承了Thread类，就不能继承其他类。但是实现Runnable接口，还可以继承其他类。

（3）实现Runnable方式，将线程和任务代码进行分离，降低程序的耦合度，提高了代码的重用性。

（4）使用Runnable方式可以方便共享数据，而继承Thread共享数据不方便。



综上所述：推荐Runnable形式！！



### 4、start方法和run方法区别

start方法是开启一个新线程，没有线程执行的代码。

run方法是线程的执行代码，不能开启新线程。





## 五、线程生命周期

### 1、生命周期

![img](https://img2018.cnblogs.com/blog/1679365/201905/1679365-20190509193240010-608767567.png)

（1）新建状态

使用new创建一个线程对象，此时线程处于新建状态。

（2）可运行状态（就绪）

调用线程的start方法，开启线程，该线程处于可运行状态。还没有运行。

线程进入cpu队列，等待cpu来执行它。

（3）运行状态

CPU从队列中选取该线程，执行线程的任务代码，这个时候线程处于运行状态。

（4）阻塞状态

CPU在运行该线程时发生了阻塞，该线程进度阻塞队列，这时线程处于阻塞状态。

阻塞完毕，重新进入CPU队列中等待执行。

（5）死亡状态

当CPU执行完该线程的所有任务代码，该线程处于死亡状态。



### 2、CPU执行原理

（1）所有可运行的线程进入队列中等待执行。

（2）CPU每次会选择其中一个线程来执行。

（3）CPU会为本次执行该线程分配一个时间片。

（4）如果时间片到期，CPU会将该线程放入队列中，该线程继续等待执行。

（5）如果时间片没有到期，运行时出现阻塞，CPU会将该线程放入阻塞队列。

（6）如果时间片没有到期，线程代码执行完毕，该线程被销毁。



注意：

（1）CPU每次选择哪个线程来执行，我们不知道，随机。

（2）CPU每次分配的时间片大小，我们不知道，随机。

因此，多线程程序每次执行结果都可能不一样！！！！



## 六、线程方法

### 1、设置和获取名称

通过构造器的形式，给创建的线程对象起名字。

- - | `Thread(Runnable target, String name)`  分配一个新的 `Thread`对象。 |
    | ------------------------------------------------------------ |
    | `Thread(String name)`  分配一个新的 `Thread`对象。           |

通过方法来给线程对象起名。

- - | `void` | `setName(String name)`  将此线程的名称更改为等于参数 `name` 。 |
    | ------ | ------------------------------------------------------------ |

获取线程对象的名字。

- - | `String` | `getName()`  返回此线程的名称。 |
    | -------- | ------------------------------- |

```java
package com.hs;

public class TestMain03 {
    //主线程
    public static void main(String[] args) {

        Thread   t1=new MyThread1();
        Thread   t2=new MyThread1("线程2");
        Thread   t3=new MyThread1();
        t3.setName("线程3");

        System.out.println(t1.getName());
        System.out.println(t2.getName());
        System.out.println(t3.getName());
        
        Thread   t4=new Thread(new MyThread2(),"t4");

    }
}
```



```java
package com.hs;

public class MyThread1 extends   Thread{

//    private  int  idd=9;
        private  static  int  idd=9;

    public  MyThread1(){}

    public  MyThread1(String  name){
        super(name);
    }

    @Override
    public void run() {
        idd++;
        //run方法中定义当前线程要执行的代码
        System.out.println("t1   begin");
        for (int i = 0; i < 1000; i++) {
//            获取当前线程，设置和获取名字
            Thread.currentThread().setName("线程111");
            String  currName=Thread.currentThread().getName();
            System.out.println(currName+i);
        }
        System.out.println("t1  end");
    }
}
```



```java
package com.hs;

public class MyThread2 implements   Runnable{
    private  int   id=10;

    @Override
    public void run() {
        id++;
        //线程要执行的任务代码
        System.out.println("t2  begin");
        for (int i = 0; i < 1000; i++) {
            Thread.currentThread().setName("t2:");
            String name = Thread.currentThread().getName();
            System.out.println(name+i);
        }

        System.out.println("t2   end");
    }
}
```



### 2、设置和获取优先级

不同的线程优先级可以不同。

线程的优先级，决定了被CPU选中的概率。

优先级越高，被CPU选中的概率越高。

线程的优先级范围是：1-10，默认是5.

- - | `static int` | `MAX_PRIORITY`  线程可以拥有的最大优先级。 10 |
    | ------------ | --------------------------------------------- |
    | `static int` | `MIN_PRIORITY`  线程可以拥有的最小优先级。 1  |
    | `static int` | `NORM_PRIORITY`  分配给线程的默认优先级。5    |



```java
package com.hs;

public class TestMain04 {


    public static void main(String[] args) {

        Thread  t1=new MyThread1();
        Thread  t3=new MyThread1();
        Thread   t2=new Thread(new MyThread2());

        t1.setPriority(10);
        t2.setPriority(3);

        System.out.println(t1.getPriority());
        System.out.println(t2.getPriority());
        System.out.println(t3.getPriority());


        t1.start();
        t2.start();

    }
}

```



优先级高，不代表先执行，只是被选中的概率较高。

t1--10,被选中的概率假如是80%，不被选中的概率20%。

t2--3,被选中的概率假如是30%，不被选中的概率70%。



### 3、线程阻塞：sleep方法

当前线程退出CPU，进入阻塞队列，n毫秒后结束阻塞，进入CPU队列中等待执行。

```java
package com.hs;

public class MyThread3 implements   Runnable{
    @Override
    public void run() {
        //run不能抛出异常，只能使用try-catch处理异常

        for (int i = 0; i < 100; i++) {
//            休眠3000毫秒
            try {
//                当前线程退出CPU，进入阻塞队列，3000毫秒后结束阻塞，进入CPU队列中等待执行。
                Thread.sleep(3000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }

            System.out.println(Thread.currentThread().getName()+":"+i);
        }
    }
}
```





```java
package com.hs;

public class TestMain05 {

    public static void main(String[] args) {

        Thread   t1=new Thread(new MyThread3());
        t1.start();


    }

}
```

### 4、线程阻塞：join方法

在一个线程中，调用了另一个线程的join方法。

当前线程阻塞，直到另一个线程全部代码运行完毕，结束阻塞，才能继续执行。

```java
package com.hs;

public class MyThread5 implements Runnable{
    @Override
    public void run() {
        for (int i = 0; i < 10; i++) {
            System.out.println("t5:"+i);
        }
    }
}
```



```java
package com.hs;

public class MyThread4 implements   Runnable{
    private  Thread   t5;

    public MyThread4(Thread t5) {
        this.t5 = t5;
    }

    @Override
    public void run() {

        try {
            //当前线程需要等t5线程结束后才能继续执行，中间一直阻塞
            t5.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        for (int i = 0; i < 10; i++) {
            System.out.println("t4:"+i);
        }


    }
}
```





```java
package com.hs;

public class TestMain06 {

    public static void main(String[] args) {
        Thread  t5=new Thread(new MyThread5());   //线程5
        Thread  t4=new Thread(new MyThread4(t5)); //线程4

        t5.start();
        t4.start();

    }
}
```



## 七、多线程内存分配

<img src="https://images0.cnblogs.com/i/485345/201405/300854081661499.jpg" alt="img" style="zoom:67%;" />



### 1、程序计数器

一块较小的内存空间，它的作用可以看做是当前线程所执行的字节码的行号指示器。

“线程私有”的内存。



### 2、Java 虚拟机栈

用于存储局部变量表、操作栈、动态链接、方法出口等信息。

“线程私有”的内存。



### 3、本地方法栈

本地方法栈（Native Method Stacks）与虚拟机栈所发挥的作用是非常相似的，其

区别不过是虚拟机栈为虚拟机执行Java 方法（也就是字节码）服务，而本地方法栈则

是为虚拟机使用到的Native 方法服务。



### 4、Java 堆

各个线程共享的内存区域。

对于大多数应用来说，Java 堆（Java Heap）是Java 虚拟机所管理的内存中最大的

一块。Java 堆是被所有线程共享的一块内存区域，在虚拟机启动时创建。此内存区域的

唯一目的就是存放对象实例，几乎所有的对象实例都在这里分配内存。



### 5、方法区

方法区（Method Area）与Java 堆一样，是各个线程共享的内存区域。

它用于存储已被虚拟机加载的类信息、常量、静态变量、即时编译器编译后的代码等数据。



### 6、运行时常量池

运行时常量池（Runtime Constant Pool）是方法区的一部分。Class 文件中除了有

类的版本、字段、方法、接口等描述等信息外，还有一项信息是常量池（Constant Pool

Table），用于存放编译期生成的各种字面量和符号引用，这部分内容将在类加载后存放

到方法区的运行时常量池中。

![img](https://images0.cnblogs.com/i/485345/201405/300854449949413.jpg)







多线程内存分配：

多个线程共享堆内存和方法区，但是计数器和栈是每个线程私有的。



## 八、线程同步

### 1、多线程同时访问统一对象，导致数据不一致的问题

案例：同时有3个窗口卖票，总票数为100张。

```java
package com.hs;

public class TicketWindow implements   Runnable{
    private  int  ticket=100;

    @Override
    public void run() {
        //卖票
        while(true){
            
            if(ticket>0){
                System.out.println(Thread.currentThread().getName()+"，卖出的票号为："+ticket);
                ticket--;
            }else{
                break;
            }
        }
    }
}
```

```java
package com.hs;

public class TestTicketWindowMain {
    //主线程
    public static void main(String[] args) {

//      线程任务：卖票
        TicketWindow   window=new TicketWindow();

//        3个窗口同时卖票：3个线程。
        Thread   t1=new Thread(window,"1号窗口");
        Thread   t2=new Thread(window,"2号窗口");
        Thread   t3=new Thread(window,"3号窗口");

        t1.start();
        t2.start();
        t3.start();

    }
}
```



执行结果：

![image-20210813105723505](14多线程.assets/image-20210813105723505.png)



问题：两个窗口卖出了同一张票。

解决：线程同步。

​			一张票卖完，才能卖下一张票。



### 2、线程同步（3种）

（1）同步块

将一块代码锁起来，每次只能一个线程执行。

一个线程执行完毕同步块，下一个线程才能执行。



原理：

对象锁：一个对象对应一把锁。

通过该对象锁，锁住某块代码。

哪个线程获取到这个对象锁，哪个线程就可以执行同步块中的代码。其他线程阻塞。

该线程执行完同步块代码，主动释放锁。其他线程竞争这个对象锁。

```
synchronized(对象名){
	//同步的代码块
}
```

```java
package com.hs;

public class TicketWindow implements   Runnable{
    private  int     ticket=100;
    private Object   o=new Object();

    @Override
    public void run() {
        //卖票
        while(true){
            //卖一张票的整个操作
            //通过对象o锁，锁住代码块。
            synchronized (o) {
                if (ticket > 0) {
                    System.out.println(Thread.currentThread().getName() + "，卖出的票号为：" + ticket);
                    ticket--;
                } else {
                    break;
                }
            }
        }
    }
}
```



（2）同步方法

通过当前对象this的锁，锁住整个方法。

this表示调用的方法所属的对象。

哪个线程获得this锁，哪个线程就能访问该方法。

```java
[修饰符]  synchronized   返回值类型   方法名([参数]){
	方法体：同步代码
}
```



注意：多个线程的this必须指向同一个对象，否则没有同步效果。

```java
package com.hs;

public class TicketWindow2 implements Runnable{

    private  int     ticket=100;

    @Override
    public void run() {
        //卖票
        while (true){
            //卖出一张票
            saleTicket();

            if(ticket<=0){
                break;
            }
        }

    }

    //同步方法
//    通过当前对象this的锁，锁住整个方法
    public  synchronized   void  saleTicket(){
        if(ticket>0) {
            System.out.println(Thread.currentThread().getName() + "，卖出的票号为：" + ticket);
            ticket--;
        }
    }
}
```



（3）lock方式

jdk1.5提供的一种同步方式。

Lock接口：java.util.concurrent.locks.Lock

- - | `void` | `lock()`  获得锁。 |
    | ------ | ------------------ |

- - | `void` | `unlock()`  释放锁。 |
    | ------ | -------------------- |

实现类：ReentrantLock



多个线程竞争同一把锁，实现线程同步。

和同步块效果一样。

```java
package com.hs;

import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

public class TicketWindow3 implements   Runnable{
    private  int     ticket=100;

//    创建一把锁
    private Lock lk=new ReentrantLock();

    @Override
    public void run() {
        //卖票
        while(true){
            //卖一张票的整个操作
//           获取锁
            lk.lock();
                if (ticket > 0) {
                    System.out.println(Thread.currentThread().getName() + "，卖出的票号为：" + ticket);
                    ticket--;
                }
            
//          释放锁
            lk.unlock();

                if(ticket<=0){
                    break;
                }

        }
    }
}

```



（4）lock和同步块比较

lock更直观，直接在代码中可以看见锁。

lock可以解决同步块中出现异常释放锁的问题。

```java
package com.hs;

import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

public class TicketWindow3 implements   Runnable{
    private  int     ticket=100;

//    创建一把锁
    private Lock lk=new ReentrantLock();

    @Override
    public void run() {
        //卖票
        while(true){
            //卖一张票的整个操作
//           获取锁
            lk.lock();
            try {
                if (ticket > 0) {
                    System.out.println(Thread.currentThread().getName() + "，卖出的票号为：" + ticket);
                    ticket--;
                }
            }catch(Exception  e){
            }finally {
                //释放锁
                lk.unlock();
            }


                if(ticket<=0){
                    break;
                }

        }
    }
}
```



## 九、线程通信：死锁处理

### 1、线程同步的问题：死锁

```java
package com.hs;

public class MyThread11  implements   Runnable {
    private   Object   a;
    private   Object   b;

    public MyThread11(Object a, Object b) {
        this.a = a;
        this.b = b;
    }

    @Override
    public void run() {
        String name = Thread.currentThread().getName();
        synchronized (a){
            System.out.println(name+"获得了a锁");
            synchronized (b){
                System.out.println(name+"获得了b锁");
                System.out.println(name+"11111111111111111111111");
                System.out.println(name+"释放了b锁");
            }
            System.out.println(name+"释放了a锁");
        }
    }
}
```



```java
package com.hs;

public class MyThread12 implements   Runnable{
    private   Object   a;
    private   Object   b;

    public MyThread12(Object a, Object b) {
        this.a = a;
        this.b = b;
    }

    @Override
    public void run() {
        String name = Thread.currentThread().getName();
        synchronized (b){
            System.out.println(name+"获得了b锁");
            synchronized (a){
                System.out.println(name+"获得了a锁");
                System.out.println(name+"22222222222222222222");
                System.out.println(name+"释放了a锁");
            }
            System.out.println(name+"释放了b锁");
        }
    }
}
```



```java
package com.hs;

public class TestMain07 {
    public static void main(String[] args) {

        Object  a=new Object();
        Object  b=new Object();
        MyThread11  t11=new MyThread11(a,b);
        MyThread12  t12=new MyThread12(a,b);

//        创建线程
        Thread  t1=new Thread(t11,"线程1：");
        Thread  t2=new Thread(t12,"线程2：");

//        开启线程
        t1.start();
        t2.start();
    }
}
```



出现下列执行结果：

![image-20210813144920972](14多线程.assets/image-20210813144920972.png)



### 2、死锁

两个线程各有一把锁，同时继续执行又需要对方的锁，出现相互阻塞的现象。



### 3、解决方案

通过线程通信的方式，让其中一方先放弃手中的锁，让对方先用完。

对方用完之后，在通知你来用。



对象名.wait()     //释放对象锁，然后线程阻塞，直到被唤醒才能继续执行。

对象名.notify()   //唤醒一个等待该对象锁的阻塞线程

对象名.notifyAll()   //唤醒所有等待该对象锁的阻塞线程



```java
package com.hs;

public class MyThread11  implements   Runnable {
    private   Object   a;
    private   Object   b;

    public MyThread11(Object a, Object b) {
        this.a = a;
        this.b = b;
    }

    @Override
    public void run() {

        String name = Thread.currentThread().getName();

        synchronized (a){
            System.out.println(name+"获得了a锁");
            try {
                //当前线程11放弃a对象的锁，然后进入阻塞状态等待，直到被其他线程唤醒才能继续执行。
                //防止没有线程唤醒的情形
                if(Flag.f){
                    a.wait();
                }

            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            synchronized (b){
                System.out.println(name+"获得了b锁");
                System.out.println(name+"11111111111111111111111");
                System.out.println(name+"释放了b锁");
            }
            System.out.println(name+"释放了a锁");
        }
    }
}
```



```java
package com.hs;

public class MyThread12 implements   Runnable{
    private   Object   a;
    private   Object   b;

    public MyThread12(Object a, Object b) {
        this.a = a;
        this.b = b;
    }

    @Override
    public void run() {
        String name = Thread.currentThread().getName();
        synchronized (b){
            System.out.println(name+"获得了b锁");
            synchronized (a){
                Flag.f=false;
                System.out.println(name+"获得了a锁");
                System.out.println(name+"22222222222222222222");
                System.out.println(name+"释放了a锁");

                //只能唤醒一个等待对象a锁的线程，由cpu决定是哪一个线程
                //a.notify();
                //唤醒所有等待对象a锁的线程

                a.notifyAll();
            }

            System.out.println(name+"释放了b锁");
        }
    }
}
```



### 4、wait和sleep区别

都是线程阻塞的方法。



区别：

wait方法是Object方法；sleep方法是Thread方法。

wait方法会释放锁；sleep方法不会释放锁。

wait阻塞，需要其他线程调用notify、notifyAll方法来唤醒；sleep阻塞，到时间自动结束阻塞。



## 十、线程池

### 1、使用Callable实现多线程

（1）Thread  也实现了Runnable

不管是继承Thread，还是实现Runnable，都要重写run方法。

run方法的缺陷：没有返回值。

​				            不能抛出异常。



（2）Callable接口：call方法有返回值，可以声明抛出异常。

```java
public interface Callable<V> {
    /**
     * Computes a result, or throws an exception if unable to do so.
     *
     * @return computed result
     * @throws Exception if unable to compute a result
     */
    V call() throws Exception;
}
```



（3）实现Callable接口创建线程

第一，实现Callable

第二，实现call方法（任务代码，和run一样）：这个方法有返回值，还可以声明抛出异常。

```java
package com.hs;

import java.util.concurrent.Callable;

public class MyThread21 implements Callable<String> {
    @Override
    public String call() throws Exception {
        System.out.println("call  in  .......");
        return "call-110";
    }
}
```

第三，创建线程对象。

第四，开启线程。

```java
package com.hs;

import java.util.concurrent.Future;
import java.util.concurrent.FutureTask;

public class TestCallable {

    public static void main(String[] args) {

//        创建线程任务
        MyThread21   call=new MyThread21();

//        创建线程对象
//        FutureTask=Runnable+ Future
        FutureTask<String>   task=new FutureTask<>(call);
        Thread  t=new Thread(task);

//        开启线程
        t.start();

    }
}
```



（4）Future类

用来跟踪和存储Callable执行过程和结果。

- - | `V`  | `get()`  等待计算完成，然后检索其结果。 |
    | ---- | --------------------------------------- |

- - | `boolean` | `isDone()`  返回 `true`如果任务已完成。 |
    | --------- | --------------------------------------- |



（5）FutureTask

实现了Runnable和Future。

```java
package com.hs;

import java.util.concurrent.ExecutionException;
import java.util.concurrent.Future;
import java.util.concurrent.FutureTask;

public class TestCallable {

    public static void main(String[] args) throws InterruptedException, ExecutionException {

//        创建线程任务
        MyThread21   call=new MyThread21();

//        创建线程对象
//        FutureTask=Runnable+ Future
        FutureTask<String>   task=new FutureTask<>(call);
        Thread  t=new Thread(task);

//        开启线程
        t.start();

//        跟踪线程是否执行完毕
        Thread.sleep(1000);
        System.out.println(task.isDone());
        System.out.println(task.get());
		
    }
}
```



### 2、线程池

线程池是我们创建线程的第四种方式。

线程池是一个线程的集合，包含多个线程。



我们在启动程序时，先创建好一些线程，保存在线程池中。

当我们需要执行任务代码时，从线程池中取出一条线程，然后在这个线程中执行该任务代码。

当任务代码执行完毕时，将线程在放入线程池中。



线程池的优点：

当任务到达时，可以不需要等待线程创建就能立即执行。

降低资源消耗：通过重复利用已创建的线程降低线程创建和销毁造成的消耗。

提高线程的可管理性：线程是稀缺资源，如果无限制的创建，不仅会消耗系统资源，还会降低系统的稳定性，使用线程池可以进行统一的分配，监控和调优。

提高响应速度。



### 3、四种线程池

我们使用java.util.concurrent.Executors 创建线程池。

（1）单一线程池

- - | `static ExecutorService` | `newSingleThreadExecutor()`  创建一个使用从无界队列运行的单个工作线程的执行程序。 |
    | ------------------------ | ------------------------------------------------------------ |



使用场景：多个任务顺序执行。

```java
//      单一线程池：有且仅有一个线程。
        ExecutorService single = Executors.newSingleThreadExecutor();
        Task   t=new Task();//Runnable
        Task2   t2=new Task2();//Callable

//        线程池执行任务：从线程池取出一个线程，执行该任务。
        single.execute(t);
//       线程池提交任务：从线程池取出一个线程，执行该任务。
        single.submit(t2);

//       关闭线程池
		single.shutdown();
```

（2）固定线程池

- - | `static ExecutorService` | `newFixedThreadPool(int nThreads)`  创建一个线程池，该线程池重用固定数量的从共享无界队列中运行的线程。 |
    | ------------------------ | ------------------------------------------------------------ |



使用场景：同时要执行的任务数量比较多的情况，控制线程的数量。

```java
//        固定线程池:有且仅有n个线程
        ExecutorService fixedPool = Executors.newFixedThreadPool(2);

        Task   t=new Task();//Runnable
        Task2   t2=new Task2();//Callable
        Task   t3=new Task();//Runnable
        Task2   t4=new Task2();//Callable
        fixedPool.submit(t);
        fixedPool.submit(t2);
        fixedPool.submit(t3);
        fixedPool.submit(t4);

//        关闭线程池
        fixedPool.shutdown();
```



（3）可变线程池

- - | `static ExecutorService` | `newCachedThreadPool()`  创建一个根据需要创建新线程的线程池，但在可用时将重新使用以前构造的线程。 |
    | ------------------------ | ------------------------------------------------------------ |

初始时，线程数量为0.

当有任务时，创建线程，执行任务。

执行完毕后，放回线程池。

空闲线程空闲时间大于指定时间，销毁该线程。



使用场景：同时执行的任务比较少的时候。

```java
//        可变线程池
        ExecutorService cachedPool = Executors.newCachedThreadPool();

        Task   t=new Task();//Runnable
        Task2   t2=new Task2();//Callable
        Task   t3=new Task();//Runnable
        Task2   t4=new Task2();//Callable
        cachedPool.submit(t);
        cachedPool.submit(t2);
        cachedPool.submit(t3);
        cachedPool.submit(t4);

//        关闭线程池
        cachedPool.shutdown();
```



（4）定时线程池（任务调度线程池）

- - | `static ScheduledExecutorService` | `newScheduledThreadPool(int corePoolSize)`  创建一个线程池，可以调度命令在给定的延迟之后运行，或定期执行。 |
    | --------------------------------- | ------------------------------------------------------------ |



使用场景：延迟执行，或者定期执行。



```java
//        定时线程池
        ScheduledThreadPoolExecutor scheduledPool=(ScheduledThreadPoolExecutor)Executors.newScheduledThreadPool(10);

//        执行任务
        Task   t=new Task();
//        立马执行
//        scheduledPool.submit(t);
//        定时执行
        scheduledPool.schedule(t,10, TimeUnit.SECONDS);

//        关闭线程池
//        不能关闭，应为关闭了线程也被销毁了。
        //scheduledPool.shutdown();
```



### 4、ExecutorService的submit和execute方法区别

submit执行完毕后有返回值。

execute执行完毕后没有返回值。



### 5、四种线程池的比较

![img](https://upload-images.jianshu.io/upload_images/6024478-26abbf2238c2d4ba.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp)



### 6、自定义线程

以上4种线程池，都是使用下面这个构造器创建的。

我们可以使用这个构造器来自定义线程池。

```java
public ThreadPoolExecutor(int corePoolSize, int maximumPoolSize, long keepAliveTime, TimeUnit unit, BlockingQueue<Runnable> workQueue) {
    this(corePoolSize, maximumPoolSize, keepAliveTime, unit, workQueue,
         Executors.defaultThreadFactory(), defaultHandler);
}
```



参数说明：

1、corePoolSize（线程池基本大小）：当向线程池提交一个任务时，若线程池已创建的线程数小于corePoolSize，即便此时存在空闲线程，也会通过创建一个新线程来执行该任务，直到已创建的线程数大于或等于corePoolSize时，（除了利用提交新任务来创建和启动线程（按需构造），也可以通过 prestartCoreThread() 或 prestartAllCoreThreads() 方法来提前启动线程池中的基本线程。）

2、maximumPoolSize（线程池最大大小）：线程池所允许的最大线程个数。当队列满了，且已创建的线程数小于maximumPoolSize，则线程池会创建新的线程来执行任务。另外，对于无界队列，可忽略该参数。

3、keepAliveTime（线程存活保持时间）当线程池中线程数大于核心线程数时，线程的空闲时间如果超过线程存活时间，那么这个线程就会被销毁，直到线程池中的线程数小于等于核心线程数。

4、workQueue（任务队列）：用于传输和保存等待执行任务的阻塞队列。

5、threadFactory（线程工厂）：用于创建新线程。threadFactory创建的线程也是采用new Thread()方式，threadFactory创建的线程名都具有统一的风格：pool-m-thread-n（m为线程池的编号，n为线程池内的线程编号）。

5、handler（线程饱和策略）：当线程池和队列都满了，再加入线程会执行此策略。



![img](https://upload-images.jianshu.io/upload_images/6024478-88ee7b20f8f45825.png?imageMogr2/auto-orient/strip|imageView2/2/w/937/format/webp)























