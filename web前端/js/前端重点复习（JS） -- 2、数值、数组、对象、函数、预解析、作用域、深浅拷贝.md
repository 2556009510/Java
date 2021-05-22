**目录**

[9、数值（转换为数值）](#9、数值（转换为数值）)

[（1）parseInt 字符串转换整数](#（1）parseInt 字符串转换整数)

[（2）parseFloat字符串转换小数](#（2）parseFloat字符串转换小数)

[（3）Number任何转换数值](#（3）Number任何转换数值)

[（4）toFixed、toPrecision](#（4）toFixed、toPrecision)

[10、数组](#10、数组)

[1）](#1）)

[（1）toString数组转换字符串](#（1）toString数组转换字符串)

[（2）join拼接](#（2）join拼接)

[2）添加：](#2）添加：)

[（3）unshift头部添加](#（3）unshift头部添加)

[（4）push尾部添加](#（4）push尾部添加)

[3)删除：](#3)删除：)

[（5）pop删除尾部](#（5）pop删除尾部)

[（6）shift删除头部](#（6）shift删除头部)

[（7）splice删除指定位置](#（7）splice删除指定位置)

[4）](#4）)

[（8）slice获取指定数值](#（8）slice获取指定数值)

[（9）concat合并数组](#（9）concat合并数组)

[5）排列](#5）排列)

[（10）sort顺序](#（10）sort顺序)

[（11）reverse逆序](#（11）reverse逆序)

[6）遍历](#6）遍历)

[（12）for](#（12）for)

[（13）forEach](#（13）forEach)

[（14）map](#（14）map)

[（15）for in](#（15）for in)

[7）筛选](#7）筛选)

[（16）filter返回满足条件的元素](#（16）filter返回满足条件的元素)

[（17）every全部满足才返回turn](#（17）every全部满足才返回turn)

[（18）some只要有一个满足就返回turn](#（18）some只要有一个满足就返回turn)

[（19）reduce累加](#（19）reduce累加)

[11、对象](#11、对象)

[1）定义对象两种方式](#1）定义对象两种方式)

[（1）new方式](#（1）new方式)

[（2）字面量方式](#（2）字面量方式)

[1、简单字面量方式](#1、简单字面量方式)

[2、(常用) 嵌套字面量方式](#2、(常用) 嵌套字面量方式)

[2）属性](#2）属性)

[（1）写法](#（1）写法)

[3）序列化](#3）序列化)

[（1）JSON.stringify()  方法是将JS值(对象或者数组)转换JSON字符串](#（1）JSON.stringify()  方法是将JS值(对象或者数组)转换JSON字符串)

[（2）JSON.parse()       方法是将JSON字符串转换为对象](#（2）JSON.parse()       方法是将JSON字符串转换为对象)

[（3）hasOwnProperty()       判断对象的属性是否存在](#（3）hasOwnProperty()       判断对象的属性是否存在)

[（4）assign()               对象的合并](#（4）assign()               对象的合并)

[（5）defineProperties()  直接在一个对象上定义新的属性或修改现有属性，并返回该对象](#（5）defineProperties()  直接在一个对象上定义新的属性或修改现有属性，并返回该对象)

[（6）keys()  返回一个由一个给定对象的自身可枚举属性组成的数组](#（6）keys()  返回一个由一个给定对象的自身可枚举属性组成的数组)

[（7）values();        返回一个给定对象自己的所有可枚举属性值的数组](#（7）values()%3B        返回一个给定对象自己的所有可枚举属性值的数组)

[（8）entries();       返回一个给定对象自身可枚举属性的键值对数组](#（8）entries()%3B       返回一个给定对象自身可枚举属性的键值对数组)

[（9）delete删除](#（9）delete删除)

[12、函数](#12、函数)

[（1）函数声明与函数表达式](#（1）函数声明与函数表达式)

[（2）自调用函数（自动调用）](#（2）自调用函数（自动调用）)

[（3）arguments](#（3）arguments)

[（4）写法](#（4）写法)

[写法一：](#写法一：)

[写法二（推荐）](#写法二（推荐）)

[写法三（推荐）](#写法三（推荐）)

[13、预解析](#13、预解析)

[14、作用域](#14、作用域)

[注意1](#注意1)

[注意2](#注意2)

[15、深浅拷贝](#15、深浅拷贝)

------



# 9、数值（转换为数值）

parseInt() 方法            //字符串转换整数

parseFloat() 方法         //字符串转换小数

Number() 方法            //任何转换数值



toFixed()       //返回字符串值，从小数后开始数

toPrecision() //返回字符串值，从整个数字开始数

![img](https://img-blog.csdnimg.cn/20210518123139549.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518123157146.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518123202399.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)**//****去掉双引号，为30**

## （1）parseInt 字符串转换整数

![img](https://img-blog.csdnimg.cn/20210518123251451.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) //30

![img](https://img-blog.csdnimg.cn/20210518123308160.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （2）parseFloat字符串转换小数

![img](https://img-blog.csdnimg.cn/20210518123321291.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （3）Number任何转换数值

![img](https://img-blog.csdnimg.cn/20210518123340986.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （4）toFixed、toPrecision

toFixed()       //返回字符串值，从小数后开始数

toPrecision() //返回字符串值，从整个数字开始数

![img](https://img-blog.csdnimg.cn/20210518123408123.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

# 10、数组

![img](https://img-blog.csdnimg.cn/20210518123505917.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

1. toString()      数组转换字符串
2. join()             拼接元素
3. unshift()        头部添加 
4. push()           尾部添加 
5. pop()            删除尾部
6. shift()            删除头部，并把所有其他元素“位移”到更低的索引
7. splice()          删除或替换指定元素
8. slice()             获取指定元素，不会改变原数组
9. concat()        拼接数组
10. sort ()            顺序
11. reverse()        逆序
12. for                 遍历
13. forEach()        方法用于调用数组的每个元素，并将元素传递给回调函数。
14. map
15. for in
16. filter()             返回满足条件的元素
17. every()           全部满足返回turn
18. some()           只要有一个满足就返回turn
19. reduce           累加，数组全部相加

## 1）

### （1）toString数组转换字符串

### ![img](https://img-blog.csdnimg.cn/20210518123550697.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### （2）join拼接

### ![img](https://img-blog.csdnimg.cn/20210518123616589.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518123616625.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518123616633.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 2）添加：

### （3）unshift头部添加

### （4）push尾部添加

![img](https://img-blog.csdnimg.cn/20210518123932527.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 3）删除：

### （5）pop删除尾部

### （6）shift删除头部

### （7）splice删除指定位置

![img](https://img-blog.csdnimg.cn/20210518124032231.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

\-------------------------------------------------------------------------------

![img](https://img-blog.csdnimg.cn/20210518124041310.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//替换

![img](https://img-blog.csdnimg.cn/20210518124053851.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//6和7换成3

## 4）

### （8）slice获取指定数值

![img](https://img-blog.csdnimg.cn/20210518124130952.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### （9）concat合并数组

![img](https://img-blog.csdnimg.cn/20210518124149997.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 5）排列

### （10）sort顺序

![img](https://img-blog.csdnimg.cn/20210518124218209.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021051812422160.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### （11）reverse逆序

## 6）遍历

### （12）for

![img](https://img-blog.csdnimg.cn/20210518124305746.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518124308935.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) ![img](https://img-blog.csdnimg.cn/20210518124311189.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### （13）forEach

![img](https://img-blog.csdnimg.cn/20210518124334587.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### （14）map

![img](https://img-blog.csdnimg.cn/20210518124347982.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021051812435297.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**区别：**map的区别在于，只是forEach没有返回值

### （15）for in

**集合{}：**![img](https://img-blog.csdnimg.cn/20210518124413387.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518124425769.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518124435180.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**数组[]：**![img](https://img-blog.csdnimg.cn/20210518124432196.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) **//获取的是下标**

## 7）筛选

### （16）filter返回满足条件的元素

```javascript
     var arr15 = [2,3,5,6,7,18,9];
     var a15 = arr15.filter(function(item,index){
        return item >5;   
     });
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//[6,7,18,9]

//返回满足条件的元素

### （17）every全部满足才返回turn

### ![img](https://img-blog.csdnimg.cn/202105181245411.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### （18）some只要有一个满足就返回turn

![img](https://img-blog.csdnimg.cn/20210518124557482.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### （19）reduce累加

![img](https://img-blog.csdnimg.cn/20210518124610622.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

# 11、对象

## 1）定义对象两种方式

### （1）new方式

var person = **new Object()**;

![img](https://img-blog.csdnimg.cn/2021051812484099.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### （2）字面量方式

### 1、简单字面量方式

var person2 = **{}**;

![img](https://img-blog.csdnimg.cn/20210518124925642.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518124929892.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021051812494086.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518124943469.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518124945868.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### 2、(常用) 嵌套字面量方式

![img](https://img-blog.csdnimg.cn/20210518125047228.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021051812505092.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518125052781.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 2）属性

### （1）写法

![img](https://img-blog.csdnimg.cn/20210518125139375.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210518125141448.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 3）序列化

1. JSON.stringify()   方法是将JS值(对象或者数组)转换JSON字符串
2. JSON.parse()        方法是将JSON字符串转换为对象
3. hasOwnProperty() 该方法可以判断对象的自有属性是否存在
4. assign()                该方法主要用于对象的合并
5. defineProperties()  直接在一个对象上定义新的属性或修改现有属性，并返回该对象。
6. keys()                  返回一个由一个 给定对象的自身可枚举属性组成的数组
7. values();                返回一个给定对象自己的所有可枚举属性值的数组
8. entries();               返回一个给定对象自身可枚举属性的键值对数组



## （1）JSON.stringify()  方法是将JS值(对象或者数组)转换JSON字符串

## （2）JSON.parse()       方法是将JSON字符串转换为对象

![img](https://img-blog.csdnimg.cn/20210518125247960.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
    var obj3 = {name:'abc',age:18,id:1};
    console.log(typeof  JSON.stringify(obj3))  //string
console.log(typeof  obj3); 					//object

    var str = JSON.stringify(obj3);
    console.log(typeof  JSON.parse(str));   	//object
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （3）hasOwnProperty()       判断对象的属性是否存在

**方式一：**

检测属性是否是自有属性

![img](https://img-blog.csdnimg.cn/20210518125357257.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**方式二：**

检测属性是否存在于某个对象中，自有属性和继承属性都返回true

![img](https://img-blog.csdnimg.cn/20210518125357338.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**//true**

**区别：**

![img](https://img-blog.csdnimg.cn/20210518125357339.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （4）assign()               对象的合并

![img](https://img-blog.csdnimg.cn/20210518125418794.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

===========================================================

![img](https://img-blog.csdnimg.cn/20210518125418816.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

===========================================================

![img](https://img-blog.csdnimg.cn/20210518125418833.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)



## （5）defineProperties()  直接在一个对象上定义新的属性或修改现有属性，并返回该对象

defineProperty()  定义单个

defineProperties() 定义多个

![img](https://img-blog.csdnimg.cn/20210518125501852.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

===========================================================

writable:false

![img](https://img-blog.csdnimg.cn/20210518125501862.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

===========================================================

![img](https://img-blog.csdnimg.cn/20210518125510206.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

===========================================================

![img](https://img-blog.csdnimg.cn/20210518125510171.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （6）keys()  返回一个由一个给定对象的自身可枚举属性组成的数组

![img](https://img-blog.csdnimg.cn/20210518125528657.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) //返回的是属性（数组类型）

## （7）values();        返回一个给定对象自己的所有可枚举属性值的数组

![img](https://img-blog.csdnimg.cn/20210518125546204.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//返回的是值（数组类型）

## （8）entries();       返回一个给定对象自身可枚举属性的键值对数组

![img](https://img-blog.csdnimg.cn/20210518125604114.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （9）delete删除

![img](https://img-blog.csdnimg.cn/20210518125626954.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) //为18

# 12、函数

![img](https://img-blog.csdnimg.cn/20210518125709299.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518125709335.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518125709309.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （1）函数声明与函数表达式

![img](https://img-blog.csdnimg.cn/20210518125727317.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （2）自调用函数（自动调用）

![img](https://img-blog.csdnimg.cn/20210518125753554.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518125756436.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （3）arguments

![img](https://img-blog.csdnimg.cn/20210518125812551.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## （4）写法

![img](https://img-blog.csdnimg.cn/20210518125827101.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### 写法一：

```javascript
    var _name = document.getElementById('name')
var _phone = document.getElementById('phone')

    //成为焦点
    _name.onfocus = function () {
        //nextSibling返回某个元素之后紧邻的节点
        this.nextSibling.style.display = "none";//紧邻的同级样式隐藏     
    };
    _phone.onfocus = function () {
        this.nextSibling.style.display = "none";//紧邻的同级样式隐藏 
    };
    
    //失去焦点
    _name.onblur = function () {
    //判断  如果表单的值为空   错误提示显示，反之表单的值不为空，错误提示隐藏
        if(this.value==''){   
            this.nextSibling.style.display="inline"; //紧邻的同级样式显示
        }else {
            this.nextSibling.style.display="none";  //紧邻的同级样式隐藏 
        }
    };
    _phone.onblur = function () {
    //判断  如果表单的值为空   错误提示显示，反之表单的值不为空，错误提示隐藏
        if(this.value==''){   
            this.nextSibling.style.display="inline";//紧邻的同级样式显示
        }else {
            this.nextSibling.style.display="none";  //紧邻的同级样式隐藏 
        }
    };
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//onfocus（成为焦点）

onblur（失去焦点）换成chlick也可以

![img](https://img-blog.csdnimg.cn/20210518125907182.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518125907185.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### 写法二（推荐）

![img](https://img-blog.csdnimg.cn/202105181259293.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/202105181259297.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021051812592915.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021051812592927.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) //$是与querySelector无关

![img](https://img-blog.csdnimg.cn/20210518125935813.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) //一样

![img](https://img-blog.csdnimg.cn/20210518125935854.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)  //面向对象的写法

### 写法三（推荐）

![img](https://img-blog.csdnimg.cn/20210518125952155.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021051812595270.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) //一样

# 13、预解析

**预处理：**创建一个词法环境，扫描JS中的用声明的方式声明的函数，用var定义的变量并将它们加到预处理阶段的词法环境中去

**预解析：**在全局中寻找var关键字声明的变量和通过function关键字声明的函数，主要把var , function , 参数等一些东西 存储进仓库里面(内存)。

![img](https://img-blog.csdnimg.cn/20210518130024761.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)  //先全部声明，再打印

**========================================================**

![img](https://img-blog.csdnimg.cn/20210518130024697.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**========================================================**

![img](https://img-blog.csdnimg.cn/20210518130024696.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**//****函数的优先级更高**

**========================================================**

![img](https://img-blog.csdnimg.cn/20210518130033570.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) //结果为99

![img](https://img-blog.csdnimg.cn/20210518130033625.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210518130033539.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

// ? 第一行写c会报错c去掉了

//a、b、d、e都是undefined，c是报错

![img](https://img-blog.csdnimg.cn/20210518130042935.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210518130042899.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

# 14、作用域

**作用域：**

在ES5中只有全局作用域和函数作用域，没有块级作用域。

在ES6中添加了let\const，他可以保证外层块不受内层块的影响。即内层块形成了一个块级作用域，这是let\const的一个特点;今天我们着重讲的是函数作用域与全局作用域。



(1)在全局变量和局部变量不同名时，其作用域是整个程序

(2)在全局变量和局部变量同名时，全局变量的作用域不包含同名局部变量的作用域

**同名时：内外都是var a=1，则各做各的**

![img](https://img-blog.csdnimg.cn/2021051813011781.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/2021051813011726.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021051813011787.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/2021051813011747.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 注意1

**同名时：内外都是var a=1，则各做各的**

![img](https://img-blog.csdnimg.cn/20210518130147406.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210518130147407.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//结果为undefined原因：变量同名

## 注意2

![img](https://img-blog.csdnimg.cn/20210518130156637.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210518130156714.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//结果为undefined原因：变量同名,但是变量范围大小不同

 ![img](https://img-blog.csdnimg.cn/20210518130156715.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)  ![img](https://img-blog.csdnimg.cn/20210518130156716.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

# 15、深浅拷贝

![img](https://img-blog.csdnimg.cn/20210518130239305.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210518130239272.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210518130239274.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**========================================================**

![img](https://img-blog.csdnimg.cn/20210518130246578.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210518130246665.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**========================================================**

![img](https://img-blog.csdnimg.cn/20210518130246627.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)