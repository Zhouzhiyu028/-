# 02DOM操作

## 一、BOM

### 1、浏览器对象模型(BrowserObjectModel)

是用于描述这种对象与对象之间层次关系的模型，浏览器对象模型提供了独立于内容的、可以与浏览器窗口进行互动的对象结构。



### 2、BOM模型

BOM由多个对象组成，其中代表浏览器窗口的Window对象是BOM的顶层对象，其他对象都是该对象的子对象。

document=window.document;

history=window.history;

location=window.location;

forms=window.document.forms;

images=window.document.images;

cookie=window.document.cookie

event=window.event;

![img](https://bkimg.cdn.bcebos.com/pic/810a19d8bc3eb135481babffac1ea8d3fc1f4491?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U4MA==,g_7,xp_5,yp_5/format,f_auto)

### 3、浏览器对象

浏览器根据bom模型来创建这些对象，赋予这些对象属性和方法，以及层次关系。



### 4、浏览器的差异

不同的浏览器厂商对BOM模型的支持是不同的，导致浏览器之间存在一定的差异。





## 二、DOM

### 1、文档对象模型（Document Object Model，简称DOM）

DOM模型是W3C制定的标准接口规范，是一种处理HTML和XML文件的标准API。DOM提供了对整个文档的访问模型，将文档作为一个树形结构，树的每个结点表示了一个HTML标签或标签内的文本项。DOM树结构精确地描述了HTML文档中标签间的相互关联性。





### 2、DOM树形结构

html文档的源码：

```
<html>
	<head>
		<title>文档标题</title>
	</head>
	<body>
		<a   href="">我的链接</a>
		<h1>我的标题</h1>
	</body>
</html>
```



浏览器加载html文档，转为DOM树形结构：

![img](https://bkimg.cdn.bcebos.com/pic/4afbfbedab64034f72451c62afc379310b551dcd?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U4MA==,g_7,xp_5,yp_5/format,f_auto)



DOM模型的顶级对象是document。DOM模型描述了文档内各个标签之间的层次关系，以及各个元素的内容。

浏览器加载html文档，构建dom树。



### 3、document对象

我们使用的document对象是BOM和DOM模型的综合。



## 三、DOM操作

按照dom模型，对页面内容进行增删改查操作。

```
	<ul  id="aihao"  style="background-color: greenyellow;">

        <li id="lanqiu">篮球</li>
        <li id="zuqiu">足球</li>
        <li>排球</li>

    </ul>
    <style>
        .aihao{
            color:red;
        }
    </style>

```



### 1、元素操作

```
		// 1\创建元素
        var  li1=document.createElement("li");
        var  li2=document.createElement("li");

        var  li3=document.createElement("li");
        var  li4=document.createElement("li");


        //2\获取元素(6种方法)
        var  ul=document.getElementById("aihao");

        //3\插入元素
        // ul内容：尾插
        ul.appendChild(li1);
        // ul内容：前插
        var  lanqiu=document.getElementById("lanqiu");
        ul.insertBefore(li2,lanqiu);

        // ul前面
        ul.before(li3);
        // ul后面
        ul.after(li4);

        //4\删除元素
        ul.removeChild(lanqiu);
```



### 2、属性操作

元素对象.setAttribute("属性名","属性值")

元素对象.getAttribute("属性名")

元素对象.removeAttribute("属性名")



```
// 属性操作
        var  zuqiu=document.getElementById("zuqiu");
        //  设置属性
        zuqiu.setAttribute("class","aihao");
        //   获取属性值
        var   zuqiuclass=zuqiu.getAttribute("class");
        //alert(zuqiuclass);
        //   移除属性
        zuqiu.removeAttribute("class");

```



### 3、内容操作

元素对象.innerHTML

用于保存或者修改元素的内容。

```
//  内容操作
//      设置内容
        li1.innerHTML="打游戏";
        li2.innerHTML="吹牛逼";
        li3.innerHTML="<b>放风筝</b>";
        li4.innerHTML="<i>看小说</i>";

//       获取内容
        alert(li4.innerHTML);
        
//      清除内容
		li4.innerHTML="";
        
```



### 4、操作css样式

元素对象.style.样式属性名

```
//   css样式修改
        li4.style.backgroundColor="blue";
        alert(li4.style.backgroundColor);
        
        li4.style.fontSize="24px";
        alert(li4.style.fontSize);
```

