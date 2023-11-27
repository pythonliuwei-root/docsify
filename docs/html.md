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

### 颜色、样式和阴影

| 属性          | 描述                                     |
| ------------- | ---------------------------------------- |
| fillStyle     | 设置或返回用于填充绘画的颜色、渐变或模式 |
| strokeStyle   | 设置或返回用于笔触的颜色、渐变或模式     |
| shadowColor   | 设置或返回用于阴影的颜色                 |
| shadowBlur    | 设置或返回用于引用的模糊级别             |
| shadowOffsetX | 设置或返回阴影与形状的水平距离           |
| shadowOffsetY | 设置或返回阴影与形状的垂直距离           |

| 方法                   | 描述                                      |
| ---------------------- | ----------------------------------------- |
| createLinearGradient() | 创建线性渐变(用在画布内容上)              |
| createPattern()        | 在指定的方向上重复指定的元素              |
| createRadialGradient() | 创还能放射状/环状的渐变（用在画布内容上） |
| addColorStop()         | 规定渐变对象中的颜色和停止位置            |

### 线条样式

| 属性       | 描述                                       |
| ---------- | ------------------------------------------ |
| lineCap    | 设置或返回线条的结束端点样式               |
| lineJoin   | 设置或返回两条线相交时，所创建的拐角类型。 |
| lineWidth  | 设置或返回当前的线条宽度                   |
| miterLimit | 设置或返回最大斜接长度                     |

### 矩形

| 方法         | 描述                         |
| ------------ | ---------------------------- |
| rect()       | 创建矩形                     |
| fillRect()   | 绘制"被填充"的矩形           |
| strokeRect() | 绘制矩形(无填充)             |
| clearRect()  | 在给定的矩形内清除指定的像素 |

### 路径

| 方法                                                         | 描述                                                      |
| ------------------------------------------------------------ | --------------------------------------------------------- |
| fill()                                                       | 填充当前绘图（路径）                                      |
| stroke()                                                     | 绘制已定义的路径                                          |
| beginPath()                                                  | 起始一条路径,或重置当前路径                               |
| moveTo()                                                     | 把路径移动到画布中的指定点，不创建线条                    |
| closePath()                                                  | 创建从当前点回到起始点的路径                              |
| lineTo()                                                     | 添加一个新店，然后再画布中创还能从该店到最后指定点的线条  |
| clip()                                                       | 从原始画布剪切任意形状和尺寸的区域                        |
| [quadraticCurveTo()](https://www.runoob.com/tags/canvas-quadraticcurveto.html) | 创建二次贝塞尔曲线。                                      |
| [bezierCurveTo()](https://www.runoob.com/tags/canvas-beziercurveto.html) | 创建三次贝塞尔曲线。                                      |
| [arc()](https://www.runoob.com/tags/canvas-arc.html)         | 创建弧/曲线（用于创建圆形或部分圆）。                     |
| [arcTo()](https://www.runoob.com/tags/canvas-arcto.html)     | 创建两切线之间的弧/曲线。                                 |
| [isPointInPath()](https://www.runoob.com/tags/canvas-ispointinpath.html) | 如果指定的点位于当前路径中，则返回 true，否则返回 false。 |

## 转换

| 方法                                                         | 描述                                             |
| :----------------------------------------------------------- | :----------------------------------------------- |
| [scale()](https://www.runoob.com/tags/canvas-scale.html)     | 缩放当前绘图至更大或更小。                       |
| [rotate()](https://www.runoob.com/tags/canvas-rotate.html)   | 旋转当前绘图。                                   |
| [translate()](https://www.runoob.com/tags/canvas-translate.html) | 重新映射画布上的 (0,0) 位置。                    |
| [transform()](https://www.runoob.com/tags/canvas-transform.html) | 替换绘图的当前转换矩阵。                         |
| [setTransform()](https://www.runoob.com/tags/canvas-settransform.html) | 将当前转换重置为单位矩阵。然后运行 transform()。 |

## 文本

| 属性                                                         | 描述                                       |
| :----------------------------------------------------------- | :----------------------------------------- |
| [font](https://www.runoob.com/tags/canvas-font.html)         | 设置或返回文本内容的当前字体属性。         |
| [textAlign](https://www.runoob.com/tags/canvas-textalign.html) | 设置或返回文本内容的当前对齐方式。         |
| [textBaseline](https://www.runoob.com/tags/canvas-textbaseline.html) | 设置或返回在绘制文本时使用的当前文本基线。 |



| 方法                                                         | 描述                         |
| :----------------------------------------------------------- | :--------------------------- |
| [fillText()](https://www.runoob.com/tags/canvas-filltext.html) | 在画布上绘制"被填充的"文本。 |
| [strokeText()](https://www.runoob.com/tags/canvas-stroketext.html) | 在画布上绘制文本（无填充）。 |
| [measureText()](https://www.runoob.com/tags/canvas-measuretext.html) | 返回包含指定文本宽度的对象。 |

## 图像绘制

| 方法                                                         | 描述                           |
| :----------------------------------------------------------- | :----------------------------- |
| [drawImage()](https://www.runoob.com/tags/canvas-drawimage.html) | 向画布上绘制图像、画布或视频。 |

## 像素操作

| 属性                                                         | 描述                                                  |
| :----------------------------------------------------------- | :---------------------------------------------------- |
| [width](https://www.runoob.com/tags/canvas-imagedata-width.html) | 返回 ImageData 对象的宽度。                           |
| [height](https://www.runoob.com/tags/canvas-imagedata-height.html) | 返回 ImageData 对象的高度。                           |
| [data](https://www.runoob.com/tags/canvas-imagedata-data.html) | 返回一个对象，其包含指定的 ImageData 对象的图像数据。 |



| 方法                                                         | 描述                                                        |
| :----------------------------------------------------------- | :---------------------------------------------------------- |
| [createImageData()](https://www.runoob.com/tags/canvas-createimagedata.html) | 创建新的、空白的 ImageData 对象。                           |
| [getImageData()](https://www.runoob.com/tags/canvas-getimagedata.html) | 返回 ImageData 对象，该对象为画布上指定的矩形复制像素数据。 |
| [putImageData()](https://www.runoob.com/tags/canvas-putimagedata.html) | 把图像数据（从指定的 ImageData 对象）放回画布上。           |

## 合成

| 属性                                                         | 描述                                     |
| :----------------------------------------------------------- | :--------------------------------------- |
| [globalAlpha](https://www.runoob.com/tags/canvas-globalalpha.html) | 设置或返回绘图的当前 alpha 或透明值。    |
| [globalCompositeOperation](https://www.runoob.com/tags/canvas-globalcompositeoperation.html) | 设置或返回新图像如何绘制到已有的图像上。 |

## 其他

| 方法          | 描述                             |
| :------------ | :------------------------------- |
| save()        | 保存当前环境的状态。             |
| restore()     | 返回之前保存过的路径状态和属性。 |
| createEvent() |                                  |
| getContext()  |                                  |
| toDataURL()   |                                  |



## HTML 音频/视频 方法

| 方法                                                         | 描述                                      |
| :----------------------------------------------------------- | :---------------------------------------- |
| [addTextTrack()](https://www.runoob.com/tags/av-met-addtexttrack.html) | 向音频/视频添加新的文本轨道。             |
| [canPlayType()](https://www.runoob.com/tags/av-met-canplaytype.html) | 检测浏览器是否能播放指定的音频/视频类型。 |
| [load()](https://www.runoob.com/tags/av-met-load.html)       | 重新加载音频/视频元素。                   |
| [play()](https://www.runoob.com/tags/av-met-play.html)       | 开始播放音频/视频。                       |
| [pause()](https://www.runoob.com/tags/av-met-pause.html)     | 暂停当前播放的音频/视频。                 |

## HTML 音频/视频属性

| 属性                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [audioTracks](https://www.runoob.com/tags/av-prop-audiotracks.html) | 返回表示可用音频轨道的 AudioTrackList 对象。                 |
| [autoplay](https://www.runoob.com/tags/av-prop-autoplay.html) | 设置或返回是否在加载完成后随即播放音频/视频。                |
| [buffered](https://www.runoob.com/tags/av-prop-buffered.html) | 返回表示音频/视频已缓冲部分的 TimeRanges 对象。              |
| [controller](https://www.runoob.com/tags/av-prop-controller.html) | 返回表示音频/视频当前媒体控制器的 MediaController 对象。     |
| [controls](https://www.runoob.com/tags/av-prop-controls.html) | 设置或返回音频/视频是否显示控件（比如播放/暂停等）。         |
| crossOrigin                                                  | 设置或返回音频/视频的 CORS 设置。                            |
| [currentSrc](https://www.runoob.com/tags/av-prop-currentsrc.html) | 返回当前音频/视频的 URL。                                    |
| [currentTime](https://www.runoob.com/tags/av-prop-currenttime.html) | 设置或返回音频/视频中的当前播放位置（以秒计）。              |
| [defaultMuted](https://www.runoob.com/tags/av-prop-defaultmuted.html) | 设置或返回音频/视频默认是否静音。                            |
| [defaultPlaybackRate](https://www.runoob.com/tags/av-prop-defaultplaybackrate.html) | 设置或返回音频/视频的默认播放速度。                          |
| [duration](https://www.runoob.com/tags/av-prop-duration.html) | 返回当前音频/视频的长度（以秒计）。                          |
| [ended](https://www.runoob.com/tags/av-prop-ended.html)      | 返回音频/视频的播放是否已结束。                              |
| [error](https://www.runoob.com/tags/av-prop-error.html)      | 返回表示音频/视频错误状态的 MediaError 对象。                |
| [loop](https://www.runoob.com/tags/av-prop-loop.html)        | 设置或返回音频/视频是否应在结束时重新播放。                  |
| [mediaGroup](https://www.runoob.com/tags/av-prop-mediagroup.html) | 设置或返回音频/视频所属的组合（用于连接多个音频/视频元素）。 |
| [muted](https://www.runoob.com/tags/av-prop-muted.html)      | 设置或返回音频/视频是否静音。                                |
| [networkState](https://www.runoob.com/tags/av-prop-networkstate.html) | 返回音频/视频的当前网络状态。                                |
| [paused](https://www.runoob.com/tags/av-prop-paused.html)    | 设置或返回音频/视频是否暂停。                                |
| [playbackRate](https://www.runoob.com/tags/av-prop-playbackrate.html) | 设置或返回音频/视频播放的速度。                              |
| [played](https://www.runoob.com/tags/av-prop-played.html)    | 返回表示音频/视频已播放部分的 TimeRanges 对象。              |
| [preload](https://www.runoob.com/tags/av-prop-preload.html)  | 设置或返回音频/视频是否应该在页面加载后进行加载。            |
| [readyState](https://www.runoob.com/tags/av-prop-readystate.html) | 返回音频/视频当前的就绪状态。                                |
| [seekable](https://www.runoob.com/tags/av-prop-seekable.html) | 返回表示音频/视频可寻址部分的 TimeRanges 对象。              |
| [seeking](https://www.runoob.com/tags/av-prop-seeking.html)  | 返回用户是否正在音频/视频中进行查找。                        |
| [src](https://www.runoob.com/tags/av-prop-src.html)          | 设置或返回音频/视频元素的当前来源。                          |
| [startDate](https://www.runoob.com/tags/av-prop-startdate.html) | 返回表示当前时间偏移的 Date 对象。                           |
| [textTracks](https://www.runoob.com/tags/av-prop-texttracks.html) | 返回表示可用文本轨道的 TextTrackList 对象。                  |
| [videoTracks](https://www.runoob.com/tags/av-prop-videotracks.html) | 返回表示可用视频轨道的 VideoTrackList 对象。                 |
| [volume](https://www.runoob.com/tags/av-prop-volume.html)    | 设置或返回音频/视频的音量。                                  |

## HTML 音频/视频事件

| 事件                                                         | 描述                                               |
| :----------------------------------------------------------- | :------------------------------------------------- |
| [abort](https://www.runoob.com/tags/av-event-abort.html)     | 当音频/视频的加载已放弃时触发。                    |
| [canplay](https://www.runoob.com/tags/av-event-canplay.html) | 当浏览器可以开始播放音频/视频时触发。              |
| [canplaythrough](https://www.runoob.com/tags/av-event-canplaythrough.html) | 当浏览器可在不因缓冲而停顿的情况下进行播放时触发。 |
| [durationchange](https://www.runoob.com/tags/av-event-durationchange.html) | 当音频/视频的时长已更改时触发。                    |
| emptied                                                      | 当目前的播放列表为空时触发。                       |
| [ended](https://www.runoob.com/tags/av-event-ended.html)     | 当目前的播放列表已结束时触发。                     |
| [error](https://www.runoob.com/tags/av-event-error.html)     | 当在音频/视频加载期间发生错误时触发。              |
| [loadeddata](https://www.runoob.com/tags/av-event-loadeddata.html) | 当浏览器已加载音频/视频的当前帧时触发。            |
| [loadedmetadata](https://www.runoob.com/tags/av-event-loadedmetadata.html) | 当浏览器已加载音频/视频的元数据时触发。            |
| [loadstart](https://www.runoob.com/tags/av-event-loadstart.html) | 当浏览器开始查找音频/视频时触发。                  |
| [pause](https://www.runoob.com/tags/av-event-pause.html)     | 当音频/视频已暂停时触发。                          |
| [play](https://www.runoob.com/tags/av-event-play.html)       | 当音频/视频已开始或不再暂停时触发。                |
| [playing](https://www.runoob.com/tags/av-event-playing.html) | 当音频/视频在因缓冲而暂停或停止后已就绪时触发。    |
| [progress](https://www.runoob.com/tags/av-event-progress.html) | 当浏览器正在下载音频/视频时触发。                  |
| [ratechange](https://www.runoob.com/tags/av-event-ratechange.html) | 当音频/视频的播放速度已更改时触发。                |
| [seeked](https://www.runoob.com/tags/av-event-seeked.html)   | 当用户已移动/跳跃到音频/视频中的新位置时触发。     |
| [seeking](https://www.runoob.com/tags/av-event-seeking.html) | 当用户开始移动/跳跃到音频/视频中的新位置时触发。   |
| [stalled](https://www.runoob.com/tags/av-event-stalled.html) | 当浏览器尝试获取媒体数据，但数据不可用时触发。     |
| [suspend](https://www.runoob.com/tags/av-event-suspend.html) | 当浏览器刻意不获取媒体数据时触发。                 |
| [timeupdate](https://www.runoob.com/tags/av-event-timeupdate.html) | 当目前的播放位置已更改时触发。                     |
| [volumechange](https://www.runoob.com/tags/av-event-volumechange.html) | 当音量已更改时触发。                               |
| [waiting](https://www.runoob.com/tags/av-event-waiting.html) | 当视频由于需要缓冲下一帧而停止时触发。             |

# HTML Emoji

Emoji 是来自 UTF-8 字符集的字符: 😄 😍 💗。

表情符号（英语：emoji，日语：絵文字／えもじ emoji），是使用在网页和聊天中的形意符号，最初是日本在无线通信中所使用的视觉情感符号（图画文字）。表情意指面部表情，图标则是图形标志的意思，可用来代表多种表情，如笑脸表示笑、蛋糕表示食物等。 Emoji 看起来像一张图片或图标，其实不是。

Emoji 实际上是 UTF-8 (Unicode) 字符集上的字符。

UTF-8 几乎涵盖了世界上所有的字符和符号。

### HTML charset 属性

想要正常显示一个 HTML 页面，浏览器就需要知道网页使用的字符集。 网页中的字符集使用 [](https://www.runoob.com/tags/tag-meta.html) 标签来指定：

```
<meta charset="UTF-8">
```

> **注：**如果我们没有刻意指定 meta 属性，默认的字符集编码也是 UTF-8。
>
> 更多 UTF-8 编码可以参考：
>
> HTML Unicode（UTF-8） 参考手册

## UTF-8 字符

很多 UTF-8 字符无法在键盘上输入，但我们可以使用数字（称为实体编号）来表示：

- A 为 65
- B 为 66
- C 为 67

## 实例

<!DOCTYPE html> <html> <head> <meta charset="UTF-8"> </head> <body>  <p>显示结果： A B C</p> <p>显示结果： &#65; &#66; &#67;</p>  </body> </html>


[尝试一下 »](https://www.runoob.com/try/try.php?filename=tryhtml_emoji)

**实例解析：**

<meta charset="UTF-8"> 定义来字符集。

A, B, 和 C 也可以使用 65, 66, 和 67 来表示。

实体编号需要以 **&#** 开头并以分号 **;** 结尾，这样才能正确显示一个字符。

同样 Emoji 也是字符，可以在 HTML 页面中跟其他字符一样使用它：

## 实例

<!DOCTYPE html> <html> <head> <meta charset="UTF-8"> </head> <body>  <h1>Emoji 标签符号</h1> <p>可以通过 font-size 属性，像设置字体大小一样，设置表情的大小。</p> <p style="font-size:48px"> &#128512; &#128516; &#128525; &#128151; </p>  </body> </html>


[尝试一下 »](https://www.runoob.com/try/try.php?filename=tryhtml_emoji2)

------

## Emoji 表情符号

下表列出来一些 Emoji 表情符号：

| Emoji | 值         |
| :---- | :--------- |
| 🗻     | & #128507; |
| 🗼     | & #128508; |
| 🗽     | & #128509; |
| 🗾     | & #128510; |
| 🗿     | & #128511; |
| 😀     | & #128512; |
| 😁     | & #128513; |
| 😂     | & #128514; |
| 😃     | & #128515; |
| 😄     | & #128516; |
| 😅     | & #128517; |
