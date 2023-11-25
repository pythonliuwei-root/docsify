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

