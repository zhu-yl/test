### 文件结构

![25](F:\photo\笔记图片\25.PNG)

## 全局配置文件

### pages

- 新建文件夹

```
// "pages/demo01/demo01"新建一个文件夹，含四个
```

pages里的文件顺序就是微信小程序的显示顺序

### window字段

- 添加下方工具栏按钮图标

```
"tabBar": {
    "list": [
      {
        "pagePath": "pages/index/index",/* 重点是路径 */
        "text": "首页",
        "iconPath": "icon/_home.png",
        "selectedIconPath": "icon/home.png"
      },
      {
        "pagePath": "pages/img/img",
        "text": "图片",
        "iconPath": "icon/_img.png",
        "selectedIconPath": "icon/img.png"
      }
  ]
  },
```

### 代码编辑器技巧demo03

- text 相当于以前web中的 span标签 行内元素 不会换行
- view 相当于以前web中的 div标签 块级元素 会换行
- checkbox 以前的复选框标签 

```
<!-- <text>1</text>

<text>2</text>

<view>1</view>

<view>2</view> -->

```

1. 字符串

```
<view> {{msg}} </view>
```

2. 数字类型 

```
<view>{{num}}</view>
```

3. bool类型

```
<view> 是否是伪娘: {{isGirl}} </view>
```

4. object类型

```
<view>{{person.age}}</view>

<view>{{person.height}}</view>

<view>{{person.weight}}</view>

<view>{{person.name}}</view>
```

5. 在标签的属性中使用

```
<view data-num="{{num}}"> 自定义属性</view>
```

6. 使用bool类型充当属性 checked 

  1 字符串和 花括号之间一定不要存在空格 否则会导致识别失败 

   以下写法就是错误的示范

  <checkbox checked="    {{isChecked}}"> </checkbox>

```
<view>

 <checkbox checked="{{isChecked}}"> </checkbox>

</view>
```

7.  运算 => 表达式

- 可以在花括号中 加入 表达式 -- “语句”
- 表达式

   指的是一些简单 运算 数字运算 字符串 拼接 逻辑运算。。

​        1 数字的加减。。

​        2 字符串拼接

​        3 三元表达式 

- 语句

   1 复杂的代码段

​    1 if else

​    2 switch

​    3 do while 。。。。

​    4 for 。。。

```
<view>{{1+1}}</view>
<view>{{'1'+'1'}}</view>
<view>{{ 11%2===0 ? '偶数' : '奇数' }}</view>
```

8. 列表循环

  1 wx:for="{{数组或者对象}}" wx:for-item="循环项的名称" wx:for-index="循环项的索引"

  2 wx:key="唯一的值" 用来提高列表渲染的性能

   1 wx:key 绑定一个普通的字符串的时候 那么这个字符串名称 肯定是 循环数组 中的 对象的 唯一属性

   2 wx:key ="*this" 就表示 你的数组 是一个普通的数组 *this 表示是 循环项 

​    [1,2,3,44,5]

​    ["1","222","adfdf"]

  3 当出现 数组的嵌套循环的时候 尤其要注意 以下绑定的名称 不要重名

​    wx:for-item="item" wx:for-index="index"

  4 默认情况下 我们 不写

​    wx:for-item="item" wx:for-index="index"

​    小程序也会把 循环项的名称 和 索引的名称 item 和 index 

​    只有一层循环的话 （wx:for-item="item" wx:for-index="index"） 可以省略

 9 对象循环

  1 wx:for="{{对象}}" wx:for-item="对象的值" wx:for-index="对象的属性"

  2 循环对象的时候 最好把 item和index的名称都修改一下

   wx:for-item="value" wx:for-index="key"

```
<view>

  <view 

 wx:for="{{list}}"

 wx:for-item="item"

 wx:for-index="index"

 wx:key="id"

  \>

   索引：{{index}}

   \--

   值:{{item.name}}

  </view>

 </view>



 <view>

  <view>对象循环</view>

  <view 

 wx:for="{{person}}"

 wx:for-item="value" 

 wx:for-index="key"

 wx:key="age"

 \>

   属性:{{key}}

   \--

   值:{{value}}

  </view>

 </view>
```

10. block

  1 占位符的标签 

  2 写代码的时候 可以看到这标签存在

  3 页面渲染 小程序会把它移除掉

```
<view>

  <block 

  wx:for="{{list}}"

  wx:for-item="item"

  wx:for-index="index"

  wx:key="id"

  class="my_list"

  \>

   索引：{{index}}

   \--

   值:{{item.name}}

  </block>

 </view>


```

11. 条件渲染

   1 wx:if="{{true/false}}"

​    1 if , else , if else

​    wx:if

​    wx:elif

​    wx:else 

   2 hidden 

​    1 在标签上直接加入属性 hidden 

​    2 hidden="{{true}}"



   3 什么场景下用哪个

​    1 当标签不是频繁的切换显示 优先使用 wx:if

​     直接把标签从 页面结构给移除掉 

​    2 当标签频繁的切换显示的时候 优先使用 hidden

​     通过添加样式的方式来切换显示 

​     hidden 属性 不要和 样式 display一起使用

  

```
<view>

   <view>条件渲染</view>

   <view wx:if="{{true}}">显示</view>

   <view wx:if="{{false}}">隐藏</view>



   <view wx:if="{{flase}}">1</view>

   <view wx:elif="{{flase}}">2 </view>

   <view wx:else> 3 </view>



   <view>---------------</view>

   <view hidden >hidden1</view>

   <view hidden="{{false}}" >hidden2</view>



   <view>-----000-------</view>

   <view wx:if="{{false}}">wx:if</view>

   <view hidden style="display: flex;" >hidden</view>

  </view>
```

### 事件绑定demo04

<!-- 

1. 需要给input标签绑定 input事件 

  绑定关键字 bindinput

2. 如何获取 输入框的值 

  通过事件源对象来获取 

  e.detail.value 

3. 把输入框的值 赋值到 data当中

  不能直接 

```
   1 this.data.num=e.detail.value 

   2 this.num=e.detail.value 
```

  正确的写法

```
   this.setData({

    num:e.detail.value 

   })
```

4. 需要加入一个点击事件 

- bindtap
- 无法在小程序当中的 事件中 直接传参 
- 通过自定义属性的方式来传递参数
- 事件源中获取 自定义属性

 -->

```
<input type="text" bindinput="handleInput" />

<button bindtap="handletap" data-operation="{{1}}" >+</button>

<button bindtap="handletap" data-operation="{{-1}}">-</button>

<view> 

 {{num}}

</view>
```

js里

```
// pages/demo04/demo04.js
Page({
  data: {
    num: 0
  },
  // 输入框的input事件的执行逻辑
  handleInput(e) {
    // console.log(e.detail.value );
    this.setData({
      num: e.detail.value
    })
  },
  // 加 减 按钮的事件
  handletap(e) {
    // console.log(e);
    // 1 获取自定义属性 operation
    const operation = e.currentTarget.dataset.operation;
    this.setData({
      num: this.data.num + operation
    })
  }
})
```

### 样式rpx

1. 小程序中 不需要主动来引入样式文件 

2. 需要把页面中某些元素的单位 由 px 改成 rpx

 1 设计稿 750x

  750 px = 750 rpx 

  1 px = 1 rpx

 2 把屏幕宽度 改成 375px

  375 px = 750 rpx

  1 px = 2rpx

  1rpx = 0.5px

3. 存在一个设计稿 宽度 414 或者 未知 page 

 1 设计稿 page 存在一个元素 宽度 100px

 2 拿以上的需求 去实现 不同宽度的页面适配 



 page px = 750 rpx

 1 px = 750 rpx / page

 100 px = 750 rpx * 100 / page 

 假设 page = 375px

4. 利用 一个属性 calc属性 css 和 wxss 都支持 一个属性

 1 750 和 rpx 中间不要留空格

 2 运算符的两边也不要留空格

```
 view{

  /* width: 200rpx; */

  height: 200rpx;

  font-size: 40rpx;

  background-color: aqua;

 /* 以下代码写法是错误 */

 /* width:750 rpx * 100 / 375 ; */

 width:calc(750rpx * 100 / 375);

 }
```

### 样式导入

- 直接新建文件输入styles/common.wxss可直接创建styles文件夹并在里面创建common.wxss文件。

- 1 引入的 代码 是通过 @import 来引入

  2 路径 只能写相对路径

  ```
  @import "../../styles/common.wxss";
  ```

- common的代码

```
view{
  color: aqua;
  font-size: 100px;
}
```

## 组件

### view和text标签

- 长按文字复制 selectable
- 对文本内容 进行 解码decode
- &lt=<

```
<text selectable decode>
  text &nbsp; 123 &lt;
</text>
```

### image标签

 1 src 指定要加载的图片的路径

  图片存在默认的宽度和高度 320 * 240   原图大小是 200 * 100

 2 mode 决定 图片内容 如何 和 图片标签 宽高 做适配

-    scaleToFill 默认值 不保持纵横比缩放图片，使图片的宽高完全拉伸至填满 image 元素 
-    aspectFit 保持宽高比 确保图片的长边 显示出来  页面轮播图 常用
-    aspectFill 保持纵横比缩放图片，只保证图片的 短 边能完全显示出来。 少用
-    widthFix 以前web的图片的 宽度指定了之后 高度 会自己按比例来调整  常用 
-    bottom。。 类似以前的backgroud-position 

 3 小程序当中的图片 直接就支持 懒加载 lazy-load

-   1 lazy-load 会自己判断 当 图片 出现在 视口 上下 三屏的高度 之内的时候 自己开始加载图片 

```
 <image mode="bottom" lazy-load src="https://tva2.sinaimg.cn/large/007DFXDhgy1g51jlzfb4lj305k02s0sp.jpg" />
```

### swiper

 1 轮播图外层容器 swiper

 2 每一个轮播项 swiper-item

 3 swiper标签 存在默认样式

-   1 width 100%
-   2 height 150px  image 存在默认宽度和高度 320 * 240 
-   3 swiper 高度 无法实现由内容撑开 

 4 先找出来 原图的宽度和高度 等比例 给swiper 定 宽度和高度

  原图的宽度和高度 1125 * 352 px

  swiper 宽度 / swiper 高度 = 原图的宽度 / 原图的高度

  swiper 高度 = swiper 宽度 * 原图的高度 / 原图的宽度

  height: 100vw * 352 / 1125

 5 autoplay 自动轮播

 6 interval 修改轮播时间

 7 circular 衔接轮播

 8 indicator-dots 显示 指示器 分页器 索引器 

 9 indicator-color 指示器的未选择的颜色 

 10 indicator-active-color 选中的时候的指示器的颜色 

```
<swiper autoplay interval="1000" circular indicator-dots indicator-color="#0094ff" indicator-active-color="#ff0094">

  <swiper-item> <image mode="widthFix" src="//gw.alicdn.com/imgextra/i1/44/O1CN013zKZP11CCByG5bAeF_!!44-0-lubanu.jpg" /> </swiper-item>

  <swiper-item> <image mode="widthFix" src="//aecpm.alicdn.com/simba/img/TB1CWf9KpXXXXbuXpXXSutbFXXX.jpg_q50.jpg" /> </swiper-item>

  <swiper-item> <image mode="widthFix" src="//gw.alicdn.com/imgextra/i2/37/O1CN01syHZxs1C8zCFJj97b_!!37-0-lubanu.jpg" /> </swiper-item>

</swiper>
```

### navigator

0 块级元素 默认会换行 可以直接加宽度和高度 

 1 url 要跳转的页面路径 绝对路径 相对路径

 2 target 要跳转到当前的小程序 还是其他的小程序的页面

-   self 默认值 自己 小程序的页面 
-   miniProgram 其他的小程序的页面

 3 open-type 跳转的方式

-   1 navigate 默认值 保留当前页面，跳转到应用内的某个页面，但是不能跳到 tabbar 页面
-   2 redirect 关闭当前页面，跳转到应用内的某个页面，但是不允许跳转到 tabbar 页面。
-   3 switchTab 跳转到 tabBar 页面，并关闭其他所有非 tabBar 页面
-   4 reLaunch 关闭所有页面，打开到应用内的某个页面

```
 <navigator url="/pages/demo10/demo10"> 轮播图页面 </navigator>

 <navigator url="/pages/index/index"> 直接跳转到 tabbar页面 </navigator>

 <navigator open-type="redirect" url="/pages/demo10/demo10"> 轮播图页面 redirect </navigator>

 <navigator open-type="switchTab" url="/pages/index/index"> switchTab直接跳转到 tabbar页面 </navigator>

 <navigator open-type="reLaunch" url="/pages/index/index"> reLaunch 可以随便跳 </navigator> 
```

###  rich-text 富文本标签

 1 nodes属性来实现

-   1 接收标签字符串 
-   2 接收对象数组 

```
 <rich-text nodes="{{html}}"></rich-text>
```

```
// pages/demo12/demo12.js

Page({

 data: {

  // 1 标签字符串 最常用的

    // html:'复制的淘宝图标代码'

  // 2 对象数组

  html:[

   {

​    // 1 div标签 name属性来指定

​    name:"div",

​    // 2 标签上有哪些属性

​    attrs:{

​     // 标签上的属性 class style

​     class:"my_div",

​     style:"color:red;"

​    },

​    // 3 子节点 children 要接收的数据类型和 nodes第二种渲染方式的数据类型一致 

​    children:[

​     {

​      name:"p",

​      attrs:{},

​      // 放文本

​      children:[

​       {

​        type:"text",

​        text:"hello"

​       }

​      ]

​     }

​    ]

   }

  ]

 }

})
```

###  button 标签

 1 外观的属性

  1 size 控制按钮的大小

-    1 default 默认大小
-    2 mini 小尺寸

  2 type 用来控制按钮的颜色

-    1 default 灰色
-    2 primary 绿色
-    3 warn 红色

  3 plain 按钮是否镂空，背景色透明

  4 loading 文字前显示正在等待图标

```
 <button>默认按钮</button>

 <button size="mini"> mini 默认按钮</button>

 <button type="primary"> primary 按钮</button> 

 <button type="warn"> warn 按钮</button> 

 <button type="warn" plain> plain 按钮</button> 

 <button type="primary" loading> loading 按钮</button> 
```

 button 开发能力

 open-type：

 1 contact 直接打开 客服对话功能 需要在微信小程序的后台配置  只能够通过真机调试来打开 

 2 share 转发当前的小程序 到微信朋友中  不能把小程序 分享到 朋友圈 

 3 getPhoneNumber 获取当前用户的手机号码信息 结合一个事件来使用 不是企业的小程序账号 没有权限来获取用户的手机号码 

-   1 绑定一个事件 bindgetphonenumber 
-   2 在事件的回调函数中 通过参数来获取信息 
-   3 获取到的信息 已经加密过了 

   需要用户自己待见小程序的后台服务器，在后台服务器中进行解析 手机号码，返回到小程序中 就可以看到信息了

 4 getUserInfo 获取当前用户的个人信息

-   1 使用方法 类似 获取用户的手机号码
-   2 可以直接获取 不存在加密的字段 

 5 launchApp 在小程序当中 直接打开 app

-   1 需要现在 app中 通过app的某个链接 打开 小程序
-   2 在小程序 中 再通过 这个功能 重新打开 app
-   3 找到 京东的app 和 京东的小程序 

 6 openSetting 打开小程序内置的 授权页面

-   1 授权页面中 只会出现 用户曾经点击过的 权限 

 7 feedback 打开 小程序内置的 意见反馈页面 

-   1 只能够通过真机调试来打开 

```
contact</button>

<button open-type="share">share</button>

<button open-type="getPhoneNumber" bindgetphonenumber="getPhoneNumber">getPhoneNumber</button>

<button open-type="getUserInfo" bindgetuserinfo="getUserInfo">getUserInfo</button>

<button open-type="launchApp">launchApp</button>

<button open-type="openSetting">openSetting</button>

<button open-type="feedback">feedback
```

### icon 小程序中的字体图标

 1 type 图标的类型

  success|success_no_circle|info|warn|waiting|cancel|download|search|clear

 2 size 大小 

 3 color 图标的颜色

```
<icon type="cancel" size="60" color="#0094ff"> </icon>
```

###  radio 单选框

 1 radio标签 必须要和 父元素 radio-group来使用

 2 value 选中的单选框的值 

 3 需要给 radio-group 绑定 change事件 

 4 需要在页面中显示 选中的值

```
 <radio-group bindchange="handleChange">

  <radio color="red" value="male">男</radio>

  <radio color="red" value="female" >女</radio>

 </radio-group>



 <view>您选中的是:{{gender}}</view>
```

js文件

```
// pages/demo15/demo15.js
Page({
  data: {
    gender: ""
  },
  handleChange(e){
    // 1 获取单选框中的值
    let gender=e.detail.value;
    // 2 把值 赋值给 data中的数据
    this.setData({
      // gender:gender
      gender
    })
  }
})
```

### checkbox复选框 

wxml

```
<view>
  <checkbox-group bindchange="handleItemChange">
    <checkbox value="{{item.value}}" wx:for="{{list}}" wx:key="id">
      {{item.name}}
    </checkbox>

  </checkbox-group>
  <view>
    选中的水果:{{checkedList}}
  </view>
</view>
```

js

```
// pages/demo16/demo16.js
Page({
  data: {
    list:[
      {
        id:0,
        name:"🍎",
        value:"apple"
      },
      {
        id:1,
        name:"🍇",
        value:"grape"
      },
      {
        id:2,
        name:"🍌",
        value:"bananer"
      }
    ],
    checkedList:[]
  },
  // 复选框的选中事件
  handleItemChange(e){
    // 1 获取被选中的复选框的值
    const checkedList=e.detail.value;
    // 2 进行赋值
    this.setData({
      checkedList
    })
  }
})
```

## 自定义组件

### 组件的创建

1. 先创建组件文件夹命名Tabs。

2. 然后在demo的json调用组件。

```
{
  "usingComponents": {
    "Tabs":"../../components/Tabs/Tabs"
  }
}
```

3. 然后在wxml里当作普通标签使用

```
<Tabs></Tabs>
```



- 父组件(页面) 向子组件 传递数据 通过 标签属性的方式来传递
      1 在子组件上进行接收
      2 把这个数据当成是data中的数据直接用即可
- 子向父传递数据 通过事件的方式传递
      1 在子组件的标签上加入一个 自定义事件

wxml

```
<Tabs tabs="{{tabs}}" binditemChange="handleItemChange" >

<block wx:if="{{tabs[0].isActive}}">0 </block>
<block wx:elif="{{tabs[1].isActive}}">1 </block>
<block wx:elif="{{tabs[2].isActive}}">2 </block>
<block wx:else>3</block>

</Tabs>

```

