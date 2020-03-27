# HTML学习笔记

## 1. HTML基础结构

``` html
<!DOCTYPE html>										<!--[声明] 为HTML5文档-->
<html>												<!--HTML页面的 [根元素]-->
    <head>											<!--包含文档元(meta)数据, [头]-->
        <meta charset="utf-8">			<!--定义页面 [编码]-->
        <meta name="keywords" content="HTML">
        								<!--为搜索引擎定义关键词-->
        <meta name="description" content="Web">
        								<!--为网页定义描述内容-->
        <meta name="author" content="nano-cat">
              							<!--定义网页作者-->
        <meta http-equiv="refresh" content="30">
        								<!--没30秒刷新当前页面-->
        <title>网页标题</title> 		  <!--描述文档 [标题]-->
        <link rel="stylesheet" type="text/css" href="mystyle.css">
        								<!--外部[样式]链接-->
    </head>
    <body>											<!--包含可见的 [页面内容]-->
        <h1>内容标题</h1>			 	 <!--有<h1>-<h6>6级 [标题] -->
        <p>								<!--[段落]-->
            第一段
            <br>						<!--[新段落] (不产生新行)-->
            第二段
            <strong>加粗文本</strong>	 <!--文本 [格式化]-->
            <em>斜体文本</em><small>小号字</small>
            <sub>下标字</sub><sup>上标字</sup>
            <del>删除字</del><ins>插入字</ins>
        </p>
        <hr>						   <!--[水平线/分割线] (<hr>用来分割内容)-->
        <a href="https://www.baidu.com/" target="_blank">百度链接</a>
        								<!-- 新窗口打开 [链接]-->
        <img src="/img/logo.png" width="50" height="50">
        								<!-- 图片链接
    </body>
</html>
```

## 2. HTML基础

### 2.1 HTML标题

#### &nbsp;&nbsp; 标题

* HTML标题通过`<h1> - <h6>`标签定义

	```HTML
	<h1>一级标题</h1>
	<h6>六级标题</h6>
	```

### 2.2 HTML段落

#### &nbsp;&nbsp; 段落

* ```html
  <p>这是段落</p>
  ```

#### &nbsp;&nbsp;水平线

* `hr`用于分割内容

  ```html
  <p>这是一个段落。</p>
  <hr>				<!--分割线-->
  <p>这是一个段落。</p>
  ```

#### &nbsp;&nbsp;折行

* 不产生新段落 换行, 用 `<br>`  标签

  ```html
  <p>第一行<br>第二行<br>第三行</p>
  ```

#### &nbsp;&nbsp;格式化文本

* | 标签                | 描述             |
  | ------------------- | ---------------- |
  | `<strong></strong>` | 粗体文本         |
  | `<em></em>`         | 斜体文本         |
  | `<small></small>`   | 小号字           |
  | `<sub></sub>`       | 下标字           |
  | `<sup></sup>`       | 上标字           |
  | `<del></del>`       | 删除字(中间划掉) |
  | `<ins></ins>`       | 插入字(下划线)   |

#### &nbsp;&nbsp;注释

* ```html
  <!--注释内容-->
  ```

### 2.3 HTML链接

#### &nbsp;&nbsp;普通链接

* ```HTML
  <a href="https://www.baidu.com/">百度链接</a>
  ```

#### &nbsp;&nbsp;链接属性

* **target属性**(定义被链接的文档在何处显示)

  ```html
  <a href="https://www.baidu.com/" target="_blank">百度链接</a>  <!--新窗口打开-->
  ```

* **id属性**(可用于创建在一个HTML文档书签标记)
  * 插入id: `<a id="tips">有用的提示部分</a>`
  * 链接到该id: `<a href="#tips">访问有用的提示部分</a>`
  * 另一个页面链接该id: `<a href="http://*.com/index.html#tips">访问有用的提示部分</a>`

### 2.4 HTML图像

* ```html
  <img src="/img/logo.png" alt="logo" width="50" height="50">
  ```
  
  * Alt属性 (用来为图像定义一串预备的可替换文本
  
* 图片链接:

  ```html
  <a href="//www.runoob.com/html/html-tutorial.html"><img border="0" src="smiley.gif" alt="HTML 教程" width="32" height="32"></a>
  ```

### 2.5 HTML头部

#### &nbsp;&nbsp;**`<base>`**元素

* 描述基本的链接地址/链接目标

  ```HTML
  <base href="http://www.nano-cat.com/img/" target="_blank">
  ```

#### &nbsp;&nbsp;**`<style>`元素**

#### &nbsp;&nbsp;**`<meta`>元素**

#### &nbsp;&nbsp;**`<script>`元素**

### 2.7 HTML表格

* ```HTML
  <table border="1"> <!--border边框-->
      <tr>
          <th>表头1</th>
          <th>表头2</th>
      </tr>
      <tr> <!--行-->
          <td>1-1</td> <!--表格数据table data-->
          <td>1-2</td>
      </tr>
      <tr>
          <td>2-1</td>
          <td>2-2</td>
      </tr>
  </table>
  ```

### 2.8 HTML列表

* 无序列表

  ```html
  <ul>
  	<li>Coffee</li>
  	<li>Milk</li>
  </ul>
  ```

* 有序列表

  ```html
  <ol> <!--type="A"(大写字母列表)"a"(小写)"I"(大写罗马)"i"(小写罗马)-->
  	<li>Coffee</li>
  	<li>Milk</li>
  </ol>
  ```

* 自定义列表

  ```html
  <dl>
  	<dt>Coffee</dt>
  	<dd>- black hot drink</dd>
  	<dt>Milk</dt>
  	<dd>- white cold drink</dd>
  </dl>
  ```

### 2.9 HTML区块

* **`<div>`** 元素 (块级元素,常见的用途是文档布局)

  ```html
  <div style="color:#0000FF">
    <h3>这是一个在 div 元素中的标题。</h3>
    <p>这是一个在 div 元素中的文本。</p>
  </div>
  ```

* **`<span>`** 元素 (内联元素,可用于为部分文本设置样式属性)

  ```html
  <p>汤姆有一双 <span style="color:blue">蓝色</span> 的眼睛。</p>
  ```

### 2.10 HTML表单输入

* 文本域

  ```html
  <form>
      <fieldset>
          <legend>带框的表单</legend>
          文本: <input type="text" name="Text Fields"><br>
          密码: <input type="password" name="pwd">
      </fieldset>
  </form>
  ```

* 单/复选框

  ```html
  <form>
  <input type="radio" name="1" value="1">单选1<br>
  <input type="radio" name="2" value="2">单选2
  <input type="checkbox" name="3" value="3">复选1<br>
  <input type="checkbox" name="4" value="4">复选2
  </form>
  ```

  * value：提交数据到服务器的值（后台程序PHP使用）
  *  name：为控件命名，以备后台程序 ASP、PHP 使用
  *  checked：当设置 checked="checked" 时，该选项被默认选中

* 提交按钮

  ```html
  <form name="input" action="html_form_action.php" method="get">
  用户名: <input type="text" name="user">
  <input type="submit" value="提交">
  </form>
  ```

* 下拉列表

  ```html
  <select>
      <optgroup label="描述">
          <option value="下拉1">下拉1</option>
          <option value="下拉2">下拉2</option>
      </optgroup>
  </select>
  ```

## 3. 颜色

* RGBA（Red-Green-Blue-Alpha）它是在 RGB 上扩展包括了 **“alpha”** 通道，运行对颜色值设置透明度。

  ```css
  div {
  	background:rgba(255,0,0,0.5);
  }
  ```

  

## 4. CSS样式



## 5. Script脚本

* `<noscript>`标签

  ```html
  <script>
  document.write("Hello World!")
  </script>
  <noscript>抱歉，你的浏览器不支持 JavaScript!</noscript>
  ```

## 6. HTML字符实体

* | 字符 | 描述        | 实体名称   | 实体编号  |
  | ---- | ----------- | ---------- | --------- |
  |      | 空格        | `&nbsp;`   | `&#160;`  |
  | <    | 小于号      | `%lt;`     | `&#60;`   |
  | >    | 大于号      | `&gt;`     | `&#62;`   |
  | &    | 和号        | `&amp;`    | `&#38;`   |
  | "    | 引号        | `&quot;`   | `&#34;`   |
  | '    | 撇号        | `&apos;`   | `&#39;`   |
  | ¥    | 人民币/日元 | `&yen;`    | `&#165;`  |
  | ©    | 版权        | `&copy;`   | `&#169;`  |
  | ®    | 注册商标    | `&reg;`    | `&#174;`  |
  | ™    | 商标        | `&trade;`  | `&#8482;` |
  | ×    | 乘号        | `&times;`  | `&#215;`  |
  | ÷    | 除号        | `&divide;` | `&#247;`  |

## . HTML属性

### .1 通用属性

* | 属性  | 描述                         |
  | ----- | ---------------------------- |
  | class | 定义类名(类名从样式文件引入) |
  | id    | 定义元素唯一id               |
  | style | 规定元素行内样式             |
  | title | 描述元素额外信息             |



# HTML5笔记

## 1. 画布`<canvas>`

* 一个画布在网页中是一个矩形框

  ```HTML
  <canvas id="myCanvas" width="200" height="100" style="border:1px solid #000000;"></canvas>
  ```

* 使用 JavaScript 来绘制图像

  ```javascript
  var c=document.getElementById("myCanvas");
  var ctx=c.getContext("2d");
  //矩形图像
  ctx.fillStyle="#FF0000";
  ctx.fillRect(0,0,150,75);
  //绘制线条
  ctx.moveTo(0,0);
  ctx.lineTo(200,100);
  ctx.stroke();
  //绘制圆
  ctx.beginPath();
  ctx.arc(95,50,40,0,2*Math.PI);
  ctx.stroke();
  ```

* 使用 JavaScript绘制文本

  ```js
  var c=document.getElementById("myCanvas");
  var ctx=c.getContext("2d");
  //实心文字
  ctx.font="30px Arial";
  ctx.fillText("Hello World",10,50);
  //空心文字
  ctx.font="30px Arial";
  ctx.strokeText("Hello World",10,50);
  ```

* 渐变

  ```js
  var c=document.getElementById("myCanvas");
  var ctx=c.getContext("2d");
  // 创建渐变(线性渐变)
  var grd=ctx.createLinearGradient(0,0,200,0);
  grd.addColorStop(0,"red");
  grd.addColorStop(1,"white");
  // 填充渐变
  ctx.fillStyle=grd;
  ctx.fillRect(10,10,150,80);
  // 创建渐变(圆渐变)
  var grd=ctx.createRadialGradient(75,50,5,90,60,100);
  grd.addColorStop(0,"red");
  grd.addColorStop(1,"white");
  // 填充渐变
  ctx.fillStyle=grd;
  ctx.fillRect(10,10,150,80);
  ```

* 放置图像

  ```js
  var c=document.getElementById("myCanvas");
  var ctx=c.getContext("2d");
  var img=document.getElementById("scream");
  ctx.drawImage(img,10,10);
  ```

## 2. H5视频

* ```html
  <video width="640" height="360" controls>
  	<source src="movie.mp4" type="video/mp4">
      您的浏览器不支持H5播放器.
  </video>
  ```

* 使用DOM控制

  ```html
  <div style="text-align:center"> 
    <button onclick="playPause()">播放/暂停</button> 
    <button onclick="makeBig()">放大</button>
    <button onclick="makeSmall()">缩小</button>
    <button onclick="makeNormal()">普通</button>
    <br> 
    <video width="640" >
  	<source src="movie.mp4" type="video/mp4">
      您的浏览器不支持H5播放器.
    </video>
  </div> 
  <script> 
  var myVideo=document.getElementById("video1"); 
      function playPause(){ 
          if (myVideo.paused) 
            myVideo.play(); 
          else 
            myVideo.pause(); 
      } 
      function makeBig(){ 
          myVideo.width=1280; 
      } 
      function makeSmall(){ 
          myVideo.width=320; 
      } 
      function makeNormal(){ 
          myVideo.width=640; 
      } 
  </script>
  ```

## 3. H5 音频

* ```html
  <audio controls>
    <source src="music.mp3" type="audio/mpeg">
  </audio>
  ```

## 4. H5 新的input类型

### 4.1 选取颜色 color

* ```html
  <form action="demo-form.php">
    选择你喜欢的颜色: <input type="color" name="favcolor"><br>
    <input type="submit">
  </form>
  ```

### 4.2 选取日期 date

* ```html
  <form action="demo-form.php">
    生日: <input type="date" name="bday">
    <input type="submit">
  </form>
  ```

### 4.3 email

* ```html
  <form action="demo-form.php">
    E-mail: <input type="email" name="usremail">
    <input type="submit">
  </form>
  ```

### 4.4 数字number

* ```html
  <form action="demo-form.php">
    数量 ( 1 到 5 之间): <input type="number" name="quantity" min="1" max="5">
    <input type="submit">
  </form>
  <!--还有很多限定条件-->
  ```

### 4.5 滑动条 range

* ```html
  <form action="demo-form.php" method="get">
  Points: <input type="range" name="points" min="1" max="10">
  <input type="submit">
  </form>
  ```

### 4.6 搜索域 search

* ```html
  <form action="demo-form.php">
    Search Google: <input type="search" name="googlesearch"><br>
    <input type="submit">
  </form>
  ```

### 4.7 URL

* ```html
  <form action="demo-form.php">
    添加你的主页: <input type="url" name="homepage"><br>
    <input type="submit">
  </form>
  ```

## 5. H5 表单元素

### 5.1 选项列表 `<datalist>`

* ```html
  <form action="demo-form.php" method="get">
  <input list="browsers" name="browser">
  <datalist id="browsers">
    <option value="Internet Explorer">
    <option value="Firefox">
    <option value="Chrome">
    <option value="Opera">
    <option value="Safari">
  </datalist>
  <input type="submit">
  </form>
  ```

### 5.2 autofocus 属性

* ```html
  <form action="demo-form.php">
    First name: <input type="text" name="fname" autofocus><br>
      <!-- input 输入域在页面载入时自动聚焦-->
    <input type="submit">
  </form> 
  ```

### 5.3 图片提交按钮

* ```html
  <form action="demo-form.php">
    First name: <input type="text" name="fname"><br>
    Last name: <input type="text" name="lname"><br>
    <input type="image" src="img_submit.gif"  alt="Submit" width="48" height="48">
  </form>
  ```

## 6. H5 Web储存

### 6.1 localStorage和sessionStorage

* localStorage - 用于长久保存整个网站的数据，保存的数据没有过期时间，直到手动去除。
* sessionStorage - 用于临时保存同一窗口(或标签页)的数据，在关闭窗口或标签页之后将会删除这些数据。



***

### 未完待更

