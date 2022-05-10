[TOC]



## 一、基础内容

### 前端学习路线

HTML入门→CSS入门→HTML进阶→CSS进阶→JavaScript入门→jQuery入门→ASP.NET入门（或PHP入门）→Ajax→ASP.NET进阶（或PHP进阶）

## 二、HTML的基本标签

### 1、标签的种类

| 单标签 | 双标签 |
| ------ | ------ |
| img    | h1-h6  |
| br     | div    |
| hr     | span   |
|        | p      |
|        | a      |
|        | ul+li  |

根据标签的种类区分两个等级，分别是容器级和文本级

1. 容器级：元素内部除了可以存放文本意外，还可以嵌套标签
2. 文本级：元素内部只能存放文本或文本级标签

| 容器级标签                  | 文本级标签     |
| --------------------------- | -------------- |
| div,ol,ul,li,dl,dt,dd,h1-h6 | span,img,b,u,i |



### 2、HTML基本语法

1. ​    整个网页是从<html>这里开始的，然后到</html>结束

2. ​	标签的属性是标签身上的特殊职能

3. ​	文字的位置不会根据书写标签的位置决定，而是根据标签的种类决定(块级，行内级)

4. 文本的空白折叠现象

5. 在普通普通文字之间，如果有空格、换行、缩进导致的空白。在浏览器加载时会被折叠成一个空格显示(多个缩减成一个)

   - 空格可以使用字符实体替换书写，在代码书写&nbsp;

   - 换行可以使用"br"单标签进行书写

### 3、HTML常见标签

#### 	1、h系列标签

- 一共六级标签h1~h6
- 全部都是双标签，容器级标签
- 作用：给内部内容添加对应的标题的语义
- 从我们对文本的定义来讲，权重就是文本的权重，比如设置h标签的文字就赋予了标签的语义
- 如果从浏览器的角度去考虑，它的权重在搜索引擎的优化，搜索引擎的优化除了会抓取meta标签配置的keywords之外还会优先抓取标题的内容，h1标签的权重是最高的，通常一个页面只使用一个h1，通常用来制作网页的**Logo**，如果你在页面中设置多个h1标签，搜索引擎会认为你在作弊，从而降低排名

#### 	2、p标签

- 双标签，文本级标签
- 作用：添加一个完整段落的含义

#### 	3、img标签

- 单标签，文本级标签

- 作用：在指定位置插入一张图片

- img标签的属性

  - src：引入图片的路径
  - alt：图片无法加载时替换的文本
  - width：设置图片的宽度
  - height：设置图片的高度

  注：只设置宽度或者高度，另外一个属性会等比例的进行缩放

  - title：鼠标在图片上的悬停文本
  - border：给图片添加边框

  注：边框主要是通过css进行设置

#### 4、相对路径和绝对路径

##### 相对路径：从html文件出发，找到对应图片位置的路径

如果进入到某个文件使用'/',如果出某个文件夹使用'../'

引入路径

<img src="image/1.jsp" alt="">

如果文件夹内部是文件，图片在文件夹外面

<img src="../1.jsp" alt="">

如果需要出多个文件夹，则添加多个../

##### 绝对路径

盘符绝对地址和网站绝对地址

盘符绝对地址：从C盘根目录出发去查找你对应文件位置(一般不使用这种方法)

网站绝对地址：https://#$%^&*(***^%$&*)类似于这种的



#### 5、a标签

锚点<a></a>

- 双标签，文本级标签
- 作用：在指定位置添加一个超级链接，从而实现相应的跳转
- 属性：
  - href：超文本引用<a href="https//www.baidu.com">跳转到百度</a>
    -  也可以通过相对路径跳转
    - <a href="D:\Users\Tang\Desktop\Tiktok\阿阳AYANG YouTube订阅地址.html">跳转到订阅地址</a>
  - target：点击后在新标签打开链接，值为_blank
    - <a href="https//www.baidu.com" target="_blank">跳转到百度</a>
  - title：同上
  - name：<a name="你就是歌姬吧"></a>
    - 通过name命名来使用href进行定位实现页面内的跳转
    - <a href="#你就是歌姬吧">跳转到歌姬</a>

#### 6、页面锚点的使用

点击超级链接实现**页面内**的跳转

​	注：一般用于空锚点

两种使用方法

##### 方法一

设置一个空锚点，然后给空锚点设置一个name属性值和锚的href属性是一样的

- 锚：href属性后面要加"#"
  - <a href="#你就是歌姬吧">跳转到歌姬</a>
- 点：name属性设置被跳转的点
  - ```html
    <a name="你就是歌姬吧"></a>
    ```

##### 方法二

设置锚点的点标签为id属性来进行跳转

- 锚：href属性后面要加"#"
  - <a href="#你就是歌姬吧">跳转到歌姬</a>
  
- 点：使用其他标签的id属性
  
  `<h3 id="你就是歌姬吧"></h3>`

#### 7、列表

列表不是单独的，通常都是一组标签组成

##### 1、无序列表

- 定义一个没有顺序的列表结构

- 由两个标签构成

  - ul：无序列表

  - li：列表项

  - ul与li是嵌套关系

  - ```html
    <ul>
        <li>红楼梦</li>
        <li>三国演义</li>
        <li>西游记</li>
        <li>水浒传</li> 
    </ul>

注：ul内部嵌套li，它们是父子关系
    
**"ul"标签的内部必须是"li"，"li"标签内可以嵌套任何标签，甚至是"ul"**

```html
<ul>
    <li>
      <h4>西游记</h4>
      <ul>
        <li>唐僧</li>
        <li>悟空</li>
        <li>八戒</li>
        <li>悟净</li>
      </ul>
    </li>
</ul>
```

无序列表之间没有先后顺序
    
列表项之前的前缀样式是由css去控制的，目前只负责结构的搭建

##### 2、有序列表

- 定义一个有序列表的列表结构

- 两个标签组成"ol","li"

  - ol：有序列表

  - li：列表项

  - ol与li是嵌套关系

  
  ```html
  <ol>
       <li>3班 97分</li>
       <li>2班 94分</li>
       <li>4班 92分</li>
      <li>1班 89分</li>
  </ol>
  
- 注：ol内部嵌套li，它们是父子关系
  
  **"ol"标签的内部必须是"li"，"li"标签内可以嵌套任何标签，甚至是"ol"**
  
  ```html
  <ol>
     <li>
        <h4>师徒四人战力排行</h4>
        <ol>
          <li>唐僧</li>
          <li>悟空</li>
          <li>八戒</li>
          <li>悟净</li>
        </ol>
      </li>
  </ol>
  ```

##### 3、定义列表

- 定义一个标题和内容自定义的列表结构

- 三个标签组成"dl","dt","dd"

  - dl：创建一个自定义列表结构
  - dt：定义主题或者定义术语，表示一个列表的主题
  - dd：定义解释向，表示解释和说明前面的主题内容

  注：dl内部只能嵌套dt、dd，dt与dd是兄弟关系

```html
<h2>我爱你</h2>
  <dl>
    <dt>爱着你</dt>
    <dd>就像老鼠爱大米</dd>
    <dt>爱着他</dt>
    <dd>就像老鼠爱大米</dd>
    <dt>爱着我</dt>
    <dd>就像老鼠爱大米</dd>
  </dl>
```

​		注：dd里面可以嵌套多个p标签，dl、dt、dd都是配套出现，一个页面有多个dt和dd，这么进行书写的原因是更好的搭建布局

#### 8、表格

##### 	1、表格基础

- 表格由三个标签组成

  - table：定义一个表格的布局
    - table内有两个属性
      - border="1" 该属性是用来设置表格的边框，如果没有这个属性，边框不显示
      - style="border-collapse:collapse"是css样式，作用是合并表格
  - tr：定义表格的行
    - tr内可以嵌套th，用来设置表头，th自带字体加粗
  - td：定义表格的单元格

  ```html
  <table border="1" style="border-collapse:collapse" >
   <tr>
        <th>1</th>
        <th>2</th>
        <th>3</th>
        <th>4</th>
      </tr>
      <tr>
        <td>第一行，第一列</td>
        <td>第一行，第二列</td>
        <td>第一行，第三列</td>
        <td>第一行，第四列</td>
      </tr>
      <tr>
        <td>第二行，第一列</td>
        <td>第二行，第二列</td>
        <td>第二行，第三列</td>
        <td>第二行，第四列</td>
      </tr>
    </table>
  ```

##### 	2、单元格合并

一部分单元格需要进行跨行跨列合并，可以给对应的td和th标签设置相关属性

- rowspan：上下跨行合并
- colspan：左右跨列合并

属性值是数字，数字是几就代表跨几行或者几列

```html
<tr>
    <td rowspan="2">1</td>
    <td>2</td>
    <td colspan="2">3</td>
</tr>
<tr>
    <td>4</td>
    <td rowspan="2">5</td>
     <td>6</td>
</tr>
```

##### 	3、表格分区

- 一个完整的表格主要包含三个部分
  - 表格标题、表格表头、表格主题
- 一个table内部实际还有两个分区标签组成
  - caption：定义表格的主题
  - thead：定义表格的头部，内部嵌套tr>th
  - tbody：定义表格主体，内部嵌套tr>td

```html
<table border="1" style="border-collapse:collapse">
<!-- 主题分区 -->
    <caption>各地区资产投资情况</caption>
    <!-- 表头分区 -->
    <thead>
    	<tr>
        	<th rowspan="2" style="width: 100px;">地区</th>
            	<th colspan="2">按总量分</th>
                <th colspan="2">按比重分</th>
        </tr>
        <tr>
                <th>自年初统计（亿元）</th>
                <th>去年同期增长（%）</th>
                <th>自年初累计（%）</th>
                <th>自年同期（%）</th>
        </tr>
     </thead>
        <tbody>
            <tr>
                <td>全国</td>
                <td>123123</td>
                <td>41231</td>
                <td>34531</td>
                <td>234321</td>
            </tr>
        </tbody>
    </table>
```

#### 9、表单元素

##### 1、form标签

form是容器级标签，内部存放可输入的控件，如果输入的表单需要提交到数据，所有的控件需要被form表单包裹

- method：方法的意思，指的数据提交的方法，属性值是post和get
- action：是数据提交的位置



##### 2、input标签

input标签是输入框的一种，但是不仅仅只有输入框，通过type属性，可以拓展多功能

input的type属性非常丰富

###### 	1、输入框

两个重要属性：value placeholder

- value：设置默认显示的内容，属性值为自定义内容
- placeholder：如果没有value时，提示用户的文字占位符

```html
<form action="">
  <p>
    说出汝名：<input type="text" placeholder="你就是歌姬吧">
  </p>
</form>
```

###### 	2、密码框

通过type值为password设置的，显示效果为掩码形式显示

```html
<form action="">
  <p>
    说出汝名：<input type="password" placeholder="输入密码">
  </p>
</form>
```

###### 	3、单选框

通过type值为radio设置的，单选按钮都是成组出现的

如若想实现一组按钮的互斥，需要设置相同的name属性

```html
<p>
   性别：<input type="radio" name="性别" >男
         <input type="radio" name="性别" >女
         <input type="radio" name="性别" >保密
</p>
```

###### 	4、复选框

也称多选框，通过type值为checkbox设置

复选框可以对自身进行反复的点击

可以对同一组的复选框设置同一个name属性来增强阅读性

```html
<p>
   爱好：<input type="checkbox" name="hobby">运动
        <input type="checkbox"  name="hobby">跳舞
        <input type="checkbox" name="hobby">音乐
        <input type="checkbox" name="hobby">洗澡
        <input type="checkbox" name="hobby">人体研究
</p>
```

单选框和多选框都有一个默认被选中的功能，给input添加checked属性

```html
<input type="checkbox"  name="b" checked="checked">跳舞
```



有一种现象是如果点击文字是不能触发对应单选或者多选框的点击事件

这时候就需要用到label标签去扩大触发范围

```html
<label>
   input type="radio" name="性别" >保密
</label>
```



###### 5、文本域

标签是textarea

input的单行输入框只能输入单行文本

textarea标签是一个双标签，是文本级

- rows：定义文本域的可视区域有几行
- cols：当前行显示的字节数量（以英文为准），单位为数字
- placeholder：占位符

```html
<textarea rows="4s" cols="50" placeholder="自我介绍" ></textarea>
```

textarea默认是可以通过拖动在右下角实现放大或缩小文本域的，如果我们不希望缩放文本域可以通过设置style属性中的resize属性，值为none，去掉可拖拽区域

```html
<textarea rows="4s" cols="50" placeholder="自我介绍" style="resize: none;"></textarea>
```



###### 6、下拉菜单

下拉菜单需要一组标签进行制作，两个标签

select：选择，搭建下拉项

option：选项，搭建下拉项

两者的关系select>option，默认选择常规是最上面，如想要其他选项使用selected

```html
<p>
   请选择你所居住的城市
   <select>
      <option>北京</option>
      <option>上海</option>
      <option selected="selected">广州</option>
      <option>深圳</option>
   </select>
</p>
```



## 三、HTML注释

在代码中有一些特殊结构，特点是在编辑器能看到，在浏览器中看不到

这种结构叫注释，特点是浏览器中不加载

注释有两个作用

- 用来注解代码，添加合理的解释，从而实现对代码的可读性

```html
<!-- 这是在注解内容快捷键为Ctrl+/ -->
```

- 先注释掉一部分不使用的代码，便于后期恢复，多用于调试代码



## 四、HTML字符实体

在网页中普通文字部分，在键盘中是打不出来的，比如我们的版权符号，商标符号等等。还有一种场景就是替代字符，HTML会识别一部分字符



```html
<div>
   使用标签<h1>巴拉巴拉
</div>
```

浏览器会识别标签进行加载，可以使用标签实体进行转换

```html
<div>
   使用标签&lt;<h1>巴拉巴拉
</div>
```

字符实体的规定以&符号开头以;结尾

### 常用的字符实体

| 实体空格 | `&nbsp;` |
| -------- | -------- |
| 小于号   | `&lt;`   |
| 大于号   | `&gt;`   |
| 版权符号 | `&copy;` |
| 注册商标 | `&reg;`  |
| 引号     | `&quot;` |
| 和号     | `&amp;`  |

五、div和span

div和span都是常用的布局标签，俗称盒子，用于分割页面布局

- div：分割跨度大跨度

  - div是容器级标签， 双标签
  - div指的是跨度布局分割

  ```html
   <!-- 顶部 -->
      <div>
  
      </div>
  
      <!-- 中心部分 -->
      <div>
  
      </div>
  
      <!-- 底部 -->
      <div>
  
      </div>
  ```

  HTML+CSS又叫div+CSS

  div主要作用是进行网页布局的拆分，没有明确的含义

- span：小区域小跨度

  - span是文字分割

  span标签的作用是一个极限小，只适用于文字的跨度划分

  ```html
  <p>
      今天一共收入<span style="color: red;">300</span>元
  </p>
  ```

  

