

# js

## 基础

### 准备

#### 1.在html中插入js

```
<head>
        <meta http-equiv="Content-Type" content="text/html; charset=gb18030">
        <title>插入js代码</title>
        <script type="text/javascript">
        <!--插入代码-->
        document.write("开启JS之旅!");
    </script>
     <!--插入代码-->
    </head>

```

#### 2.引用js外部文件

```
<head>
<script src="script.js"></script>
<!--调用外部js，然后在script.js直接写js代码-->
</head>
```

#### 3.js的位置

```
<head>
<title>JS代码的位置</title>
<script type="text/javascript">
 document.write("I love");
</script>
</head>
<body>
<script type="text/javascript">
 document.write("javascript");
 <!--我们一般放在网页的head或者body部分。html时是按先后顺序的，所以前面的script就先被执行。-->
</script>
</body>
```

#### 4.js格式

语句;

```
<script type="text/javascript">
   document.write("I");
   document.write("love");
   document.write("JavaScript");
</script>
```

#### 5.注释

```
// 我是单行注释，该语句功能在网页中输出内容
 /*
    多行注释
    养成书写注释的良好习惯
   */
```

#### 6.变量

变量命名规则

1. 变量必须使用字母、下划线(_)或者美元符($)开始。

2. 然后可以使用任意多个英文字母、数字、下划线(_)或者美元符($)组成。

3. 不能使用JavaScript关键词与JavaScript保留字。

先声明再赋值，可以重复赋值（区分大小写）

```
var mychar;
mychar="javascript";
mychar="hello";
```

#### 7.判断语句

```
<script type="text/javascript">
   var myage = 18;
   if(myage>=18)  //myage>=18是判断条件
   { document.write("你是成年人。");}
   else  //否则年龄小于18
   { document.write("未满18岁，你不是成年人。");}
</script>
```

#### 8.函数

```
function add2(){
   var sum = 3 + 2;
   alert(sum);
}
```

调用函数

```
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>函数调用</title>
   <script type="text/javascript">
      function contxt() //定义函数
      {
         alert("哈哈，调用函数了!");
      }
   </script>
</head>
<body>
   <form>
      <input type="button"  value="点击我" onclick="    contxt()" />  
   </form>
</body>
</html>
```

### 互动

#### 1.输出

- ```
  <script type="text/javascript">
    document.write("I love JavaScript！"); //内容用""括起来，""里的内容直接输出。
  </script>
  ```

- ```
  <script type="text/javascript">
    var mystr="hello world!";
    document.write(mystr);  //直接写变量名，输出变量存储的内容。
  </script>
  ```

- ```
  <script type="text/javascript">
    var mystr="hello";
    document.write(mystr+"I love JavaScript"); //多项内容之间用+号连接
  </script>
  ```

- ```
  <script type="text/javascript">
    var mystr="hello";
  document.write(mystr+"<br>");//输出hello后，输出一个换行符
    document.write("JavaScript");
  </script>
  ```

#### 2.警告

先跳出hello，点确定，再跳出30。

```
<script type="text/javascript">
   var mynum = 30;
   alert("hello!");
   alert(mynum);
</script>
```

#### 3.消息对话框confirm

```
<script type="text/javascript">
    var mymessage=confirm("你喜欢JavaScript吗?");
    if(mymessage==true)
    {   document.write("很好,加油!");   }
    else
    {  document.write("JS功能强大，要学习噢!");   }
</script>
```

#### 4.提问回答，prompt消息对话框

```
var myname=prompt("请输入你的姓名:");
if(myname!=null)
  {   alert("你好"+myname); }
else
  {  alert("你好 my friend.");  }
```

#### 5.新窗口

```
window.open([URL], [窗口名称], [参数字符串])
```

窗口名称：可选参数，被打开窗口的名称。
    1.该名称由字母、数字和下划线字符组成。
    2."_top"、"_blank"、"_self"具有特殊意义的名称。
       _blank：在新窗口显示目标网页
       _self：在当前窗口显示目标网页
       _top：框架网页中在上部窗口中显示目标网页
    3.相同 name 的窗口只能创建一个，要想创建多个窗口则 name 不能相同。
   4.name 不能包含有空格。

```
<script type="text/javascript"> window.open('http://www.imooc.com','_blank','width=300,height=200,menubar=no,toolbar=no, status=no,scrollbars=yes')
</script>
```

![](F:\photo\笔记图片\微信图片_20200608153928.jpg)

#### 6.关闭窗口

```
window.close();//关闭本窗口
<窗口对象>.close();   //关闭指定的窗口
eg：
<script type="text/javascript">
   var mywin=window.open('http://www.imooc.com'); //将新打的窗口对象，存储在变量mywin中
   mywin.close();
</script>
<!--本例子打开窗口同时关闭窗口-->
```

### 控制

#### 1.dom

<u>理解不深</u>

#### 2.用id获取元素

```
document.getElementById("id") 
```

例子为什么是结果:[object HTMLParagraphElement]不知道
eg：

```
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>document.getElementById</title>
</head>
<body>
<p id="con">JavaScript</p>
<script type="text/javascript">
  var mychar=  document.getElementById("con")         ;
  document.write("结果:"+mychar); //输出获取的P标签。 
</script>
</body>
</html>
```

#### 3.获取或替换

```
Object.innerHTML
```

eg：

```
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>innerHTML</title>
</head>
<body>
<h2 id="con">javascript</H2>
<p> JavaScript是一种基于对象、事件驱动的简单脚本语言，嵌入在HTML文档中，由浏览器负责解释和执行，在网页上产生动态的显示效果并实现与用户交互功能。</p>
<script type="text/javascript">
  var mychar=  document.getElementById("con")        ;
  document.write("原标题:"+mychar.innerHTML+"<br>"); //输出原h2标签内容
  mychar.innerHTML="Hello world!";
  document.write("修改后的标题:"+mychar.innerHTML); //输出修改后h2标签内容
</script>
</body>
</html>
```

#### 4.改变html样式

![](F:\photo\笔记图片\微信图片_20200608164421.jpg)

```
mychar.style.color="red";
   mychar.style.backgroundColor ="#CCC";
    mychar.style.width="300px";
```

#### 5.显示和隐藏

```
Object.style.display = value
```



```
function hidetext()  
		{  
		var mychar = document.getElementById("con");
        mychar.style.display = "none"
		}  
		function showtext()  
		{  
		var mychar = document.getElementById("con");
        mychar.style.display = "block"
		}
```

#### 6.控制类名

```
object.className = classname
```

### 练习

<u>取消设置未成功</u>

```
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" Content="text/html; charset=utf-8" />
<title>javascript</title>
<style type="text/css">
body{font-size:12px;}
#txt{
    height:400px;
    width:600px;
	border:#333 solid 1px;
	padding:5px;}
p{
	line-height:18px;
	text-indent:2em;}
</style>
</head>
<body>
  <h2 id="con">JavaScript课程</H2>
  <div id="txt"> 
     <h5>JavaScript为网页添加动态效果并实现与用户交互的功能。</h5>
        <p>1. JavaScript入门篇，让不懂JS的你，快速了解JS。</p>
        <p>2. JavaScript进阶篇，让你掌握JS的基础语法、函数、数组、事件、内置对象、BOM浏览器、DOM操作。</p>
        <p>3. 学完以上两门基础课后，在深入学习JavaScript的变量作用域、事件、对象、运动、cookie、正则表达式、ajax等课程。</p>
  </div>
  <form>
  <!--当点击相应按钮，执行相应操作，为按钮添加相应事件-->
    <input type="button" value="改变颜色" onClick="color()">  
    <input type="button" value="改变宽高" onClick="wihi()">
    <input type="button" value="隐藏内容" onClick="hide()">
    <input type="button" value="显示内容" onClick="display()">
    <input type="button" value="取消设置" onClick="cancle()">
  </form>
  <script type="text/javascript">
  var mydiv = document.getElementById("txt");
//定义"改变颜色"的函数
function color(){
mydiv.style.color="red";
mydiv.style.backgroundColor="#ccc";    
}
//定义"改变宽高"的函数
function wihi(){
mydiv.style.width="200px";
mydiv.style.height="300px";    
}
//定义"隐藏内容"的函数
function hide(){
mydiv.style.display="none";
}
//定义"显示内容"的函数
function display(){
mydiv.style.display="block";
}

//定义"取消设置"的函数
function cancle(){
var mymessage=confirm("是否取消");
    if(mymessage==true)
    {    mydiv.removeAttribute("style");  }
    else
    {  alert("再见！")；}
}
  </script>
</body>
</html>
```

能打开网址，但网址进不去

```
<!DOCTYPE html>
<html>
 <head>
  <title> new document </title>  
  <meta http-equiv="Content-Type" content="text/html; charset=gbk"/>   
  <script type="text/javascript">  
    function openWindow(){
    var mymessage=confirm("是否打开?");
    if(mymessage==true)
    {var myname=prompt("请输入网址:","http：//www.baidu.com/"); 
      if(myname!=null)
        {  window.open(myname,'_blank','width=400,height=500')}
      else
        {  alert("再见");  }
    }
    else
    {  alert("再见")  }}
    // 新窗口打开时弹出确认框，是否打开

    // 通过输入对话框，确定打开的网址，默认为 http：//www.imooc.com/

    //打开的窗口要求，宽400像素，高500像素，无菜单栏、无工具栏。
    
  </script> 
 </head> 
 <body> 
	  <input type="button" value="新窗口打开网站" onclick="openWindow()" /> 
 </body>
</html>
```

## 进阶

### 语法

#### 1.变量命名

必须以字母、下划线或美元符号开头，后面可以跟字母、下划线、美元符号和数字。

```
    mysum            
    _mychar         
    $numa1 
```

不允许使用JavaScript关键字和保留字做变量名。![](F:\photo\笔记图片\微信图片_20200609095503.png)

#### 2.变量声明

```
var num1,mun2 ; //声明多个变量，逗号隔开
```

#### 3.变量赋值

```
var num1 = 123;       // 123是数值
var num2 = "一二三";    //"一二三"是字符串，双引号
var num3=true;    //布尔值true（真），false(假)
```

#### 4.自加自减

```
mynum = mynum + 1;//等同于mynum++
mynum = mynum - 1;//等同于mynum--
```

#### 5.比较操作符

```
var a = 5;//定义a变量，赋值为5
var b = 9; //定义b变量，赋值为9
document.write (a<b); //a小于b的值吗? 结果是真(true)
document.write (a>=b); //a大于或等于b的值吗? 结果是假(false)
document.write (a!=b); //a不等于b的值吗? 结果是真(true)
document.write (a==b); //a等于b的值吗? 结果是假(false)
```

得到值为真（true）和假(false)。

```
numa=1;
numb=7;
jq1= numa>numb        ;//jq1=false
jq2= numa!=numb       ;//jq2=true
```



#### 6.逻辑与或非操作符

```
b>a && b<c    //“&&”是并且的意思, 读法"b大于a"并且" b小于c "与数学里的相交一样，∩ 同时满足
```

![](F:\photo\笔记图片\微信图片_20200609101440.png)

```
var a=3;
var b=5;
var c;
c=b>a ||a>b;  //b>a是true，a>b是false，c是true，与数学里的∪一样，或，or
```

![](F:\photo\笔记图片\微信图片_20200609101851.jpg)

```
var a=3;
var b=5;
var c;
c=!(b>a);  // b>a值是true,! (b>a）值是false
c=!(b<a);  // b<a值是false, ! (b<a）值是true赋值，不是不等于
//与数学里的非一样 ！
```

#### 7.操作符优先级

操作符之间的优先级（高到低）:

算术操作符 → 比较操作符 → 逻辑操作符 → "="赋值符号

#### 8.取余运算

```
100%7=2
```

#### 9.练习

```
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>JS基础</title>
<script type="text/javascript">
  var a,b,sum;
  var  a  = 5;
  var  b  = 100%7;  
  sum = a > b && a*b > 0 ;
  document.write( "我认为 a 的值是:" + 5 + " b的值是:" + 2 + "sum 的值是:" +　false+"<br/>");
  document.write( "答案是,第一轮计算后，a 为："+ a +";b为："+b +";第一次计算sum为："+ sum +"<br/>");

  sum = ( (++a)+ 3 ) / (2- (--b) ) * 3;  
  document.write( "再一次计算后，我认为 a 的值是:" +  6  + " b的值是:" +  1+ "sum 的值是:" +  27 +"<br/>"); 
  
  document.write( "答案是，第二轮计算后，a 为：" + a + ";b为：" + b +";第二次计算sum为："+ sum +",sum的类型也发生变化了。");
</script>
</head>
<body>
</body>
</html>
```

注意：++a后a的值也要变

```
var a=1; 

var b=a++;//此时输出结果b为1，a为2 
/*因为等于的运算符优先级大于a++这种形式的运算符，所以先运算=  所以先b先等于a 故b的值为1，a再++ 所以为2；*/
```

```
var a=1; 

var b=++a;//此时输出结果b为2，a为2 
/*因为等于的运算符优先级小于++a这种形式的运算符，所以先运算++a  所以a先加然后结果为2 ，再把值给b 所以b也为2；*/

```

### 数组

#### 1.创建数组

```
var myarray= new Array(8); //创建数组，存储8个数据。 
```

- 创建的新数组是空数组，没有值，如输出，则显示undefined
- 虽然创建数组时，指定了长度，但实际上数组都是变长的，也就是说即使指定了长度为8，仍然可以将元素存储在规定长度以外。

#### 2.数组赋值

```
var myarray = new Array(66,80,90,77,59);//创建数组同时赋值

var myarray = [66,80,90,77,59];//直接输入一个数组（称 “字面量数组”）
```

问题：赋一个值和设置长度的区别。

#### 3.数组属性

```
var arr=[55,32,5,90,60,98,76,54];//包含8个数值的数组arr 
document.write(arr.length); //显示数组长度8
document.write(arr[7]); //显示第8个元素的值54
arr.length=10; //增大数组的长度
document.write(arr.length); //数组长度已经变为10
var arr=[98,76,54,56,76]; // 包含5个数值的数组
document.write(arr.length); //显示数组的长度5
arr[15]=34;  //增加元素，使用索引为15,赋值为34
alert(arr.length); //显示数组的长度16
```

#### 4.二维数组

- 二维数组的定义方法一

  ```
  var myarr=new Array();  //先声明一维 
  for(var i=0;i<2;i++){   //一维长度为2
     myarr[i]=new Array();  //再声明二维 
     for(var j=0;j<3;j++){   //二维长度为3
     myarr[i][j]=i+j;   // 赋值，每个数组元素的值为i+j
     }
   }
  ```

- 二维数组的定义方法二

  ```
  var Myarr = [[0 , 1 , 2 ],[1 , 2 , 3]]
  ```

- 赋值

  ```
  myarr[0][1]=5; //将5的值传入到数组中，覆盖原有值。
  //myarr[0][1] ,0 表示表的行，1表示表的列。
  ```

#### 5.练习

<u>问题：显示不出数组，显示出全是NaN。</u>

```
<!DOCTYPE  HTML>
<html >
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>数组</title>
<script type="text/javascript">
 //创建数组
 var  arr = ['*','##',"***","&&","****","##*"];
   arr[7] = "**";
 //显示数组长度
 alert(arr.length)
 for(i=0;i<7;i++)
 {
 document.write(+arr[i]+"<br>");
 }
</script>
</head>
<body>
</body>
</html>
```

### 流程控制

#### 1.4-1