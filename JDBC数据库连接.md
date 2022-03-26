# JDBC数据库连接

## 一、jdbc

### 1、java数据库连接

java    database    connection

jdbc是java提供的连接数据库的API，相关的类和接口的统称。



javaSe类库：java.sql.*

- - java.sql.DriverManager 
  - java.sql.Connection
  - java.sql.Statement(PreparedStatement)
  - java.sql.ResultSet



### 2、jdbc作用

连接数据库

进行CRUD操作



### 3、连接mysql原理

底层就是一个基于TCP的网络编程

![image-20210820091739434](JDBC数据库连接.assets/image-20210820091739434.png)



### 4、驱动程序

jdbc连接mysql，需要一个mysql驱动程序。



（1）计算机使用经验

我们一台计算机裸机。

首先，安装bios程序。

其次，安装操作系统。

然后，安装驱动程序。

最后，安装应用程序。



驱动程序是一种可以使[计算机](https://baike.baidu.com/item/计算机/140338)和[设备](https://baike.baidu.com/item/设备/3794003)进行相互通信的[特殊程序](https://baike.baidu.com/item/特殊程序/23123052)。相当于[硬件](https://baike.baidu.com/item/硬件/479446)的接口，[操作系统](https://baike.baidu.com/item/操作系统/192)只有通过这个接口，才能控制硬件设备的工作，假如某设备的驱动程序未能正确安装，便不能正常工作。

驱动程序是操作系统和硬件连接的桥梁。



（2）mysql驱动程序

java应用程序连接mysql数据库的桥梁。

jdbc通过mysql驱动连接mysql数据库。



![image-20210820092839567](JDBC数据库连接.assets/image-20210820092839567.png)





## 二、使用jdbc连接mysql数据库

### 1、注册驱动

#### （1）下载java连接mysql的驱动程序

下载地址：

mysql官网下载

maven仓库下载（推荐）

mysql程序下获取



#### （2）将驱动程序引入项目中使用

在项目根目录下创建lib目录，将驱动jar包拷贝到lib下

![image-20210820095414637](JDBC数据库连接.assets/image-20210820095414637.png)

将lib目录设为项目引入的jar目录

![image-20210820095531796](JDBC数据库连接.assets/image-20210820095531796.png)



![image-20210820095602937](JDBC数据库连接.assets/image-20210820095602937.png)



![image-20210820095631066](JDBC数据库连接.assets/image-20210820095631066.png)



![image-20210820095646588](JDBC数据库连接.assets/image-20210820095646588.png)



最后apply保存



#### （3）Java程序中注册驱动

```java
//        注册驱动
//        8.x
        Class.forName("com.mysql.cj.jdbc.Driver");

//        5.x
//        Class.forName("com.mysql.jdbc.Driver");
```



![image-20210820100522425](JDBC数据库连接.assets/image-20210820100522425.png)









### 2、建立连接

url:

【通信协议】://【主机】:【端口号】/【资源的路径】
//        jdbc:mysql://localhost:3306/my1

```java
//        2\建立连接
//        url:【通信协议】://【主机】:【端口号】/【资源的路径】
//        jdbc:mysql://localhost:3306/my1
//        5.x
//        String   url="jdbc:mysql://localhost:3306/my1";
//        8.x
        String   url="jdbc:mysql://localhost:3306/my1?serverTimezone=Asia/Shanghai";
        String   user="root";
        String   password="root";
        Connection conn=DriverManager.getConnection(url,user,password);
```



### 3、创建sql语句对象

Statement对象，底层封装了Socket。

Statement对象用于发送sql语句，和接收mysql的执行结果。

```java
//        3、创建sql语句对象
        Statement stmt=conn.createStatement();
```



### 4、执行sql

发送sql语句，接收执行结果



```java
//        4\执行sql语句
//        使用stmt发送sql语句给mysql
//        mysql执行sql语句
//          mysql发送执行结果给Java程序

//        ----增删改sql语句的执行，使用executeUpdate(),返回成功影响了几条
//        ----查询sql执行，使用executeQuery()，返回结果集。
//        案例：插入数据到user1表
           int   i=stmt.executeUpdate("insert  into  user1  values(4,'李潇','lixiao','111')");
```



### 5、根据执行结果，进行业务逻辑处理

```java
//          5、根据执行结果，进行业务处理
        System.out.println(i);
        if(i>0){
            System.out.println("添加成功");
        }else{
            System.out.println("添加失败");
        }
```



### 6、断开连接

```java
//        6、断开连接(释放资源)
        stmt.close();
        conn.close();
```





## 三、使用jdbc完成CRUD

### 1、添加操作

```sql
package com.hs;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;

public class JdbcDemo01 {
    public static void main(String[] args) throws Exception {

//       1\ 注册驱动
//       8.x
        Class.forName("com.mysql.cj.jdbc.Driver");

//        5.x
//        Class.forName("com.mysql.jdbc.Driver");

//        2\建立连接
//        url:【通信协议】://【主机】:【端口号】/【资源的路径】
//        jdbc:mysql://localhost:3306/my1
//        5.x
//        String   url="jdbc:mysql://localhost:3306/my1";
//        8.x
        String   url="jdbc:mysql://localhost:3306/my1?serverTimezone=Asia/Shanghai";
        String   user="root";
        String   password="root";
        Connection conn=DriverManager.getConnection(url,user,password);


//        3、创建sql语句对象
        Statement stmt=conn.createStatement();

//        4\执行sql语句
//        使用stmt发送sql语句给mysql
//        mysql执行sql语句
//          mysql发送执行结果给Java程序

//        ----增删改sql语句的执行，使用executeUpdate(),返回成功影响了几条
//        ----查询sql执行，使用executeQuery()，返回结果集。
//        案例：插入数据到user1表
           int   i=stmt.executeUpdate("insert  into  user1  values(4,'李潇','lixiao','111')");

//          5、根据执行结果，进行业务处理
        System.out.println(i);
        if(i>0){
            System.out.println("添加成功");
        }else{
            System.out.println("添加失败");
        }

//        6、断开连接(释放资源)
        stmt.close();
        conn.close();

    }


}
```





### 2、修改操作

```java
package com.hs;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;

public class JdbcDemo02 {
    public static void main(String[] args) throws   Exception{

        //       1\ 注册驱动
//       8.x
        Class.forName("com.mysql.cj.jdbc.Driver");

//        5.x
//        Class.forName("com.mysql.jdbc.Driver");

//        2\建立连接
//        url:【通信协议】://【主机】:【端口号】/【资源的路径】
//        jdbc:mysql://localhost:3306/my1
//        5.x
//        String   url="jdbc:mysql://localhost:3306/my1";
//        8.x
        String   url="jdbc:mysql://localhost:3306/my1?serverTimezone=Asia/Shanghai";
        String   user="root";
        String   password="root";
        Connection conn= DriverManager.getConnection(url,user,password);


//        3、创建sql语句对象
        Statement stmt=conn.createStatement();

//        4\执行sql语句
//        使用stmt发送sql语句给mysql
//        mysql执行sql语句
//          mysql发送执行结果给Java程序

//        ----增删改sql语句的执行，使用executeUpdate(),返回成功影响了几条
//        ----查询sql执行，使用executeQuery()，返回结果集。
//        案例：修改数据到user1表
        String  sql="update   user1   set   name='hello'   where   name  is  null";
        int   i=stmt.executeUpdate(sql);

//          5、根据执行结果，进行业务处理
        System.out.println(i);
        if(i>0){
            System.out.println("修改成功");
        }else{
            System.out.println("修改失败");
        }

//        6、断开连接(释放资源)
        stmt.close();
        conn.close();


    }
}
```



### 3、删除操作

```java
package com.hs;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;

public class JdbcDemo03 {
    public static void main(String[] args) throws  Exception{

        //       1\ 注册驱动
//       8.x
        Class.forName("com.mysql.cj.jdbc.Driver");

//        5.x
//        Class.forName("com.mysql.jdbc.Driver");

//        2\建立连接
//        url:【通信协议】://【主机】:【端口号】/【资源的路径】
//        jdbc:mysql://localhost:3306/my1
//        5.x
//        String   url="jdbc:mysql://localhost:3306/my1";
//        8.x
        String   url="jdbc:mysql://localhost:3306/my1?serverTimezone=Asia/Shanghai";
        String   user="root";
        String   password="root";
        Connection conn= DriverManager.getConnection(url,user,password);


//        3、创建sql语句对象
        Statement stmt=conn.createStatement();

//        4\执行sql语句
//        使用stmt发送sql语句给mysql
//        mysql执行sql语句
//          mysql发送执行结果给Java程序

//        ----增删改sql语句的执行，使用executeUpdate(),返回成功影响了几条
//        ----查询sql执行，使用executeQuery()，返回结果集。
//        案例：user1表，删除id=2数据
        String  sql="delete   from  user1  where  id=2";
        int   i=stmt.executeUpdate(sql);

//          5、根据执行结果，进行业务处理
        System.out.println(i);
        if(i>0){
            System.out.println("删除成功");
        }else{
            System.out.println("删除失败");
        }

//        6、断开连接(释放资源)
        stmt.close();
        conn.close();
    }
}
```





### 4、查询操作

增删改的结果是成功了几条。

查询的结果不是成功了几条，而是查询的结果集。



```java
package com.hs;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

public class JdbcDemo04 {
    public static void main(String[] args) throws  Exception{

        //       1\ 注册驱动
//       8.x
        Class.forName("com.mysql.cj.jdbc.Driver");

//        5.x
//        Class.forName("com.mysql.jdbc.Driver");

//        2\建立连接
//        url:【通信协议】://【主机】:【端口号】/【资源的路径】
//        jdbc:mysql://localhost:3306/my1
//        5.x
//        String   url="jdbc:mysql://localhost:3306/my1";
//        8.x
        String   url="jdbc:mysql://localhost:3306/my1?serverTimezone=Asia/Shanghai";
        String   user="root";
        String   password="root";
        Connection conn= DriverManager.getConnection(url,user,password);


//        3、创建sql语句对象
        Statement stmt=conn.createStatement();

//        4\执行sql语句
//        使用stmt发送sql语句给mysql
//        mysql执行sql语句
//          mysql发送执行结果给Java程序

//        ----增删改sql语句的执行，使用executeUpdate(),返回成功影响了几条
//        ----查询sql执行，使用executeQuery()，返回结果集。
//        案例：查询user1表中所有数据
        String  sql="select  *  from user1";
//        ResultSet结果集：用于保存查询的若干条记录
        ResultSet  rs=stmt.executeQuery(sql);

//          5、根据执行结果，进行业务处理
//        从结果集中取出每一行数据
//        rs.next()  判断结果集中是否有下一条数据
//        如果有，返回true,指针下移，指向这条数据
//        如果没有,返回false
        while(rs.next()){
//            取出这一行数据
//            一行:一列一列的取出

//            （1）第一种取出方式：按照结果集中的列名取出
            int id = rs.getInt("id");
            String name = rs.getString("name");
            String username = rs.getString("username");
            String passwd = rs.getString("passwd");

//            （2）第二种取出方式：按照列的下标
//            int id = rs.getInt(1);
//            String name = rs.getString(2);
//            String username = rs.getString(3);
//            String passwd = rs.getString(4);

            System.out.println(id   +" "+name+" "+username+" "+passwd);
        }



//        6、断开连接(释放资源)
        rs.close();
        
        stmt.close();
        conn.close();
    }
}
```





## 四、用户登录案例

### 1、业务需求：

用户输入用户名和密码，登录。

判断：登录成功还是失败。



### 2、代码实现：

```java
package com.hs;

import java.sql.*;
import java.util.Scanner;

public class UserLogin {
    public static void main(String[] args) {

//        用户输入：用户名和密码
        Scanner   scanner=new Scanner(System.in);
        System.out.println("请输入用户名：");
        String username = scanner.nextLine();
        System.out.println("请输入密码：");
        String password = scanner.nextLine();

//        验证登录：去数据库查询，然后比对
        Connection  conn=null;
        Statement statement=null;
        ResultSet  rs=null;
        try {
            String  driverName="com.mysql.cj.jdbc.Driver";
            String   url="jdbc:mysql:///my1?serverTimezone=Asia/Shanghai";
            String   user="root";
            String   passwd="root";

            Class.forName(driverName);
            conn= DriverManager.getConnection(url,user,passwd);
            statement= conn.createStatement();

//            执行登录查询
            String  sql="";
            rs=statement.executeQuery("select  *  from  user1 where  username='"+username+"'  and  passwd='"+password+"'");

//            登录业务处理
            if(rs.next()){
                System.out.println("登录成功");
            }else{
                System.out.println("登录失败");
            }
        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        }finally {
            if(rs!=null){
                try {
                    rs.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }

            if(statement!=null){
                try {
                    statement.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }

            if(conn!=null){
                try {
                    conn.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
        }


    }
}
```



## 五、PreparedStatement

### 1、登录案例分析

存在的问题：

sql语句需要进行复杂的拼接

存在sql注入漏洞



拼接：select   *   from   user1  where   username='aaa'  and  passwd='bbb'  or  '1=1'

![image-20210820145639575](JDBC数据库连接.assets/image-20210820145639575.png)



### 2、使用PreparedStatement解决

```java
PreparedStatement extends Statement
```

避免复杂的拼接；

避免sql注入漏洞。

![image-20210820151019624](JDBC数据库连接.assets/image-20210820151019624.png)



```java
package com.hs;

import java.sql.*;
import java.util.Scanner;

public class UserLogin02 {
    public static void main(String[] args) {

//        用户输入：用户名和密码
        Scanner scanner=new Scanner(System.in);
        System.out.println("请输入用户名：");
        String username = scanner.nextLine();
        System.out.println("请输入密码：");
        String password = scanner.nextLine();

//        验证登录：去数据库查询，然后比对
        Connection conn=null;
//        Statement statement=null;
        PreparedStatement   ps=null;
        ResultSet rs=null;
        try {
            String  driverName="com.mysql.cj.jdbc.Driver";
            String   url="jdbc:mysql:///my1?serverTimezone=Asia/Shanghai";
            String   user="root";
            String   passwd="root";

            Class.forName(driverName);
            conn= DriverManager.getConnection(url,user,passwd);
//            statement= conn.createStatement();

//           避免了复杂的sql拼接
//            可以使用？作为占位符
            String  sql="select *  from  user1  where  username=?   and  passwd=?";
            ps=conn.prepareStatement(sql);
//            使用set方法设置？的数据
//            可以过滤sql问题
            ps.setString(1,username);
            ps.setString(2,password);

//            执行登录查询
//            String  sql="select  *  from  user1 where  username='"+username+"'  and  passwd='"+password+"'";
//            rs=statement.executeQuery(sql);
            rs=ps.executeQuery();

//            登录业务处理
            if(rs.next()){
                System.out.println("登录成功");
            }else{
                System.out.println("登录失败");
            }
        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        }finally {
            if(rs!=null){
                try {
                    rs.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }

//            if(statement!=null){
//                try {
//                    statement.close();
//                } catch (SQLException throwables) {
//                    throwables.printStackTrace();
//                }
//            }
            if(ps!=null){
                try {
                    ps.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }

            if(conn!=null){
                try {
                    conn.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
        }


    }
}
```



## 六、基于PreparedStatement的CRUD

![image-20210820152948500](JDBC数据库连接.assets/image-20210820152948500.png)

### 1、添加

```java
//    添加操作
    public   void  insert(){
//        四条连接信息
        String  driverName="com.mysql.cj.jdbc.Driver";
        String  url="jdbc:mysql:///my1?serverTimezone=Asia/Shanghai";
        String  user="root";
        String  password="root";

//        jdbc对象
        Connection   conn=null;
        PreparedStatement  ps=null;

        try {
//            1、注册驱动
            Class.forName(driverName);
//            2、建立连接
            conn= DriverManager.getConnection(url,user,password);
//            3、创建sql对象
            String  sql="insert  into  user1  values(5,'高猛','gao','meng')";
            ps=conn.prepareStatement(sql);
//            4、执行sql
            int  i=ps.executeUpdate();
//            5\业务处理
            System.out.println(i);
            if(i>0){
                System.out.println("添加成功");
            }else{
                System.out.println("添加失败");
            }
        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        }finally {
//            6断开连接
            if(ps!=null){
                try {
                    ps.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
            if(conn!=null){
                try {
                    conn.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
        }

    }
```



### 2、修改

```java
//    修改操作
    public    void   update(){
//        四条连接信息
        String  driverName="com.mysql.cj.jdbc.Driver";
        String  url="jdbc:mysql:///my1?serverTimezone=Asia/Shanghai";
        String  user="root";
        String  password="root";

//        jdbc对象
        Connection   conn=null;
        PreparedStatement  ps=null;

        try {
//            1、注册驱动
            Class.forName(driverName);
//            2、建立连接
            conn= DriverManager.getConnection(url,user,password);
//            3、创建sql对象
            String  sql="update   user1  set  name='helloworld' ";
            ps=conn.prepareStatement(sql);
//            4、执行sql
            int  i=ps.executeUpdate();
//            5\业务处理
            System.out.println(i);
            if(i>0){
                System.out.println("修改成功");
            }else{
                System.out.println("修改失败");
            }
        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        }finally {
//            6断开连接
            if(ps!=null){
                try {
                    ps.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
            if(conn!=null){
                try {
                    conn.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
        }
    }
```



### 3、删除

```java
//    删除操作
    public   void   delete(){
//        四条连接信息
        String  driverName="com.mysql.cj.jdbc.Driver";
        String  url="jdbc:mysql:///my1?serverTimezone=Asia/Shanghai";
        String  user="root";
        String  password="root";

//        jdbc对象
        Connection   conn=null;
        PreparedStatement  ps=null;

        try {
//            1、注册驱动
            Class.forName(driverName);
//            2、建立连接
            conn= DriverManager.getConnection(url,user,password);
//            3、创建sql对象
            String  sql="delete  from  user1  where  id=3";
            ps=conn.prepareStatement(sql);
//            4、执行sql
            int  i=ps.executeUpdate();
//            5\业务处理
            System.out.println(i);
            if(i>0){
                System.out.println("删除成功");
            }else{
                System.out.println("删除失败");
            }
        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        }finally {
//            6断开连接
            if(ps!=null){
                try {
                    ps.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
            if(conn!=null){
                try {
                    conn.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
        }
    }
```



### 4、查询

```java
//    查询操作
    public   void  select(){
//        四条连接信息
        String  driverName="com.mysql.cj.jdbc.Driver";
        String  url="jdbc:mysql:///my1?serverTimezone=Asia/Shanghai";
        String  user="root";
        String  password="root";

//        jdbc对象
        Connection   conn=null;
        PreparedStatement  ps=null;
        ResultSet   rs=null;

        try {
//            1、注册驱动
            Class.forName(driverName);
//            2、建立连接
            conn= DriverManager.getConnection(url,user,password);
//            3、创建sql对象
            String  sql="select  *  from  user1";
            ps=conn.prepareStatement(sql);
//            4、执行sql
            rs = ps.executeQuery();
//            5\业务处理
            while(rs.next()){
                int id = rs.getInt("id");
                String name = rs.getString("name");
                String username = rs.getString("username");
                String passwd = rs.getString("passwd");

                System.out.println(id+" "+name+" "+username+" "+passwd);
            }
        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        }finally {
//            6断开连接
            if(rs!=null){
                try {
                    rs.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }

            if(ps!=null){
                try {
                    ps.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
            if(conn!=null){
                try {
                    conn.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
        }
    }
```







## 七、jdbc优化

### 1、增删改优化

（1）增删改方法将sql提取为参数。

（2）增删改将业务处理代码删除，放在方法调用后处理。

（3）增删改操作返回int

（4）将增删改方法合并为更新方法。



```java
//   更新操作：增删改
    public    int   update(String sql){
//        四条连接信息
        String  driverName="com.mysql.cj.jdbc.Driver";
        String  url="jdbc:mysql:///my1?serverTimezone=Asia/Shanghai";
        String  user="root";
        String  password="root";

//        jdbc对象
        Connection   conn=null;
        PreparedStatement  ps=null;

        int  i=0;

        try {
//            1、注册驱动
            Class.forName(driverName);
//            2、建立连接
            conn= DriverManager.getConnection(url,user,password);
//            3、创建sql对象
            ps=conn.prepareStatement(sql);
//            4、执行sql
            i=ps.executeUpdate();
//            5\业务处理
        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        }finally {
//            6断开连接
            if(ps!=null){
                try {
                    ps.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
            if(conn!=null){
                try {
                    conn.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
        }

        return   i;
    }
```





### 2、查询优化

（1）将sql提取为参数

（2）将业务处理代码删除

（3）将结果集作为返回值

```java
//    查询操作
    public   ResultSet  select(String  sql){
//        四条连接信息
        String  driverName="com.mysql.cj.jdbc.Driver";
        String  url="jdbc:mysql:///my1?serverTimezone=Asia/Shanghai";
        String  user="root";
        String  password="root";

//        jdbc对象
        Connection   conn=null;
        PreparedStatement  ps=null;
        ResultSet rs=null;

        try {
//            1、注册驱动
            Class.forName(driverName);
//            2、建立连接
            conn= DriverManager.getConnection(url,user,password);
//            3、创建sql对象
            ps=conn.prepareStatement(sql);
//            4、执行sql
            rs = ps.executeQuery();
//            5\业务处理

        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        }finally {
//            6断开连接
            if(rs!=null){
                try {
                    rs.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }

            if(ps!=null){
                try {
                    ps.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
            if(conn!=null){
                try {
                    conn.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
        }

        return  rs;
    }
```





测试报错：

![image-20210820163607498](JDBC数据库连接.assets/image-20210820163607498.png)

原因：

关闭结果集或者断开连接，不允许再从结果集中取数据！！！



### 3、继续优化查询和更新操作

（1）提取4条连接信息作为工具类的属性

（2）提取jdbc对象作为工具类的属性

（3）将jdbc的前两步提取成一个方法getConnection(),然后在update方法和select方法中调用即可。

（4）将断开连接的操作提取成一个方法close()。

（5）在业务处理完毕后，调用close()方法关闭。

```java
package com.hs.ps;

import java.sql.*;

public class DBUtil {
//    四条连接信息
    private static final String  driverName="com.mysql.cj.jdbc.Driver";
    private static final String  url="jdbc:mysql:///my1?serverTimezone=Asia/Shanghai";
    private static final String  user="root";
    private static final String  password="root";

//  jdbc对象
    private Connection   conn=null;
    private PreparedStatement  ps=null;
    private ResultSet  rs=null;


//    获取连接的方法
    public   void  getConnection(){
        try {
//            1、注册驱动
            Class.forName(driverName);
//            2、建立连接
            conn= DriverManager.getConnection(url,user,password);
        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        }
    }

//    断开连接的方法
    public  void  close(){
        //            6断开连接
        if(rs!=null){
            try {
                rs.close();
            } catch (SQLException throwables) {
                throwables.printStackTrace();
            }
        }
        if(ps!=null){
            try {
                ps.close();
            } catch (SQLException throwables) {
                throwables.printStackTrace();
            }
        }
        if(conn!=null){
            try {
                conn.close();
            } catch (SQLException throwables) {
                throwables.printStackTrace();
            }
        }
    }


//   更新操作：增删改
    public    int   update(String sql){
        int  i=0;
        try {
            getConnection();
//            3、创建sql对象
            ps=conn.prepareStatement(sql);
//            4、执行sql
            i=ps.executeUpdate();
//            5\业务处理
        } catch ( SQLException e) {
            e.printStackTrace();
        }
        return   i;
    }

    //    查询操作
    public   ResultSet  select(String  sql){
        try {
            getConnection();
//            3、创建sql对象
            ps=conn.prepareStatement(sql);
//            4、执行sql
            rs = ps.executeQuery();
//            5\业务处理

        } catch (SQLException e) {
            e.printStackTrace();
        }
        return  rs;
    }
}
```



```java
package com.hs.ps;

import java.sql.ResultSet;
import java.sql.SQLException;

public class Test {
    public static void main(String[] args) {
        DBUtil    db=new DBUtil();
        //int  i=db.update("insert  into  user1  values(7,'liuyuheng','liu','yu')");
        //System.out.println(i);
//        db.close();

//        int i = db.update("delete  from   user1  where  id=1");
//        System.out.println(i);
//        db.close();

//        int  i=db.update("update  user1  set  name='hello'");
//        System.out.println(i);
//        db.close();


//        ResultSet rs = db.select("select  *  from  user1");
//        try {
//            while (rs.next()) {
//                int id = rs.getInt("id");
//                String name = rs.getString("name");
//                String username = rs.getString("username");
//                String passwd = rs.getString("passwd");
//
//                System.out.println(id + " " + name + " " + username + " " + passwd);
//            }
//        }catch (SQLException throwables) {
//            throwables.printStackTrace();
//        }
//        db.close();
    }
}
```

### 4、最终优化

（1）优化驱动

（2）优化sql拼接

（3）优化属性文件

```java
package com.hs.ps;

import java.io.FileReader;
import java.io.IOException;
import java.sql.*;
import java.util.Properties;

public class DBUtil {
//    四条连接信息
    private static  String  driverName;
    private static  String  url;
    private static  String  user;
    private static  String  password;

//  jdbc对象
    private Connection   conn=null;
    private PreparedStatement  ps=null;
    private ResultSet  rs=null;

//    注册驱动：静态块，只需要注册一次即可
    static{

//        0\初始化连接信息
    try {
        Properties  properties=new Properties();
        properties.load(new FileReader("src/db.properties"));

        driverName=properties.getProperty("driverName");
        url=properties.getProperty("url");
        user=properties.getProperty("user");
        password=properties.getProperty("password");
    } catch (IOException e) {
        e.printStackTrace();
    }

    //      1、注册驱动
    try {
//            通过反射，注册驱动
        Class.forName(driverName);
    } catch (ClassNotFoundException e) {
        e.printStackTrace();
    }
}

//    获取连接的方法
    public   void  getConnection(){
        try {
//            2、建立连接
            conn= DriverManager.getConnection(url,user,password);
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }

//    断开连接的方法
    public  void  close(){
        //            6断开连接
        if(rs!=null){
            try {
                rs.close();
            } catch (SQLException throwables) {
                throwables.printStackTrace();
            }
        }
        if(ps!=null){
            try {
                ps.close();
            } catch (SQLException throwables) {
                throwables.printStackTrace();
            }
        }
        if(conn!=null){
            try {
                conn.close();
            } catch (SQLException throwables) {
                throwables.printStackTrace();
            }
        }
    }


//   更新操作：增删改
    public    int   update(String sql,Object[]   objs){
        int  i=0;
        try {
            getConnection();
//            3、创建sql对象
            ps=conn.prepareStatement(sql);
            for (int j = 0; j < objs.length; j++) {
                ps.setObject(j+1,objs[j]);
            }

//            4、执行sql
            i=ps.executeUpdate();
//            5\业务处理
        } catch ( SQLException e) {
            e.printStackTrace();
        }
        return   i;
    }

    //    查询操作
    public   ResultSet  select(String  sql,Object[]   objs){
        try {
            getConnection();
//            3、创建sql对象
            ps=conn.prepareStatement(sql);
            for (int j = 0; j < objs.length; j++) {
                ps.setObject(j+1,objs[j]);
            }
//            4、执行sql
            rs = ps.executeQuery();
//            5\业务处理

        } catch (SQLException e) {
            e.printStackTrace();
        }
        return  rs;
    }
}
```



```java
package com.hs.ps;

import java.sql.ResultSet;
import java.sql.SQLException;

public class Test {
    public static void main(String[] args) {
        DBUtil    db=new DBUtil();

//        Object[]   objs={8,"赵倩","zhao","123"};
//        int  i=db.update("insert  into  user1  values(?,?,?,?)",objs);
//        System.out.println(i);
//        db.close();

//        Object[]  objs={"zhao"};
//        ResultSet  rs=db.select("select  *  from  user1  where  username=?",objs);
//        try {
//            while (rs.next()) {
//                int id = rs.getInt("id");
//                String name = rs.getString("name");
//                String username = rs.getString("username");
//                String passwd = rs.getString("passwd");
//
//                System.out.println(id + " " + name + " " + username + " " + passwd);
//            }
//        }catch (SQLException throwables) {
//            throwables.printStackTrace();
//        }
//        db.close();


        Object[]  objs={};
        ResultSet  rs=db.select("select  *  from  user1",objs);
        try {
            while (rs.next()) {
                int id = rs.getInt("id");
                String name = rs.getString("name");
                String username = rs.getString("username");
                String passwd = rs.getString("passwd");

                System.out.println(id + " " + name + " " + username + " " + passwd);
            }
        }catch (SQLException throwables) {
            throwables.printStackTrace();
        }
        db.close();

       
    }
}
```







## 八、各种数据库连接

### 1、不同的数据库驱动不同

### 2、不同的数据库连接信息不同

（1）mysql

5.x

```
driverName=com.mysql.jdbc.Driver
url=jdbc:mysql:///mydb
user=root
password=root
```

8.x

```
driverName=com.mysql.cj.jdbc.Driver
url=jdbc:mysql:///mydb?serverTimezone=Asia/Shanghai
user=root
password=root
```

（2）oracle

```
driverName=oracle.jdbc.driver.OracleDriver
url=jdbc:oracle:thin:@localhost:1521:orcl
user=
password=
```



（3）sql  server

```
driverName=com.microsoft.sqlserver.SQLServerDriver
url=jdbc:sqlserver://localhost:1433;DatabaseName=mydb
user=
password=
```



（4）db2

```
driverName=com.ibm.db2.jdbc.app.DB2Driver
url=jdbc:db2://localhost:5000/mydb
user=
password=
```

