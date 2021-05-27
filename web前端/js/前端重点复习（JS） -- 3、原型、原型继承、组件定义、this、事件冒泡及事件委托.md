**目录**

[16、原型](#16、原型)

[（1）定义：](#（1）定义：)

[（2）JS对象分两种：](#（2）JS对象分两种：)

[（3）写法：](#（3）写法：)

[（4）验证是否是原型：](#（4）验证是否是原型：)

[17、原型继承](#17、原型继承)

[（1）原型的继承](#（1）原型的继承)

[（2）构造函数的继承](#（2）构造函数的继承)

[（3）组合继承（相当于综合上面的继承一起使用）](#（3）组合继承（相当于综合上面的继承一起使用）)

[（4）原型链](#（4）原型链)

[18、组件定义](#18、组件定义)

[（1）动态定义](#（1）动态定义)

[（2）字面量定义](#（2）字面量定义)

[（3）面向对象定义](#（3）面向对象定义)

[（4）原型继承定义（推荐）](#（4）原型继承定义（推荐）)

[（5）公共传参](#（5）公共传参)

[19、this](#19、this)

[（1）在简单函数中](#（1）在简单函数中)

[1.简单函数](#1.简单函数)

[2.内置函数](#2.内置函数)

[3.回调函数](#3.回调函数)

[4.数组](#4.数组)

[（2）在对象的方法中](#（2）在对象的方法中)

[（3）在构造函数中](#（3）在构造函数中)

[（4）如何改变this的指向](#（4）如何改变this的指向)

[20、事件冒泡及事件委托](#20、事件冒泡及事件委托)

[（1）事件冒泡和捕获](#（1）事件冒泡和捕获)

[（2）事件委托](#（2）事件委托)

------



# 16、原型

## （1）定义：

用原型实例指向创建对象的类，使用于创建新的对象的类的共享原型的属性与方法

原型是一个对象，其它对象可以通过它实现属性继承



prototype是函数才有的属性

__proto__是每个对象都有的属性

所以只有函数对象才有原型



**优点：**同一个原型对象

**缺点：**不能修改原型对象

## （2）JS对象分两种：

![img](https://img-blog.csdnimg.cn/20210527102221137.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//函数对象f1、普通对象f2

![img](https://img-blog.csdnimg.cn/20210527102228971.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102228995.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102228939.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527104302276.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （3）写法：

**方式一：**

```javascript
   //需求：生成多个实例
   var cat1 = {};//创建一个空对象
   cat1.name="大明";
   cat1.color ="黄色";

   var cat2 = {};//创建一个空对象
   cat2.name="小明";
   cat2.color ="白色";
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**方式二：封装方式**

```javascript
   //封装一个公共的对象
   function cat(name,color){
      return {
         name:name,
         color:color
      }
   }
   var c1 = cat("大明","黄色");
   var c2 = cat("大明","黄色");
   var c3 = cat("大明","黄色");
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**方式三：构造函数**

```javascript
   //构造函数
   function Cat(name,color){
      this.name = name;
      this.color = color;
   };
   var c1 = new Cat("大明","黄色");
   var c2 = new Cat("大明","黄色");
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**方式四：protoype原型**

![img](https://img-blog.csdnimg.cn/20210527102353331.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210527102410816.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
   //构造函数
   function Cat(name,color){
      this.name = name;
      this.color = color;
   };
================================ 添加 ==================================
   Cat.prototype.type = '动物';
   Cat.prototype.eat = function(){console.log('吃老鼠')};
=======================================================================
   var c1 = new Cat("大明","黄色");
   var c2 = new Cat("大明","黄色");
================================ 添加 ==================================
   c1.eat() 
   //c2.eat()  //直接调用即可
=======================================================================
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （4）验证是否是原型：

![img](https://img-blog.csdnimg.cn/20210527102448630.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//in 都返回true

//hasOwnProperty()自身返回true，原型返回false

# 17、原型继承

## （1）原型的继承

![img](https://img-blog.csdnimg.cn/20210527102547216.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//改变的不是原型里的type，而是b1里面的type

**优点：**同一个原型对象

**缺点：**不能修改原型对象（如下）

如果想要改变原型：（全部都会改变）

![img](https://img-blog.csdnimg.cn/20210527102600977.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**当父类子类都有type属性时：**

通过__proto__拿到原型对象内的值

通过c1**.**type普通方式拿到自身Cat对象的值

![img](https://img-blog.csdnimg.cn/20210527102608707.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102612929.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102623714.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

===========================================================

![img](https://img-blog.csdnimg.cn/20210527102635288.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （2）构造函数的继承

简单说，就是将this.type = “动物”拷贝一遍到Cat对象中

![img](https://img-blog.csdnimg.cn/20210527102655180.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

优点：不存在修改原型对象影响所有实例，各自拥有独立属性

缺点：父类的成员会被创建多次，存在冗余且不是同一个原型对象

注意：apply、call只能拷贝成员，原型对象不会拷贝

apply与call区别：

前者直接处理，后者一条一条处理

![img](https://img-blog.csdnimg.cn/20210527102658901.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) //如果是call里面中括号就可以不用写

## （3）组合继承（相当于综合上面的继承一起使用）

## ![img](https://img-blog.csdnimg.cn/2021052710271539.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （4）原型链

![img](https://img-blog.csdnimg.cn/20210527102728199.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

# 18、组件定义

## （1）动态定义

.html

![img](https://img-blog.csdnimg.cn/20210527102753725.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

.css

![img](https://img-blog.csdnimg.cn/20210527102758689.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102802558.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102804676.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021052710280832.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （2）字面量定义

.html

![img](https://img-blog.csdnimg.cn/20210527102820472.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102820475.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102826782.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102826831.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102826743.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （3）面向对象定义

![img](https://img-blog.csdnimg.cn/20210527102850401.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102852774.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （4）原型继承定义（推荐）

html

![img](https://img-blog.csdnimg.cn/2021052710290792.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021052710290786.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102911437.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102914602.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102918295.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//添加一个按钮直接复制一遍即可

![img](https://img-blog.csdnimg.cn/2021052710292548.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102926942.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （5）公共传参

**优点：直接在html的标签上写颜色、标签等等**

![img](https://img-blog.csdnimg.cn/2021052710294491.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**.index****文件内**

![img](https://img-blog.csdnimg.cn/20210527102952639.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527102952595.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**.index****文件内**

![img](https://img-blog.csdnimg.cn/20210527103000848.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527103002895.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527103005179.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

# 19、this

## （1）在简单函数中

内置函数、回调函数利用this返回的都是window

### 1.简单函数

![img](https://img-blog.csdnimg.cn/20210527103057485.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527103057486.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### 2.内置函数

![img](https://img-blog.csdnimg.cn/20210527103110669.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### 3.回调函数

![img](https://img-blog.csdnimg.cn/20210527103120357.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//个f2：各结果为hello、undefined、window(因为写了this)

![img](https://img-blog.csdnimg.cn/20210527103127264.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//为5个window

内置函数、回调函数利用this返回的都是window

### 4.数组

![img](https://img-blog.csdnimg.cn/2021052710315049.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)  ![img](https://img-blog.csdnimg.cn/2021052710315054.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//第二个是因为this已经就指向f对象,而f对象里面没有f3

//window一般就是空 

## （2）在对象的方法中

![img](https://img-blog.csdnimg.cn/20210527103216277.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//obj.init()是obj调用，那么this指向obj对象

![img](https://img-blog.csdnimg.cn/20210527103216422.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021052710322649.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//分别为：3、3、"sonia"

## （3）在构造函数中

所谓构造函数，就是通过这个函数生成一个新对象（object）。当一个函数作为构造器使用时(通过 new 关键字), 它的 this 值绑定到新创建的那个对象。如果没使用 new 关键字, 那么他就只是一个普通的函数, this 将指向 window 对象。

![img](https://img-blog.csdnimg.cn/20210527103254540.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//Fun {name: "abc", age: 18, action: ƒ}

在上面的示例中, 有一个名为 Fun() 的构造函数。通过使用 new 操作符创建了一个全新的对象，名为 fun。同时还通传给构造函数参数, 作为新对象的name、age属性。通过最后一行代码中可以看到这个字

符串成功地打印出来了, 因为 this 指向的是新创建的对象, 而不是构造函数本身。

## （4）如何改变this的指向

有apply()、call()、bind()三种方式

![img](https://img-blog.csdnimg.cn/20210527103314998.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527103318638.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

apply括号内的是：**（复制到哪里，[形参，形参]）**

//分别是：
"100 1 2"
10 1 2
10 1 2

//如果用call()，自己去掉中括号即可

![img](https://img-blog.csdnimg.cn/20210527103327455.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**//****结果为9999 1 2**

![img](https://img-blog.csdnimg.cn/20210527103333303.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**//****改成（obj5，1，2）结果是100 1 2**

![img](https://img-blog.csdnimg.cn/20210527103339207.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

apply() 方法接收两个参数:

第一个是要设置为 this 的那个对象,

第二个参数是可选的，如果要传入参数, 则封装为数组作为 apply() 的第二个参数即可。



call() 方法 和 apply() 基本上是一样的, 除了后面的参数不是数组， 而是分散开一个一个地附加在后面。

```javascript
var num = 10;
function test(){
return this.num;
};
var obj ={
num : 5,
fun:test
}
console.log(obj.fun.call(this)) 	//返回的值是10，当前的this表示全局对象
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
var num = 10;
function test(){
return this.num;
};
var obj ={
num : 5,
fun:test
}
console.log(obj.fun.call(obj)) 	//返回值为5，当前的this为obj对象
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

# 20、事件冒泡及事件委托

## （1）事件冒泡和捕获

![img](https://img-blog.csdnimg.cn/20210527103433983.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527103440540.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
    // 事件冒泡和捕获
    // 当事件发生后，这个事件就要开始传播(从里到外或者从外向里)。
    // 为什么要传播呢？因为事件源本身（可能）并没有处理事件的能力，即处理事件的函数（方法）并未绑定在该事件源上。
    document.querySelector(".div1").onclick = function (e) {
        console.log("div1");
    }
    document.querySelector(".div2").onclick = function (e) {
        console.log("div2");
    }
    document.querySelector(".div3").onclick = function (e) {
        console.log("div3");
    }
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527103453675.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
    // 事件冒泡和捕获
    // 当事件发生后，这个事件就要开始传播(从里到外或者从外向里)。
    // 为什么要传播呢？因为事件源本身（可能）并没有处理事件的能力，即处理事件的函数（方法）并未绑定在该事件源上。
    document.querySelector(".div1").onclick = function (e) {
        console.log("div1");
    }
document.querySelector(".div2").onclick = function (e) {
============================= 添加 =====================================
        e.stopPropagation();	//阻止事件冒泡
=======================================================================
        console.log("div2");
    }
document.querySelector(".div3").onclick = function (e) {
============================= 添加 =====================================
        e.stopPropagation();	//阻止事件冒泡
=======================================================================
        console.log("div3");
    }
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021052710350618.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

当事件发生后，这个事件就要开始传播(从里到外或者从外向里)。

为什么要传播呢？因为事件源本身（可能）并没有处理事件的能力，即处理事件的函数（方法）并未绑定在该事件源上。

例如我们点击一个按钮时，就会产生一个click事件，但这个按钮本身可能不能处理这个事件，事件必须从这个按钮传播出去，从而到达能够处理这个事件的代码中（例如我们给按钮的onclick属性赋一个函数的名字，就是让这个函数去处理该按钮的click事件）

## （2）事件委托

简单说就是将事件委托给另一个人

![img](https://img-blog.csdnimg.cn/20210527103524338.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
    //1、傻傻地一个个去领取
    var list = document.getElementById("list");
    var li = list.getElementsByTagName("li");
    for (var i = 0; i < li.length; i++) {
        li[i].onclick = function () {
            this.style.color = 'red';
        }
    }
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527103536983.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//点谁，随变红

```javascript
    //2、事件委托 将事件绑定到父节点，点击子节点通过事件冒泡到父并处理
    var list = document.getElementById("list");
    list.onclick = function (e) {
        if (e.target.nodeName === 'LI') {
            e.target.style.color = 'red';
        }
    }
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527103551975.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//一样

![img](https://img-blog.csdnimg.cn/20210527103557939.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```html
    <!-- event.target 和 event.currentTarget -->
    <h1>event.target 和 event.currentTarget </h1>
    <div class="d1">
        div1
        <div class="d2">
            div2
            <div class="d3">
                div3
            </div>
        </div>
    </div>
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
    //event对象  事件的状态
    // event.target;  触发事件的元素
    // event.currentTarget;  绑定事件的元素
    // this   绑定事件的元素
    document.querySelector(".d1").onclick = function (e) {
        console.log('1111');
        this.style.color = 'blue';
    }
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021052710365983.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527103659208.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210527103659216.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//全部变蓝

![img](https://img-blog.csdnimg.cn/20210527103659217.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527103659219.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210527103659218.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//全部变蓝

```javascript
    //event对象  事件的状态
    // event.target;  触发事件的元素
    // event.currentTarget;  绑定事件的元素
    // this   绑定事件的元素
    document.querySelector(".d1").onclick = function (e) {
        console.log('1111');
        //this.style.color = 'blue';
        e.target.style.color = 'yellow';  //e.target不会变化  指向的是触发的对象
    }
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527103713524.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)  

![img](https://img-blog.csdnimg.cn/20210527103713528.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//倒置版冒泡（本来结果演示是点谁点谁，出问题？）

```javascript
    //event对象  事件的状态
    // event.target;  触发事件的元素
    // event.currentTarget;  绑定事件的元素
    // this   绑定事件的元素
    document.querySelector(".d1").onclick = function (e) {
        console.log('1111');
        //this.style.color = 'blue';
        //e.target.style.color = 'yellow';  //e.target不会变化  指向的是触发的对象（推荐）
        e.currentTarget.style.color = 'yellow'; 
    }
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527103726697.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210527103726696.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//全部变黄（跟第一个一样）

事件委托，通俗地来讲，就是把一个元素响应事件（click、keydown......）的函数委托到另一个元素；

一般来讲，会把一个或者一组元素的事件委托到它的父层或者更外层元素上，真正绑定事件的是外层元素，当事件响应到需要绑定的元素上时，会通过事件冒泡机制从而触发它的外层元素的绑定事件上，然后在外层元素上去执行函数。

举个例子，比如一个宿舍的同学同时快递到了，一种方法就是他们都傻傻地一个个去领取，还有一种方法就是把这件事情委托给宿舍长，让一个人出去拿好所有快递，然后再根据收件人一一分发给每个宿舍同学；

在这里，取快递就是一个事件，每个同学指的是需要响应事件的 DOM 元素，而出去统一领取快递的宿舍长就是代理的元素，所以真正绑定事件的是这个元素，按照收件人分发快递的过程就是在事件执行中，需要判断当前响应的事件应该匹配到被代理元素中的哪一个或者哪几个。