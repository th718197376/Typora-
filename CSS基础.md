[TOC]

# CSS基础

## 一、CSS基础概念

CSS有两个重要的概念，分别是样式和布局

- 样式有两种
  - 文字的样式
  - 盒模型的样式
- 辅助页面布局

​		完成HTML不能完成的功能，比如精确定位显示



### 前端三层

- 结构层：HTML作用是从语义的角度进行网页结构的搭建
- 样式层：CSS作用从美观的角度讲修饰页面样式
- 交互层：JavaScript作用从交互的角度讲述页面的行为



## 二、CSS常用字体属性

CSS常用的文字属性有三个：color、font-size、font-family

CSS的属性样式发生了改变由HTML的k='v'变为k:v

### 1、color文字颜色

- 属性名：color
- 基本使用

```html
<p style="color:green;">今天天气真不错</p>
```

- 属性值：分为两种
  - 单词表示法
  - 颜色值（十六进制、rgba）

<img src="C:\Users\Tang\AppData\Roaming\Typora\typora-user-images\image-20220410132331618.png" alt="image-20220410132331618" style="zoom: 150%;" />



### 2、font-size字号

- 属性名：font-size 
- 属性值：常用的是以px为单位的数字值
  - 根据浏览器的不同，默认不同的字号大小，如：IE与Chrome默认为16px
  - 每个浏览器都有自己最小的显示像素，如：Chrome最小为8px，IE为1px

- 基本使用

```html
<p style="font-size: 20px;">天气真的不咋地</p>
```

### 3、font-family字体

- 属性名：font-family

- 属性值：必须以双引号包裹，属性值可以有多个，使用都好隔开

  - 中文字体的常用属性值：微软雅黑，宋体
  - 英文字体的常用属性值：Arial，consolas
  - 大多数浏览器默认字体为微软雅黑

- 基本使用

  - 可以设置多个字体，按照顺序，如果识别不出第一个就会顺序到第二个

  - 如果中文和英文混合出现，需要同时设置对应的字体

```html
<p style="font-family: '宋体';">我看你真的就是歌姬吧</p>
```

```html
<p style="font-family: 'Arial','consolas','黑体','宋体';">我是个sb</p>
```



## 三、盒子的三属性

盒子也有三属性

- width：宽度
- height：高度

高度与宽度常用属性值都是以px为单位的数值

- background-color：属于background系列属性的一种

属性值和color一样分为单词和颜色值表示法

```html
<div style="width: 100px;height: 500px;background-color: aquamarine;"></div>
```



## 四、CSS样式表

style写在标签内的叫做行内式样式

### 1、行内式样式表

基本语法：

```html
<div style="width: 100px;height: 500px;background-color: aquamarine;"></div>
```

使用分号隔开



### 2、内嵌式样式表

基本语法

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div {
                color: aquamarine;
                font-size: 18px;
        }
    </style>
</head>
<body>
    <div>文字</div>
</body>
```

### 3、外链式样式表

基本语法

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="1.css">
</head>
<body>
    <div>文字</div>
</body>
</html>
```

 link标签的作用就是引入外部文件，通过href属性，属性值是文件地址

rel属性值如果是stylesheet，代表的就是引入样式表

css文件不需要写其他任何标签直接写属性和css选择器



### 4、导入式样式表

基本语法：

```html
<style>
	@import url(css/1/.css);
</style>
```

注：导入式必须要写在style标签里面的最顶部

```html
<style>
	@import url(css/1/.css);
	div{
		color:red;
	}
</style>
```

url内部是css文件的引入地址





四种样式表的区别与优缺点

| 样式表       | 权重                   | 优点                                                | 缺点                                                         |
| ------------ | ---------------------- | --------------------------------------------------- | ------------------------------------------------------------ |
| 行内式样式表 | 最高                   | 权重高，样式设置更精确                              | 1、结构与样式没有进行分离<br>2、不能批量修改样式<br />       |
| 内嵌式样式表 | 大于导入式，等于外链式 | 能够将CSS样式和估计进行分离，可以进行批量属性的修改 | 样式和骨架没有完全分离，多个html文件不能使用同一套CSS代码    |
| 外链式样式表 | 大于导入式，等于内嵌式 | 样式和骨架进行了完全分离，一份CSS代码可以重复使用   | 如果我们小的demo的时候，每次写外链式比较麻烦，并且看起来不直观 |
| 导入式样式表 | 最低                   | 样式和骨架进行了完全分离，一份CSS代码可以重复使用   | 导入式有样式问题，引入导入式涉及到加载顺序，说白了，页面会白一下，体验不好 |



## 五、选择器

选择器分为两种

- 基础选择器
  - 标签选择器
  - id选择器
  - 类名选择器
- 高级选择器
  - 后代选择器
  - 交集选择器
  - 并集选择器



### 1、标签选择器

- 选择方法：通过标签名称去选择
- 书写方法：标签名
- 选择范围：HTML文档中所有的同名标签

基本使用

```html
<style>
        p{
            color: antiquewhite;
        }
        h3{
            color: azure;
        }
</style>
```

注：标签选择器无视嵌套规则，只要是同名标签就会被选择

- 用途：实现全选同名标签，设置公共样式
- 缺点：只能进行全选，不能进行单独的布局搭建



### 2、id选择器

- 选择方法：通过标签上id进行选择
- 书写方法：#id属性值(自定义)
- 选择范围：只能选定特定id

基本使用

```html
<style>
   #p1{
     	color: antiquewhite;
   }
</style>
```

```html
<p id="p1">第1段文字</p>
```

一个页面中不允许有同名id属性

- 优点：id属性的权重高
- 缺点：只能实现单选



### 3、类名属性

- 选择方法：通过标签上的class进行选择
- 书写方法：.(对应的class的属性值)
- 选择范围：选中所有的同名class属性标签

基本使用

```html
<head>
	<style>
        .par1{
            color: rgb(26, 161, 60);
        }
    </style>
</head>
<body>
    <p class="par1">第1段文字</p>
    <p class="par1">第2段文字</p>
    <p class="par1">第3段文字</p>
</body>
```

每一个标签内的class属性可以有多个，他们之间用空格隔开

```html
<head>
	<style>
        .par1{
            color: rgb(26, 161, 60);
        }
        .par2{
            color: yellow;
        }
    </style>
</head>
<body>
    <p class="par1">第1段文字</p>
    <p class="par1 par2">第2段文字</p>
    <p class="par1">第3段文字</p>
</body>
```

**id和class属性的命名规范，第一个字符必须是字母、数字、下划线**



4、通配符选择器

- 书写方法：*
- 选择范围：选中包含HTML标签在内的所有标签

通配符*后面添加的样式，每一个标签都会加载一次，通常使用该方法清除页面的默认样式

基本使用

```html
<head>  
	<style>
        * {
            color: yellow;
        }
    </style>
</head>
<body>
    <span>文字</span>
    <p>p标签</p>
    <div>div</div>
    <h3>h3</h3>
</body>
```

```html
可以通过这种方法来统一更改
* {
    margin: 0;
    padding: 0;
}
```



### 5、后代选择器

- 选择方法：.(标签内class 标签1 标签2)通过标签之间的后代关系去决定选择某个范围内的元素
- 书写方法：使用空格连续
- 作用：通过标签之间的后代关系去决定选择某个范围内的元素，具有精确匹配性

基本使用

```html
<head>
   <style>
        .box1 ul li{
            color: blue;
        }
    </style>
</head>
<body>
    <div class="box1">
        <ul>
            <li>li里面的box</li>
            <li>li里面的box</li>
            <li>li里面的box</li>
            <li>li里面的box</li>
        </ul>
    </div>
</body>
```

需要注意的是，后代关系不一定是父子关系(直接嵌套关系)

```html
.box1 li{
    color: blue;
}
```

表示选择类名为box1的后代li标签



### 6、交集选择器

- 作用：进行满足所有选择器条件的匹配
- 书写方法：将多个选择器连接书写，中间没有空格直接连接，不需要添加任何符号

基本使用

```html
<head>
    <style>
        p.par {
            color: aqua;
        }
    </style>
</head>
<body>
    <p class="par">文字</p>
    <div class="par">文字</div>
</body>
```

### 7、并集选择器

并集选择器有着“和”的意思，代表多个标签设置同样的属性

- 书写方法：将多个选择用逗号进行连接，最后一个不加逗号
- 选择范围：多个选中标签的集合

```html
<head>
    <style>
        p,div {
            color: aqua;
        }
    </style>
</head>
<body>
    <p >文字</p>
    <div>文字</div>
</body>
</html>
```

并集选择器非常灵活，可以结合多种选择器使用，就是利用都好就行分割，从而区分属性

```html
#par .par li.p{
	color: red;
}
```

上述代码代表#par里面的.par里面的li和p标签的文字颜色为红色



## 六、CSS的继承性和层叠性

### 1、继承性

只需要给先祖元素设置文字属性，后代元素就能加载这个属性，这个特性我们叫做继承性

```html
<head>
    <style>
        .box {
            color: red;
        }
    </style>
</head>
<body>
    <div class="box">
        <ul>
            <li>文字</li>
        </ul>
    </div>
</body>
```

通过网页F12可以查看

![image-20220415102710746](C:\Users\Tang\AppData\Roaming\Typora\typora-user-images\image-20220415102710746.png)

**注：CSS可以继承的属性都是关于文字的，比如：color，font-size，font-family**



### 2、层叠性

CSS样式表又叫做“层叠式样式表”

```html
<p class="par" id="par">文字</p>
```

```html
<style>
        p{
            color: red;
        }
        .par{
            font-size: 20px;
        }
        #par{
            /* 给文字添加下划线 */
            text-decoration: underline;
        }
</style>
```

标签可以被多个选择器选中，并设置对应的属性

如果多个选择器，设置了同一个属性

```html
<head>
    <style>
        p{
            color: red;
        }
        .par{
            color: blue;
        }
        #par{
            color: green;
        }
    </style>
</head>
<body>
    <p class="par" id="par">文字</p>
</body>
```

id选择器的权重大，其余两个在后台被刷掉了，这就是CSS的层叠性



***id选择器>class类名选择器>标签选择器***



#### 练习——针对选择器都选中同一个标签情况

```html
<head>
    <style>
        .box1 div.box2 #box3 p{
            color: aqua;
        }
        #box1 #box2 div.box3 p{
            color: beige;
        }
        #box1 div.box2 .box3 p{
            color:blue;
        }
    </style>
</head>
<body>
    <div id="box1" class=""box1>
        <div id="box2" class="box2">
            <div id="box3" class="box3" >
                <p>文字</p>
            </div>
        </div>
    </div>
</body>
```

结果为blue

首先将所有的选择器罗列出来，一次比较id选择器、class选择器、标签选择器的数量，如果选择器数量相同，后写的覆盖先写的



#### 练习——选择器没有选中对应标签

```html
<head>
        <style>
            #box1 #box2 {
                color: rgb(32, 32, 3);
            }
            .box1 .box2 .box3{
                color:blue;
            }
        </style>
    </head>
    <body>
        <div id="box1" class="box1">
            <div id="box2" class="box2">
                <div id="box3" class="box3" >
                    <p>文字</p>
                </div>
            </div>
        </div>
    </body>
```

如果都没有选中标签，则里的最近的选择器内的元素生效



#### 总结：如遇到复杂的选择，先看是否同时选中的一个元素

- 如果都选择的是同一个元素，则数权重
- 如果层级不同，有的是父亲级别，有的是爷爷级别，就近原则
- 如果所有的权重一样，选择位置也一样，后书写的覆盖先书写的



## 七、CSS文字属性的深入认识

### 1、字体

#### 1、颜色 color

color作用是用来设置文字的颜色

属性值：颜色名、颜色值

颜色值：包含rbg和十六进制

- rgb模式就是三原色（red、green、blue）
  - rgb(红色，绿色，蓝色)逗号分隔开每个颜色的色值

使用方法

```html
.rgb{
            color: rgb(200, 32, 100);
        }
```

```html
<p class="rgb">文字的颜色</p>
```

- 十六进制是将rgb颜色表示法进行了简化，将十进制的0-255颜色表示法替换成十六进制颜色表示法(0-9,a-f)
  - 红色#ff0000
  - 绿色#00ff00
  - 蓝色#0000ff

使用方法

```html
.rgb{
            color: #00ff00;
        }
```

```html
<p class="rgb">文字的颜色</p>
```

部分特殊的十六进制可以简化，如：黑色#000000可以简化为#000

复杂的是不可以简化的，#aa00ff可以简化为#a0f



#### 2、字体 font-family

- 设置文字使用哪种字体显示
- 属性值：必须要用引号包裹，值可以有多个，中间使用逗号隔开
- 常用的中文字体：
  - 微软雅黑的英文表示法：Miscrosoft Yahei
  - 宋体的英文表示法：Smisum
- 常用的英文表示法：
  - Arial
  - consolas



#### 3、字号 font-size

- 设置文字大小
- 属性值：
  - px为单位，数值表示多少像素
  - 百分比为单位，参考的是继承的字号的百分比
  - em为单位，数值表示继承字号的几倍

使用方法

```html
<head>
    <style>
        div{
            font-size: 12px;
        }
        p{
            font-size: 200%;
        }
        p1{
            font-size: 2em;
        }
    </style>
</head>
<body>
    <div>
        <p>
            文字
        </p>
        <p1>
            文字
        </p1>
    </div>
</body>
```

#### 4、行高 line-height

- 文字在一定的高度内垂直居中
- 属性值：
  - px为单位，数值代表行高为多少像素
  - 百分比为单位，数值代表继承字体大小的百分比的行高
  - em为单位，数值代表继承字体大小的倍数的行高

利用行高的特点可以设置文字在盒子内的垂直居中

```html
<head>
    <style>
        *{
            padding: 0;
            margin: 0;
        }
        p{
            font-size: 24px;
            background-color: greenyellow;
            width: 100px;
            height: 200px;
            margin: 100px auto;
            line-height: 200px;
        }
    </style>
</head>
<body>
    <div>
        <p>
            文字
        </p>
    </div>
</body>
```

#### 5、字体加粗 font-weight

- 设置字体是否进行加粗显示

- 属性值：单词法、数值法

  - 数值：100-700，以整百为单位

  使用方法

  ```html
  p{
  	font-size:20px;
  	font-weight:700;
  }
  ```

  - 单词：
    - normal表示正常不加粗
    - bold表示加粗，数值和700是相同的

  使用方法

  ```html
  p{
  	font-size:20px;
  	font-weight:bold;
  }
  ```



#### 6、字体样式 font-style

- 用来设置文字是否采用斜体

- 属性值：

  - normal：正常，没有倾斜
  - italic：字体倾斜，如果字体带有倾斜则有倾斜，反之无法倾斜
  - oblique：与字体无关倾斜，无论带不带有倾斜样式都可以倾斜

  最常用的是italic

使用方法

```html
<head>
    <style>
        .normal{
            font-style: normal;
        }
        .italic{
            font-style: italic;
        }
        .oblique{
            font-style: oblique;
        }
    </style>
</head>
<body>
    <p class="normal">倾斜</p>
    <p class="italic">斜体</p>
    <p class="oblique">与字体无关斜体</p>
</body>
```

font属性综合写法：包含五个单一属性，书写是属性值之间空格隔开，字号和行高使用斜杠分割。字号、行高、字体必须连续书写，顺序不能颠倒，而且必须位于倒数后三个

```html
<head>
    <style>
        .font{
            /* 倾斜 加粗 字体大小/行高 字体样式 */
            font: italic bold 24px/48px 'Simsun';
        }
    </style>
</head>
<body>
    <p class="font">综合属性字体</p>
</body>
```



### 2、文本

#### 1、对齐方式 text-align

- 用来设置段落的整体水平方向对齐
- 属性值：left、center、right

文本默认是左对齐

使用方法

```html
<head>
    <style>
        p{
            width: 100px;
            height: 100px;
            border: 1px solid red;
            text-align: center;
        }
    </style>
</head>
<body>
    <p>普通段落</p>
</body>
```

#### 2、文本修饰 text-decoration bv

- 设置文本整体是否有线条修饰
- 属性值：
  - none：没有修饰
  - overline：上划线
  - line-through：删除线
  - underline：下划线

​	使用方法

```html
<head>
    <style>
        .none{
            text-decoration: none;
        }
        .overline{
            text-decoration: overline;
        }
        .line-through{
            text-decoration: line-through;
        }
        .underline{
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <p class="none">没有修饰</p>
    <p class="overline">上划线</p>
    <p class="line-through">删除线</p>
    <p class="underline">下划线</p>
</body>
```

通常使用text-decoration属性取消a标签的默认下划线



#### 3、缩进 text-indent

- 设置段落的首行缩进

- 属性值：

  - px为单位，数字是多少代表首行缩进多少

  ```html
  text-indent: 200px
  ```

  - 百分比为单位，参考标签的父级width属性值的百分比

  ```html
  text-indent: 100%
  ```

  - em为单位，代表首行缩进几个中文字符

```html
text-indent: 2em
```

## 八、盒模型

又叫框模型，是css的重要布局属性，包含了五个属性，width(宽度)

height（高度）、padding（内边距）、border（边框）、margin（外边距）

盒子的实际加载区域：width+height

盒子可实体化显示区域：width+height+padding+border

盒子实际占位区域：width+height+padding+border+margin

![image-20220421175231691](C:\Users\Tang\AppData\Roaming\Typora\typora-user-images\image-20220421175231691.png)

```html
<head>
    <style>
        div{
            width: 100px;
            height: 100px;
            padding: 10px;
            border: 5px solid black;
            margin: 10px;
        }
    </style>
</head>
<body>
    <div></div>
</body>
```

### 1、宽度和高度

- 设置加载内容的区域

- 宽度：width

- 高度：height
- 属性值z
  - 以px为单位的数字表示法，数值是多少表示宽度或者高度为多少像素

```html
<head>
    <style>
        div{
            width: 200px;
            height: 20px;
            background-color: aqua;
        }
    </style>
</head>
<body>
    <div>
        一段普通的段落
    </div>
</body>
```

- 以百分比为单位的百分比表示法，数值是多少表示宽度或者高度为父类继承的百分之多少

```html
<head>
    <style>
        div{
            width: 200px;
            height: 20px;
            background-color: aqua;
        }
        p{
        	width:50%;
        	height:50%;
        	background-color: blue;
        }
    </style>
</head>
<body>
    <div>
    	<p>一段普通的段落</p>
    </div>
</body>
```

注：如果盒子不设置宽度回撑满父盒子的宽度，如果盒子不设置高度，会默认被内容撑高



### 2、内边距

- 设置宽高到边框的间距
- 特点：不能加载内容，可以加载背景
- 属性名：padding
- 属性值：以px为单位的数值

padding属性是一个综合属性，可以根据不同方向进行单一属性设置

```html
padding-top: 50px;
padding-left: 50px;
padding-bottom: 50px;
padding-right: 50px;
```

可以使用padding进行综合书写，四个方向按照顺时针顺序进行书写

```html
padding: 10px 20px 30px 40px;
```

出去四个值还可以进行三值、两值表示，分别为上、左右、下；上下、左右



### 3、边框

- 设置盒子的显示边缘，都可以进行四值设置
- 属性名：border

```html
border: 10px solid rebeccapurple;
```

- 属性值：

  - 边框宽度：border-width

  ```html
  border-width: 10px 20px 30px 40px;
  ```

  - 线型：border-style

  ```
  border-style: solid dashed dotted double;
  ```

  - 种类：
    - 实线 solid
    - 虚线 dashed
    - 点线 dotted
    - 双线 double
    - 边框凹陷效果 groove
    - 边框凸显效果 rideg
    - 内容凹陷效果 inset
    - 内容凸显效果 outset
  - 边框颜色：border-color

```html
 border-color: red blue black pink;
```

### 4、外边距

- 设置盒子与其他盒子之间的间距
- 属性名：margin
- 属性值：与padding相同



### 5、清除默认样式

很多标签都有自己的默认样式，这些默认样式是开发中不需要的，如：h1系列标签的字号加粗；p标签的默认边距；ul、li的默认小圆点

使用方法：

```html
<style>
body,div,p,h1,h2,h3,h4,h5,h6,ul,ol,li,dl,dt,dd,th,td,input{
	margin: 0;
    padding: 0;
}
ul,ol{
	list-style: none;
}
h1,h2,h3,h4,h5,h6{
	font-weight: normal;
	font-size: 100%;
}
</style>
```

也可以简便的方法：

```html
<style>
    *{
        margin:0;
        padding:0;
    }
</style>
```



网站除了需要清楚默认样式外，还需要对部分标签或者整体文本进行初始设置



页面的默认设置

```html
<head>
    <style>
        /* 清除标签默认样式 */
        body,div,p,h1,h2,h3,h4,h5,h6,ul,ol,li,dl,dt,dd,th,td,input{
	        margin: 0;
            padding: 0;
        }
        ul,ol{
	        list-style: none;
        }
        h1,h2,h3,h4,h5,h6{
	        font-weight: normal;
	        font-size: 100%;
        }
        /* 网页文字初始默认样式 */
        body{
            color: black;
            font-size: 14px;
            font-family: '微软雅黑','宋体','Arial';
        }
        a{
            text-decoration: none;
            color: black;
        }
        /* 自定义布局 */
        .header{
            width: 500px;
            height: 35px;
        }
        li{
            width: 99px;
            line-height: 35px;
            float: left;
            background-color: gold;
            color: yellow;
            border-right: 1px solid white;
            text-align: center;
        }
    </style>
</head>
<body>
    <div>
        <div class="header">
            <ul>
                <li><a href="#">首页</a></li>
                <li><a href="#">商店</a></li>
                <li><a href="#">库存</a></li>
                <li><a href="#">社区</a></li>
            </ul>
        </div>
    </div>
</body>
```



### 6、height属性扩展

<!--一个盒子必须有高度，否则看不到内容央视，高度可以有多个配置内容，如超出部分，如果显示盒子没有设置高度，则被内容撑高，如果设置了高度，内部高度大于盒子本身的高度，不会被隐藏，会自动超出盒子内容显示-->

关于高度超出部分，是有属性可配置的

- 属性名：overflow
- 使用方法 overflow:属性值
- 其作用指的是超出盒子部分怎么显示
  - 属性值：visible 可见的,默认的（正常显示）
  - 属性值：hidden 超出高度部分隐藏
  - 属性值：scroll 给盒子添加滚动条不管有没有超出
  - 属性值：auto 盒子内容超出部分滚动条显示

关于height属性，如果希望盒子与内容同高，可以设置值为'auto'



### 7、居中

主要有两种：盒子、文字

#### 1、文字

- 水平居中：
  - 使用text-align：center
- 垂直居中：
  - 使用line-height(其中数值与盒子的高度数值一样)
- 如果需要单行文本水平垂直都居中
  - 设置text-align：center，line-height：盒子高度
- 如果是多行文本设置垂直居中不能使用行高等于盒子高度
  - 方法：盒子不设置高度，设置上下相同的padding属性值

```html
p{
	width:100px;
	border:1px solid #ccc;
	text-align:center;
	padding:20px 0;
}
```

#### 2、盒子居中

- 水平居中：
  - 给目标元素设置margin：自定义值 auto;

```html
<head>
	<style>
        *{
            margin:0;
            padding:0;
        }
        div{
            width:600px;
            height:300px;
            background-color:pink;
        }
        p{
            width:100px;
            height:100px;
            background-color:green;
            margin: auto;
        }
    </style>
</head>
<body>
    <div>
        <p></p>
    </div>
</body>
```

- 垂直居中：
  - 与文字类似，父盒子不设置高度，设置上下的padding数值

```html
<style>
        *{
            margin:0;
            padding:0;
        }
        div{
            width:600px;
            padding:75px 0;
            background-color:pink;
        }
        p{
            width:100px;
            height:100px;
            background-color:green;
            margin: auto;
        }
</style>
```

如果设置盒子上下左右都居中的状态，首先盒子设置margin：0 auto；

父盒子不设置高度，设置上下padding，一般来说设置居中不使用padding来挤高度



### 8、margin塌陷现象

margin塌陷一般都是上下放下的塌陷

- 同方向的margin会有塌陷

在垂直方向上，如果有相遇的margin，两个盒子之间不是属性值的和，而是比较两个盒子谁的margin更大，使用的就是margin值更大的一方

- 父子元素也会有塌陷的现象

```html
<head>
    <style>
        *{
            margin:0;
            padding:0;
        }
        div{
            width:600px;
            padding:75px 0;
            background-color:pink;
        }
        p{
            width:100px;
            height:100px;
            background-color:green;
            margin-top:50px;
        }
</style>
</head>
<body>
    <div>
        <p></p>
    </div>
</body>
```

![image-20220430212824982](C:\Users\Tang\AppData\Roaming\Typora\typora-user-images\image-20220430212824982.png)

父子盒子，如果子盒子设置margin-top，父盒子没有设置或者margin-top的值小于子盒子，此时会存在margin塌陷的现象



解决margin塌陷的现象

- 兄弟关系：统一设置一个方向的margin，都设置margin-bottom
- 父子盒子：给父盒子设置border或者padding，其实这两种方法都不合适，正常情况下都不会使用子盒子去向上蹭父盒子，而是使用父盒子加padding



## 九、标准文档流

### 1、元素类型

从HTML的角度讲元素分为两个级别：容器级和文本级

从CSS的角度讲将元素分为三种类型：块级元素、行内元素、行内块元素



块级元素

- 特点：可以设置宽度、高度，元素独占一行
- 常用的块级元素：div、p、h1~h6、ul、ol、dl等



行内元素

- 特点：文字并排显示，不能设置盒子的宽度和高度
- 常用的行内元素：span、a、b、u、i等



行内块元素

- 特点：可以设置宽度和高度、盒子也可以并排显示
- 常用的行内块元素：input、img、table



### 2、display显示模式

大部分标签默认的时候都会以各自的显示状态(类型)进行加载，标签的显示状态并不是固定不变的，可以通过CSS属性display进行切换

- display属性值

  - block：表示标签以块级元素加载

  ```html
  display:block;
  ```

  - inline：表示标签以行内元素加载

  ```
  display:inline;
  ```

  - inline-block：表示标签以行内块元素加载

```
display:inline-block;
```

如果一个网站只有标准文档流，很多效果是不能实现的，如果要实现非标准特点的页面就必须让标签去标准化

标签脱离标准流的方法：浮动、定位



## 十、浮动

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


![image-20220512154941902](CSS基础/image-20220512154941902.png)



### 1、浮动的性质

标准流元素是区分行、块

