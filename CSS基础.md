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



