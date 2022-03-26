# 05JSON

## 一、json

### 1、前后端分离开发

前端人员：负责应用程序界面的设计，和后端交互（调用java接口，数据展示）。

后端人员：设计数据库，编写java接口。



前后端交互时，需要发送数据。

数据发送必须遵守约定的格式。



全球统一格式：xml和json格式。



### 2、json

**J**ava**S**cript **O**bject **N**otation(JavaScript 对象表示法)



### 3、json作用

JSON 是存储和交换文本信息的语法，类似 XML。



### 4、json特点

数据结构更简单，解析方便。

轻量级，占用空间小。



## 二、json格式

### 1、表示对象

json对象格式语法：

{

​	"属性名1":"属性值1"，

​	"属性名2":"属性值2"，

。。。。

}



比如1：学生张三的信息

{

"name":"张三",

"sex":"男",

"age":"23",

"birth":"2010-10-10"

}





比如2：学生李四的信息

{

"name":"李四",

"sex":"男",

"age":"23",

"birth":"2010-10-10"，

"hobby":["篮球","足球","打游戏"]

}



### 2、表示数组或集合

json数组格式语法：

[元素1，元素2，。。。。]



比如1：5个学生的姓名

["张三","李四","王五","马六","赵琦"]

比如2：3个学生的信息

[

{"name":"张三","sex":"男","age":"23","birth":"20202-1-1"},

{"name":"lisi","sex":"女","age":"24","birth":"2020-2-2"},

{"name":"wangwu","sex":"男","age":"25","birth":"2020-3-3"}

]





## 三、json在JavaScript中使用

### 1、json对象的使用

```
	// json对象
        var   jsonObj={
                        "name":"李四",
                        "sex":"男",
                        "age":"23",
                        "birth":"2010-10-10",   
                        "hobby":["篮球","足球","打游戏"]
                        };
        //获取json对象中保存的数据                
        alert(jsonObj.name+","+jsonObj.sex+","+jsonObj.age+","+jsonObj.birth);
        for(var  h  of  jsonObj.hobby){
            alert(h);
        }  
```





### 2、json数组的使用

```
// json数组
        var  jsonArr=[
                    {"name":"张三","sex":"男","age":"23","birth":"20202-1-1"},
                    {"name":"lisi","sex":"女","age":"24","birth":"2020-2-2"},
                    {"name":"wangwu","sex":"男","age":"25","birth":"2020-3-3"}
                    ];
        //获取json数组的数据
        for(var   student  of   jsonArr){
            alert(student.name+","+student.sex+","+student.age+","+student.birth);
        }
```



### 3、json对象转为json格式String

客户端发送数据，最后要求发送的是字符串。

需要将json对象转为json格式的字符串。



# JSON.stringify()

```
//json对象转为字符串
        var   jsonString=JSON.stringify(jsonObj);
        alert(jsonString);

        var   jsonString2=JSON.stringify(jsonArr);
        alert(jsonString2);
```





### 4、json格式String转为json对象

客户端从服务器获取的响应的json格式的字符串数据。

为了方便解析，需要将字符串转为json对象。



# JSON.parse()

```
//json字符串转为json对象
        var  jsonObj2=JSON.parse(jsonString);
        var   jsonArr2=JSON.parse(jsonString2);

        // alert(jsonObj2.name+" "+jsonObj2.sex+" "+jsonObj2.age+" "+jsonObj2.birth);
        // for(var  h  of  jsonObj2.hobby){
        //     alert(h);
        // }  
        
        
        for(var  student  of   jsonArr2){
            alert(student.name+" "+student.sex+" "+student.age+" "+student.birth);
        }
```







## 四、json在java中使用

### 1、json字符串和java对象的转换

```
package com.hs;

import com.fasterxml.jackson.annotation.JsonFormat;

import java.util.Date;

public class Student {
    private  String  name;
    private  String  sex;
    private  int     age;
    @JsonFormat(pattern = "yyyy-MM-dd")
    private Date birth;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getSex() {
        return sex;
    }

    public void setSex(String sex) {
        this.sex = sex;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public Date getBirth() {
        return birth;
    }

    public void setBirth(Date birth) {
        this.birth = birth;
    }
}
```



```
package com.hs;

import com.fasterxml.jackson.core.JsonProcessingException;
import com.fasterxml.jackson.databind.ObjectMapper;

public class JsonTest {
    public static void main(String[] args) throws JsonProcessingException {

        ObjectMapper  mapper=new ObjectMapper();

//        1、json字符串转为java对象
        String   jsonString="{\"name\":\"zhangsna\",\"sex\":\"男\",\"age\":\"23\",\"birth\":\"2020-10-10\"}";

        Student student = mapper.readValue(jsonString, Student.class);
//        System.out.println(student.getName());
//        System.out.println(student.getSex());
//        System.out.println(student.getAge());
//        System.out.println(student.getBirth());

//        2、java对象转为json字符串
        String jsonString2 = mapper.writeValueAsString(student);
        System.out.println(jsonString2);



    }
}
```



### 2、json字符串和java数组\集合的转换



```
package com.hs;

import com.fasterxml.jackson.core.JsonProcessingException;
import com.fasterxml.jackson.core.type.TypeReference;
import com.fasterxml.jackson.databind.ObjectMapper;

import java.lang.reflect.Array;
import java.lang.reflect.Type;
import java.util.*;

public class JsonTest2 {
    public static void main(String[] args) throws JsonProcessingException {

//       1\java集合转JSON数组字符串
        List<Student> list=new ArrayList<>();
        Student  s1=new Student();
        Student  s2=new Student();
        Student  s3=new Student();

        s1.setName("张三");
        s1.setAge(23);
        s1.setSex("男");
        s1.setBirth(new Date());

        s2.setName("张三2");
        s2.setAge(23);
        s2.setSex("男");
        s2.setBirth(new Date());

        s3.setName("张三3");
        s3.setAge(23);
        s3.setSex("男");
        s3.setBirth(new Date());

        list.add(s1);
        list.add(s2);
        list.add(s3);

        ObjectMapper  mapper=new ObjectMapper();
        String json = mapper.writeValueAsString(list);
        //System.out.println(json);

        
        //2\将json转为java数组和集合
//        数组
        Student[]   arrs= mapper.readValue(json,Student[].class);
        for (Student student : arrs) {
            System.out.println(student.getName());
            System.out.println(student.getAge());
            System.out.println(student.getSex());
            System.out.println(student.getBirth());
        }

//        集合方式一
//        List<LinkedHashMap>   list2= mapper.readValue(json,List.class);
//        for (LinkedHashMap map : list2) {
//            System.out.println(map.get("name"));
//            System.out.println(map.get("age"));
//            System.out.println(map.get("sex"));
//            System.out.println(map.get("birth"));
//        }
//          集合方式二
//        List<Student>   list3= Arrays.asList(mapper.readValue(json,Student[].class));
//        for (Student student : list3) {
//            System.out.println(student.getName());
//            System.out.println(student.getAge());
//            System.out.println(student.getSex());
//            System.out.println(student.getBirth());
//        }
//        集合方式三
        List<Student>   list4= mapper.readValue(json, new TypeReference<List<Student>>() {});
        for (Student student : list4) {
            System.out.println(student.getName());
            System.out.println(student.getAge());
            System.out.println(student.getSex());
            System.out.println(student.getBirth());
        }


    }
}

```



### 3、json第三方API使用

Jackson，Gson，fastJson，json-lib

我们今天使用Jackson。



