# MySql数据库

## 一、数据库的概念

### 1、数据库

（1）存储数据的仓库。

比如：

用户信息

商品信息

订单信息

购物信息

==

（2）将数据按照指定的结构，存储在计算机的硬盘上。

硬盘：永久存储。



### 2、数据模型

（1）网状模型

（2）层次模型

（3）关系模型（重点）

将数据以二维表格的形式来存储。

如下：

一行数据，我们称为一条记录；

列，我们称为字段；

每列的数据，我们为数据项。

| 姓名 | 年龄 | 性别 | 成绩 |
| ---- | ---- | ---- | ---- |
| 张三 | 30   | 男   | 93   |
| 李四 | 40   | 女   | 47   |
|      |      |      |      |
|      |      |      |      |
|      |      |      |      |



### 3、关系型数据库

使用关系模型存储数据的数据库，我们叫关系型数据库。

常见：

mysql，oracle，db2，sql server。





### 4、mysql数据库

AB公司设计的，被sun收购，sun被oracle收购。

oracle现有2大数据库：mysql，oracle。

 

### 5、DBMS

（1）DB

数据库DataBase

（2）DBMS

数据库管理系统DataBase   Management   System

（3）DBMS是一个软件

功能：

创建数据库和管理数据库。

==



（4）DBA

数据库管理员DataBase  Adminstrator
工作岗位



## 二、数据库的安装

### 1、常用的版本

5.X

8.X

### 2、下载

https://www.mysql.com/downloads/

（1）安装版

（2）压缩版

### 3、mysql安装

（1）压缩版安装

https://www.cnblogs.com/qujialin/p/11191806.html

（2）安装版安装

双击运行，下一步。

安装时，需要检查安装环境（.net   framework  4.5.2）。



### 4、检查安装结果

mysql    -uroot   -proot

![image-20220315112158534](MySql数据库.assets/image-20220315112158534.png)

### 5、mysql卸载

如果卸载后，再安装，必须卸载干净。

（1）卸载程序

删除服务

（2）删除程序目录

（3）删除注册表

（4）删除mysql相关的其他目录，以及隐藏文件。



建议：

使用卸载软件去卸载！！



## 三、数据库操作

![image-20220315114129871](MySql数据库.assets/image-20220315114129871.png)

### 1、登录mysql  DBMS

mysql      [-h主机 -P端口号]    -u用户名    -p密码

![image-20220315112659787](MySql数据库.assets/image-20220315112659787.png)

### 2、查看管理的所有数据库

show   databases;

![image-20220315113214815](MySql数据库.assets/image-20220315113214815.png)

### 3、创建新数据库

create   database   数据库名;

![image-20220315113412179](MySql数据库.assets/image-20220315113412179.png)

### 4、删除数据库

drop     database   数据库名;

![image-20220315113523480](MySql数据库.assets/image-20220315113523480.png)

### 5、选择数据库

use   数据库名;

选择或切换管理的数据库。

![image-20220315113804285](MySql数据库.assets/image-20220315113804285.png)



### 6、退出系统

exit

## 四、表操作

### 1、表的存储

mysql数据库中，使用表来存储数据。

我们对数据进行了分类，每类信息使用一张表来存储。

### 2、数据类型

（1）数字型

int   整数

double  双精度浮点数

decimal  浮点数，可以指定精度



数据可以直接写出：11  ，  11.5

（2）字符串型

CHAR（n）   固定长度字符串

VARCHAR（n）   可变长度字符串

TEXT             大文本

BLOB           二进制文件内容



存储'a'，char(3)和varchar(3)区别：

char(3)  ,  'a  '

varchar(3),'a'



字符串类型的数据,必须加单引号：'afjalkdjflkads'



（3）日期时间型

DATE    存储日期：年月日

TIME    存储时间：时分秒

YEAR    存储年份

DATETIME    存储日期时间：年月日时分秒

TIMESTAMP    存储时间戳



日期时间的本质：就是一个带有特殊格式的字符串。YYYY-MM-DD HH:MM:SS。

数据：'2020-2-2  10:10:10'



（4）null值

null是一个缺省值，可以是任何类型的数据。

null表示未知的值。



### 3、表的创建

语法：

create   table   表名(

​	列名1   数据类型   [列级约束],

​	...

​	列名n   数据类型  [列级约束]，

​	[表级约束]，[索引]

);

![image-20220315151305503](MySql数据库.assets/image-20220315151305503.png)

### 4、查询所有表

show  tables;

![image-20220315151316844](MySql数据库.assets/image-20220315151316844.png)



### 5、查看表结构

desc   表名；



![image-20220315151353018](MySql数据库.assets/image-20220315151353018.png)





### 6、删除表

drop   table    表名;

![image-20220315151529884](MySql数据库.assets/image-20220315151529884.png)



### 7、修改表结构

alter  table  表名    修改操作；



![image-20220315151818622](MySql数据库.assets/image-20220315151818622.png)





## 五、数据操作CRUD（重点）

### 1、新增记录

（1）插入一行所有列的数据

insert  into  表名  values(一行所有列的数据);       

![image-20220315160002752](MySql数据库.assets/image-20220315160002752.png)

（2）插入一行部分列的数据

insert   into  表名（部分列）    values(一行部分列数据)

注意：没有插入数据的列，系统自动插入缺省值null

![image-20220315160323086](MySql数据库.assets/image-20220315160323086.png)

（3）插入多条数据

insert   into   表名 （。。。）   values(....),(....),。。。(....)；

![image-20220315160704152](MySql数据库.assets/image-20220315160704152.png)



### 2、查询记录

select   *   from  表名;



![image-20220315160021521](MySql数据库.assets/image-20220315160021521.png)



### 3、删除记录

#### （1）delete删除

语法：

delete   from  表名    [where  条件];

如果没有条件，表示清空表，删除所有行的数据。

如果有条件，删除满足条件的行。



![image-20220315162430236](MySql数据库.assets/image-20220315162430236.png)

where 条件：

1）使用比较运算符

=  !=        >   >=   <  <=   

![image-20220315163038500](MySql数据库.assets/image-20220315163038500.png)

2）多条件

使用and 和  or连接



![image-20220315163508704](MySql数据库.assets/image-20220315163508704.png)

3）连续范围条件

列名  between  ..   and   ..

列名   not   between   ..  and   ..

![image-20220315163847875](MySql数据库.assets/image-20220315163847875.png)

4）不连续的范围

列名   in(情况1，情况2.....)

列名   not   in(情况1，情况2.....)

![image-20220315164114457](MySql数据库.assets/image-20220315164114457.png)

5）模糊筛选

like

not   like

%表示：匹配0到多个字符，比如'张%'   匹配  张     张三   张三丰   张三蛇精病

_表示：一个字符



![image-20220315164644410](MySql数据库.assets/image-20220315164644410.png)



6）null值判断

null值，表示未知的值。

null和任何值都不相等，包括null。

使用：

​	列名  is   null

​	列名  is   not   null

![image-20220315164941334](MySql数据库.assets/image-20220315164941334.png)





#### （2）truncate删除

truncate   table   表名

清空表数据。

![image-20220315165251452](MySql数据库.assets/image-20220315165251452.png)

#### （3）truncate和delete区别

truncate  清空表，同时会删除索引。

delete 可以清空表，也可以删除部分记录，不会删除索引。



### 4、修改记录

update   表名      

set   字段名=新的值,.......    

 [where    条件];



如果没有条件，修改所有行。

如果有条件，修改满足条件的行。

![image-20220315173215807](MySql数据库.assets/image-20220315173215807.png)





## 六、客户端工具的安装和使用

### 1、命令行操作

![image-20220315173428193](MySql数据库.assets/image-20220315173428193.png)

### 2、图形化的客户端工具

mysql-front

**navicat**

**sqlyog**

mysql自带的客户端工具



### 3、navicat安装和破解

看教程

![image-20220315180151676](MySql数据库.assets/image-20220315180151676.png)

### 4、navicat使用

（1）建立连接

![image-20220315180208963](MySql数据库.assets/image-20220315180208963.png)

（2）各种数据库操作

![image-20220315180233029](MySql数据库.assets/image-20220315180233029.png)

## 七、查询语句-语法

select   [distinct]    *|列名

from   表名  ...   [on  连接条件]

where   条件

group   by   分组字段..

having   条件

order   by   排序字段,排序方向

limit    起始位置，长度;  



## 八、单表查询

### 1、from子句

从那张表中查询。

可以是一张表，也可以查多张表

select  *  from  表名

select  *   from  表名1,表名2   ...

![image-20220316100005447](MySql数据库.assets/image-20220316100005447.png)



### 2、where子句

筛选表中满足条件的行。

条件的写法：

（1）使用比较运算符

（2）多条件使用and 和  or 连接

（3）连续范围：between  ..  and  ..

（4）不连续范围：in(..)

（5）模糊匹配：like      %   _

（6）null判断：is   null



![image-20220316101250056](MySql数据库.assets/image-20220316101250056.png)

### 3、select子句

筛选列。

 *代表所有列。

也可以只选择部分列。



select   *   from 表名;

select  所有列名  from  表名

select  部分列名   from 表名



![image-20220316100320863](MySql数据库.assets/image-20220316100320863.png)



distinct作用：将结果集中重复的行合并为一条。

![image-20220316100608529](MySql数据库.assets/image-20220316100608529.png)



### 4、order  by  子句

对查询结果进行排序。

排序有两种方向：默认升序，asc；降序，desc。

语法：order   by   字段名  方向

![image-20220316103918304](MySql数据库.assets/image-20220316103918304.png)







### 5、limit子句

限制。

从结果集中取出一部分数据。



语法：limit   结果集种的起始位置，长度

![image-20220316104657644](MySql数据库.assets/image-20220316104657644.png)

limit   长度；从0开始取

![image-20220316104924961](MySql数据库.assets/image-20220316104924961.png)

limit主要用于分页查询。

每页的起始位置=（页码-1）*每页长度



###  6、group  by分组查询

（1）分组查询

前面不分组查询，查询结果是表中的数据。

分组查询查，不是表中数据，而是查询到的是表中数据的统计信息。

一组对应一条统计信息。



分组的目的是为了统计每组的信息！！！！



统计：使用聚合函数。

count(列名)统计每组的数量。

sum(列名)统计每组该列总和。

avg(列名)统计每组该列的平均值。

max(列名)统计每组该列的最大值。

min(列名)统计每组该列的最小值。

![image-20220316113215030](MySql数据库.assets/image-20220316113215030.png)





![image-20220316113153990](MySql数据库.assets/image-20220316113153990.png)



（2）别名

可以给结果集中的列起别名，也可以给表名起别名。



表：是物理硬盘中的一个存储空间。永久存储。

结果集：是物理内存中的一个存储空间。临时存储。

![image-20220316115243406](MySql数据库.assets/image-20220316115243406.png)





（3）筛选满足条件的组

having   条件；

![image-20220316113503949](MySql数据库.assets/image-20220316113503949.png)







where和having区别：

where是分组之前，选择的是表中的行；

having是分组之后，选择满足条件的组。



![](MySql数据库.assets/image-20220316114139785.png)





## 九、查询执行顺序

### 1、书写语法顺序

select   [distinct]    *|列名

from   表名  ...

where   条件

group   by   分组字段..

having   条件

order   by   排序字段,排序方向

limit    起始位置，长度;  



### 2、查询执行顺序

from

where

group by  

select   【distinct】

【having】

order  by

limit



## 十、多表查询



### 1、笛卡尔积

我们查询两张表。

查询结果是：依次拿a表的每一行和b的所有行进行数据的拼接。

假如：a表中有8行，b表中有4行，笛卡尔积是8*4=32行。



### 2、多表查询本质

本质：其实就是单表查询，把笛卡尔积作为我们查询的目标。



查询两张表，和查询笛卡尔积是一样的。

笛卡尔积中的列，是两张表的列的总和。

笛卡尔中的行数，就是两张表的行数相乘。



### 3、多表查询

（1）内连接查询

从笛卡尔积中，查询满足连接条件的数据行。

写法1：

select   *

from   表1 ，  表2

where   连接条件  and  其他条件;

```sql
select  *  
from   emp,dept
where  emp.deptno=dept.deptno;
```

写法2：

select  *

from    表1   inner  join   表2   on   连接条件

where   其他条件；

```sql
select  *
from   emp   inner  join   dept   on    emp.deptno=dept.deptno;
```



![image-20220316160715705](MySql数据库.assets/image-20220316160715705.png)

（2）外连接查询

从笛卡尔积中，查询满足连接条件的数据行；

以及两张表中不满足的行。



外连接分为：outer   join

左外连接left       [outer]   join：从笛卡尔积中，查询满足连接条件的数据行。以及，左表中不满足条件的行。

右外连接right    [outer]    join：从笛卡尔积中，查询满足连接条件的数据行。以及，右表中不满足条件的行。



## 十一、子查询

一条查询语句作为另一条查询语句的一部分，这样的查询我们称为子查询。

### （1）单行单列

子语句查询结果是单行单列的，也就是只有一个值。

我们一般使用比较运算符来连接子语句。



![image-20220316172358953](MySql数据库.assets/image-20220316172358953.png)



### （2）多行单列

子语句的查询结果是多行单列的。

一般我们使用in来连接子语句。



![image-20220316172652253](MySql数据库.assets/image-20220316172652253.png)



### （3）单行多列

子语句查询结果是单行多列的。

使用比较运算符来连接子语句。



例如：

查询和**张三的部门、工资**一样的员工。



![image-20220316173900208](MySql数据库.assets/image-20220316173900208.png)



### （4）多行多列

子语句查询结果是多行多列的。

使用in连接子语句。



例如：

查询和张三、赵敏一样的部门和工资的员工信息



![image-20220316174024717](MySql数据库.assets/image-20220316174024717.png)



## 十二、union合并查询

### 1、union用途

将两个查询结果合并到一起。



### 2、语法

select  1    **union**  select  2



合并的前提条件是：

两个查询语句的结果集中，列数相同，对应顺序的列的数据类型相同。

### 3、案例

（1）查询id<1003 和id>1008的所有员工

（2）实现mysql全外连接



## 十三、自查询

案例：

查询员工的姓名和他领导的姓名。



![image-20220317111302238](MySql数据库.assets/image-20220317111302238.png)







## 十四、SQL语言

### 1、SQL

结构化查询语言（Structured Query Language）简称SQL，是一种特殊目的的编程语言

### 2、用途

sql语句是用于操作数据库的语言。

用于存取数据以及查询、更新和管理[关系数据库系统]

### 3、分类

结构化查询语言包含6个部分：

1、数据查询语言（[DQL](https://baike.baidu.com/item/DQL): Data Query Language）：其语句，也称为“数据检索[语句](https://baike.baidu.com/item/语句)”，用以从表中获得数据，确定数据怎样在应用程序给出。保留字[SELECT](https://baike.baidu.com/item/SELECT/10735068)是DQL（也是所有SQL）用得最多的动词，其他DQL常用的保留字有WHERE，ORDER BY，GROUP BY和HAVING。这些DQL保留字常与其它类型的SQL语句一起使用。 [4] 

2、[数据操作语言](https://baike.baidu.com/item/数据操作语言)（DML：Data Manipulation Language）：其语句包括动词[INSERT](https://baike.baidu.com/item/INSERT)、[UPDATE](https://baike.baidu.com/item/UPDATE)和[DELETE](https://baike.baidu.com/item/DELETE)。它们分别用于添加、修改和删除。 [4] 

3、事务控制语言（TCL）：它的语句能确保被DML语句影响的表的所有行及时得以更新。包括COMMIT（提交）命令、SAVEPOINT（保存点）命令、ROLLBACK（回滚）命令。

4、[数据控制语言](https://baike.baidu.com/item/数据控制语言)（DCL）：它的语句通过GRANT或REVOKE实现权限控制，确定单个用户和用户组对[数据库对象](https://baike.baidu.com/item/数据库对象)的访问。某些RDBMS可用GRANT或REVOKE控制对[表单](https://baike.baidu.com/item/表单)个列的访问。 [4] 

5、数据定义语言（[DDL](https://baike.baidu.com/item/DDL/21997)）：其语句包括动词CREATE,ALTER和DROP。在数据库中创建新表或修改、删除表（CREATE TABLE 或 DROP TABLE）；为表加入索引等。 [4] 

6、指针控制语言（CCL）：它的语句，像DECLARE CURSOR，FETCH INTO和UPDATE WHERE CURRENT用于对一个或多个表单独行的操作。



### 4、mysql数据库引擎（扩展）

（1）**InnoDB**

支持事务，索引采用聚簇索引。

（2）**MyISAM**

不支持事务，索引采用非聚簇索引。





## 十五、约束

约束是对数据的增删改操作的限制，目的：保证数据的完整性。

数据的完整性：

（1）实体完整性：通过主键约束

（2）参照完整性：通过外键约束

（3）域完整性：通过列级约束



创建表结构时，添加约束。

约束分为：表级约束和列级约束。



### 1、是否允许为空

列级约束：

null  默认是null

not   null：不管是添加还是修改操作，都允许该列的值为null。

![image-20220317114103502](MySql数据库.assets/image-20220317114103502.png)



### 2、唯一性约束

列级约束

unique：该列的值不允许重复。

注意：null和任何值都不相等，null和null也不相等。

```
create  table  user(

id   int ,
username  VARCHAR(20)     not  null UNIQUE,
passwd    VARCHAR(20)     not  null

)
```



![image-20220317114448386](MySql数据库.assets/image-20220317114448386.png)



### 3、缺省值

列级约束

系统默认的缺省值是null。

我们可以使用default修改缺省值。

用法：default   缺省值



![image-20220317115009732](MySql数据库.assets/image-20220317115009732.png)

![image-20220317115027552](MySql数据库.assets/image-20220317115027552.png)

### 4、检查约束

列级约束

检查插入或者修改的数据是否符合指定的条件。

用法：check （条件）

![image-20220317144805839](MySql数据库.assets/image-20220317144805839.png)





mysql5.X低版本不支持。

check是8.0.16新特性

![image-20220317144729176](MySql数据库.assets/image-20220317144729176.png)



 

### 5、主键

表级约束

作用：**用于区别每行数据，确定数据的唯一性的信息。**

比如：身份证号码可以区别所有中国人的不同；

​			学号可以区别一个学校中所有学生的不同；

​			城市的编码，可以区别城市的不同。

**一个表最多只能有一个主键，主键可以由一列或多列的信息构成。**

主键：单列主键和复合主键。

![image-20220317151044882](MySql数据库.assets/image-20220317151044882.png)



**主键约束：有且唯一，not null+unique。**

![image-20220317145710703](MySql数据库.assets/image-20220317145710703.png)



![image-20220317145754891](MySql数据库.assets/image-20220317145754891.png)



复合主键：

![image-20220317150602321](MySql数据库.assets/image-20220317150602321.png)

不推荐使用复合主键，建议采用单列主键。





### 6、自动增长

列级约束

auto_increment，从1开始。

作用：某列的值，系统自动插入增长的值。

**前提：该列是整数类型，并且该列是构成主键的列。**



mysql支持自动增长，oracle数据库不支持，oracle使用序列实现自增。

![image-20220317155117668](MySql数据库.assets/image-20220317155117668.png)



![image-20220317155133824](MySql数据库.assets/image-20220317155133824.png)

### 7、外键

表级约束

**用来表示两张表之间的关系的。**



从表创建外键：

**FOREIGN   KEY(外键列)  REFERENCES   主表(主键列)**

从表的外键关联到主表的主键上。



**一张表可以有多个外键，每个外键都由一列构成。**

**外键约束：从表的外键列数据必须来源于主表的主键列中。**

![image-20220317160433303](MySql数据库.assets/image-20220317160433303.png)





外键可以插入null，这样也不会违背外键约束。

![image-20220317160745946](MySql数据库.assets/image-20220317160745946.png)





总结外键约束：

先建主表，再建从表；

先删从表，再删主表。

先添加主表数据，再添加从表数据；

先删除从表数据，再删除主表数据。

**在企业中开发，设计数据库时，我们一般不添加外键约束。心中有外键就可以了。**



## 十六、数据库三范式

根据要存储的数据来设计数据库：有哪些表，每张表有哪些字段，表有哪些约束，表有哪些索引，每个字段的数据类型是什么？

按照数据库的三范式来设计。



### 1、范式

我们在设计数据库时，应该遵守的规范和原则。

我们一共有六个规范：

第一范式（1NF），第二范式（2NF），第三范式（3NF）

巴斯科德范式（BCNF），第四范式（4NF），第五范式（5NF，完美范式）。



![QQ图片20220317164624](MySql数据库.assets/QQ图片20220317164624.png)

### 2、第三范式（3NF）

企业要求满足第三范式，基本就可以了。

第二范式必须先满足第一范式。

第三范式必须先满足第二范式。

#### （1）第一范式

第一范式（1NF）是指在[关系模型](https://baike.baidu.com/item/关系模型)中，对于添加的一个规范要求，**所有的域都应该是原子性的**，即数据库表的每一列都是不可分割的原子数据项，而不能是集合，数组，记录等非原子数据项。

![image-20220317165350786](MySql数据库.assets/image-20220317165350786.png)

第一范式，要求每列只能存储一个值。所以上面这个表格中的name列不符合第一范式要求。

![image-20220317165411279](MySql数据库.assets/image-20220317165411279.png)





#### （2）第二范式

在1NF的基础上，非码属性必须完全依赖于候选码（在1NF基础上消除非主属性对主码的部分函数依赖）

通俗的讲，每个表中必须有一个主键。

![image-20220317165614422](MySql数据库.assets/image-20220317165614422.png)

如下图：

我们学生的信息通过学号来区别。其他列必须依赖学号。

![img](https://pic2.zhimg.com/80/v2-7f7eebadb49ad8f4ce7ad6a4d81d5709_720w.jpg)





#### （3）第三范式

在2NF基础上，任何非主[属性](https://baike.baidu.com/item/属性)不依赖于其它非主属性（在2NF基础上消除传递依赖）。



使用一张表存储员工的信息以及员工所在的部门信息。

部门信息存在大量的重复，造成数据存储冗余。

![image-20220317170617284](MySql数据库.assets/image-20220317170617284.png)

## 十七、索引和视图

### 1、索引

#### （1）索引作用

为了提高查询效率。

#### （2）索引为什么能够提高查询效率呢？

将关键字和我们数据的地址建立关联，通过关键字直接可以找到地址，获取到数据。

![image-20220317171833064](MySql数据库.assets/image-20220317171833064.png)

#### （3）索引采用的数据结构

采用B+树存储索引信息。

原因：层数少，查询效率高，存储的数据量大。



Innodb 创建表后生成的文件有：

- frm:创建表的语句
- idb:表里面的数据+索引文件

Myisam 创建表后生成的文件有

- frm:创建表的语句

- MYD:表里面的数据文件（myisam data）

- MYI:表里面的索引文件（myisam index）

  

myISAM使用非聚簇索引（主键和地址）。

![img](https://pic1.zhimg.com/80/v2-d9a03627e8e1319e46f42e6963c35e30_720w.jpg)



innodb使用聚簇索引（主键和数据）。

![img](https://pic2.zhimg.com/80/v2-6e16b355e3d0f05ed8bfb0f7c71de8f1_720w.jpg)



聚簇索引和非聚簇索引：

![img](https://img-blog.csdn.net/20161102111454921?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)



#### （4）创建索引

创建表时：

```
create   table   dept(

deptno   int   PRIMARY  KEY,
dname   VARCHAR(20),
loc      VARCHAR(50),
index(dname),
index(loc)
)
```

表创建完毕，添加索引：

```
create   table   dept(

deptno   int   PRIMARY  KEY,
dname   VARCHAR(20),
loc      VARCHAR(50)
)


create   INDEX   dname_index   on   dept(dname)
```



#### （5）索引的分类

​	1）.普通索引index
​	2）.唯一索引unique
​	3）.主键索引primary  key



#### （6）索引创建策略

问题：

是不是索引创建的越多越好？

越多是不是查询效率就越高呢？

解答：

索引要适量。

索引会影响增删改的效率，增删改时需要添加索引信息。

索引多了，会消耗内存和硬盘，反而会影响查询效率。



**哪些列需要建立索引：**

**主键列自动建索引。**

**唯一键列自定建立索引。**

**常出现where和on后面的列，建立索引。**



#### （7）删除索引

drop   index   索引名



#### （8）索引失效

  

```
   ** 1.如果条件中有or，即使其中有条件带索引也不会使用(这也是为什么尽量少用or的原因)**

　　要想使用or，又想让索引生效，只能将or条件中的每个列都加上索引**

　　** 2.对于多列索引，不是使用的第一部分，则不会使用索引**

　　** 3.like查询以%开头**

　　** 4.如果列类型是字符串，那一定要在条件中将数据使用引号引用起来,否则不使用索引**

　　** 5.如果mysql估计使用全表扫描要比使用索引快,则不使用索引**
　　
　　** 6.null值不创建索引
　　
　　** 7.truncate会删除索引
```



### 2、视图

（1）视图的作用

视图是按照指定的要求，将表里的数据展示出来。

视图主要用于查询，不做增删改操作。

（2）使用视图的原因

有些敏感字段或者安全要求比较高的字段我们是不能展示的。

将一些比较复杂数据查询，通过视图直接提供出来，就不需要我们去写这些复杂的查询语句了。



（3）创建视图

create  view  视图名   as   表的查询语句；

![image-20220318110454448](MySql数据库.assets/image-20220318110454448.png)

（4）查询视图

查询视图的语句和查询表是一样的。



![image-20220318110609423](MySql数据库.assets/image-20220318110609423.png)



（5）视图的本质

视图对象中只存储了一条表的查询语句而已，并没有存储数据。

数据还是在表中存储的。



我们查询视图时，先去执行表的查询语句，然后在此基础上继续查询罢了。

所以，视图的效率不高。



（6）删除视图

drop  view  视图名;



## 十八、存储过程

### 1、是什么

存储过程是一个sql语句的集合，和我们java中的方法一样。



### 2、创建存储过程

语法：

```txt
create    procedure     过程名（参数）

begin

过程体：解决问题的语句组；

end；
```





### 3、删除存储过程

语法：

drop    procedure    过程名;



### 4、调用存储过程

语法：

call    过程名(实参)；



![image-20220318111627982](MySql数据库.assets/image-20220318111627982.png)





![image-20220318111643792](MySql数据库.assets/image-20220318111643792.png)



### 5、过程体中声明变量

声明：

declare    变量名    数据类型    【default(缺省值)】；    

赋值：

set     变量名  =   值；

select  查询字段   into    变量名    .....

![image-20220318112300523](MySql数据库.assets/image-20220318112300523.png)





![image-20220318113212225](MySql数据库.assets/image-20220318113212225.png)

### 6、流程控制语句

（1）分支

第一种：

if-then-else

![image-20220318113738125](MySql数据库.assets/image-20220318113738125.png)

第二种：

case-when-else



（2）循环

第一种：while

![image-20210819102945058](MySql数据库.assets/image-20210819102945058.png)





第二种：loop

![image-20220318144217895](MySql数据库.assets/image-20220318144217895.png)

第三种：repeat

![image-20210819103541686](MySql数据库.assets/image-20210819103541686.png)



### 7、参数

参数类型：in     out     inout

- 输入值使用in参数。
- 返回值使用out参数。
- inout参数就尽量的少用。



（1）in

![image-20210819110440859](MySql数据库.assets/image-20210819110440859.png)





（2）out

![image-20210819110846238](MySql数据库.assets/image-20210819110846238.png)



### 8、游标

存储查询结果的集合。

```sql
create   PROCEDURE    mycursor3()
begin

DECLARE   deptno  int;
DECLARE   dname  varchar(20);
DECLARE    loc   varchar(20);

DECLARE   done   int   DEFAULT  false;
--  声明游标
DECLARE     cs   CURSOR    for  select  *  from  dept;
--  游标读写完毕标记
declare continue handler for not found set done = true;

--  遍历游标：从游标中取数据
-- (1)打开游标
open  cs;
-- （2）取一行数据
cccc:loop

	FETCH   cs   into   deptno,dname,loc;
	
	if  done  then
		leave  cccc;
	else  
		select  deptno,dname,loc;
	end  if;
	
end  loop;
--  （3）关闭游标
close   cs;
end;



call   mycursor3();
```



### 9、存储过程的优点和缺点

原来的开发，金融、电信、银行、国家政府系统项目，他们都喜欢使用存储过程。



优点：

将复杂的业务封装到存储过程中，我们Java开发将变得很简单。

将核心业务隐藏在存储过程中，对外透明，提升系统的安全性。

缺点：

不同的数据库，存储过程的语法有区别，不方便移植。

数据库的负载比较重。



## 十九、触发器

### 1、作用

mysql的触发器和java的监听器作用是一样。

当数据库中执行对应的操作，就会触发执行我们触发器中的代码。



触发器包含两个功能：监听和处理。

### 2、创建触发器

语法：

触发时机

before:在操作之前执行处理代码

after:在操作完毕后执行处理代码

监听的操作：

insert  /   delete   /update

操作的表：

on   表名

```
create trigger     触发器名称  

**after**/before      **insert**/**update**/**delete**       **on** 表名 

 **for** each row

begin

//处理操作

end;
```



```sql
for  each  row
begin
	DECLARE    a  int;
	select  count  into   a  from  test2  order  by   count  desc	limit  1;
	set   a=a+1;
	insert  into  test2  values(a);

end;
```





### 3、测试触发器

insert  into  test   values(null,'赵琦1',27,'2020-2-2 2:2:2'),(null,'赵琦2',27,'2020-2-2 2:2:2'),(null,'赵琦3',27,'2020-2-2 2:2:2')



### 4、删除触发器

drop  trigger  触发器名





## 二十、存储函数

和java中有返回值的方法一样。

### 1、系统函数

#### （1）数字函数

abs(x)	求x的绝对值

rand()    返回0到1的随机数

round(x)  x四舍五入取整

```sql
select  abs(-10);
select  rand();
select  round(5.5);
```

#### （2）字符串函数

ascii(str)    返回str的ascii码

length(str)   返回字符串的长度

concat(str1,str2)  字符串拼接

Lcase(str)转换成小写

Ucase(str)转换成大写

trim(str)  取消前后的空格

substr（str,开始位置，长度）  字符串截取

replace(str,旧字符，新字符)   替换



```sql
select   ascii('a');
select  LENGTH('adfalmdfjkl');
select  concat('asss','12222');
select  LCASE('aaaaSSSS');
select  UCASE('aaaaSSSS');
select  trim('    d d    ');
select  substr('abcdefg',2,3);
select  REPLACE('abacda','a','f');
```

#### （3）日期函数

now()   返回当前日期时间

curDate()   返回当前日期

curTime()   返回当前时间



date(d)     获取d中年月日

day（d）获取日

month（d）获取月

year(d)  获取年



dateDiff(d1,d2)返回两个日期的差值



```sql
select  now();
select  curdate();
select  curtime();
select  date('2020-2-18 17:00:20')
select  day('2020-2-18 17:00:20')
select  month('2020-2-18 17:00:20');
select  year('2020-2-18 17:00:20');

select  datediff('2020-2-08 17:00:20','2020-2-10 17:00:20')

```



#### （4）聚合函数

用于统计的函数

max（列名）

min（列名）

sum（列名）

avg（列名）

count（列名）



#### （5）其他函数

if（exp,v1,v2）  如果表达式成立返回v1,否则返回v2。

ifnull(exp1,exp2)   如果exp1为null，返回exp2的结果；否则返回exp1。



database()  获取当前的数据库名

CURRENT_USER()   获取当前用户

version()     获取mysql版本

```sql
select  if(1<0,'yes','no');
select  IFNULL(null,0);

select  DATABASE();
select  CURRENT_USER();
select  version();
```



### 2、自定义函数

语法：

```sql
create function 函数名([参数列表]) returns 数据类型
DETERMINISTIC
begin
 sql语句;
 return 值;
end;
```

![image-20220318152418821](MySql数据库.assets/image-20220318152418821.png)

```sql
create   FUNCTION   myfun01()
RETURNS   int
DETERMINISTIC 
begin

return   10;

end;

```



调用：

select  函数名(实参);



删除函数：

drop   function  函数名;



### 3、函数和存储过程区别

存储函数有返回值，存储过程没有返回值（可以输出数据）；

存储函数使用select调用，存储过程使用call调用。



## 二十一、用户和权限

### 1、创建用户

系统安装时，会自动创建超级管理员root，拥有任何权限。

但是在实际开发时，不同的工作人员一般会分配相应权限的用户，不会使用root。

java开发人员，主要的数据库操作是：数据的CRUD。



创建新用户：

create  user    用户名 @主机   IDENTIFIED    by   密码；



```sql
create   user   xiao@localhost  IDENTIFIED   by  '123';


ALTER USER 'xiao'@'localhost' IDENTIFIED WITH mysql_native_password BY '123'
```



![image-20210819160208510](MySql数据库.assets/image-20210819160208510.png)



新建的用户可以登录mysql，但是没有任何操作权限。



### 2、删除用户

drop   user  用户名;



### 3、修改密码

使用管理员登录：

alter   user  用户名@主机   identified  by  '新密码';



### 4、授权

给用户赋予相应的操作权限



使用管理员登录：

grant    权限      to   用户名@主机名;

![image-20210819162236043](MySql数据库.assets/image-20210819162236043.png)

![image-20210819162411161](MySql数据库.assets/image-20210819162411161.png)



![image-20210819162522347](MySql数据库.assets/image-20210819162522347.png)

![image-20210819162722343](MySql数据库.assets/image-20210819162722343.png)



5、mysql权限

GRANT语句中的`<权限类型>`的使用说明如下：

#### 1) 授予数据库权限时，<权限类型>可以指定为以下值：

- SELECT：表示授予用户可以使用 SELECT 语句访问特定数据库中所有表和视图的权限。
- INSERT：表示授予用户可以使用 INSERT 语句向特定数据库中所有表添加数据行的权限。
- DELETE：表示授予用户可以使用 DELETE 语句删除特定数据库中所有表的数据行的权限。
- UPDATE：表示授予用户可以使用 UPDATE 语句更新特定数据库中所有数据表的值的权限。
- REFERENCES：表示授予用户可以创建指向特定的数据库中的表外键的权限。
- CREATE：表示授权用户可以使用 CREATE TABLE 语句在特定数据库中创建新表的权限。
- ALTER：表示授予用户可以使用 ALTER TABLE 语句修改特定数据库中所有数据表的权限。
- SHOW VIEW：表示授予用户可以查看特定数据库中已有视图的视图定义的权限。
- CREATE ROUTINE：表示授予用户可以为特定的数据库创建存储过程和存储函数的权限。
- ALTER ROUTINE：表示授予用户可以更新和删除数据库中已有的存储过程和存储函数的权限。
- INDEX：表示授予用户可以在特定数据库中的所有数据表上定义和删除索引的权限。
- DROP：表示授予用户可以删除特定数据库中所有表和视图的权限。
- CREATE TEMPORARY TABLES：表示授予用户可以在特定数据库中创建临时表的权限。
- CREATE VIEW：表示授予用户可以在特定数据库中创建新的视图的权限。
- EXECUTE ROUTINE：表示授予用户可以调用特定数据库的存储过程和存储函数的权限。
- LOCK TABLES：表示授予用户可以锁定特定数据库的已有数据表的权限。
- ALL 或 ALL PRIVILEGES：表示以上所有权限。

#### 2）授予表权限时，<权限类型>可以指定为以下值：

- SELECT：授予用户可以使用 SELECT 语句进行访问特定表的权限。
- INSERT：授予用户可以使用 INSERT 语句向一个特定表中添加数据行的权限。
- DELETE：授予用户可以使用 DELETE 语句从一个特定表中删除数据行的权限。
- DROP：授予用户可以删除数据表的权限。
- UPDATE：授予用户可以使用 UPDATE 语句更新特定数据表的权限。
- ALTER：授予用户可以使用 ALTER TABLE 语句修改数据表的权限。
- REFERENCES：授予用户可以创建一个外键来参照特定数据表的权限。
- CREATE：授予用户可以使用特定的名字创建一个数据表的权限。
- INDEX：授予用户可以在表上定义索引的权限。
- ALL 或 ALL PRIVILEGES：所有的权限名。

#### 3）授予列权限时，<权限类型>的值只能指定为 SELECT、INSERT 和 UPDATE，同时权限的后面需要加上列名列表 column-list。



#### 4) 最有效率的权限是用户权限。

授予用户权限时，<权限类型>除了可以指定为授予数据库权限时的所有值之外，还可以是下面这些值：

- CREATE USER：表示授予用户可以创建和删除新用户的权限。
- SHOW DATABASES：表示授予用户可以使用 SHOW DATABASES 语句查看所有已有的数据库的定义的权限。



### 5、收回权限

```  sql
revoke    权限   from   用户名@主机名
```



![image-20210819163429999](MySql数据库.assets/image-20210819163429999.png)



## 二十二、数据的备份和恢复

### 1、备份

![image-20210819170330181](MySql数据库.assets/image-20210819170330181.png)



![image-20210819170347504](MySql数据库.assets/image-20210819170347504.png)



![image-20210819170411955](MySql数据库.assets/image-20210819170411955.png)

![image-20210819170422707](MySql数据库.assets/image-20210819170422707.png)



![image-20210819170445909](MySql数据库.assets/image-20210819170445909.png)



### 2、恢复

新建数据库，然后导入备份文件。



![image-20210819170830611](MySql数据库.assets/image-20210819170830611.png)



![image-20210819170903087](MySql数据库.assets/image-20210819170903087.png)





![image-20210819170913913](MySql数据库.assets/image-20210819170913913.png)



![image-20210819170935233](MySql数据库.assets/image-20210819170935233.png)



![image-20210819170951321](MySql数据库.assets/image-20210819170951321.png)



### 3、表的复制

create   table   备份表名   as    select  *    from    表名;



![image-20210819171148683](MySql数据库.assets/image-20210819171148683.png)



![image-20210819171158987](MySql数据库.assets/image-20210819171158987.png)





### 4、养成备份的习惯

不管是数据库，还是java程序，我们在做修改和删除操作时，一定要先备份，避免操作失误带来的问题。







## 二十三、高级内容（springboot阶段）

### 1、主从复制

读写分离

![image-20210819172048081](MySql数据库.assets/image-20210819172048081.png)

### 2、分布式数据库

myCat实现MySQL分布式数据库



![image-20210819172606056](MySql数据库.assets/image-20210819172606056.png)



