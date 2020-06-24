### 米修在线实战

#### 代码

###### html主要模版

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <meta name="description" content="文本"><!--标签描述-->
    <meta name="keywords" content="文本"><!-- 关键词用于浏览器搜索 -->
    <link rel="stylesheet" href="css/font-awesome.min.css"><!-- 图标库 -->
    <link rel="stylesheet" href="css/style.css"><!-- 引入外部标签 -->
    <title>文本</title><!-- 网址顶栏显示内容 -->
</head>
<body>
 <header>
 主体
 </header>
 <section 
 <!-- 第一区块 -->
 </section>
 <section id="名称">
 <!-- 第二区块 -->
 </section>
 <footer id="main-footer">
     <!-- &copy版权声明符号 -->
 </footer>
</body>
</html>
```

###### css主要模板

```
/* reset */
*{
    padding:0;/*padding 简写属性在一个声明中设置所有内边距属性。*/
    margin:0;
    box-sizing:border-box;
    /* 浏览器样式重置，boxsizing设置后期加pading不影响布局 
https://blog.csdn.net/qq_26780317/article/details/80736514
    box-sizing:border-box容器宽度自适应的理解网址
    */
}
/* main styling */
html,body{
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;/* 字体 */
    line-height: 1.7em;/* 行高 */
}
a{/* 重置标签 */
    color:#333;
    text-decoration: none;/* ？？？？？？？清除下划线 */
}
h1,h2,h3{
    padding-bottom:20px;/* 标题样式 */
}
p{
    margin:10px 0;/* p标签样式 y轴，x轴 */
}
/* utility classes */
.container{/* 通用样式 */
    margin:0 auto;/* 水平居中 */
    max-width: 1100px;/* 最大宽度 */
    overflow: hidden;/* 防止margin塌陷以及浮动 */
    padding:0 20px;
}
.bg-dark{
    background:#444;
    color:#fff;
}/* 背景颜色常用到 放通用类里 */
.clr{
    clear:both;
}/* 清除样式 */
.l-heading{/* 字体样式 */
    font-size:40px;
    padding-top:20px;
}
/* navbar */
#navbar{/* 导航栏样式 */
    background:#333;
    color:#fff;
    overflow: auto;
}
#navbar a{
    color:#fff;/* a标签的字体颜色 */
}
/* h1，h2分布在左右两侧 */
#navbar h1{
    float:left;/* 左浮动 */
    padding-top:20px;/* 往下坐 */
}
#navbar ul{
    float:right;
    list-style: none;/* 清除样式 */
}
#navbar ul li{
    float:left;/* 添加左浮动 */
}
#navbar ul li a{
    display: block;/* 转换成块标签 */
    padding:20px;
    text-align: center;
}
#navbar ul li a:hover,/* 鼠标滑动效果 */
#navbar ul li a.current{/* 设置类的样式 */
    background:#444;
    color:#f7c08a;
}
/* showcase */
#showcase{/* 设置图片 */
    background:url('../img/01index-showcase-bg.jpg') no-repeat center center/cover;
    /* 插入背景图片 不重复 定位 全覆盖 */
    height:100%;
}
#showcase .showcase-content{/* 文本格式 */
    color:#fff;
    text-align: center;/* 文本居中 */
    padding-top:170px;/* 和顶部有距离 */
}
#showcase .showcase-content h1{/* 欢迎来到的标签样式 */
    font-size: 60px;
    line-height: 1.2em;
}
#showcase .showcase-content p{/* 设置p标签格式 */
    font-size:20px;
    line-height:1.7em;
    padding-bottom:20px;/* 使按钮与文本有距离 */
}
.btn{
    display: inline-block;/* 把行标签转化成行块标签 */
    font-size:18px;
    color:#fff;
    background:#333;
    padding:13px 20px;
    border:none;/* 清除边框 */
}
.btn:hover{
    background:#f7c08a;/* 鼠标滑过 */
}
.btn-light{
    background:#f4f4f4;
    color:#333;
}
/* home-info */
#home-info{
    height:450px;
}
#home-info .info-img{/* 区块的图片格式 ..是返回上一级*/
    float:left;
    width:50%;
    background:url('../img/02index-homeinfo-bg.jpg') no-repeat center center/cover;
    height:100%;
}
#home-info .info-content{/* 区块的文本格式 */
    float:right;
    width:50%;
    text-align: center;
    height:100%;
    padding:50px 30px;/* 上下距离 左右距离 */
    overflow: hidden;/* 超出部分隐藏 */
}
#home-info .info-content p{
    padding-bottom:30px;
}

/* features */
.box{
    float:left;/* 左浮动，让三个盒子并列一行 */
    width:33.3%;/* 平分 */
    padding:50px;/* 四周的距离 */
    text-align:center;/* 文本居中 */
}
.box i{
    margin-bottom:10px;/* 使图标和下面的文字有距离 */
}
.bg-light{
    background:#f4f4f4;/* 白色背景 */
    color:#333;
}
.bg-primary{
    background:#f7c08a;
    color:#333;
}
/* about-info */
#about-info .info-left{
    float:left;
    width:50%;
    height:100%;
}
#about-info .info-right{
    float:right;
    width:50%;
    height:100%;
}
#about-info .info-right img{
    display:block;/* 转化为块标签 */
    width:80%;
    margin:0 auto;/* 图片居中 */
    border-radius: 50%;/* 圈 */
}

/* testimonals */
#testimonials{
    height:100%;
    background:url('../img/04about-testimonals-bg.jpg') no-repeat center center/cover;
    /* 插入背景图片 */
    padding-top:100px;
}
#testimonials h2{/* 文本样式 */
    color:#fff;
    text-align: center;
    padding-bottom:40px;/* 设置距离 */
}
#testimonials .testimonial{
    padding:20px;
    margin-bottom:40px;/* 上下距离 */
    border-radius:5px;/* 圆角 */
    opacity:0.9;
}
#testimonials .testimonial img{
    width:100px;
    height:100px;
    border-radius:50%;
    float:left;
    margin-right:20px;
}
/* contact-form */
#contact-form .form-group{
    margin-bottom:20px;
}
#contact-form label{
    display: block;/* 块标签 */
    margin-bottom:5px;
}
#contact-form input,
#contact-form textarea{
    width:100%;
    padding:10px;
    border:1px #ddd solid;
}/* 同时设置，一样的属性 */
#contact-form textarea{
    height:200px;
}
#contact-form input:focus,/* 点击边框变色 */
#contact-form textarea:focus{
    outline:none;/* 清除自带边框 */
    border-color:#f7c08a;
}
/* footer */
#main-footer{
    text-align:center;
    background:#333;
    color:#fff;
    padding:20px;
}
```





###### 常用代码格式功能

```

<nav id="标签"><!-- 导航栏标签 -->
</nav>


<h1><a href="index.html">文本</a></h1><!-- a标签进行页面跳转 -->


<ul><!-- 页面切换用ul包裹 -->
   <li><a class=" 类名" href="跳转页面">首页</a></li><!-- 跳转路径，设置一个类current设置默认选中 -->
   <li><a href="跳转页面">显示文本</a></li>
   <li><a href="跳转页面">联系我们</a></li>
</ul>



<div class="可设第一个样式">
     <h1>文本1<span class="类名"> 文本2</span></h1><!-- 给一个span标签用于设置文本2样式 类名可以通用-->


<a class="格式" href="about.html">文本</a><!-- 链接跳转 及文本格式--><!-- 设置按钮样式 先设类btn -->


<section id="块里有图标">
     <div class="box 样式"><!-- 字体图标 box 课设多个盒子可设置浮动 样式块可设置盒子样式-->
       <i class="fa fa-users fa-3x"></i> <!-- 网址上的图标代码 -->
        <!-- 文本内容 -->
     </div>   
</section>
 
 
<div class="form-group">
        <label for="message">反馈内容</label>
        <textarea type="text" name="message" id="message"></textarea>
</div><!-- 可填写文本框 -->


<button type="submit" class="btn">提交</button>



```

​     



###### input和textarea的区别

1. input是一个单行输入框，有value属性（value属性指定初始值），但是它不能自动换行；用来放置字数较少的单行文字内容

2. textarea是一个多行输入框，没有value属性，但是它能自动换行；一般让用户可以输入多行文字,输入的文字信息量相比较大

###### display属性block、inline、inline-block的区别

1. display:block就是将元素显示为块级元素，一般是其他元素的容器，可容纳其他块级元素和内联元素，块级元素排斥与其他元素位于同一行，宽度(width)和高度(height)起作用，常见的块级元素有div和p.

2. display:inline就是将元素显示我内联元素，内联元素只能容纳文本或其他内联元素，它允许内联元素与其位于同一行，宽度和高度不起作用，常见的内联元素有a.

3. display:inline-block将对象呈递为内联对象，但是对象的内容作为块对象呈递。旁边的内联对象会被呈递在同一行内，允许空格。(准确地说，应用此特性的元素呈现为内联对象，周围元素保持在同一行，但可以设置宽度和高度地块元素的属性。

###### pading和margin

- margin：外边距；设置对象四边的外延边距。
  1. margin: 20rpx 10rpx 25rpx 10rpx ：如果提供全部四个参数值，将按上、右、下、左的顺序作用于四边。
  2. margin：20rpx：如果只提供一个，将用于全部的四边。
  3. margin：20rpx 20rpx：如果提供两个，第一个用于上、下，第二个用于左、右。
  4. margin：20rpx 20rpx 10rpx：如果提供三个，第一个用于上，第二个用于左、右，第三个用于下。
  5. 某些相邻的margin会发生合并，称之为margin折叠，具体的现象就如果两个块级元素都设置了margin，那取两者之间的最大值做为两个元素的外边距。
  6. 注意：margin折叠常规认知：
  7. margin折叠只发生在块级元素上；
  8. 浮动元素的margin不与任何margin发生折叠；
  9. 设置了属性overflow且值不为visible的块级元素，将不与它的子元素发生margin折叠；
  10. 绝对定位元素的margin不与任何margin发生折叠；
  11. 根元素的margin不与其它任何margin发生折叠.
- padding：内边距：设置对象四边的内部边距。
  1. padding: 20rpx 10rpx 25rpx 10rpx ：如果提供全部四个参数值，将按上、右、下、左的顺序作用于四边。
  2. padding：20rpx：如果只提供一个，将用于全部的四边。
  3. padding：20rpx 20rpx：如果提供两个，第一个用于上、下，第二个用于左、右。
  4. padding：20rpx 20rpx 10rpx：如果提供三个，第一个用于上，第二个用于左、右，第三个用于下。
- margin-top，margin-right，margin-bottom，margin-left对应的分别是上右下左外边的距离，可取值：auto／数值／百分比。
- padding-top，padding-right，padding-bottom，padding-left对应的分别是上右下左内边的距离，可取值：auto／数值／百分比。




#### 步骤

##### 创建及导航栏样式

1. 创建文件夹，创建三个html页面，创建一个css文件夹，创一个css文件。

2. 在主页index加声明。

3. header里建nav标签，完成页面跳转。(<nav> 标签定义导航链接的部分。)

   ![](F:\photo\笔记图片\1.PNG)

   未添加css样式，为纯文本。

4. 添加style.css的样式

   - 重置浏览器
   - 设置主体文本格式
   - 重置a标签
   - 设置container的通用格式
   - 设置导航栏样式

   ![](F:\photo\笔记图片\2.PNG)本身样式

   ![](F:\photo\笔记图片\3.PNG)

   - 设置h1标签位置导航栏字体样式
   - 设置三个块的样式

   ![4](F:\photo\笔记图片\4.PNG)本来样式

   ![5](F:\photo\笔记图片\5.PNG)

   - 设置选中字后颜色改变
   - 首页默认选定

   ![6](F:\photo\笔记图片\6.PNG)

##### 首页展示及介绍

1. 建一个div块用于展示文本内容，要用上通用格式防止塌陷变形。

![7](F:\photo\笔记图片\7.PNG)

2. 插入图片 在css文件里插入showcase，图片位置一般用/，不要用\

![8](F:\photo\笔记图片\8.PNG)

3. 设置首页文本内容格式

![9](F:\photo\笔记图片\9.PNG)

4. 设置欢迎来到的标签样式

![10](F:\photo\笔记图片\10.PNG)

5. 设置米修在线的标签样式

![11](F:\photo\笔记图片\11.PNG)

**问题：区分. 和# 优先级**----id用# class用.

6. 设置英文文本格式 p标签格式

![12](F:\photo\笔记图片\12.PNG)

7. 设置关于我们的按钮样式，加类btn，设置鼠标滑动的样式

![13](F:\photo\笔记图片\13.PNG)

**疑问？哪一行代码使出现了按钮样式**------------------------------------------

8. 设置头标签下的区块，用section，设置阅读更多按钮

![14](F:\photo\笔记图片\14.PNG)

9. 设置区块的图片格式，文本格式

![15](F:\photo\笔记图片\15.PNG)

**？100%是相对谁 什么时候用id 什么时候用class** ------------------------

10. 设置背景颜色

![16](F:\photo\笔记图片\16.PNG)

**？距离的参照线一般是什么**-------------------------------------------------------

11. 设置阅读更多的按钮位置，与文本距离

![17](F:\photo\笔记图片\17.PNG)

12. 设置btn-light 鼠标滑过阅读更多的样式

##### 字体图标及底部制作

1. 先在font网址里找图标，重点是head里引用库，把css图标库文件拉到文件夹里，然后复制网页代码至底部区域块里。

![18](F:\photo\笔记图片\18.PNG)

2. 设三个图标及文本内容，设置盒子并排显示。

![19](F:\photo\笔记图片\19.PNG)

3. 添加三个块的背景颜色

**为什么不能用按钮的背景色要重新设类**---------------------------------------![](F:\photo\笔记图片\20.PNG)

4. 设置版权声明，底部标签

![21](F:\photo\笔记图片\21.PNG)

**清除格式的作用不是很懂**----------------------------------------------------------

##### 关于我们制作

1. 先复制粘贴，把不需要的删了。
2. 继续用contrain格式
3. 建两个类，左右两个板块

![22](F:\photo\笔记图片\22.PNG)

3. 调整板块位置
4. 插入学员信息，两条，背景图片

##### 联系我们制作

F:\xiaomixiu\ms-mywebsite-lesson-7