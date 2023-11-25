# HTML

## 什么是HTML
HTML诞生于1999年，从那以后Web世界已经发生了巨变。HTML5的出现使Web世界的HTML更加丰富，现在很多浏览器已经具备了支持HTML5。

新的HTML5增加了一些有趣的特性
* 用于绘画的canvas元素
* 用于媒介回放的video和audio元素
* 对本地离线存储的更好的支持
* 新的特殊内容元素
    - article
    - footer
    - header
    - nav
    - section
* 新的表单控件
    - calendar
    - date
    - time
    - email
    - url
    - search


## <!DOCTYPE>是什么
`<!doctype>`必须位于HTML5文档中的第一行，使用非常简单。
它的功能如下:
1. 定义文档类型，使用它生命了文档类型，指示浏览器使用哪个HTML规范来解析文档。不同的HTML版本有不同的规范和特性，因此制定正确的文档类型非常重要。
2. 规范浏览器的渲染模式，它可以影响浏览器的渲染模式。在标准模式下，浏览器会按照规范进行渲染，在怪异模式下，浏览器会尝试向后兼容旧版本的HTML,可能导致不一致的渲染结果。
3. 提供验证信息，它同事提供了验证工具用于检查HTML文档的正确性。验证工具可以根据文档类型定义的规范来验证标记的正确性，帮助开发者检测和修复HTML错误。

```html
<!DOCTYPE html>
```
### 最小的HTML文档
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>文档标题</title>
</head>
 
<body>
文档内容......
</body>
 
</html>
```


> 注意:对于中文网页需要使用<meta charset="utf8">声明编码，否则会出现乱码

### HTML5的改进
* 新元素
* 新属性
* 支持css3
* video和audio
* 2d/3d制图
* 本地存储
* 本地sql数据
* web应用

### HTML5多媒体
使用 HTML5 你可以简单的在网页中播放 视频(video)与音频 (audio) 。

* `<video>`
* `<audio>`

### HTML5应用
* 本地数据存储
* 访问本地文件
* 本地sql数据
* 缓存引用
* javascript工作者
* XHTMLHttpRequest2

### HTML5图形
* `<canvas></canvas>`元素
* 内联SVG
* css3 2d转换、3d转换

### HTML5使用css3
* 新选择器
* 新属性
* 动画
* 2d/3d转换
* 圆角
* 阴影效果
* 可下载字体

### 语义元素

| 标签       | 描述                                                     |
| ---------- | -------------------------------------------------------- |
| article    | 定义页面独立的内容区域                                   |
| aside      | 定义页面的侧边栏内容                                     |
| bdi        | 允许您设置一段文本，使其脱离父元素的文本方向设置         |
| command    | 定义命令按钮，比如单选按钮、复选框或者按钮               |
| details    | 用于描述文档或文档某部分的细节                           |
| dialog     | 定义对话框，比如提示框                                   |
| summary    | 标签包含details元素的标题                                |
| figure     | 规定独立的流内容（图像、图表、照片、代码等等）           |
| figcaption | 定义figure的标题                                         |
| footer     | 定义section或document的页脚                              |
| header     | 定义文档的头部                                           |
| mark       | 定义带有记号的文本                                       |
| meter      | 定义度量衡，仅用于已知最大和最小值的度量                 |
| nav        | 定义导航链接的部分                                       |
| progress   | 定义任何类型的任务的进度                                 |
| ruby       | 定义ruby注释（中文注音或字符）                           |
| rt         | 定义字符（中文注音或字符）的解释或发音                   |
| rp         | 在ruby注释中使用，定义不支持ruby元素的浏览器所显示的内容 |
| section    | 定义文档中的节（section、区段）                          |
| time       | 定义日期和时间                                           |
| wbr        | 规定在文本中的何处适合添加换行符                         |

### HTML5表单

新表单元素，新属性，新输入类型，自动验证

### 视频实例

```html
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
</head>
<body>
 
<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
  你的浏览器不支持 video 标签。
</video>
 
</body>
</html>
```

### 支持HTML5的浏览器

- safari
- chrome
- firefox
- edge

### IE9以下浏览器支持HTML5的方法

使用静态资源`html5shiv`包

```
<!--[if lt IE 9]>
    <script src="http://cdn.static.runoob.com/libs/html5shiv/3.7/html5shiv.min.js"></script>
<![endif]-->
```

载入后，初始化新标签的css

```
/*html5*/
article,aside,dialog,footer,header,section,nav,figure,menu{display:block}
```

### 自定义标签

你可以为HTML添加自定义标签，自定义标签名称是myHero

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>为 HTML 添加新元素</title>
<script>
document.createElement("myHero")
</script>
<style>
myHero {
    display: block;
    background-color: #ddd;
    padding: 50px;
    font-size: 30px;
}
</style> 
</head>
<body>
<h1>我的第一个标题</h1>
<p>我的第一个段落。</p>
<myHero>我的第一个新元素</myHero>
</body>
</html>
```

### HTML5新元素

**canvas**

| 标签   | 描述                                                         |
| ------ | ------------------------------------------------------------ |
| canvas | 标签定义图形，比如图表和其他图像，这个标签基于javascript的绘图api |

**多媒体元素**

| 标签   | 描述                                     |
| ------ | ---------------------------------------- |
| audio  | 定义音频内容                             |
| video  | 定义视频                                 |
| source | 定义多媒体资源 video或者audio的子标签    |
| embeb  | 定义嵌入的内容，比如插件                 |
| track  | 为video和audio标签的媒介规定外部文本轨道 |

**新表单元素**

| 标签     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| datalist | 定义选项列表，与input标签配合使用，它是用来定义input可能的值 |
| keygen   | 定义用于表单密钥对生成器字段                                 |
| output   | 定义不同类型的输出，比如脚本的输出。                         |

**新的语义和结构标签**

| 标签       | 描述                                                     |
| ---------- | -------------------------------------------------------- |
| article    | 定义页面独立的内容区域                                   |
| aside      | 定义页面的侧边栏内容                                     |
| bdi        | 允许设置一段文本，使其脱离其父标签的文本方向设置         |
| command    | 定义命令按钮，比如单选按钮、复选按钮、普通按钮           |
| details    | 用于描述文档或文档某个部分的细节                         |
| dialog     | 定义对话框，比如提示框                                   |
| summary    | 标签包含details元素的标题                                |
| figure     | 规定独立的流内容（图像、图表、照片、代码等等）           |
| figcaption | 定义figure标签的标题                                     |
| footer     | 定义section或document的页脚                              |
| header     | 定义文档头部区域                                         |
| mark       | 定义带记号的文本                                         |
| meter      | 定义度量衡，仅用于最大值和最小值的度量衡                 |
| nav        | 定义导航链接部分                                         |
| progress   | 定义任何类型的任务和进度                                 |
| ruby       | 定义ruby注释（中文注音或者字符）                         |
| rt         | 定义字符（中文注音或字符）的解释或发音                   |
| rp         | 在ruby注释中使用，定义不支持ruby标签的浏览器所显示的内容 |
| section    | 定义文档中的节（section、区段）                          |
| time       | 定义日期和时间                                           |
| wbr        | 规定在文本中的何处适合添加换行符                         |

## Canvas

`<canvas>`标签定义图形，比如图表和其他图像，你必须使用脚本来绘制图形。

### 创建画布

```
<canvas width="200" height="100" id="myCanvas"></canvas>
```

### 使用javascript来绘制图像

canvas标签是没有绘图能力的，所有的绘制工作必须在javascript内容完成

```javascript
var c = document.getElementById("myCanvas");
var ctx = getContext("2d");
ctx.fillStyle = "#FF0000";
ctx.fillRect(0, 0, 150, 75);
```

#### 实例解析

首先找到id名称为myCanvas的标签

```javascript
var c = document.getElementById("myCanvas");
```

然后，创建context对象

```javascript
var ctx = getContext("2d");
```

getContext("2d")对象内建的HTML5对象，拥有多种绘制路径、矩形、圆形】字符以及添加图像的方法

下面的两行代码绘制一个红色的矩形

```javascript
ctx.fillStyle = "#FF0000";
ctx.fillRect(0, 0, 150, 75);
```

fillStyle属性可以是css颜色，渐变或者图案。fillStyle默认设置是#000000（黑色）

fillRect(x,y,width,height)方法定义了矩形当前的填充方式。

### Canvas坐标

canvas是一个二维网格，canvas的左上角坐标为(0,0)。fillRect方法拥有参数(0,0,150,75) 意思是在画布上绘制150x75的矩形，从左上角（0，0）开始。

### Canvas路径

在Canvas上划线，我们将使用下面两种方法

1. moveTo(x, y)定义线条开始坐标
2. lineTo(x, y)定义线条结束坐标

绘制线条必须使用到"link"的方法，就像stroke()

#### 实例

定义开始坐标为(0, 0)和结束坐标(200, 100), 然后使用stroke()方法来绘制线条

```javascript
var c = document.getElementById("myCanvas");
var ctx = c.getContext("2d");
ctx.moveTo(0, 0);
ctx.lineTo(200, 100);
ctx.stroke();
```

### Canvas绘制圆形

在canvas绘制圆形，我们使用以下方法：

`arc(x, y, r, start, stop)`

绘制圆形时使用了"link"的方法，比如stroke()或者fill()

#### 实例

使用arc()方法绘制一个圆

```javascript
var c = document.getElementById("myCanvas");
var ctx = c.getContext("2d");
ctx.beginPath();
ctx.arc(95, 50, 40, 0, 2*Math.PI);
ctx.stroke();
```

### Canvas绘制文本

在canvas绘制文本，重要的属性和方法如下：

* font 定义字体
* fillText(text, x, y) 在canvas上绘制实心的文本
* strokeText(text, x, y) 在canvas上绘制空心的文本

#### 实例

**使用fillText**

```javascript
var c = document.getElementById("myCanvas");
var ctx = c.getContext("2d");
ctx.font = "30px Arial";
ctx.fillText("hello world", 10, 50);
```

**使用strokeText**

```javascript
var c = document.getElementById("myCanvas");
var ctx = c.getContext("2d");
ctx.font = "30px Arial";
ctx.strokeText("hello world", 10, 50);
```

### Canvas绘制渐变

渐变可以填充在矩形、圆形、线条、文本等等，各种形状可以自定义不同的颜色。以下有两种不同的方式来设置canvas的渐变。

* createLinearGradient(x, y, x1, y1) 创建线条渐变
* createRadialGradient(x, y, r, x1, y1, r1) 创建一个径向/圆渐变

使用渐变时，必须使用两种或两种以上的停止颜色。addColorStop()方法指定颜色停止，参数使用坐标来描述，可以是0至1。

使用渐变时，设置fillStyle或strokeStyle的值为渐变，然后绘制形状，如矩形、文本、或一条线，

#### 实例

**使用createLinearGradient**

```javascript
var c = document.getElementById("myCanvas");
var ctx = c.getContext("2d");

var grd = ctx.createLinearGradient(0, 0, 200, 0);
grd.addColorStop(0, "red");
grd.addColorStop(1, "white");

ctx.fillStyle = grd;
ctx.fillRect(10, 10, 150, 80);
```

**使用createRadialGradient**

```javascript
var c = document.getElementById("myCanvas");
var ctx = c.getContext("2d");

var grd = ctx.createRadialGradient(75， 50，5, 90，60, 100 );
grd.addColorStop(0, "red");
grd.addColorStop(1, "white");

ctx.fillStyle = grd;
ctx.fillRect(10, 10, 150, 80);
```

### Canvas绘制图像

把一幅画放到话不上，使用以下方法

* drawImage(image, x, y)

#### 实例

把一幅画放置到画布上

```javascript
var c = document.getElementById("myCanvas");
var ctx = c.getContext("2d");
var img = document.getElementById("scream");
ctx.drawImage(img, 10,10);
```

