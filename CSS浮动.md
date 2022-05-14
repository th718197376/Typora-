[TOC]

# CSS浮动

## 一、浮动

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



### 1、浮动的性质

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

2、依次贴边