**目录**

[2、去重（Set）：](#2、去重（Set）：)

[3、选择器：](#2、选择器：)

[1、2、1：](#1、2、1：)

[3、](#3、)

[2、](#2、)

[3、](#3、)

[4、点击事件](#4、点击事件)

[1、onclick（单击）](#1、onclick（单击）)

[2、ondblclick（双击）](#2、ondblclick（双击）)

[3、4  onmousedown（按下鼠标）onmouseup（鼠标松开）   ](#3、4  onmousedown（按下鼠标）onmouseup（鼠标松开）   )

[5、6  onmouseenter（移入）onmouseleave（移出）](#5、6  onmouseenter（移入）onmouseleave（移出）)

[7、8  onmouseover（移至） onmouseout（移出）](#7、8  onmouseover（移至） onmouseout（移出）)

[9、 onmousemove（移入）     鼠标被移动。      ](#9、 onmousemove（移入）     鼠标被移动。      )

[1、 onkeydown（按下）  ](#1、 onkeydown（按下）  )

[5、放大镜案例](#5、放大镜案例)

[6、document对象常见属性和方法](#6、document对象常见属性和方法)

[1、](#1、)

[2、](#2、)

[3、4、5、](#3、4、5、)

[6、](#6、)

[8、](#8、)

[可能会出现的问题：](#可能会出现的问题：)

[7、数据类型](#7、数据类型)

[数组Array：](#数组Array：)

[对象Object：](#对象Object：)

[函数function：](#函数function：)

[8、字符串](#8、字符串)

[1、charAt() 方法可返回指定位置的字符。](#1、charAt() 方法可返回指定位置的字符。)

[2、concat() 方法用于连接两个或多个字符串。](#2、concat() 方法用于连接两个或多个字符串。)

[3、indexOf() 方法可返回某个指定的字符串值在字符串中首次出现的位置。](#3、indexOf() 方法可返回某个指定的字符串值在字符串中首次出现的位置。)

[4、lastIndexOf() 方法可返回一个指定的字符串值最后出现的位置](#4、lastIndexOf() 方法可返回一个指定的字符串值最后出现的位置)

[5、includes() 方法用于判断字符串是否包含指定的子字符串](#5、includes() 方法用于判断字符串是否包含指定的子字符串)

[6、replace() 用于在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串](#6、replace() 用于在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串)

[7、split() 方法用于把一个字符串分割成字符串数组](#7、split() 方法用于把一个字符串分割成字符串数组)

[8、substr() 方法可在字符串中抽取从开始下标开始的指定数目的字符](#8、substr() 方法可在字符串中抽取从开始下标开始的指定数目的字符)

[9、substring() 方法用于提取字符串中介于两个指定下标之间的字符](#9、substring() 方法用于提取字符串中介于两个指定下标之间的字符)

[10、slice(start, end) 方法可提取字符串的某个部分，并以新的字符串返回被提取的部分](#10、slice(start%2C end) 方法可提取字符串的某个部分，并以新的字符串返回被提取的部分)

[11、toLowerCase() 方法用于把字符串转换为小写](#11、toLowerCase() 方法用于把字符串转换为小写)

[12、toUpperCase() 方法用于把字符串转换为大写](#12、toUpperCase() 方法用于把字符串转换为大写)

[13、trim() 方法用于删除字符串的头尾空格](#13、trim() 方法用于删除字符串的头尾空格)

------



# **2、去重（Set）：**

```javascript
    var a1 = [1,2,3,4,5,6,6,6];
    var a2 = [...new Set(a1)];   
    alert(a2);  //[1,2,3,4,5,6]
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

# 3、选择器：

选择dom中的元素时，常用选择器：

1. **document.getElementById();**                选择Id选择器，来选择标签
2. **document.getElementsByTagName()****；**  标签名来选择标签
3. **document.getElementsByName()****；**        name属性来选择标签

**IE8****及以上：**

1. **document.getElementsByClassName()****；**Class选择器来选择标签
2. **document.querySelector();**             可以像css一样，选择标签。（但只能设置第一行）
3. **document.querySelectorAll()****；**      选择所有的返回的是类数组

## 1、2、1：

![img](https://img-blog.csdnimg.cn/202105131430200.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
    //1：document.getElementById();  通过选择Id选择器，来选择标签
    document.getElementById("div").innerHTML="您好 div";
    document.getElementById("div").style.color="red";
    //document.getElementsByTagName()；通过标签名来选择标签
    document.getElementsByTagName("h1")[1].innerHTML = "您好 h1";
    //document.getElementsByClassName()；通过Class选择器来选择标签
    document.getElementsByClassName("demo")[0].style.color="blue";
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513143054910.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 3、

![img](https://img-blog.csdnimg.cn/20210513143126431.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
    //document.getElementsByName()；通过name属性来选择标签   IE8及以上
    document.getElementsByName("p")[0].style.background="yellow";
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 2、

```javascript
    //document.querySelector(); 可以像css一样，选择标签   获取文档中的第一个元素
    document.querySelector("#h").innerHTML="您好 div";
    document.querySelector(".a").innerHTML="您好 aaa";
    document.querySelector("p").innerHTML="您好 ppp";
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 3、

```javascript
    //document.querySelectorAll()；  选择所有的，返回类似数组
    document.querySelectorAll(".h2")[1].style.color="red";
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

# 4、点击事件



**鼠标点击：**

1.onclick（单击）                  当用户点击某个对象时调用的事件句柄。      

2.ondblclick（双击）             当用户双击某个对象时调用的事件句柄。      



3.onmousedown（按下）     鼠标按钮被按下。      

4.onmouseup（松开）          鼠标按键被松开。



5.onmouseenter（移入）      当鼠标指针移动到元素上时触发。   

6.onmouseleave（移出）      当鼠标指针移出元素时触发      



**下面两个一样：（上面两个不支持冒泡）**

7.onmouseover（移入）        鼠标移到某元素之上。      

8.onmouseout（移出）         鼠标从某元素移开。   



9.onmousemove（移入）     鼠标被移动。      

9与上面两个移入区别：     鼠标在框内移动也算移入

**（好处内容可见）**

**键盘点击：**

1、onkeydown（按下）          某个键盘按键被按下。      

2、onkeypress（按下并松开） 某个键盘按键被按下并松开。   

3、onkeyup（松开）               某个键盘按键被松开。

## 1、onclick（单击）

**方式一：**

```javascript
window.onload = function() {

}

function fun() {
    document.getElementById("h1").style.color = "red"
}
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

方式二：（写在大括号里面）

```javascript
    document.getElementsByTagName("button")[1].onclick=function(){
        document.getElementById("h1").innerHTML = "我是按钮";
    }
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

方式三：（常用？）

```javascript
    document.getElementsByTagName("button")[1].onclick=fun2;

    function fun2(){
        document.getElementById("h1").innerHTML = "我是按钮";
    };
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
												   //添加监听事件
    document.getElementsByTagName("button")[1].addEventListener("click",fun2);

    function fun2(){
        document.getElementById("h1").innerHTML = "我是按钮";
    };
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 2、ondblclick（双击）

```javascript
    document.querySelector(".btn2").ondblclick =fun2;
    function fun2(){
        document.getElementById("h1").innerHTML = "我是按钮";
    };
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 3、4  onmousedown（按下鼠标）onmouseup（鼠标松开）   

```javascript
    //按下、松开
    document.querySelector(".btn3").onmousedown=function(){
        document.getElementById("h1").innerHTML = "按钮按下了";
    }
    document.querySelector(".btn3").onmouseup=function(){
        document.getElementById("h1").innerHTML = "按钮松开了";
    };
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 5、6  onmouseenter（移入）onmouseleave（移出）

## 7、8  onmouseover（移至） onmouseout（移出）

```javascript
    //移入、移出
    document.querySelector(".btn4").onmouseover=function(){
        this.style.background = "rgba(68,157,68,1)";
    }
    document.querySelector(".btn4").onmouseout=function(){
        this.style.background = "rgba(68,157,68,.6)";
    }
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 9、 onmousemove（移入）     鼠标被移动。      

```javascript
好处：

document.querySelector(".btn4").onmousemove=function(event){
        //当前鼠标移入与X轴的距离
        document.getElementById("h1").innerHTML = event.clientX;    
    }
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 1、 onkeydown（按下）  

```javascript
    //键盘事件  按下键盘时发生的状态
    document.querySelector(".input").onkeyup = function(){
        document.getElementById("h1").innerHTML = this.value;
    }
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**2****、**onkeypress（按下并松开）  某个键盘按键被按下并松开。   

**3****、**onkeyup（松开）                某个键盘按键被松开。

# 5、放大镜案例

```html
<body>
<div id="box">
    <!--左侧-->
    <div class="small_pic">
       <!--滑块-->
       <span class="slider"></span>
       <!--图片-->
       <img src="img/1.jpg" />
    </div>
    <!--右侧-->
    <div class="big_pic">
       <!--图片-->
       <img class="big_img" src="img/1.jpg" width="720" height="1000"/>
    </div>
</div>
</body>
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```css
#box {
    position: relative;
}
.small_pic {
    width:360px;
    height:500px;
}
    .small_pic img {
        width:100%;
        height:100%;
    }
    .small_pic .slider {
        width:180px;
        height:250px;
        position: absolute;
        background:rgba(255,255,255,.3);
        cursor:move;
        display:none;
    }
.big_pic {
    width:360px;
    height:500px;
    position: absolute;
    top:0;
    left:370px;
    border:1px solid #333;
    overflow: hidden;
    display:none;
}
    .big_pic .big_img {
        position: absolute;
    }
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**Index.js**

```javascript
window.onload = function(){
    //选择器封装
    function $(name) {
        return document.querySelector(name); 
    };
    var small_pic = $(".small_pic"),   //左侧的图片
        slider = $(".slider"),    //滑块

    //移入
    small_pic.onmousemove = function(event){   //event对象  事件的状态
        slider.style.display = 'block';
        //event.clientX  			当前移入点与X轴的坐标   
        //slider.offsetWidth   	滑块的宽度
        var left = event.clientX - slider.offsetWidth/2;
        var top = event.clientY - slider.offsetHeight/2;

        slider.style.left = left +'px';
        slider.style.top = top +'px';
};

    //移出  onmouseleave
    small_pic.onmouseout= function(){   //onmouseleave也可用

    };
}
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513145458857.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**Index.js**

```javascript
window.onload = function(){
    //选择器封装
    function $(name) {
        return document.querySelector(name); 
    };
    var small_pic = $(".small_pic"),   //左侧的图片
        slider = $(".slider"),    //滑块

    //移入
    small_pic.onmousemove = function(event){   //event对象  事件的状态
        slider.style.display = 'block';
        //event.clientX  			当前移入点与X轴的坐标   
        //slider.offsetWidth   	滑块的宽度
        var left = event.clientX - slider.offsetWidth/2;
        var top = event.clientY - slider.offsetHeight/2;
================================ 添加 ==================================
        var w = this.offsetWidth - slider.offsetWidth;
        var h = this.offsetHeight - slider.offsetHeight;
        //移动范围
        if(left <0) {
            left = 0;
        }else if(left > w) {
            left = w;
        };
        if(top <0) {
            top = 0;
        }else if(top > h) {
            top = h;
        };
=======================================================================
        slider.style.left = left +'px';
        slider.style.top = top +'px';
};

    //移出  onmouseleave
    small_pic.onmouseout= function(){   //onmouseleave也可用

    };
}
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513145517283.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//设置滑块的边界

**Index.js**

```javascript
window.onload = function(){
    //选择器封装
    function $(name) {
        return document.querySelector(name); 
    };
    var small_pic = $(".small_pic"),   //左侧的图片
        slider = $(".slider"),    //滑块

    //移入
    small_pic.onmousemove = function(event){   //event对象  事件的状态
        slider.style.display = 'block';
================================ 添加 ==================================
        big_pic.style.display = 'block';
=======================================================================
        //event.clientX  			当前移入点与X轴的坐标   
        //slider.offsetWidth   	滑块的宽度
        var left = event.clientX - slider.offsetWidth/2;
        var top = event.clientY - slider.offsetHeight/2;
        var w = this.offsetWidth - slider.offsetWidth;
        var h = this.offsetHeight - slider.offsetHeight;
        //移动范围
        if(left <0) {
            left = 0;
        }else if(left > w) {
            left = w;
        };
        if(top <0) {
            top = 0;
        }else if(top > h) {
            top = h;
        };
        slider.style.left = left +'px';
        slider.style.top = top +'px';
};

    //移出  onmouseleave
small_pic.onmouseout= function(){   //onmouseleave也可用
================================ 添加 ==================================
        slider.style.display = 'none';
        big_pic.style.display = 'none';
=======================================================================
    };
}
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513145541391.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**Index.js**

```javascript
window.onload = function(){
    //选择器封装
    function $(name) {
        return document.querySelector(name); 
    };
    var small_pic = $(".small_pic"),   	//左侧的图片
        slider = $(".slider"),    		//滑块
================================ 添加 ==================================
        big_pic = $(".big_pic"),    		//右侧BOX
        big_img  = $(".big_img");   		//右侧大图
=======================================================================

    //移入
    small_pic.onmousemove = function(event){   //event对象  事件的状态
        slider.style.display = 'block';
        big_pic.style.display = 'block';
        //event.clientX  			当前移入点与X轴的坐标   
        //slider.offsetWidth   	滑块的宽度
        var left = event.clientX - slider.offsetWidth/2;
        var top = event.clientY - slider.offsetHeight/2;
        var w = this.offsetWidth - slider.offsetWidth;
        var h = this.offsetHeight - slider.offsetHeight;
        //移动范围
        if(left <0) {
            left = 0;
        }else if(left > w) {
            left = w;
        };
        if(top <0) {
            top = 0;
        }else if(top > h) {
            top = h;
        };
        slider.style.left = left +'px';
        slider.style.top = top +'px';
};

    //移出  onmouseleave
small_pic.onmouseout= function(){   //onmouseleave也可用
        slider.style.display = 'none';
        big_pic.style.display = 'none';
    };
}
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513145600524.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//右侧只显示鼠标刚移入进来时的位置

**Index.js**

```javascript
window.onload = function(){
    //选择器封装
    function $(name) {
        return document.querySelector(name); 
    };
    var small_pic = $(".small_pic"),   	//左侧的图片
        slider = $(".slider"),    		//滑块
        big_pic = $(".big_pic"),    		//右侧BOX
        big_img  = $(".big_img");   		//右侧大图

    //移入
    small_pic.onmousemove = function(event){   //event对象  事件的状态
        slider.style.display = 'block';
        big_pic.style.display = 'block';
        //event.clientX  			当前移入点与X轴的坐标   
        //slider.offsetWidth   	滑块的宽度
        var left = event.clientX - slider.offsetWidth/2;
        var top = event.clientY - slider.offsetHeight/2;
        var w = this.offsetWidth - slider.offsetWidth;
        var h = this.offsetHeight - slider.offsetHeight;
        //移动范围
        if(left <0) {
            left = 0;
        }else if(left > w) {
            left = w;
        };
        if(top <0) {
            top = 0;
        }else if(top > h) {
            top = h;
        };
        slider.style.left = left +'px';
        slider.style.top = top +'px';
================================ 添加 ==================================
        big_img.style.left = -(left*2) +'px';   //右侧大图的距离
        big_img.style.top = -(top*2) +'px';
=======================================================================
};

    //移出  onmouseleave
small_pic.onmouseout= function(){   //onmouseleave也可用
        slider.style.display = 'none';
        big_pic.style.display = 'none';
    };
}
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//完成

# 6、document对象常见属性和方法

1. document.activeElement()           返回当前获取焦点元素
2. document.addEventListener()     向文档添加句柄
3. document.createElement()          创建元素节点。
4. document.createTextNode()               创建文本节点。
5. appendChild()     方法可向节点的子节点列表的末尾添加新的子节点。
6. lastChild            返回最后一个子节点
7. firstChild        返回第一个子节点
8. childNodes()      返回所有子节点对象

## 1、

方式一：

![img](https://img-blog.csdnimg.cn/20210513150117113.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
window.onload = function(){
    //document.activeElement    返回当前获取焦点元素
					 //活动 元素
    alert(document.activeElement.id);
}
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150126380.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

方式二：

```javascript
    document.getElementById("my").onclick=function(){
        var _name = document.activeElement.tagName;  //tagName（标签名）
        document.getElementById("test").innerHTML = _name;
    }
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150152900.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150152962.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150152996.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150152994.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150152997.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 2、

![img](https://img-blog.csdnimg.cn/20210513150203952.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
//document.addEventListener()   向文档添加句柄
document.getElementById("my").addEventListener('click',function(){
var _name = document.activeElement.tagName;
document.getElementById("test").innerHTML = _name;
});
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//结果一样

![img](https://img-blog.csdnimg.cn/20210513150230783.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//结果一样

## 3、4、5、

![img](https://img-blog.csdnimg.cn/20210513150240118.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150243145.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
  //动态的操作DOM，添加内容 <div>hello world</div>
  document.querySelector(".btn").onclick=function(){
      var _div = document.createElement("div");				//创建元素节点
      var _text = document.createTextNode("hello world"); //创建文本节点
      _div.appendChild(_text);  //把文本节点添 加到元素节点末尾
      document.body.appendChild(_div);
  }           //注意body
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 6、

![img](https://img-blog.csdnimg.cn/20210513150259206.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150302698.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

```javascript
    //扩展  需求：二个列表，单击按钮时，左边最后一个数据移动到右边
    //lastChild    返回最后一个子节点
    //firstChild   返回第一个子节点
    document.querySelector(".change").onclick = function(){
        //左边的最后一个数据
        var _left = document.querySelector(".listL").lastChild;
        //右边添 加数据
        document.querySelector(".listR").appendChild(_left);
    };
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150315756.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150317526.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//32.55

## 8、

```javascript
    //扩展二  需求：二个列表，左侧选 中的数据移入到右侧
    var _listL = document.querySelector(".listL");
var child = _listL.childNodes;   	//获取子节点  ['red','orange']

    for(var i=0;i<child.length;i++){
        child[i].onclick = function(){  //arr[0]
            document.querySelector(".listR").appendChild(this);  //this表示当前单击的对象
        }
    };
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150341142.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150341164.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 可能会出现的问题：

![img](https://img-blog.csdnimg.cn/20210513150349839.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//复制（只是写法不同）

![img](https://img-blog.csdnimg.cn/20210513150355463.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150358499.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150401597.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513150406282.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//用nodeType解决

元素节点的属性是返回1，

文本节点的属性是返回3

# 7、数据类型

![img](https://img-blog.csdnimg.cn/20210513150428507.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//引用数据类型有堆栈

值类型(基本类型)：

字符串（String）、

数字(Number)、

布尔(Boolean)、

空对象（Null）、

未定义（Undefined）



引用数据类型(复杂类型)：

对象(Object)、

数组(Array)、

函数(function)

## 数组Array：

**方式一：**![img](https://img-blog.csdnimg.cn/20210513150500672.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) ![img](https://img-blog.csdnimg.cn/20210513150500767.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) 

**方式二：**![img](https://img-blog.csdnimg.cn/20210513150500764.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) 

**方式三：**![img](https://img-blog.csdnimg.cn/20210513150500766.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) 

## 对象Object：

**方式一：**

![img](https://img-blog.csdnimg.cn/20210513150515222.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**方式二：**

![img](https://img-blog.csdnimg.cn/20210513150515230.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

//结果是20

## 函数function：

**方式一：**![img](https://img-blog.csdnimg.cn/20210513150538397.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

**方式二：**

![img](https://img-blog.csdnimg.cn/20210513150544331.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//结果为hello world

# 8、字符串

1. charAt()         方法可返回指定位置的字符。
2. concat()        方法用于连接两个或多个字符串。
3. indexOf()       方法可返回某个指定的字符串值在字符串中首次出现的位置。
4. lastIndexOf() 方法可返回一个指定的字符串值最后出现的位置
5. includes()      方法用于判断字符串是否包含指定的子字符串
6. replace()       方法用于在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串
7. split()            方法用于把一个字符串分割成字符串数组
8. substr()         方法可在字符串中抽取从开始下标开始的指定数目的字符
9. substring()     方法用于提取字符串中介于两个指定下标之间的字符
10. slice(start, end)     方法可提取字符串的某个部分，并以新的字符串返回被提取的部分
11. toLowerCase()      方法用于把字符串转换为小写
12. toUpperCase()      方法用于把字符串转换为大写
13. trim()            方法用于删除字符串的头尾空格



## 1、charAt() 方法可返回指定位置的字符。

![img](https://img-blog.csdnimg.cn/20210513150739405.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//1

获取最后一个：

![img](https://img-blog.csdnimg.cn/20210513150749143.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)//d

## 2、concat() 方法用于连接两个或多个字符串。

![img](https://img-blog.csdnimg.cn/20210513151036308.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210513151036310.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513151036315.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210513151036315.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 3、indexOf() 方法可返回某个指定的字符串值在字符串中首次出现的位置。

![img](https://img-blog.csdnimg.cn/20210513151046156.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTA0MjU2OQ==,size_16,color_FFFFFF,t_70)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513151050272.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) //8

## 4、lastIndexOf() 方法可返回一个指定的字符串值最后出现的位置

![img](https://img-blog.csdnimg.cn/20210513151106920.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

与上面相反，从后面开始

![img](https://img-blog.csdnimg.cn/20210513151106922.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 5、includes() 方法用于判断字符串是否包含指定的子字符串

![img](https://img-blog.csdnimg.cn/20210513151115765.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 6、replace() 用于在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串

![img](https://img-blog.csdnimg.cn/20210513151128958.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)  ![img](https://img-blog.csdnimg.cn/20210513151128956.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 7、split() 方法用于把一个字符串分割成字符串数组

![img](https://img-blog.csdnimg.cn/20210513151145118.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)  ![img](https://img-blog.csdnimg.cn/20210513151145113.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513151145115.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210513151145120.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513151145119.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210513151145121.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

\-------------------------------------------------------------------------------

![img](https://img-blog.csdnimg.cn/20210513151145127.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) //也一样

\-------------------------------------------------------------------------------

![img](https://img-blog.csdnimg.cn/20210513151145126.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 8、substr() 方法可在字符串中抽取从开始下标开始的指定数目的字符

![img](https://img-blog.csdnimg.cn/2021051315120477.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)  ![img](https://img-blog.csdnimg.cn/2021051315120478.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/2021051315120483.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/2021051315120487.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 9、substring() 方法用于提取字符串中介于两个指定下标之间的字符

![img](https://img-blog.csdnimg.cn/20210513151214302.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210513151214388.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513151214387.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210513151214391.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513151224266.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210513151214390.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 10、slice(start, end) 方法可提取字符串的某个部分，并以新的字符串返回被提取的部分

![img](https://img-blog.csdnimg.cn/20210513151234563.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210513151234564.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513151234568.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210513151234565.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==) //最后一个

![img](https://img-blog.csdnimg.cn/20210513151234572.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)  //作业

## 11、toLowerCase() 方法用于把字符串转换为小写

## 12、toUpperCase() 方法用于把字符串转换为大写

![img](https://img-blog.csdnimg.cn/20210513151253254.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

![img](https://img-blog.csdnimg.cn/20210513151253256.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

## 13、trim() 方法用于删除字符串的头尾空格

![img](https://img-blog.csdnimg.cn/20210513151306731.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)![img](https://img-blog.csdnimg.cn/20210513151301966.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)