# 03JavaScript高级

## 一、闭包

### 1、闭包的概念

在一个函数里面定义一个内部函数，这个内部函数我们称为闭包



```
<script>

        function  out(){
            var   a=10;

            return  function(){
            	//定义外部访问局部变量a的规则
            	a++;
                return   a; 
            };
        }

        var  f=out();
        alert(f());

    </script>
```



### 2、闭包的作用

将一个变量设为局部变量。只能在方法体内访问，方法体外无法访问。

外部想要访问该局部变量，可以通过闭包(内部函数)访问。





### 3、闭包的缺陷

局部变量一直被闭包引用。

闭包存在，局部变量就不会被销毁。

局部变量一直占用内存，会造成内存溢出。

```
 	function  out(){
            var   a=10;

            return  function(){
                a++;
                return   a; 
            };
        }

        var  f=out();
        alert(f());   //11
        alert(f());   //12
        alert(f());   //13
```

建议：没有必要使用闭包时，尽量不使用。



## 二、原型链

### 1、原型

每个函数都对应一个对象，这个对象我们叫原型。

原型保存共享的属性和方法。



### 2、原型链的作用

实现继承



### 3、继承实现

![image-20210901170603753](03JavaScript高级.assets/image-20210901170603753.png)



```
<script>

        function   Animal(name){
            this.name=name;

            this.eat=function(food){
                alert("eat:"+food);
            }
        }


        function  Dog(sex){
            //this.name=name;
            this.sex=sex;

            // this.eat=function(food){
            //     alert("eat:"+food);    
            // }

            this.say=function(){
                alert("dog  say");
            }
        }

        var    a=new Animal("旺财");
        Dog.prototype=a;

        var   d=new  Dog("雄性");
        alert(d.name);
        alert(d.sex);
        d.eat("骨头");
        d.say();
    </script>
```



### 4、原型链详解

![image-20210901174545811](03JavaScript高级.assets/image-20210901174545811.png)



```

        function   Animal(name){
            this.name=name;

            this.eat=function(food){
                alert("eat:"+food);
            }
        }

//      函数找原型
        Animal.prototype.sex="雄性";
        Animal.prototype.sleep=function(){
            alert("sleep");
        }

//      原型找函数
        alert(Animal.prototype.constructor);


//      对象a
        var   a=new  Animal("旺财");
        alert(a.name);
        a.eat("骨头");
// 对象a有隐式属性_proto_，可以找到原型对象
        alert(a.sex);
        a.sleep();
//  原型对象有隐式属性_proto_，可以找到Object原型    
        alert(a.toString());

```





## 三、es6：extends

```
        class   Animal{

            constructor(name,sex){
                this.name=name;
                this.sex=sex;
            }

            eat(food){
                alert("eat:"+food);
            }

            sleep(){
                alert("sleep");
            }
        }


        class  Dog  extends  Animal{
            constructor(name,sex,age){
                super(name,sex);
                this.age=age;
            }

            say(){
                alert("say");
            }
        }


        var   d=new  Dog("旺财","雄性",3);
        alert(d.name);
        alert(d.sex);
        alert(d.age);
        d.eat("骨头");
        d.sleep();
        d.say();
```



## 四、es6新语法

1、class

2、extends

3、let

4、const

5、箭头函数

6、其他