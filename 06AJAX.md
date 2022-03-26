# 06AJAX

## 一、ajax

### 1、ajax

Asynchronous JavaScript and XML（异步的 JavaScript 和 XML）。



### 2、ajax作用

在不重新加载整个页面的情况下，可以与服务器交换数据并更新部分网页内容。

（1）发送请求（同步、异步）

（2）页面不刷新

（3）部分修改页面内容



### 3、同步和异步

同步请求：

我们程序在运行时，发出了一个请求。

等待请求结束后，程序才能继续往下运行。

异步请求：

我们程序在运行时，发出了一个请求。

不等待请求结束，程序直接继续往下运行。





## 二、js原型ajax使用

| 属性               | 描述                                                         |
| :----------------- | :----------------------------------------------------------- |
| onreadystatechange | 存储函数（或函数名），每当 readyState 属性改变时，就会调用该函数。 |
| readyState         | 存有 XMLHttpRequest 的状态。从 0 到 4 发生变化。0: 请求未初始化1: 服务器连接已建立2: 请求已接收3: 请求处理中4: 请求已完成，且响应已就绪 |
| status             | 200: "OK" 404: 未找到页面                                    |





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
    
    <p>11111111</p>
    <button  onclick="ajaxTest();">ajax测试</button>
    <div  id="d1">
        
    </div>

    <script>

        function  ajaxTest(){
             // 发送ajax
            // 1、创建XMLHttpRequest 对象
            var   xhr=new  XMLHttpRequest();

            //2、设置请求信息
            // 请求行：请求的方式get，url，异步true（同步是false）
            //http://127.0.0.1:5500/a.txt
            xhr.open("get","a.txt","true");
            //请求头
            // xhr.setRequestHeader("","");


            // 获取响应
            //绑定请求对象状态改变事件
            //onreadystatechange 事件被触发 4 次（0 - 4）, 分别是： 0-1、1-2、2-3、3-4，对应着 readyState 的每个变化。
            /*
                xhr对象的readyStatus属性：
                0: 请求未初始化
                1: 服务器连接已建立
                2: 请求已接收
                3: 请求处理中
                4: 请求已完成，且响应已就绪
            */
            xhr.onreadystatechange=function(){
                if(xhr.readyState==4&&xhr.status==200){
                    //接收到响应，并且响应内容正常
                    //响应的数据保存在xhr.responseText属性中
                    document.getElementById("d1").innerHTML=xhr.responseText;
                }
            }

            //3、发送请求
            // 请求体：设置post请求体的请求参数
            xhr.send();

        }

       

    </script>


</body>
</html>
```



## 三、jquery中的ajax

### 1、$.ajax({参数})方法

https://www.w3school.com.cn/jquery/ajax_ajax.asp

参数说明：

```
async
类型：Boolean
默认值: true。默认设置下，所有请求均为异步请求。如果需要发送同步请求，请将此选项设置为 false。

type
类型：String
默认值: "GET")。请求方式 ("POST" 或 "GET")， 默认为 "GET"。注意：其它 HTTP 请求方法，如 PUT 和 DELETE 也可以使用，但仅部分浏览器支持。

url
类型：String
默认值: 当前页地址。发送请求的地址。

success
当请求之后调用。传入返回后的数据，以及包含成功代码的字符串。
```

案例：

```
//通过ajax发送请求
            // get请求
            $.ajax({
                url:"a.txt?name=zhangsan&age=23",
                type:"get",
                success:function(data){
                    //data是响应的主体内容
                    //alert(data);
                    $("div").html(data);
                }
            });
```



参数说明2：

```
data
类型：String
发送到服务器的数据。将自动转换为请求字符串格式。GET 请求中将附加在 URL 后。查看 processData 选项说明以禁止此自动转换。必须为 Key/Value 格式。如果为数组，jQuery 将自动为不同值对应同一个名称。如 {foo:["bar1", "bar2"]} 转换为 '&foo=bar1&foo=bar2'。

contentType
类型：String
默认值: "application/x-www-form-urlencoded"。发送信息至服务器时内容编码类型。
默认值适合大多数情况。如果你明确地传递了一个 content-type 给 $.ajax() 那么它必定会发送给服务器（即使没有数据要发送）。
我们发送请求参数最后转为名值对。"name=zhangsan&age=23"

post请求还有一种常用类型：application/json.
{nam=zhangsan&age=23}

dataType
类型：String
预期服务器返回的数据类型。如果不指定，jQuery 将自动根据 HTTP 包 MIME 信息来智能判断，比如 XML MIME 类型就被识别为 XML。在 1.4 中，JSON 就会生成一个 JavaScript 对象，而 script 则会执行这个脚本。随后服务器端返回的数据会根据这个值解析后，传递给回调函数。可用值:
"xml": 返回 XML 文档，可用 jQuery 处理。
"html": 返回纯文本 HTML 信息；包含的 script 标签会在插入 dom 时执行。
"script": 返回纯文本 JavaScript 代码。不会自动缓存结果。除非设置了 "cache" 参数。注意：在远程请求时(不在同一个域下)，所有 POST 请求都将转为 GET 请求。（因为将使用 DOM 的 script标签来加载）
"json": 返回 JSON 数据 。
"jsonp": JSONP 格式。使用 JSONP 形式调用函数时，如 "myurl?callback=?" jQuery 将自动替换 ? 为正确的函数名，以执行回调函数。
"text": 返回纯文本字符串


error
类型：Function
默认值: 自动判断 (xml 或 html)。请求失败时调用此函数。
有以下三个参数：XMLHttpRequest 对象、错误信息、（可选）捕获的异常对象。
如果发生了错误，错误信息（第二个参数）除了得到 null 之外，还可能是 "timeout", "error", "notmodified" 和 "parsererror"。
这是一个 Ajax 事件。
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
    <p>11111111</p>
    <button>ajax测试</button>
    <div  id="d1">
        
    </div>

    <script  src="js/jquery-3.6.0.js"></script>
    <script>
        $("button").click(function(){
            //通过ajax发送请求
            // get请求
            // $.ajax({
            //     url:"a.txt?name=zhangsan&age=23",
            //     type:"get",
            //     success:function(data){
            //         //data是响应的主体内容
            //         //alert(data);
            //         $("div").html(data);
            //     }
            // });


            $.ajax({
                url:"http://localhost:8080/json/ajax",
                type:"post",
                data:"name=zhangsan&age=23",
                success:function(data){
                    alert(data.code);
                    alert(data.message);
                    alert(data.data);    
                }
            });
        });

    </script>
    
</body>
</html>
```



### 2、跨域访问CORS

（1）浏览器为了安全考虑，请求采用同源策略。



url=【协议】://【主机】：【端口号】/【项目根目录/...】

同源：请求协议、主机、端口号、项目根目录都相同

不同源：

http://127.0.0.1:5500/ajax2.html

http://localhost:8080/json/ajax

浏览器如果发现请求不同源，请求发出，但是禁止访问。



（2）跨域处理

跨域处理方法有很多：jsonp、代理服务器、后端授权==。



后端程序授权：

浏览器访问不同的资源，必须后端程序授权才能访问。

```
package com.hs.filter;

import javax.servlet.*;
import javax.servlet.annotation.WebFilter;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebFilter("/*")
public class CorsFilter implements Filter {

    @Override
    public void init(FilterConfig filterConfig) throws ServletException {

    }

    @Override
    public void doFilter(ServletRequest req, ServletResponse res, FilterChain chain) throws IOException, ServletException {
        //处理跨域:授权，谁可以访问我。
//        允许的访问源
        response.setHeader("Access-Control-Allow-Origin", "*");
//         允许的请求方式：get、post
        response.setHeader("Access-Control-Allow-Methods", "*");
//       用来指定本次预检请求的有效期，单位为秒
        response.setHeader("Access-Control-Max-Age", "3600");
//        请求头中必须包含的键值对
        response.setHeader("Access-Control-Allow-Headers", "*");
//      允许访问的凭证是否作为响应的一部分
        response.setHeader("Access-Control-Allow-Credentials", "true");
        
        chain.doFilter(req, res);
    }

    @Override
    public void destroy() {

    }
}
```



```
package com.hs.controller;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;
import java.io.PrintWriter;


@WebServlet("/ajax")
public class AjaxServlet extends HttpServlet {

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {

        //1
        System.out.println("接收到了请求");
        String name = req.getParameter("name");
        String age = req.getParameter("age");
        System.out.println(name);
        System.out.println(age);



        //2
        resp.setContentType("application/json;charset=utf-8");
        PrintWriter out = resp.getWriter();
//        {”code“:”200“,"message":"OK","data":"我爱中国"}
        out.write("{\"code\":\"200\",\"message\":\"OK\",\"data\":\"我爱中国\"}");
        out.close();
    }


    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        doPost(req, resp);
    }
}
```



### 3、$.get(..)和$.post(..)

(1)$.get(..)

get请求

语法：

$.get(*URL,data,function(data,status,xhr),dataType)*

| 参数                        | 描述                                                         |
| :-------------------------- | :----------------------------------------------------------- |
| *URL*                       | 必需。规定您需要请求的 URL。                                 |
| *data*                      | 可选。规定连同请求发送到服务器的数据。                       |
| *function(data,status,xhr)* | 可选。规定当请求成功时运行的函数。 额外的参数： *data* - 包含来自请求的结果数据*status* - 包含请求的状态（"success"、"notmodified"、"error"、"timeout"、"parsererror"）*xhr* - 包含 XMLHttpRequest 对象 |
| *dataType*                  | 可选。规定预期的服务器响应的数据类型。 默认地，jQuery 会智能判断。 可能的类型："xml" - 一个 XML 文档"html" - HTML 作为纯文本"text" - 纯文本字符串"script" - 以 JavaScript 运行响应，并以纯文本返回"json" - 以 JSON 运行响应，并以 JavaScript 对象返回"jsonp" - 使用 JSONP 加载一个 JSON 块，将添加一个 "?callback=?" 到 URL 来规定回调 |

```
$.get("http://localhost:8080/json/ajax?name=zhangsan&age=23",function(data){
                alert(data.code);
                alert(data.message);
                alert(data.data);
            },"json");
```



(2)$.post(..)

post请求

语法：

$(*selector*).post(*URL,data,function(data,status,xhr),dataType)*

```
$.post("http://localhost:8080/json/ajax","name=zhangsan&age=23",function(data){
                alert(data.code);
                alert(data.message);
                alert(data.data);
            },"json");
```





### 4、$.getJSON(..)

必须使用get请求。

用来获取一个json文件的内容。



语法：

$(*selector*).getJSON(*url,data,success(data,status,xhr))*



| 参数                           | 描述                                                         |
| :----------------------------- | :----------------------------------------------------------- |
| *url*                          | 必需。规定将请求发送到哪个 URL。                             |
| *data*                         | 可选。规定发送到服务器的数据。                               |
| *success(\*data,status,xhr\*)* | 可选。规定当请求成功时运行的函数。 额外的参数：*data* - 包含从服务器返回的数据*status* - 包含请求的状态（"success"、"notmodified"、"error"、"timeout"、"parsererror"）*xhr* - 包含 XMLHttpRequest 对象 |



```
$.getJSON("js/city.json",function(data){
​          //alert(data); 
​          for(var sheng of data){
​            alert(sheng.provinceCode+","+sheng.provinceName);
​          }
​      });
```

