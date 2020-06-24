# vue

## vue-cli2脚手架

### node.js环境安装

常用的dos命令：

cd：打开文件夹 

md：创建新文件夹

dir：查看文件夹内容

cd..：返回上一级文件夹  

type**：打开文本

### npm安装及参数设置

**vue-cli的安装**

**npm与cnpm的区别**

- cnpm 国内淘宝镜像的npm管理器用于替代国外服务器

- npm（node package manager） 是 nodejs包管理器

 **-g 全局安装（global）**

  npm root -g 查看全局安装的文件夹位置

**vue-cli2安装**

自动安装

  npm install -g vue-cil（默认安装指令）

  cnpm install -g vue-cil（镜像安装指令，需要配置淘宝镜像）

手动淘宝镜像安装

  npm install -gd express --registry=[http://registry.npm.taobao.org](http://registry.npm.taobao.org/) 

淘宝镜像资源永久设置指令：避免每次安装都需要-registry

npm config set registry http://registry.npm.taobao.org

### npm安装及参数设置2

npm 参数

-S --save安装包信息将加入到dependencies（生产阶段的依赖）

-D --save --dev 安装包信息将加入到devDependencies(开发阶段的依赖)，所以开发阶段一般使用它（生产环境也可以）

npm i -D vue-cli 本地安装(没有-g) 会报错需要：

 npm init -f 初始化本地安装配置文件

建议全局安装

### cnpm和vue-cli2安装

**cnpm的镜像使用配置指令**

npm install -g cnpm --registry=[https://registry.npm.taobao.org](https://registry.npm.taobao.org/) 

验证cnpm是否安装成功 cnpm -v

出现版本号就代表成功了



**安装好后通过 cnpm -install -gd vue-cli 安装vue脚手架**

-gd的意思是安装到全局且开发与应用环境当中

安装完成后验证vue是否安装成功的执行指令

vue -V V一定为大写注意

出现版本号就代表成功了

### 创建vue-cli2项目

vue-cli项目创建：【init：命令，webpack：所选择的模板，projectName：工程名称(不允许输入大写字母)】

vue init webpack projectName

创建cli过程中部分配置内容：

1.Install vue-router？(Y/n)是否安装vue-router，这是官方路由，大多数情况下都使用，这里就输入“y”后回车即可。【用户页面之间的跳转】

2.Use ESLint to lint your code？(Y/n)是否使用ESLint管理代码，ESLint是个代码风格管理工具，是用来统一代码风格的，一般项目中都会使用。

3.set up unit tests  这是单元测试  Y/n        n

4.其他选择默认 n

成功启动vue-cli项目：

http://localhost:8080【端口号8080可以改变】

### 更改vue-cli2的helloword

**vue-cli项目的配置与页面绑定（第一阶段）**

先启动服务

d: - cd testcli（进入testcli文件中） - dir（查看testcil的文件目录中的文件） - cd test1（进入test1项目中） - npm run dev（运行项目）

获取到 [localhost:8080/#/](http://localhost:8080/#/) 并在浏览器中访问



**创建自己的vue helloword页面**

使用编译器打开test1项目找到src

src文件用于存放页面相关的文件如 页面vue文件、配置跳转的index.js文件

components：components文件夹下是存放自定义vue页面的

router：router文件夹中有一个index.js用于首页跳转的配置，默认配置，配置以后会指定首页页面为哪一个



**配置子的vue helloword页面**

在index.js中先用import引入我们创建的first.vue

import First from '@/components/first.vue'

//First ：是命名这个引用，业内默认首字母大写 @：是相对路径

routes: [

  {

   path: '/', //代表根目录根节点

   name: 'First', //当前跳转的命名备注

   component: First //刚刚我们import的命名

  }

 ]

### 配置语法高亮显示

sublime 配置语法高亮

https://github.com/vuejs/vue-syntax-highlight   下载压缩包

sublime打开Preferences -> 设置第一个菜单 ->浏览资源包 ->新建vue文件夹 ->将压缩包的内容都复制进去

然后回到sublime   ctrl+shift+p    搜索vue，选择第一个vue component双击

### router实现页面跳转

现效果：

在首页，可以通过链接进入a，b两个“页面”，也可以从a，b两个“页面”返回到首页



template标签下必须有一个根div标签，其他内容都要放在这个div里面

实现页面跳转：**一般都写在index和js里。**

先在src -> components里面创建A、B两个vue页面分别添加页面内容

在index.js中引用A、B两个vue组件

在需要跳转的vue页面中添加<router-link to=""></router-link>跳转，to对应index.js中component的path值

### router实现子路由1

router 实现子页面跳转再返回

创建A、B的子页面A1、B1 .vue结尾的文件

页面中编辑

index.js中的配置与逻辑

import A1与B1

A1属于A所以在A的跳转配置中加入字段

    children:[{ //常用于父框架中嵌入子页面的操作，会保留父框架的内容嵌入子框架
    
    path: '/a1',
    
     name: 'A1',
    
     component: A1
    },{}];



并在A页面的<router-link to="/A1">标签加入跳转路径

<router-view></router-view>：用于挂载子页面的位置，必须在父页面中添加这个标签，才能把要挂载的子页面显示到<router-view></router-view>中

<router-view></router-view>：点击这个链接跳转到其他组件的情况，通常会跳转到新的页面，蛋是，我们不想跳转到新页面，只在当前页面切换着显示，那么就要涉及到路由的嵌套了，也可以说是子路由的使用。





### router实现子路由2

失败 跳转不出页面 因为没有加router-view 

router-link 界面跳转  router-link to="/跳转页面路由" 

router-view 父页面挂在子页面 当子页面使用children设置路由时 子页面不显示 这时需要加上router-view来挂在子页面 才能显示

[代码](F:\代码\vue\200611)

### 为什么不用#号

**关于地址栏中 #** 

- 地址栏中，经常出现#，是什么作用，能不能去掉#？
- hash模式：地址栏包含#符号，#以后的不能呗后台获取
- history模式：具对url历史记录进行修改的功能
- 在微信支付、分享url作为参数传递时，#不能满足需求
- history需要后台配合，处理404的问题

在index.js里的routes:[上面添加mode:'history',，可以把网址中的#去掉，因为#有特殊含义，很多时候不能使用

### 单独安装eslint

**关于vue-cli 的添加与卸载**

**准备工作**

在这里以eslint为例**
**

回顾一下创建vue项目的语法：

vue init webpack projectName

eslint：为 vue 的代码的规范检查插件

注意安装的内容放到什么环境中：

-g：--global（全局）

-S：--save（生产环境：dependencies）//针对可以上线的项目

-D：--save-dev（开发环境：devDependencies）//针对开发过程中



**安装与卸载**

单独安装eslint:

安装到生产环境：npm install eslint --save

安装到开发环境：npm install eslint --save-dev

生产环境：package.json中的dependencies

开发环境：package.json中的devDependencies

卸载：npm uninstall eslint --save / npm uninstall eslint --dev

卸载router路由（生产环境）：npm uninstall vue-router --save

安装router路由（生产环境）：npm install vue-router --save

### 导入其他项目添加依赖并运行

cd进入到项目中然后npm install安装vue项目依赖

进入后可以先检查是否有vue-cli项目的运行环境，验证npm与vue是否安装即可：

npm -v 和vue -V（注意vue -V V 是大写的）

如果都出现版本号就不需要安装npm依赖直接可以npm run dev

都实现以后就可以直接将项目跑起来

npm run dev

### 居中实现（主组件的样式设置）

**系统的认识一下vue的主体结构**

app.vue是所有vue文件的父级优先级是最高的主题文件**
**

目前所有的默认配置来源于app.vue的设置其中包括：

居中：在样式中text-align: center;

图片：是第三行的标签<img src="./assets/logo.png">

**补充**

<script></script>：为逻辑层，所有的逻辑代码以及配置项都在这里完成

<style></style>：为样式层，页面的样式在这里定义

## vue-cli3脚手架

### 手动搭建vue-cli环境1

**不使用vue-cli的模板（webpage）安装组件**

- 安装依赖：npm install 或者cnpm install 
- 初始化：npm init -f 或者cnpm install -f
- 安装组件，并查看安装后的内容



**流程如下**

先在切换到D盘创建kkk文件夹**
**

d:\>md kkk

访问其中然后安装npm环境npm install

初始化kkk需要用到npm init -f（-f 的意思是自动创建配置环境，不需要人工干预，跳过项目的配置信息）

※package.json vue-cli中最重要的配置文件，所有的配置和依赖都在里面，安装的插件和版本号都会显示

接下来是手动安装 vue-router（路由跳转的工具，必装）

npm i vue-router -D（意思是开发环境和运行环境都需要安装）

**查看文件的cmd语法**

```
type pa*
```

(*代表模糊查询，打开所有含有字母pa的文件)



type package.json（打开访问package.json文件）



接下来安装eslint（语法规范工具）

npm install eslint -D



综上所述：如果不适用模板安装就会很麻烦，容易遗漏需要安装的插件，所以建议开发过程中用合适的模板创建项目，卸载可以一个一个卸载

用模板的语法为：

vue init webpack projectName

### 手动搭建vue-cli环境2

- 手动搭建vue-cli环境
- 安装依赖：npm install 或者 cnpm install
- 初始化：npm init -f 或者 cnpm init -f，f参数为全部使用默认值，无人工干预
- 安装组件，并查看安装后内容

本节内容主要是用cnpm 重新进行一次上节的操作

值得注意的是

-g：我们一般不用-g，-g用于安装到全局配置中，意思就是npm的主体中的node_modules的文件中，会通用到后面所有用npm配置的项目中；不建议这样操作，应该遵循一个项目一个配置，所以我们用-D用的比较多；

cnpm 与 npm 安装主要的区别就是node_modules文件出现的顺序不一样

cnpm：在cnpm环境搭建的时候 install 就会出现

npm：需要init初始化之后才会出现

总体不影响因为package和node_modules都是必须的所以最终都会有的



※还是跟上节一样最终还是建议用模板工具来创建，节约时间更严谨等等，但是手动安装必须要会要知道流程

### 卸载vue-cli2 安装/升级vue-cli3

vue-cli3安装、升级：

1.卸载vue-cli2：npm uninstall vue-cli -g

2.普通安装vuecli3：npm install -g @vue/cli

2.淘宝镜像安装vuecli3：cnpm install -g @vue/cli



vuecli3启动：vue ui



**安装vue-cli3**

先进入到之前创建的项目中testcli中，可以先检查一下自己的vue版本是否存在（vue -V）

不存在就可以安装了，语法相似：npm install @vue/cli

npm install -g @vue/cli ：主要是安装到全局中

vue-cli3的特点就是增加了可视化，但是建议能使用npm指令就使用npm因为使用的频率决定了你对npm的熟练度以及理解，可视化界面用于测试和找bug比较好



像 @vue/cli 这种，在全局环境下用的，多个项目共同使用的，就全局安装

而像eslink 这种包 如果只在单独一个项目中使用，则选择本地安装

### vue-cli3图形界面

安装vue-cli3的命令：

npm install -g @vue/cli;

启动项目的命令：

vue ui;

GUI图形界面:方便，运行速度比较慢，

自动弹出的项目自己创建，然后点击任务->serve->运行->打开8080网址能够刷出项目

### vue-cli3创建项目

vue-cli3创建项目：vuecli2：install   vuecli3：create

安装vuecli3：vue create vue-test3

启动vuecli3项目：npm run serve![23](F:\photo\笔记图片\23.PNG)

图上的步骤完后：

cd test3

npm run serve

作出的页面与上一节的ui一样

### vue-cli3第一个welcome

1. 先运行项目 npm run serve
2. 在components里建一个first.vue

```
<template>
	<div>
		这里是vue-cli3的第一个页面
	</div>
</template>
```

3. 先在index.js里加上以下代码

```
import First from '../components/first.vue'

const routes = [
  {
    path: '/',
    name: 'Home',
    component: First//将home改成First
  },
```

完成后网址首页改变

vuecli3中新增了views文件夹，分工更加明确了

### vue-cli3导入其他项目并运行

项目如果启动不成功，安装依赖

npm install/cnpm install

还不成功可以加上-g

在3的环境里运行2不用3的指令，用2即可

```
不用npm run serve
用npm run dev
```

### vue-cli3项目案例效果

与2类似在router实现页面跳转里面、

### vue-cli3添加样式的三种方式

1.在vue文件中的style里面添加

```
<style>
/*@import "../../public/ys1.css"*/
.ys1{
	color: green;
	font-size: 30px;
}
</style>
```

2.在public中新建一个css文件，在vue文件中的style引入css文件：@import "../../public/xxx.css"

first.vue里面

```
<style>
@import "../../public/ys1.css"
</style>
```

ys1.css

```
.ys1{
	color: green;
	font-size: 30px;
}
```

3.在项目的首页html中添加link引用css文件在head上

```
<link rel="stylesheet" type="text/css" href="ys1.css">
```

## 案例

### 案例需求分析

项目主要技术：

1.组件及组件间传值

2.axios实现读取json数据：商品的数据源存与json中

3.css相关技术进行布局

4.使用views页面级组件，使用router设置页面

5.页面的显示相关的文件存在view里，组件零件的放在components里。



axios安装：cnpm i axios -S

### 创建项目

1. 创建项目proj，步骤看vue-cli3创建项目。
2. 先设置首页，在view里建一个First

```
<template>
	<div class="main">
		<div class="left"></div>
		<div>
			<div class="top">
				<img src="img/title.PNG">
		</div>
			<div class="buttom"></div>
			 	
		</div>
		
	</div>
</template>
```

3. 在router的index里调用

```
import First from '../views/First.vue'
Vue.use(VueRouter)

  const routes = [
  {
    path: '/',

    component: First
  },
```

4. 去掉主页的home about，去app.vue里将部分代码删掉。

```
<div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
```

5. 设置了主页的基本样式，在First里。

```
<style type="text/css">
	*{
		padding: 0;
		margin: 0;
	}
	/*默认格式清除*/
	.left{/*导航栏*/
		width: 100px;
		float: left;
		margin-right: 10px;/*左右两个区块的间距*/
	}
	.right{
		width: 1000px;
		float: left;
		margin-left: 10px;
	}
	.main{
		width: 1200px;/*居中没有宽度不能居中*/
		margin: 20px auto;/*auto代表水平居中*/

	}
	.top img{
		height: 200px;
		width: 1000px;
	}
	.left,.right{/*背景色，文字块间隔露出的背景色*/
		background-color: blue;
		
	}
</style>
```

6. 设置left导航栏

- 新建一个Left.vue。

```
<template>
	<div>
		<div class="title">热门推荐</div>
		<ul>
			<li>笔记本电脑</li>
			<li>手机</li>
			<li>笔记本电脑</li>
			<li>手机</li>
			<li>笔记本电脑</li>
			<li>手机</li>
			<li>笔记本电脑</li>
			<li>手机</li>
			<li>笔记本电脑</li>
			<li>手机</li>
			<li>笔记本电脑</li>
			<li>手机</li>
			<li>笔记本电脑</li>
			<li>手机</li>
		</ul>
	</div>
</template>
```

- 在First开头里调用组件Left，最后提案script。

```
<div class="main">
		<div class="left">
			<Left></Left>/*新加的*/
		</div>
		<div class="right">
```

```
<script type="text/javascript">
	import Left from '../components/Left.vue'
	export default{
		components:{
			Left
		}
	}
</script>
```

- 在left里加样式

```
<style type="text/css">
	.title{
		width: 100px;/*与左侧主页的间距100一样*/
		color: red;
	}
	.menu li{
		list-style: none;/*把前方的戊戌点去掉*/
		height:50px;
		margin-bottom: 2px;
		background-color:white; 
		line-height: 50px;/*字高与单元格行高一样便会居中*/
	}
</style>
```

别忘了设置单元行的类名

```
<ul class="menu">
```

6. 设置右下方right。

- 先创建Right.vue

```
<template>
	<div>
		11111111
	</div>
</template>
```

- 组件的引用

```
<script type="text/javascript">
	import Left from '../components/Left.vue'/*组件的引用*/
	import Right from '../components/Right.vue'
	export default{
		components:{
			Left,
			Right
		}
	}
</script>
```

别忘了上方的调用，需要显示的地方加代码

```
<div class="buttom">
				<Right></Right>
			</div>
```

- 新建了msg.js在components里，暂时不知道作用-----------

```
import Vue from 'vue'
export default new Vue
```

问题看图![](F:\photo\笔记图片\24.PNG)-----------------------------

7. 事件触发，点击导航栏触发右下区块显示的变化

- 在left上面单元格添加代码

```
<li @click='menu1'>笔记本电脑</li>
<li @click='menu2'>手机</li>
```

- 在left下方定义

```
<script type="text/javascript">
	import Msg from './msg.js'
	export default{
		methods:{
			menu1:function(){
				Msg.$emit("val","1");/*单击事件触发*/
			},
			menu2:function(){
				Msg.$emit("val","2");
			},
		}
	}
</script>
```

- right中触发接收

```
<template>
	<div>
		{{kk}}<!-- 触发接收 -->
	</div>
</template>
<script type="text/javascript">
	import Msg from './msg.js'
	export default{
		data(){
			return{
				kk:0
			}
		},
		mounted:function(){
			var _this=this/*把this赋值给_this*/
			Msg.$on('val',function(m){
				_this.kk=m;/*注意this和_this的含义区别*/
			})
		}
	}
</script>
```

- 在right里先实现能接收到111122222333344444

```
<template>
	<div><!-- 触发接收 -->
		<div v-if="kk==1">
			111111111111
		</div>
		<div v-if="kk==2">
			22222222222
		</div>
		<div v-if="kk==3">
			33333333333333
		</div>
		<div v-if="kk==4">
			44444444444
		</div>
	</div>
</template>
```

- 在left里添加一行代码鼠标事件

```
.menu li{
		list-style: none;/*把前方的戊戌点去掉*/
		height:50px;
		margin-bottom: 2px;
		background-color:white; 
		line-height: 50px;/*字高与单元格行高一样便会居中*/
		cursor: pointer;/*鼠标事件*/
	}
```

- bos安装依赖 先ctrl+c停止运行 安装 运行

```
cnpm i axios -S
npm run serve
```

- 在main.js里添加代码

```
import axios from 'axios'

Vue.prototype.$http=axios
```

8. 4-12