# 04Jquery框架

## 一、JQuery框架

### 1、是什么

jquery是一个JavaScript框架。



所谓框架，就是使用JavaScript语言进行了封装。

目的是：降低编写程序的难度，写程序更简单。

​                写的少，做得多。



### 2、使用

在html页面中引入jquery-*.js文件。

<script  src="js/jquery-3.6.0.js"></script>



### 3、下载jquery文件

https://jquery.com/download/

### 4、测试

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script  src="js/jquery-3.6.0.js"></script>
    <script>
        // 页面加载完毕后，执行匿名函数
        $(function(){
            alert("11");
        });

    </script>
</head>
<body>
    
</body>
</html>
```



## 二、强大的选择器

万能的工厂函数：$(..)

### 1、基本选择器

通过id选择：$("#id")   返回指定id的单个元素集合（或者数组）。

通过class选择：$(".className")   返回指定class的元素集合。

通过标签名选择：$("标签名")   返回指定标签的元素集合。



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

    <h1>静夜思</h1>
    <h3>李白</h3>
    <p id="p1">床前明月光，</p>
    <p>疑是地上霜。</p>
    <p  class="p34">举头望明月，</p>
    <p  class="p34">低头思故乡。</p>


    <script  src="js/jquery-3.6.0.js"></script>
    <script>
       $(function(){
            //页面加载完毕后执行
            $("p").css("color","red");
            $("#p1").css("color","green");
            $(".p34").css("color","blue");

       }); 
    </script>
</body>
</html>
```





### 2、层次选择器

$("祖先元素  后代元素")    选择祖先元素里面的所有该后代元素

$("父元素>子元素")    选择父元素里面的所有该子元素

$("参照元素+兄弟元素")    选择参照元素的后面一个该兄弟元素。

$("参照元素~兄弟元素")    选择参照元素的后面所有该兄弟元素。



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


    <h1>静夜思</h1>
    <h3>李白</h3>
    <p id="p1">床前明月光，</p>
    <p>疑是地上霜。</p>
    <p  class="p34">举头望明月，</p>
    <p  class="p34">低头思故乡。</p>

    <div>
        <p>11111</p>
    </div>


    <script  src="js/jquery-3.6.0.js"></script>
    <script>

        //$("body  p").css("color","red");
        //$("body>p").css("color","green");

        // $("h1+h3+p").css("color","blue");
        $("h1~p").css("color","yellow");

    </script>
</body>
</html>
```



### 3、其他选择器

（1）过滤选择器

（2）子元素选择器

（3）内容过滤选择器

（4）可见性选择器

（5）属性过滤选择器

（6）表单对象属性选择器

（7）表单选择器



## 三、DOM操作

### 1、查找元素

就是前面所讲的选择器



### 2、创建元素

$("<li></li>");

$("<li>打游戏</li>")

$("<li id='dyx'>打游戏</li>")



### 3、插入元素

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
    

    <ul  id="aihao">
        <li>篮球</li>
        <li>足球</li>
        <li>排球</li>
    </ul>


    <script  src="js/jquery-3.6.0.js"></script>
    <script>

//      创建元素
        var   dyx=$("<li id='dyx'>打游戏</li>");
//      插入元素
        $("#aihao").append(dyx);

        var   kxs=$("<li id='kxs'>看小说</li>");
        $("#aihao").prepend(kxs);

        var   bpq=$("<li>兵乒球</li>");
        $("#aihao").before(bpq);

        var   dz=$("<li>弹珠</li>");
        $("#aihao").after(dz);


    </script>

</body>
</html>
```

### 4、删除元素

当前元素.remove（）方法

```
//      删除元素
        $("#dyx").remove();
```





### 5、克隆元素

目标元素.clone()方法



```
//      克隆元素
        var  kxs2=$("#kxs").clone();
        $("#aihao").append(kxs2);
```





### 6、属性操作

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

    <p   class="pp">测试属性dom操作</p>
    <script  src="js/jquery-3.6.0.js"></script>
    <script>

        $(".pp").attr("style","color:red;");
        var   styleValue=$(".pp").attr("style");
        alert(styleValue);
        $(".pp").removeAttr("style");
        
    </script>


</body>
</html>
```





### 7、内容操作

元素.html(..)

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

    <p>
        <b>测试内容</b>
    </p>

    <script src="js/jquery-3.6.0.js"></script>
    <script>

//      获取内容代码
        var  phtml=$("p").html();
        alert(phtml);

        // 设置内容代码
        $("p").html("<i>你好p</i>");

        // 清空内容
        $("p").html("");

    </script>
    
</body>
</html>
```



### 8、css操作

目标元素.css（..）



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

    <div></div>

    <script  src="js/jquery-3.6.0.js"></script>
    <script>
        // $("div").css("width","400px");
        // $("div").css("height","400px");
        $("div").height(400);
        $("div").width(400);
        $("div").css("background-color","red");


    </script>
</body>
</html>
```



### 9、遍历节点



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

    <table  border="1"   width="400"  height="200">
        <tr>
            <td>学号</td>
            <td>姓名</td>
            <td>性别</td>
            <td>年龄</td>
            <td>操作</td>
        </tr>
        <tr>
            <td>1001</td>
            <td>张三</td>
            <td>男</td>
            <td>23</td>
            <td>
                <a href="#" id="sc1">删除</a>
                <a href="#">修改</a>
            </td>
        </tr>
        <tr>
            <td>1002</td>
            <td>李四</td>
            <td>女</td>
            <td>24</td>
            <td>
                <a href="#" id="sc2">删除</a>
                <a href="#">修改</a>
            </td>
        </tr>

    </table>

    <script src="js/jquery-3.6.0.js"></script>
    <script>

            // 获取父节点
            var   td=$("#sc2").parent();
            td.css("background-color","red");

            // 获取元素的所有子元素
            var   as=td.children();
            as.css("color","green");

            // 获取前一个兄弟元素
            var   tdprev=td.prev().prev();
            tdprev.css("background-color","yellow");

            // 获取后一个兄弟元素
            var   tdnext=tdprev.next();
            tdnext.css("background-color","pink");


            //获取所有兄弟
            var  tds=tdprev.siblings();
            tds.css("font-size","20px");

    </script>

    
</body>
</html>
```





## 四、对象转换

jsDOM对象：是单个元素对象，单个对象的属性和方法。

jquery对象：全是集合对象，集合对象的方法。

### 1、jsDOM对象转jquery对象

var    jsObject=new  Object();

var   jqObject=$(jsObject);



### 2、jquery对象转jsDOM对象

var  jqObject=$("..");

var  jsObject=jqObject.get(i);



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
    
    <P  id="p1">测试对象转换</P>


    <script  src="js/jquery-3.6.0.js"></script>
    <script>
        // js对象
        var  p1=document.getElementById("p1");
        // css方法是jq方法，需要集合调用
        // p1.css("color","red");  //错误的
        // 将js对象转为jq对象（集合）
        var  $p1=$(p1);
        $p1.css("color","red");


        //获取p的内容
        // alert($p1.innerHTML);
        //jq对象转为js对象
        var  p11=$p1.get(0);
        alert(p11.innerHTML);


    </script>


</body>
</html>
```



### 3、数组和集合的遍历



```

// 数组遍历
        var   arr=["a","b","c","d","e"];
        // //数组遍历1
        // for(var  i=0;i<arr.length;i++){
        //     alert(arr[i]);
        // }


        // //数组遍历2
        // for(var  i in arr ){
        //     alert(arr[i]);
        // }


        // 数组遍历3
        // for(var  o  of   arr){
        //     alert(o);
        // }

        // 数组遍历4
        // arr.forEach(function(o){
        //     alert(o);
        // });
        // arr.forEach((o)=>{alert(o);});

//      集合遍历
        var  ps=$("p");
        // for(var  i=0;i<ps.length;i++){
        //     //alert(ps[i].innerHTML);
        //     alert(ps.get(i).innerHTML);
        // }
        
        // 集合出现了死循环
        // for(var  i  in  ps){
        //       alert(ps.get(i).innerHTML);  
        // }

        // for(var  o  of  ps){
        //       alert(o.innerHTML);  
        // }

        // 集合没有forEach方法
        ps.forEach(element => {
            alert(element.innerHTML);
        });

```







## 五、事件绑定



### 1、页面加载完毕事件绑定

$(document).ready(function(){

​	//页面加载完毕要执行的代码；

});



简写：

$(function(){

​	//页面加载完毕要执行的代码；

});



### 2、事件绑定

页面加载完毕之后，页面元素的事件绑定。

语法：

元素.bind("事件名",fn处理函数);



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
    <style>
        div{
            width: 400px;
            height: 400px;
            background-color: beige;
        }
    </style>
    <div>事件绑定测试</div>

    <script src="js/jquery-3.6.0.js"></script>
    <script>
        var  a=1;

        // 事件绑定：click事件
        $("div").bind("click",function(){
            alert("你点击了"+a+"次");
            a++;
        });

        // 事件绑定：mouseover事件
        $("div").bind("mouseover",function(){
            alert("鼠标移入");
        });

        // 事件绑定：mouseout事件
        $("div").bind("mouseout",function(){
            alert("鼠标移出");
        });



    </script>


</body>
</html>
```



### 3、简化方法

绑定点击事件：click方法

绑定鼠标移入事件：mouseover方法

绑定鼠标移出事件：mouseout方法

==



```
    <script src="js/jquery-3.6.0.js"></script>
    <script>
        var  a=1;

        // 事件绑定：click事件
        // $("div").bind("click",function(){
        //     alert("你点击了"+a+"次");
        //     a++;
        // });
        $("div").click(function(){
            alert("你点击了"+a+"次");
            a++;
        });


        // 事件绑定：mouseover事件
        // $("div").bind("mouseover",function(){
        //     alert("鼠标移入");
        // });
        $("div").mouseover(function(){
            alert("简化：移入");
        });

        // 事件绑定：mouseout事件
        // $("div").bind("mouseout",function(){
        //     alert("鼠标移出");
        // });
        $("div").mouseout(function(){
            alert("简化：移出");
        });


    </script>
```



### 4、合并事件

将多个事件一起绑定到我们的事件源对象上。

（1）多次点击事件绑定

元素对象.toggle(fn1,fn2,fn3);

jquery1.8以后已经废弃或者改变。



（2）鼠标移入和移出事件绑定

元素对象.hover(fn1,fn2);



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

    <style>
        div{
            width: 400px;
            height: 400px;
            background-color: beige;
        }
    </style>
    <div>事件绑定测试</div>
    <button>按钮</button>

    <script src="js/jquery-3.6.0.js"></script>
    <script>

//      绑定多次点击事件（1.8之后失效）
        // $("button").toggle(
        //     function(){
        //         alert(1);
        //     },
        //     function(){
        //         alert(2);
        //     },
        //     function(){
        //         alert(3);
        //     }
        // );

//    绑定移入和移出
        $("div").hover(function(){
            alert("移入");
        },function(){
            alert("移出");
        });


    </script>


    
</body>
</html>
```



### 5、一次性事件绑定

元素.one("事件名",fn);



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
    
    <button>点击按钮</button>

    <script  src="js/jquery-3.6.0.js"></script>
    <script>

//      一次性绑定
        $("button").one("click",function(){
            alert(1);
        });

    </script>

</body>
</html>
```



### 6、阻止事件冒泡

（1）事件冒泡

子元素的事件会向上传递给父元素，一直到顶级的document。



（2）阻止事件冒泡

event.stopPropagation();

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

    <div>
        2222
        <p>1111</p>
    </div>

    <script  src="js/jquery-3.6.0.js"></script>
    <script>

        $("p").click(function(){
            alert("p");
            //阻止事件冒泡
            window.event.stopPropagation();
        });

        $("div").click(function(){
            alert("div");
        });


    </script>
</body>
</html>
```





### 7、取消事件默认行为

（1）事件默认行为

超链接有发送请求的功能。

提交按钮有提交表单的功能。



（2）取消事件默认行为

event.preventDefault();

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
    
    <a  href="http://www.baidu.com">连接百度</a>

    <script  src="js/jquery-3.6.0.js"></script>
    <script>

        $("a").click(function(){
            event.preventDefault();
        });

    </script>

</body>
</html>
```



### 8、解除事件绑定

元素.unbind("事件名");

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

    <p>11111</p>
    <script  src="js/jquery-3.6.0.js"></script>
    <script>
        var   i=1;
        $("p").click(function(){
            alert(i);
            i++;
            if(i>=3){
                // 解除绑定
                $(this).unbind("click");
            }
        });
    </script>
</body>
</html>
```







## 六、动画

### 1、显示和隐藏动画

#### （1）show和hide方法

通过改变diplay属性。

display：none |block|inline|inline-block|table|table-cell  |flex  

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
    <style>
        div{
            width:400px;
            height: 200px;
            background-color:red;
        }
    </style>
    <button>显示和隐藏</button>
    <div></div>

    <script src="js/jquery-3.6.0.js"></script>
    <script>

        $("button").click(function(){

            if($("div").is(":visible")){
                $("div").hide(3000);
            }else{
                $("div").show(3000);
            }

        });


    </script>
</body>
</html>
```







#### （2）fadeOut和fadeIn方法

通过改变元素的不透明度来显示和隐藏。

opacity：0~1

```
	$("button").click(function(){

            if($("div").is(":visible")){
                $("div").fadeOut(3000);
            }else{
                $("div").fadeIn(3000);
            }

        });
```





#### （3）slideDown和slideUp方法

通过改变元素的高度来显示和隐藏的。

height：0

```
	$("button").click(function(){

            if($("div").is(":visible")){
                $("div").slideUp(3000);
            }else{
                $("div").slideDown(3000);
            }

         });
```





### 2、自定义动画

元素.animate(params,speed,[callback])

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
    <style>
        div{
            width: 200px;
            height: 200px;
            background-color: red;
            position: relative;
        }
    </style>
    <div></div>

    <script  src="js/jquery-3.6.0.js"></script>
    <script>

        $(function(){

            $("div").animate({top:"+=200px",left:"200px"},3000);
            $("div").animate({height:"300px",width:"300px"},2000,function(){
                alert("动画结束");
            });

        });

    </script>
</body>
</html>
```

