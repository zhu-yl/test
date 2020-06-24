# HTML

### 文档类声明

```
<!DOCTYPE html>:
```

### 基本格式

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>...</title>
</head>
<body>

页面展示

</body>

</html>
```

### 注释

```
<!--注释文字-->
```

### 段落

```
<p></p>
```

### 标签

```
span{

}

<span>文本</span>span>
```

### 块

```
<div></div>自定义块
```

### 头部标签

```
<head></head>
```

### 底部标签

```
<footer></footer>
```

### 侧边栏

```
<aside></aside>
```

### 区域 专栏

```
<section></section>
```

### 换行

```
<br/>
```

### 空格

```
&nbsp;
```

### 分隔线

```
<hr/>分隔线
```

### 无序列表

```
<ul>
    <li>  </li>
    <li>  </li>
</ul>
// 每个li前一个
```

### 有序列表

```
<ol>
    <li> </li>
    <li> </li>
</ol>
显示为1. 2.
```

### 插入图片

```
<img src="图片地址" alt="下载失败时的替换文本" title="提示文本">

```

### 超链接

```
<a href="目标网址"> title="鼠标滑过显示文本">
链接显示文本</a>
```

### 插入网址

```
<a href="目标网址" target="_self"> 文字一</a>
<a href="目标网址2" target="_blank"> 文字二</a>zaixinxh
_self为在当前页面打开   _blank在新窗口打开
```

### 行列

```
<table boeder="1">
   <caption> 标题</caption>
   <tr>行
      <th>  </th>列一
      <th>  </th>列二
   </tr>   第一行
   <tr>
       同上
   </tr>   第二行
</table>
```

### 优先载入

```
<thead><tbody><tfooter></tbody>
```

加上tbody加载完优先显示

### 数据传送

```
<form   method="传送方式"   action="服务器文件">
```

method ：数据传送的方式（get/post）

eg:

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>表单标签</title>
</head>
<body>
 <form method="post" action="save.php">
        <label for="username">用户名:</label>
        <input type="text" name="username" id="username" value="" />
        <label for="pass">密码:</label>
        <input type="password" name="pass" id="pass" value="" />
        <input type="submit" value="确定" name="submit" />
        <input type="reset" value="重置" name="reset" />
    </form>
</body>

</html>
```

### 输入框

```
<form>
   <input type="text/password" name="名称" value="文本" />
</form>
```

1. type
     当type="text"时，输入框为文本输入框;
     当type="password"时,输入框为密码输入框。
2. name：为文本框命名，以备后台程序ASP 、PHP使用
3. value：为文本输入框设置默认值。(一般起到提示作用)

```
eg:

<!DOCTYPE html>
<html>


<head>
    <meta charset="UTF-8">
    <title>文本输入框、密码输入框</title>
</head>

<body>

    <form method="post" action="save.php">
        账户:
        <input type="text" name="myname"/>
        <br>
        密码:
        <input type="password" name="pass"/>
    </form>

</body>

</html>
```

### 输入框占位符

```
placeholder
```

```
eg：

<!DOCTYPE html>
<html>


<head>
    <meta charset="UTF-8">
    <title>input-placeholder</title>
</head>


<body>
    <input type="text" placeholder="请输入用户名">
    <input type="password" placeholder="请输入密码">
</body>

</html>
```

### 数字输入框

input的type属性设置为number

```
eg：

<!DOCTYPE html>
<html>


<head>
    <meta charset="UTF-8">
    <title>input-number</title>
</head>


<body>
    <input type="number">
</body>

</html>
```

### 网址输入框

input的type属性设置为url。

```
eg：

<!DOCTYPE html>
<html>


<head>
    <meta charset="UTF-8">
    <title>input-url</title>
</head>

<body>
    <input type="url">
</body>

</html>
```

### 邮箱输入框

Input的type属性设置为email

```
<input type="email">
```

### 意见框，文本框。

```
<textarea  rows="行数" cols="列数">文本</textarea>

<body>

    <form>
        <textarea cols="50" rows="10">在这里输入内容...</textarea>
    </form>

</body>
```

col可用width、row可用height来代替。

### 标签

```
<label for="控件id名称">
```

```
eg：

<!DOCTYPE html>
<html>


<head>
    <meta charset="UTF-8">
    <title>label</title>
</head>

<body>

    <form>
        <label for="uname">输入你的用户名</label>
        <input type="text" id="uname" placeholder="Enter uname">
        <br>
        <label for="pass">输入你的密码</label>
        <input type="password" id="pass" placeholder="Enter password">
    </form>

</body>

</html>
```

### 单选框复选框 

```
<input   type="radio/checkbox"   value="值"    name="名称"   checked="checked"/>
```

 当 type="radio" 时，控件为单选框

 当 type="checkbox" 时，控件为复选框

当设置 checked="checked" 时，该选项被默认选中

```
eg：

<!DOCTYPE html>
<html>


<head>
    <meta charset="UTF-8">
    <title>单选框、复选框</title>
</head>


<body>

    <form action="save.php" method="post">
        <label>性别:</label>
        <label>男</label>
        <input type="checkbox" value="1" name="gender-man" checked="checked"/>
        <label>女</label>
        <input type="checkbox" value="2" name="gender-woman" />
    </form>

</body>

</html>
```

### 创建下拉菜单

select和option标签。

selected="selected"：

设置selected="selected"属性，则该选项就被默认选中。

在浏览器中显示的结果：![](F:\photo\笔记图片\微信图片_20200605105024.png)

```
eg：

<!DOCTYPE html>
<html>


<head>
    <meta charset="UTF-8">
    <title>select下拉框</title>
</head>


<body>

    <form>
        <select>
            <option value="看书">看书</option>
            <option value="旅游" selected="selected">旅游</option>
            <option value="运动">运动</option>
            <option value="购物">购物</option>
        </select>
    </form>

</body>

</html>
```

### 提交按钮

```
 <input   type="submit"   value="提交">
```

只有当type值设置为submit时，按钮才有提交作用

```
eg：

<!DOCTYPE html>
<html>


<head>
    <meta charset="UTF-8">
    <title>提交按钮</title>
</head>


<body>

    <form method="post" action="save.php">
        <label for="myName">姓名：</label>
        <input type="text" value=" " name="myName " />
        <input type="submit" value="提交" name="submitBtn" />
    </form>

</body>

</html>
```

### 重置按钮

```
<input type="reset" value="重置">
```

只有当type值设置为reset时，按钮才有重置作用

# CSS

### 样式

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>认识CSS样式</title>
    <style type="text/css">
    p {
        font-size: 12px;
        /*设置文字字号*/
        color: red;
        /*设置文字颜色*/
        font-weight: bold;
        /*设置字体加粗*/
    }
    </style>
</head>

<body>

    <p>慕课网，超酷的互联网、IT技术免费学习平台，创新的网络一站式学习、实践体验；服务及时贴心，内容专业、有趣易学。专注服务互联网工程师快速成为技术高手！</p>

</body>

</html>
```

### span 标签

head和body里


```
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>CSS样式的优势</title>
    <style type="text/css">
    span {
        color: blue;
    }
    </style>
</head>

<body>
<p>慕课网，<span>超酷的互联网</span>、IT技术免费学习平台，创新的网络一站式学习、实践体验；<span>服务及时贴心</span>，内容专业、<span>有趣易学</span>。专注服务互联网工程师快速成为技术高手</p>
</body> 
</html>
```

### 属性，值

   ```
p{font-size:12px;color:red;}
   ```

   eg:

    <style type="text/css">
       p {
           font-size: 12px;
           color: red;
           font-weight: bold;
       }
       </style>

### 注释

   CSS中也有注释语句：用`/*注释语句*/`来标明

```
（Html中使用`<!--注释语句-->`)。
```

### 内联式

   ```
<p style="color:red;font-size:12px">这里文字是红色。</p>
   ```

   eg：

   ```
   <body>
       <p>慕课网，<span style="color:blue">超酷的互联网</span>、IT技术免费学习平台，创新的网络一站式学习、实践体验；<span>服务及时贴心</span>，内容专业、<span>有趣易学</span>。专注服务互联网工程师快速成为技术高手！</p>
   </body>
   ```

###    多个嵌入

   ```
   <style type="text/css">
   span{
   color:red;
   }
   </style>
   ```

   嵌入式css样式必须写在<style></style>之间，并且一般情况下嵌入式css样式写在<head></head>之间。

### 外部式

   ```
   <link href="base.css" rel="stylesheet" type="text/css" />
   ```

   另开一个base.css文件，在这个文件里设置属性改变主程序。

```
eg：

   span{
      color:red;
     font-size:20px;
   }
```

### 优先级

内联式 > 嵌入式 > 外部式

但是嵌入式>外部式有一个前提：嵌入式css样式的位置一定在外部式的后面。

总结来说，就是就近原则（离被设置元素越近优先级别越高）。

### 标签样式，设置属性

   ```
p{font-size:12px;line-height:1.6em;}
   ```

   一般放head里

### 类选择器

   看.

   ```
   stress {
              color: red;
          }
          .a {
              color: green;
          }
   ```

   ```
   <span class="stress">
   ```

   eg：

   ```
   
   
      <!DOCTYPE html>
      <html>
   
   
      <head>
          <meta charset="UTF-8">
          <title>认识html标签</title>
          <style type="text/css">
          .stress {
              color: red;
          }
          .a {
              color: green;
          }
          </style>
   
      </head>
   
      <body>
   
          <h1>勇气</h1>
          <p>三年级时，我还是一个<span class="stress">胆小如鼠</span>的小女孩，上课从来不敢回答老师提出的问题，生怕回答错了老师会批评我。就一直没有这个<span class="stress">勇气</span>来回答老师提出的问题。学校举办的活动我也没勇气参加。</p>
          <p>到了三年级下学期时，我们班上了一节<span class="a">公开课</span>，老师提出了一个很简单的问题，班里很多同学都举手了，甚至成绩比我差很多的，也举手了，还说着："我来，我来。"我环顾了四周，就我没有举手。</p>
          <img src="http://img.mukewang.com/52b4113500018cf102000200.jpg">
      </body>
      </html>
   ```

### id选择器

   ```
   #stress {
           color: red;
       }
   ```

   在style里面

   ```
   <span id="stress">胆小如鼠</span>
   ```

   在body里面，与class用法类似，改成#。

###  类与id区别

   可以使用类选择器词列表方法为一个元素同时设置多个样式。我们可以为一个元素同时设多个样式，但只可以用类选择器的方法实现，ID选择器是不可以的。

   ```
      .stress{
          color:red;
      }
      .bigsize{
          font-size:25px;
      }
   
      <p>到了<span class="stress bigsize">三年级</span>下学期时，我们班上了一节公开课...</p>
   
   
   ```

   ID选择器只能在文档中使用一次，而类选择器可以使用多次。

### 子选择器

   ```
   .food>li{border:1px solid red;}
   ```

   这里的food只是一个例子，这个自己设置。对food里的文本加红框。在body里选择出来，如span。

### 后代选择器

   子选择器（child selector）仅是指它的直接后代，或者你可以理解为作用于子元素的第一代后代。而后代选择器是作用于所有子后代元素。后代选择器通过空格来进行选择，而子选择器是通过“>”进行选择。

   总结：**>**作用于元素的第一代后代，空格作用于元素的所有后代。

   eg：对后续所有span作用。

   ```
   .first  span{color:red;}
   ```

### 通用选择器

   ```
   * {color:red;}
   ```

   对所有标签起作用。

### 伪类选择器 

鼠标滑过的状态

   ```
   a:hover{color:red;}
   ```

   a为标签，自己定义，如span。

###  分组选择器

（,）

   ```
   h1,span{color:red;}
   =
   h1{color:red;}
   span{color:red;}
   ```

### 优先级

   选择器的优先级依次是: 内联样式 > id选择器 > 类选择器 > 标签选择器 > 通配符选择器

### 权值，优先等级

   ```
   p{color:red;} /*权值为1*/
   p span{color:green;} /*权值为1+1=2*/
   .warning{color:white;} /*权值为10*/
   p span.warning{color:purple;} /*权值为1+1+10=12*/
   #footer .note p{color:yellow;} /*权值为100+10+1=111*/
   ```

### 选择器最高层级

   !important要写在分号的前面

   ```
   p{color:red!important;}
   ```

### 样式

设置字体，大小，粗体，字体样式，颜色

   ```
   body{font-family:"宋体";}
   
   .stress{font-size:12px;}
   
   p span{font-weight:bold;}
   
   p{font-style:italic;}
   
   p{color:red;}
   p{color:rgb(133,45,200);}
   p{color:rgb(20%,33%,25%);}
   p{color:#00ffff;}
   ```

   body，怕，span等

   正常字体为normal,也是font-style的默认值。

   italic为设置字体为斜体，用于字体本身就有倾斜的样式。

   oblique为设置倾斜的字体，强制将字体倾斜。

### font简写

   ```
   body{
       font-style:italic;
       font-weight:bold; 
       font-size:12px; 
       line-height:1.5em; 
       font-family:"宋体",sans-serif;
   }
   
   =
   
   body{
       font:italic  bold  12px/1.5em  "宋体",sans-serif;
   }
   ```

   使用这一简写方式你至少要指定 font-size 和 font-family 属性，在缩写时 font-size 与 line-height 中间要加入“/”斜扛。

### 元素分类

常用的块状元素有：常常一行

```
<div>、<p>、<h1>...<h6>、<ol>、<ul>、<dl>、<table>、<address>、<blockquote> 、<form>
```

常用的内联元素有：从左到右排列

   ```
   <a>、<span>、<br>、<i>、<em>、<strong>、<label>、<q>、<var>、<cite>、<code>
   ```

 让块状元素并排显示，用浮动模型

   eg：

   ```
   div{
       width:200px;
       height:200px;
       border:2px red solid;
       float:left/right;
   }
   <div id="div1"></div>
   <div id="div2"></div>
   /*一左一右分两排定义
       #div1{float:left;}
   #div2{float:right;}*/
   ```

   也可用flex，从左到右无间隔并排显示

- a左对齐 右对齐 居中 你 （中间有间隔相等）  每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。

```css
justify-content: flex-start | flex-end | center | space-between | space-around;
```

- b上左对齐 下左对齐 居中左对齐（竖轴）项目的第一行文字的基线对齐  竖轴占满左对齐

```
align-items: flex-start | flex-end | center | baseline | stretch;
```

eg

```
.box {
        background: blue;
        display: flex;
        justify-content: flex-start;/*a*/
        align-items: flex-start;/*b*/
        
    }
    
    /*占比对齐，按1：3：2上对齐*/
    .box1 {
        flex: 1;
        background: red;
    }

    .box2 {
        flex: 3;
        background: orange;
    }

    .box3 {
        flex: 2;
        background: green;
    }
    </style>
```

常用的内联块状元素有：

```
   <img>、<input>
```

### 块元素

```
<div>、 <p>、<h1>、<form>、<ul> 和 <li>就是块级元素。设置display:block就是将元素显示为块级元素。
```

   ```
   a{display:block;}
   ```

### 内联元素

```
<span>、<a>、<label>、 <strong> 和<em>就是典型的内联元素（行内元素）（inline）元素。当然块状元素也可以通过代码display:inline
```

   ```
    div{
        display:inline;
    }
   
   ......
   
   <div>我要变成内联元素</div>
   ```

   和其他元素都在一行上；

   元素的高度、宽度及顶部和和其他元素都在一行上；

   元素的高度、宽度及顶部和底部边距不可设置；

   元素的宽度就是它包含的文字或图片的宽度，不可改变。

### 内联块状元素

```
display:inline-block
```

   inline-block 元素特点：

-    和其他元素都在一行上；
-    元素的高度、宽度、行高以及顶和底边距都可设置

   eg：a常规为内联元素，不可设置宽高。加上代码可设置

   ```
   a {
           display:inline-block;
           width: 20px;
           /*在默认情况下宽度不起作用*/
           height: 20px;
           /*在默认情况下高度不起作用*/
           background: pink;
           /*设置背景颜色为粉色*/
           text-align: center;
           /*设置文本居中显示*/
       }
   ```

### 设置不显示

   ```
   p {
           display: none;
       }
   ```

### 文本格式

   1、text-decoration可以设置添加到文本的修饰。

   2、text-decoration默认值为none, 定义标准的文本。

   3、text-decoration的值为underline为定义文本下的一条线。

   4、text-decoration的值为overline为定义文本上的一条线。

   5、text-decoration的值为line-through为定义穿过文本下的一条线，一般用于商品折扣价。

   6、首行缩进两字符。p{text-indent:2em;}

   7、行间距。p{line-height:1.5em;}

   8、中文字符字母间隔。

   ```
   h1{
       letter-spacing:50px;
   }
   ```

   9、单词间距。

   ```
   h1{
       word-spacing:50px;
   }
   ```

   10、排列方式，左对齐右对齐居中

   ```
   h1{
       text-align:center/left/right;
   }
   ```

### 长宽高填充

   ```
   div{
       width:200px;
       padding:20px;
       border:1px solid red;
       margin:10px;    
   }
   ```

   ![](F:\photo\笔记图片\微信图片_20200605173743.bmp)

   背景色div{background-color:red;}

###    盒子样式

   dashed（虚线）| dotted（点线）| solid（实线）。

   border-width（边框宽度）中的宽度也可以设置为：

   thin | medium | thick（但不是很常用），最常还是用像素（px）。

   ```
   div{
       border:2px  solid  red;
   }
   =
   div{
       border-width:2px;
       border-style:solid;
       border-color:red;
   }
   ```

   边框设置圆角，也可以详写。

   ```
    div{border-radius: 20px 10px 15px 30px;}
   ```

   自定义内、外边距上右下左

   ```
   div{padding:20px 10px 15px 30px;}
   div{margin:20px 10px 15px 30px;}
   ```

###  定位

层模型定位，浏览窗口位置。

-    绝对定位position:absolute;
-    相对定位position:relative;
-    固定定位position:fixed;

   ```
   div{
       width:200px;
       height:200px;
       border:2px red solid;
       position:absolute;
       left:100px;
       top:50px;
   }
   <div id="div1"></div>
   ```

   组合定位

-    参照定位的元素必须是相对定位元素的前辈元素：

   ```
   <div id="box1"><!--参照定位的元素-->
       <div id="box2">相对参照元素进行定位</div><!--相对定位元素-->
   </div>
   ```

   从上面代码可以看出box1是box2的父元素（父元素当然也是前辈元素了）。

-    参照定位的元素必须加入position:relative;

   ```
   #box1{
       width:200px;
       height:200px;
       position:relative;        
   }
   ```

-    定位元素加入position:absolute，便可以使用top、bottom、left、right来进行偏移定位了。

   ```
   #box2{
       position:absolute;
       top:20px;
       left:30px;         
   }
   ```

   这样box2就可以相对于父元素box1定位了（这里注意参照物就可以不是浏览器了，而可以自由设置了）。

### 文本内容显示

文本内容居中显示text-align:center（行内元素）

```

<style>
div{
    border:1px solid red;
    margin:20px;
}
.txtCenter{
	text-align:center;
}


</style>
</head>

<body>

<div class="txtCenter">我想要在父容器中水平居中显示。</div>

</body>
</html>
```

文本定宽块状元素居中显示 放div style里

```
margin-left:auto;
margin-right:auto;
```

   已知宽高盒子垂直居中![](F:\photo\笔记图片\微信图片_20200607171005.png)

宽高不定盒子水平居中

```
.box {
        border: 1px solid #00ee00;
        height: 300px;
        position: relative;

    }

    .box1 {
        border: 1px solid red;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
```











