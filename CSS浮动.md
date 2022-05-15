[TOC]

# CSS浮动

## 一、浮动的性质

### 1、浮动的元素脱标（脱离标准流）

浮动属性是专门用于进行网页并编排布局的

- 作用：脱离标准文档流，不再受元素等级的限制，又可以并排显示，又可以设置宽和高
- float：属性就是设置元素浮动
- 属性值：left、right
- 使用方法

```
float:left;
float:right;
```

浮动的特性：元素会按照书写的顺序进行一次贴边，同一个父盒子中，即可以设置左浮动，也可以设置有浮动

```html
.left{
	float:left;
}
.right{
	float:right;
}
```



案例练习
$$
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .inner{
            width: 970px;
            margin: 0 auto;
        }
        .inner .top{
            height: 103px;
            margin-bottom: 10px;
        }
        .inner .top .logo01{
            height: 103px;
            width: 277px;
            background: red;
            float: left;
        }
        .inner .top .logo02{
            height: 103px;
            width: 679px;
            float: right;
        }
        .inner .top .logo02-1{
            height: 49px;
            width: 137px;
            background: rgb(69, 184, 98);
            margin-bottom: 8px;
            float: right;
        }
        .inner .top .logo02-2{
            height: 46px;
            width: 679px;
            background: rgb(69, 184, 98);
            float: right;
        }
        .inner .middle{
            height: 435px;
            margin-bottom: 10px;
        }
        .inner .middle .middle01{
            height: 435px;
            width: 310px;
            float: left;
            background: orange;
        }
        .inner .middle .middle02{
            height: 435px;
            width: 650px;
            float: left;
            margin-left: 10px;
        }
        .inner .middle .middle02 .middle02-1{
            height: 400px;
            width: 650px;
        }
        .inner .middle .middle02 .middle02-1 .middle02-1-1{
            width: 450px;
            height: 400px;
            margin-bottom: 10px;
            float: left;
        }
        .inner .middle .middle02 .middle02-1 .middle02-1-1 .middle02-1-1-1{
            width: 450px;
            height: 240px;
            background: rgb(59, 59, 226);
            margin-bottom: 10px;
        }
        .inner .middle .middle02 .middle02-1 .middle02-1-1 .middle02-1-1-2{
            width: 450px;
            height: 110px;
            margin-bottom: 10px;
            background: rgb(59, 59, 226);
        }
        .inner .middle .middle02 .middle02-1 .middle02-1-1 .middle02-1-1-3{
            width: 450px;
            height: 30px;
            background: rgb(59, 59, 226);
        }
        .inner .middle .middle02 .middle02-1 .middle02-1-2{
            width: 190px;
            height: 400px;
            margin-bottom: 10px;
            float: right;
            background: palevioletred;
        }
        .inner .middle .middle02 .middle02-2{
            height: 25px;
            width: 650px;
            margin-top: 10px;
            background: rgb(0, 83, 0);
        }
        .inner .middle .middle02 .middle02-3{
            height: 400px;
            width: 190px;


            background: pink;
        }
        .inner .footer{
            height: 35px;
            background: blue;
        }
    </style>
</head>
<body>
    <div class="inner">
        <div class="top">
            <div class="logo01"></div>
            <div class="logo02">
                <div class="logo02-1"></div>
                <div class="logo02-2"></div>
            </div>
        </div>
        <div class="middle">
            <div class="middle01"></div>
            <div class="middle02">
                <div class="middle02-1">
                    <div class="middle02-1-1">
                        <div class="middle02-1-1-1"></div>
                        <div class="middle02-1-1-2"></div>
                        <div class="middle02-1-1-3"></div>
                    </div>
                    <div class="middle02-1-2"></div>
                </div>
                <div class="middle02-2"></div>
            </div>
        </div>
        <div class="footer"></div>
    </div>
</body>
</html>
$$


![image-20220512154941902](D:\学习笔记\Node\CSS基础\image-20220512154941902.png)

标准流元素是区分行内元素、块级元素
浮动元素是脱离标准流的，那么脱离标准流后，浮动元素有哪些特性
浮动元素脱离标准流后，既可以设置宽高，也可以实现并排显示，不区分元素状态，也就是不区分行内元素和块级元素

```html
div p{
	width: 100px;
	height: 100px;
	backgtound: purple;
}
div span{
	width: 100px;
	height: 100px;
	backgtound:	orange;
}
```

p标签和span标签都设置了宽高，但是由于元素类型的限制，span标签没有宽高

div内部元素设置浮动后

```
div p{
	width: 100px;
	height: 100px;
	backgtound: purple;
	float:left;
}
div span{
	width: 100px;
	height: 100px;
	backgtound:	orange;
	float:left;
}
```

注：兄弟元素如果有一个浮动，剩下的必须都要添加浮动
如果p标签与span标签都没有设置宽高，元素的宽度会被内容成款，不会自动撑满父盒子

### 2、依次贴边

```html
<head>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        div {
            width: 400px;
            height: 400px;
            border: 5px solid red;
            margin: 100px auto;
        }
        div p {
            width: 100px;
            height: 100px;
            float: left;
        }
        div p.part1{
            height: 400px;
            background: greenyellow;
        }
        div p.part2{
            height: 300px;
            background: yellowgreen;
        }
        div p.part3{
            height: 200px;
            background: yellow;
        }
        div p.part4{
            width: 300px;
            height: 100px;
            background: rebeccapurple;
        }
    </style>
</head>
<body>
    <div>
        <p class="part1">1</p>
        <p class="part2">2</p>
        <p class="part3">3</p>
        <p class="part4">4</p>
    </div>
</body>
```

如果父盒子的宽度不够，子盒子会一次贴边，如果前面元素中空隙当前需要贴边的元素不会钻空的现象，而之后会查询剩余宽度实现依次贴边

![image-20220514192130955](../CSS/CSS浮动/image-20220514192130955.png)

如果子盒子的宽度大于父盒子，会有溢出状态

![image-20220514192411125](../CSS/CSS浮动/image-20220514192411125.png)

向右贴边的原理与向左相同

### 3、浮动依次贴边练习

![image-20220515152821715](../CSS/CSS浮动/image-20220515152821715.png)

### 4、浮动的margin塌陷

标准流有margin塌陷的现象，去除塌陷的办法就是添加浮动

```html
<style>
	div {
            height: 240px;
            width: 60px;
            border: 1px solid black;
            margin: 80px auto;
            padding: 10px;
        }
    div p{
            float: left;
            height: 70px;
            width: 60px;
            background: chartreuse;
            border: 1px solid red;
            margin: 10px auto;
        }
</style>
```

​		设置了浮动			没设置浮动

 ![image-20220515155505831](../CSS/CSS浮动/image-20220515155505831.png)![image-20220515155823789](../CSS/CSS浮动/image-20220515155823789-16526015083441.png) 

总结：浮动元素没有了标准流的margin塌陷现象，各有各的margin，不会互相影响

### 5、浮动元素让出标准流

标准流中的元素都有一个自己的标准流位置，后面的元素只能在前面元素的后面进行加载
浮动元素脱离了标准流，它会让后面的元素占有自己原来的位置，它会在后面元素的上面，称为脱标

![image-20220515162803071](../CSS/CSS浮动/image-20220515162803071.png)

### 6、字围现象

同级元素中前面元素如果浮动了，后面的标准流会占住前面元素的位置，后面的盒子如果有文字，文字会围绕浮动元素进行加载

![image-20220515163431927](../CSS/CSS浮动/image-20220515163431927.png)

可以利用字围现象进行环境进行美化

![image-20220515174404328](../CSS/CSS浮动/image-20220515174404328.png)

```html
<style>
        *{
            padding: 0;
            margin: 0;
        }
        div{
            width: 300px;
            height: 400px;
            border: 1px solid black;
            margin: 30px auto;
        }
        div img{
            width:  100px;
            float: left;
            margin: 3px;
        }
</style>
```

