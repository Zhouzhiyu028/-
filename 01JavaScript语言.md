# 01JavaScript语言

## 一、JavaScript语言

### 1、回顾

html5：设计网页的内容

css3：设计网页内容的样式

javaScript:设计网页的动画特效，和服务器交互（调用服务器接口ajax，json）



### 2、JavaScript

java是一种设计网页的脚本语言。

浏览器直接加载运行。

JavaScript是一种【事件驱动】和【面向对象】的【客户端】脚本语言。



### 3、作用

设计网页的动画特效，和服务器交互（调用服务器接口ajax，json）



## 二、JavaScript引入

### 1、行内式

<标签名   onXXX=“javascript代码”   >  ...

### 2、文档式

<script>
​    javascript代码
</script>

### 3、外部链接式

将js代码写入*.js文件中。

然后在页面引入：<script  src="*.js”>  </script>



```html5
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>javascript引入</title>
    <script  src="1.js"></script>
    <script>
        function   abc(){
            alert(2);    
        }
    </script>
</head>
<body>
    
    <p  onclick="alert(1);">测试行内式引入</p>
    <p  onclick="abc()">测试文档式引入</p>
    <p  onclick="ef()">测试外部链接式引入</p>

</body>
</html>
```



1.js

```JavaScript
function   ef(){
    alert(3);
}
```



## 三、javaScript语法

### 1、标识符

采用字母、数字、下划线、美元符号，且不能以数字开头。

不能使用关键字和保留字。

区别大小写。

长度没限制。



行业规范：望文生义。



### 2、数据类型

javascript是弱类型的。



数字型型Number

布尔类型Boolean

字符串型String

Object型

未定义类型undefined

空值型null (没有对象的地址)



### 3、变量

声明：

var    变量名;

赋值：

变量名=值;



```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <script>

        var  a;
        a=10;
        a="abcdefg";
        a=new  Object();
        a=null;
        a=undefined;

        alert(a);

    </script>
</body>
</html>
```



### 4、运算符

（1）算数运算符

```
正负+  -
加减乘除取模  +  -  *   /   %
前后++
前后--
字符串拼接+

注意：没有整除！
```

（2）赋值运算符

```
=
+=   -=   *=     /=   %=
```

（3）比较运算符

```
==   !=
>  >=   <   <=
```

（4）逻辑运算符

```
&&    &    
||    |
!
```

（5）三目运算符

```
(boolean条件)? 语句1 :  语句2  
```



### 5、流程控制语句

（1）流程结构

默认，顺序结构。

选择结构。

循环结构。



（2）if语句

单分支：

```
if(boolean条件){
	条件为真的语句组；
}
```

双分支：

```
if(boolean条件){
条件为真的语句组；	
}else{
条件为假的语句组；
}
```

多分支：

```
if(条件1){
	语句组1
}else   if(条件2){
	语句组2；
}
。。。
else  if(条件n-1){
	语句组n-1；
}else{
	语句组n;
}
```





（3）switch语句

```
switch(表达式){

	case   常量1：语句组1；[break;]
	case   常量2：语句组1；[break;]
	....
	default:语句组n;
}
```





（4）for语句

```
for(初始化表达式;条件语句;迭代语句){
	//循环体
}

比如：
for(var   i=0;i<10;i++){
	alert(i);
}
```

​	

（5）while循环

```
while(boolean条件){
	循环体
}
```



（6）do  while条件

```
do{
	循环体
}while(boolean条件);
```



（7）流程跳转语句

break;

continue;

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
    <script>
        var   y=2021,m=8,d=31;

        var   sum=0;

        for(var  i=1;i<m;i++){
              //第i月的总天数
              var  total=0;
              switch(i){
                  case  1:
                  case  3:
                  case 5:
                  case  7:
                  case 8:
                  case  10: 
                  case 12:total=31;break;
                
                  case  4:
                  case  6: 
                  case  9:
                  case  11:total=30;break;
                  
                  case  2: 
                            if(y%400==0||(y%4==0&&y%100!=0)){
                                   total=29; 
                            }else{
                                total=28;
                            }
              } 
              
              sum+=total;
        }


        sum+=d;

        alert(sum);



    </script>


</body>
</html>
```





```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
    <script>

        var  js=7,h=0;

        var  day=0;
        while(true){
            day++;
            h+=3;
            if(h>=js){
                 break;   
            }
            h-=2;
        }

        alert(day);



    </script>


</body>
</html>
```



### 6、函数定义

函数也就是方法，一个有名字的语句组。

定义：

```
function   函数名(参数){
	方法体
}

参数：直接写名字即可。
```



调用：

```
方法名(实参);
```

方法必须调用才会执行！！！



return语句：

```
return  数据;    //方法体结束，返回一条数据。

return;              //方法体结束
```



```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
    <script>
        var  a=10;

        function  test1(){
            a++;
            alert(a);
        }

        function  test2(b){
             a+=b;
             alert(a);   
        }
    
        test1();
        test2(30);        


        var   balance=200;
        function   quqian(money){
             if(money>balance){
                   alert("余额不足");
                   return; 
             }   
             balance-=money;
        }

        quqian(100);
        quqian(200);

        var  name="zhangsan";
        function   getName(){
            return  name;
        }

        alert(getName());

    </script>
</body>
</html>
```





## 四、事件绑定

### 1、事件驱动

JavaScript是用于制作网页的语言。

JavaScript是一种事件驱动的脚本语言。



当页面上发生某件事情，调用我们的JavaScript代码来处理。

我们需要将这个事件和我们的JavaScript代码进行绑定。



### 2、html事件

https://www.runoob.com/tags/ref-eventattributes.html

（1）鼠标事件

click点击事件

dblclick双击事件

mouseover鼠标移入事件

mouseout鼠标移出事件

mousemove鼠标移动事件



```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script>

        function  danji(){
            alert("单击了一次");
        }

        function   shuangji(){
            alert("双击了一次");
        }

        function   over(){
            alert("鼠标移入div上");
        }

        function   out(){
            alert("鼠标移出div");
        }

        function   move(){
            alert(2);
        }

    </script>
</head>
<body>

    <p  onclick="danji();" > 单击事件</p>
    <p  ondblclick="shuangji();"> 双击事件</p>

    <div  style="width: 200px;height: 200px;background-color: red;"
          onmouseover="over();"   onmouseout="out();"
    >

    </div>


    <div  style="width: 200px;height: 200px;background-color: green;"
          onmousemove="move();"
    >

    </div>
    
</body>
</html>
```



（2）键盘事件

keydown键盘按下事件

keyup键盘弹起事件

keypress键盘按下弹起事件



注意：当前元素必须先获得焦点，才能触发键盘事件！！！

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <script>

        function down(){
               //alert(1);
               //alert(event.keyCode); 
               document.getElementById("ii").innerHTML=event.keyCode;
        }
    </script>

    <input  type="text"   onkeydown="down();">

    <div  id="ii">

    </div>
    
</body>
</html>
```



（3）表单事件

submit表单提交事件

focus获得焦点事件

blur失去焦点事件

# change内容改变事件



```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

    <script>

           function   check(){
                //客户端数据校验
                //如果数据符合要求，发送请求
                //如果不符合要求，不发送请求
                var  username=document.getElementById("username").value;
                var  passwd=document.getElementById("passwd").value;

                if(username==""){
                      alert("用户名必须填写");
                      return  false;  
                }

                if(passwd==""){
                    alert("密码必须填写");
                    return   false;
                }

                // 如果返回false，请求不会提交
                // 如果返回true或没有返回值，请求都会提交
                return   true;
           } 

    </script>
</head>
<body>
    
    <form  action="http://www.baidu.com"  method="GET"  onsubmit="return check();">

        用户名：<input  type="text"  name="username" id="username"><br>
        密码：<input  type="password"  name="passwd" id="passwd"><br>

        <input  type="submit"  value="登录">
    </form>

</body>
</html>
```



```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <script>
        
        function   focus2(){
            document.write("用户名获得了焦点");
        }

        function  blur2(){
            document.write("密码失去了焦点");
        }


        function   change2(){
            alert(11);
        }
    </script>

    <form  action="http://www.baidu.com"  method="GET">

        用户名：<input  type="text"  name="username" id="username" onfocus="focus2();"><br>
        密码：<input  type="password"  name="passwd" id="passwd" onblur="blur2();"><br>
        角色：<input  type="text"   name="role"    onchange="change2();">
              <select   onchange="change2();">
                  <option>老师</option>
                  <option>学生</option>
              </select>
        <input  type="submit"  value="登录">
    </form>

</body>
</html>
```





（4）加载事件

load加载完毕事件，主要用于页面和图片。

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

    <script>
        function   ready(){
            alert("页面加载完了");
        }
    </script>
</head>
<body  onload="ready();">


    <p>
        1111
    </p>
    <p>
        2222
    </p>
    
</body>
</html>
```



### 3、事件绑定

（1）第一种：静态绑定

<html标签     onXXX="JavaScript代码">。。。。



举例：

```
<p id="p1" onclick="alert(1);">点击事件</p>
```



（2）第二种：动态绑定

元素对象.onXXX=方法;

举例：

```
var   p1=document.getElementById("p1");
//匿名函数
p1.onClick=function(){
	alert(1);
}

//有名字的函数
p1.onClick=abc;
function  abc(){
	alert(1);
}
```





## 五、对象

JavaScript是一种【面向对象】的客户端脚本语言。

### 1、浏览器对象

浏览器创建的对象，我们可以在JavaScript中直接使用这些对象。

常见的浏览器对象：

window、location、history、navigator、screen、document、cookie、event



#### （1）window对象

每打开一个浏览器窗口，浏览器就会创建一个window对象。

window对象的属性和方法在调用时，window对象名可以省略不写。

注意：自定义的全局变量和方法，都是window对象的属性和方法。

3个弹出框：

```
		//警告框
        alert("你输入的用户名错误！");
        //确认框
        var   cf=confirm("你确定要删除这条信息吗？");
        alert(cf);
        //输入提示框
        var   pt=prompt("请输入姓名：");
        alert(pt);
```

2个定时器：

```
 //连续定时器：每隔2000毫秒，执行一次abc方法。
        var   i=0;
        var   id1=setInterval("abc();",2000);

        function    abc(){
            alert(i);
            i++;

            if(i==5){
                 clearInterval(id1);   
            }
        }
```



```
//延迟定时器：2000毫秒之后执行一次ef方法，然后定时器结束。
        var  id2=setTimeout("ef();",2000);

        function   ef(){
            alert(3);
        }

        clearTimeout(id2);
```



全局函数：

decodeURI(String)  对encodeURI()编码过的URI进行解码。

encodeURI(String)字符串某些字符将被十六进制的转义序列进行替换。
该方法不会对 ASCII 字母和数字进行编码，也不会对这些 ASCII 标点符号进行编码： - _ . ! ~ * ' ( ) 。

该方法的目的是对 URI 进行完整的编码，因此对以下在 URI 中具有特殊含义的 ASCII 标点符号，encodeURI() 函数是不会进行转义的：;/?:@&=+$,#

注意：如果URI组件中有分隔符，如？   #  %，则应当使用encodeURIComponent()和decodeURIComponent()对各组件进行编码和解码。



escape(String) 函数可对字符串进行编码，这样就可以在所有的计算机上读取该字符串。

其中某些字符被替换成了十六进制的转义序列

该方法不会对 ASCII 字母和数字进行编码，也不会对下面这些 ASCII 标点符号进行编码： * @ - _ + . / 。其他所有的字符都会被转义序列替换。

注释：ES3 反对使用该方法，应用使用 decodeURI() 和 decodeURIComponent() 替代它。

unescape(String)可以使用 unescape()对 escape() 编码的字符串进行解码。

ES3 反对使用该方法，应用使用 decodeURI() 和 decodeURIComponent() 替代它。



eval(String)eval() 函数可计算某个字符串，并执行其中的的 JavaScript 代码。

isNaN(任何类型)用于检查其参数是否是非数字值。

parseInt(String) 解析一个字符串，并返回一个整数。string(必写)  

parseFloat(String)可解析一个字符串，并返回一个浮点数。返回值：返回解析后的数字。



```
		alert(parseInt("10"));
        alert(parseFloat("12.4"));
        alert(isNaN(12.4));
        alert(isNaN("12.4"));
        alert(eval("1+1")); 
```



#### （2）location对象

地址栏对象，用于显示访问目标的url。

属性：

href    保存url。

```
<script>

        alert(location.href);

        location.href="http://www.baidu.com";

    </script>
```



#### （3）document对象

页面文档对象，用于保存整个页面内容的对象。



6个获取页面元素对象的方法：

getElementById("id")

getElementsByName("name")

getElementsByTagName("tagName")

getElementsByClassName("className")

querySelector("css选择器")

querySelectorAll("css选择器")



```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
    <p id="p1"  class="pp" name="pn">111</p>
    <p id="p2"  class="pp" name="pn">222</p>
    <p id="p3"  class="pp" name="pn">333</p>
    <p id="p4"  class="pp" name="pn">444</p>


    <script>
        // 通过id获取，返回元素对象
       var   p1= document.getElementById("p1");
    //    alert(p1.innerHTML);

    // 通过name获取，返回数组
       var   pns=document.getElementsByName("pn");
        for(var  i=0;i<pns.length;i++){
            //  alert(pns[i].innerHTML);   
        }

        // 通过标签名获取，返回数组
        var   ps=document.getElementsByTagName("p");
        for(var  i=0;i<ps.length;i++){
            //  alert(ps[i].innerHTML);   
        }

        // 通过class获取，返回数组
        var   pps=document.getElementsByClassName("pp");
        for(var  i=0;i<pps.length;i++){
            //  alert(pps[i].innerHTML);   
        }

        //通过css选择器,返回第一个元素对象
        var   p1=document.querySelector(".pp");
        alert(p1.innerHTML);

        //通过css选择器,返回所有元素对象的数组
        var  qpps=document.querySelectorAll(".pp");
        for(var  i=0;i<qpps.length;i++){
            alert(qpps[i].innerHTML);
        }


    </script>

</body>
</html>
```





#### （4）cookie对象

浏览器用于保存数据的小文件。

https://www.runoob.com/js/js-cookies.html



获取cookie对象：

document.cookie



保存数据：

document.cookie="键=值 ； 过期时间；访问路径";

如果没有加过期时间，关闭浏览器就会清除这个cookie值。



获取数据：

document.cookie

```
//设置cookie

​    document.cookie="name2=zhangsan";

​    document.cookie="age2=23";

​    document.cookie="sex2=男";



​    //获取cookie

​    //name2=zhangsan;age2=23;sex2=男

​    alert(document.cookie);
```



补充两个对象：

html5提供了两个新对象来替代cookie

https://www.runoob.com/jsref/obj-storage.html

localStorage   永久存储（不清除）

```
localStorage.setItem("key", "value");
localStorage.getItem("key");
localStorage.removeItem("key");
```

sessionStorage   临时存储（关闭浏览器清除）

```
sessionStorage.setItem("key", "value");
var lastname = sessionStorage.getItem("key");
sessionStorage.removeItem("key");
```



#### （5）event对象

event用于表示发生的事件对象。



event对象获取：

```
var  event=  e ||  window.event;
```



使用键盘提交表单案例：

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

    
    <form  name="f1"   onkeydown="tijiao();"  action="http://www.baidu.com"   method="GET">
        用户名:<input  type="text"  name="username"><br>
        密码：<input  type="password"   name="passwd"><br>
        <input   type="submit"   value="登录">
    </form>
    
    <script>
        function   tijiao(e){
            var   event=  e  ||  window.event;

            if(event.ctrlKey&&event.keyCode==13){
                document.f1.submit();    
            }

        }
    </script>

</body>
</html>
```







### 2、js内置对象

JavaScript库中的对象，需要我们使用new来创建。

常见的内置对象：

Number、Boolean、String、Array、Date、Math、RegExp==

#### （1）String

对象创建：

```
var   s1="abcd";
var   s2=new  String("abcd");
```



属性：

length

方法：

- charAt()

- indexOf()

- lastIndexOf()

- replace()

- split()

- substr()

- substring()

  ```
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
  </head>
  <body>
  
      <script>
  
          var  s1="abacda";
          var  s2=new  String("abcd");
  
          //alert(s1);
          //alert(s2);
  
          //属性：
          // alert(s1.length);
  
          //方法：
          // alert(s1.charAt("2"));
          // alert(s1.indexOf("c"));
          // alert(s1.lastIndexOf("c"));
          // alert(s1.trim());
          // alert(s1.substr(1,2));
          // alert(s1.substring(1,2));
          // alert(s1.replace("a","f"));
          // var  ss=s1.split("a");
          // alert(ss.length);
          
          
  
      </script>
     
  </body>
  </html>
  ```



#### （2）Date

用于存储日期时间信息。



对象的创建：

```
//      保存当前日期时间
        var   d1=new  Date();
//      保存指定日期时间
        var  d2=new  Date(2021,9,1,9,52,1);

        alert(d1);
        alert(d2);
```



方法：

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
    <script>

//      保存当前日期时间
        var   d1=new  Date();
//      保存指定日期时间
        var  d2=new  Date(2021,9,1,9,52,1);

        // alert(d1);
        // alert(d2);

        // 方法
        d1.setFullYear(2222);
        d1.setMonth(10);
        d1.setDate(23);
        d1.setHours(10);
        d1.setMinutes(33);
        d1.setSeconds(20);


        alert(d1.getFullYear());
        alert(d1.getMonth());
        alert(d1.getDate());
        alert(d1.getHours());
        alert(d1.getMinutes());
        alert(d1.getSeconds());
        alert(d1.getDay());

    </script>

</body>
</html>
```



#### （3）Math

属性：

PI

方法：

random()

round()

floor()

ceil()

```
<script>

        alert(Math.PI);
        alert(Math.random());
        alert(Math.round(3.5));
        alert(Math.floor(3.5));
        alert(Math.ceil(3.5));

    </script>
```



#### （4）Array

数组对象创建：

```
//      数组对象：长度可变
        var   arr1=new  Array();
        var   arr2=[10,11,12];
        
        //属性
        alert(arr1.length);
        arr1[0]=10;
        arr1[1]=11;
        arr1[2]=12;
        alert(arr1.length);
```

属性：

length

方法：

| [concat()](https://www.runoob.com/jsref/jsref-concat-array.html) | 连接两个或更多的数组，并返回结果。 |
| ------------------------------------------------------------ | ---------------------------------- |
| [join()](https://www.runoob.com/jsref/jsref-join.html)       | 把数组的所有元素放入一个字符串。   |

| [indexOf()](https://www.runoob.com/jsref/jsref-indexof-array.html) | 搜索数组中的元素，并返回它所在的位置。     |
| ------------------------------------------------------------ | ------------------------------------------ |
| [lastIndexOf()](https://www.runoob.com/jsref/jsref-lastindexof-array.html) | 搜索数组中的元素，并返回它最后出现的位置。 |

| [reverse()](https://www.runoob.com/jsref/jsref-reverse.html) | 反转数组的元素顺序。 |
| ------------------------------------------------------------ | -------------------- |

| [sort()](https://www.runoob.com/jsref/jsref-sort.html) | 对数组的元素进行排序。 |
| ------------------------------------------------------ | ---------------------- |

| [pop()](https://www.runoob.com/jsref/jsref-pop.html)   | 删除数组的最后一个元素并返回删除的元素。         |
| ------------------------------------------------------ | ------------------------------------------------ |
| [push()](https://www.runoob.com/jsref/jsref-push.html) | 向数组的末尾添加一个或更多元素，并返回新的长度。 |

```
    <script>
//      数组对象：长度可变
        var   arr1=new  Array();
        var   arr2=[10,11,12];
        
        //属性
        // alert(arr1.length);
        arr1[0]=15;
        arr1[1]=11;
        arr1[2]=12;
        // alert(arr1.length);
        // alert(arr2.length);

        // 方法：
        // alert(arr1.concat(arr2));
        // alert(arr1.join());
        // alert(arr1.indexOf(10));
        // alert(arr1.reverse());
        // arr1.push(9);
        // alert(arr1);
        // arr1.pop();
        // alert(arr1);

        arr1.sort();
        alert(arr1);
    </script>
    
```



#### （5）RegExp

正则表达式。

作用：用于数据校验。



正则语法：

## 修饰符

修饰符用于执行区分大小写和全局匹配:

| 修饰符                                             | 描述                                                     |
| :------------------------------------------------- | :------------------------------------------------------- |
| [i](https://www.runoob.com/js/jsref-regexp-i.html) | 执行对大小写不敏感的匹配。                               |
| [g](https://www.runoob.com/js/jsref-regexp-g.html) | 执行全局匹配（查找所有匹配而非在找到第一个匹配后停止）。 |
| m                                                  | 执行多行匹配。                                           |

## 元字符

元字符（Metacharacter）是拥有特殊含义的字符：

| 元字符                                                       | 描述                                        |
| :----------------------------------------------------------- | :------------------------------------------ |
| [.](https://www.runoob.com/jsref/jsref-regexp-dot.html)      | 查找单个字符，除了换行和行结束符。          |
| [\w](https://www.runoob.com/jsref/jsref-regexp-wordchar.html) | 查找数字、字母及下划线。                    |
| [\W](https://www.runoob.com/jsref/jsref-regexp-wordchar-non.html) | 查找非单词字符。                            |
| [\d](https://www.runoob.com/jsref/jsref-regexp-digit.html)   | 查找数字。                                  |
| [\D](https://www.runoob.com/jsref/jsref-regexp-digit-non.html) | 查找非数字字符。                            |
| [\s](https://www.runoob.com/jsref/jsref-regexp-whitespace.html) | 查找空白字符。                              |
| [\S](https://www.runoob.com/jsref/jsref-regexp-whitespace-non.html) | 查找非空白字符。                            |
| [\b](https://www.runoob.com/jsref/jsref-regexp-begin.html)   | 匹配单词边界。                              |
| [\B](https://www.runoob.com/jsref/jsref-regexp-begin-not.html) | 匹配非单词边界。                            |
| \0                                                           | 查找 NULL 字符。                            |
| [\n](https://www.runoob.com/jsref/jsref-regexp-newline.html) | 查找换行符。                                |
| \f                                                           | 查找换页符。                                |
| \r                                                           | 查找回车符。                                |
| \t                                                           | 查找制表符。                                |
| \v                                                           | 查找垂直制表符。                            |
| [\xxx](https://www.runoob.com/jsref/jsref-regexp-octal.html) | 查找以八进制数 xxx 规定的字符。             |
| [\xdd](https://www.runoob.com/jsref/jsref-regexp-hex.html)   | 查找以十六进制数 dd 规定的字符。            |
| [\uxxxx](https://www.runoob.com/jsref/jsref-regexp-unicode-hex.html) | 查找以十六进制数 xxxx 规定的 Unicode 字符。 |

## 方括号

方括号用于查找某个范围内的字符：

| 表达式                                                       | 描述                               |
| :----------------------------------------------------------- | :--------------------------------- |
| [[abc\]](https://www.runoob.com/jsref/jsref-regexp-charset.html) | 查找方括号之间的任何字符。         |
| [[^abc\]](https://www.runoob.com/jsref/jsref-regexp-charset-not.html) | 查找任何不在方括号之间的字符。     |
| [0-9]                                                        | 查找任何从 0 至 9 的数字。         |
| [a-z]                                                        | 查找任何从小写 a 到小写 z 的字符。 |
| [A-Z]                                                        | 查找任何从大写 A 到大写 Z 的字符。 |
| [A-z]                                                        | 查找任何从大写 A 到小写 z 的字符。 |
| [adgk]                                                       | 查找给定集合内的任何字符。         |
| [^adgk]                                                      | 查找给定集合外的任何字符。         |
| (red\|blue\|green)                                           | 查找任何指定的选项。               |

## 量词

| 量词                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [n+](https://www.runoob.com/jsref/jsref-regexp-onemore.html) | 匹配任何包含至少一个 n 的字符串。例如，/a+/ 匹配 "candy" 中的 "a"，"caaaaaaandy" 中所有的 "a"。 |
| [n*](https://www.runoob.com/jsref/jsref-regexp-zeromore.html) | 匹配任何包含零个或多个 n 的字符串。例如，/bo*/ 匹配 "A ghost booooed" 中的 "boooo"，"A bird warbled" 中的 "b"，但是不匹配 "A goat grunted"。 |
| [n?](https://www.runoob.com/jsref/jsref-regexp-zeroone.html) | 匹配任何包含零个或一个 n 的字符串。例如，/e?le?/ 匹配 "angel" 中的 "el"，"angle" 中的 "le"。 |
| [n{X}](https://www.runoob.com/jsref/jsref-regexp-nx.html)    | 匹配包含 X 个 n 的序列的字符串。例如，/a{2}/ 不匹配 "candy," 中的 "a"，但是匹配 "caandy," 中的两个 "a"，且匹配 "caaandy." 中的前两个 "a"。 |
| [n{X,}](https://www.runoob.com/jsref/jsref-regexp-nxcomma.html) | X 是一个正整数。前面的模式 n 连续出现至少 X 次时匹配。例如，/a{2,}/ 不匹配 "candy" 中的 "a"，但是匹配 "caandy" 和 "caaaaaaandy." 中所有的 "a"。 |
| [n{X,Y}](https://www.runoob.com/jsref/jsref-regexp-nxy.html) | X 和 Y 为正整数。前面的模式 n 连续出现至少 X 次，至多 Y 次时匹配。例如，/a{1,3}/ 不匹配 "cndy"，匹配 "candy," 中的 "a"，"caandy," 中的两个 "a"，匹配 "caaaaaaandy" 中的前面三个 "a"。注意，当匹配 "caaaaaaandy" 时，即使原始字符串拥有更多的 "a"，匹配项也是 "aaa"。 |
| [n$](https://www.runoob.com/jsref/jsref-regexp-ndollar.html) | 匹配任何结尾为 n 的字符串。                                  |
| [^n](https://www.runoob.com/jsref/jsref-regexp-ncaret.html)  | 匹配任何开头为 n 的字符串。                                  |
| [?=n](https://www.runoob.com/jsref/jsref-regexp-nfollow.html) | 匹配任何其后紧接指定字符串 n 的字符串。                      |
| [?!n](https://www.runoob.com/jsref/jsref-regexp-nfollow-not.html) | 匹配任何其后没有紧接指定字符串 n 的字符串。                  |



*<u>**常见的正则表达式**</u>*

电话号码：^1[ 358769 ] [ 0-9 ]{9}$

中文姓名：^[\u4e00-\u9fa5]{2,4}$

邮箱：  ^\w{6,18}@\w{2,10}.\w{2,5}$





创建正则表达式对象：

```
var   r1=new  RegExp("正则表达式");   //正则表达式中有特殊字符，需使用反斜杠转义
var   r2=/正则表达式/;        //正则表达式中有特殊字符，不需要转义
```



校验数据的方法：test(数据)；返回值boolean。

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

    <form   action="http://www.baidu.com"   method="GET"  onsubmit="return check();">

        用户名：<input  type="text"  name="username"   id="username"><br>
        密码：<input  type="password"  name="passwd"   id="passwd"><br>
        确认密码：<input  type="password"  name="passwd2"   id="passwd2"><br>
        电话：<input  type="text"  name="tel"   id="tel"><br>
        邮箱：<input  type="text"  name="email"   id="email"><br>
        姓名：<input  type="text"  name="name"   id="name"><br>
        
        <input  type="submit"  value="注册">
    </form>
    <script>
        function    check(){
            // 数据校验：使用正则表达式
            // 用户名：必须填写，6-18，只能使用字母
            var  usernameR=/^[A-z]{6,18}$/;
            var  username=document.getElementById("username").value;
            if(username==""){
                alert("用户名必填");
                return false;    
            }
            if(!usernameR.test(username)){
                alert("你输入的用户名不符合要求");
                return   false;    
            }

            //密码：必填，6-10，只能使用数字
            var   passwdR=/^[0-9]{6,10}$/;
            var   passwd=document.getElementById("passwd").value;
            if(!passwdR.test(passwd)){
                alert("你输入的密码不正确");
                return  false; 
            }

            //确认密码：和密码一样
            var   passwd2=document.getElementById("passwd2").value;
            if(passwd2!=passwd){
                alert("确认密码不一致");
                return  false;
            }

            //电话号码：选填
            var  telR=/^1[356789][0-9]{9}$/;
            var  tel=document.getElementById("tel").value;
            if(tel.trim()!=""){
                if(!telR.test(tel)){
                    alert("电话格式不正确");
                    return  false;
                }
            }

            //省略邮箱和姓名的校验

            return true;
        }
    </script>
    
</body>
</html>
```



总结：

需要对用户填写的数据进行校验，但是用户选择的数据不需要校验。



### 3、自定义对象

需要我们自己提供对象的模板，然后使用new创建对象。



#### （1）字面量

```
//1、字面量
        var    student1={
            name:"zhangsan",
            age:23,
            sex:"男",
            eat:function(food){
                alert("吃"+food);
            },
            sleep:function(){
                alert("睡觉");
            }
        };

        alert(student1.name);
        alert(student1.age);
        alert(student1.sex);
        student1.eat("屎");
        student1.sleep();
```

#### （2）原型+构造函数

```
function   Student(name,age,sex){
            this.name=name;
            this.sex=sex;
            this.age=age;

            this.eat=function(food){
                alert("eat"+food);
            }

            this.sleep=function(){
                alert("sleep");
            }
        }

        var   s1=new  Student("zhangsan","男",23);
        var   s2=new  Student("lisi","女",24);
        alert(s1.name);
        alert(s1.sex);
        alert(s1.age);
        s1.eat("香蕉");
        s1.sleep();

        alert(s2.name);
        alert(s2.sex);
        alert(s2.age);
        s2.eat("火锅");
        s2.sleep();
```



原型：它是一个对象。

每一个函数都对应有一个唯一的对象，这个对象叫原型对象。

原型对象用于保存共享的属性和方法。

```
//      构造函数+原型
        function   Student(name,age,sex){
            this.name=name;
            this.sex=sex;
            this.age=age;

            this.eat=function(food){
                alert("eat"+food);
            }

            this.sleep=function(){
                alert("sleep");
            }
        }


        //原型对象
        Student.prototype.className="hs";
        Student.prototype.study=function(){
            alert("xuexi");
        }

        var   s1=new  Student("zhangsan","男",23);
        var   s2=new  Student("lisi","女",24);

        alert(s1.className);
        alert(s2.className);
        s1.study();
        s2.study();


        // alert(s1.name);
        // alert(s1.sex);
        // alert(s1.age);
        // s1.eat("香蕉");
        // s1.sleep();

        // alert(s2.name);
        // alert(s2.sex);
        // alert(s2.age);
        // s2.eat("火锅");
        // s2.sleep();
```



#### （3）es6新语法：class

```
//      es6:class
        class   Student{
            
            constructor(name,sex,age){
                this.name=name;
                this.sex=sex;
                this.age=age;
            }

            eat(food){
                alert("吃"+food);
            }

            sleep(){
                alert("sleep");
            }

        }

        var  s11=new  Student("zhang1","男",21);
        var  s12=new  Student("zhang2","女",22);
        alert(s11.name);
        alert(s11.sex);
        alert(s11.age);
        s11.eat("苹果");
        s11.sleep();

        alert(s12.name);
        alert(s12.sex);
        alert(s12.age);
        s12.eat("梨");
        s12.sleep();
```





