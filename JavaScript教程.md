# 1 JavaScript简介

JavaScript 是互联网上最流行的**脚本语言**，这门语言可用于 HTML 和 web，更可广泛用于服务器、PC、笔记本电脑、平板电脑和智能手机等设备。

## 1.1 为什么学习 JavaScript?

JavaScript 是 web 开发人员必须学习的 3 门语言中的一门：

1. **HTML** 定义了网页的内容
2. **CSS** 描述了网页的布局
3. **JavaScript** 控制了网页的行为

本教程是关于 JavaScript 及介绍 JavaScript 如何与 HTML 和 CSS 一起工作。

## 1.2 JavaScript 是脚本语言

JavaScript 是一种**轻量级**的编程语言。

JavaScript 是**可插入 HTML 页面**的编程代码。

JavaScript 插入 HTML 页面后，可由所有的现代浏览器执行。

JavaScript 很容易学习。

## 1.3 JavaScript：直接写入 HTML 输出流

实例：

```javascript
document.write("<h1>这是一个标题</h1>");
document.write("<p>这是一个段落。</p>");
```

运行结果：

![image-20220310203522831](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203102035879.png)

> 注：您只能在 HTML 输出中使用 document.write。如果您在文档加载后使用该方法，会覆盖整个文档。

## 1.4 JavaScript：对事件的反应

实例：

```html
<button type="button" onclick="alert('欢迎!')">点我!</button>
```

![image-20220310204120021](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203102041065.png)

**alert() 函数**在 JavaScript 中并不常用，但它对于代码测试非常方便。

**onclick 事件**只是您即将在本教程中学到的众多事件之一。

## 1.5 JavaScript：改变 HTML 内容

使用 JavaScript 来处理 HTML 内容是非常强大的功能。

实例：

```javascript
x=document.getElementById("demo");  //查找元素
x.innerHTML="Hello JavaScript";    //改变内容
```

运行结果：

运行前（点击按钮前）：

![image-20220310204618203](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203102046248.png)

运行后（点击按钮后）：

![image-20220310204705471](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203102047514.png)

您会经常看到 **document.getElementById("*****some id*****")**。这个方法是 HTML DOM 中定义的。

DOM (**D**ocument **O**bject **M**odel)（文档对象模型）是==用于访问 HTML== 元素的正式 W3C 标准

## 1.6 JavaScript：改变 HTML 图像

本例会动态地改变 HTML <image> 的来源（src）：

实例：

```html
<script>
function changeImage()
{
    element=document.getElementById('myimage')
    if (element.src.match("bulbon"))
    {
        element.src="/images/pic_bulboff.gif";
    }
    else
    {
        element.src="/images/pic_bulbon.gif";
    }
}
</script>
<img loading="lazy" id="myimage" onclick="changeImage()" src="/images/pic_bulboff.gif" width="100" height="180">
```

![image-20220310205143008](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203102051032.png)

**解析：**

*以上实例中代码* **element.src.match("bulbon")** *的作用意思是：检索* **\<img id="myimage" onclick="changeImage()" src="images/pic_bulboff.gif" width="100" height="180">** *里面 src 属性的值有没有包含* **bulbon** *这个字符串，如果存在字符串* **bulbon**，图片 **src** *更新为* **bulboff.gif**，若匹配不到 **bulbon** 字符串，**src *则更新为* **bulbon.gif

> 注：JavaScript 能够改变任意 HTML 元素的大多数属性，而不仅仅是图片。

## 1.7 JavaScript：改变 HTML 样式

实例：

```javascript
x=document.getElementById("demo")  //找到元素 
x.style.color="#ff0000";           //改变样式
```

![image-20220310205716252](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203102057294.png)

## 1.8 JavaScript：验证输入

JavaScript 常用于验证用户的输入。

```javascript
if isNaN(x) {
    alert("不是数字");
}
```

![image-20220310210021143](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203102100191.png)

> 提示：
>
> JavaScript 与 Java 是**两种完全不同的语言**，无论在概念上还是设计上。
> Java（由 Sun 发明）是更复杂的编程语言。
>
> ECMA-262 是 JavaScript 标准的官方名称。
>
> JavaScript 由 Brendan Eich 发明。它于 1995 年出现在 Netscape 中（该浏览器已停止更新），并于 1997 年被 ECMA（一个标准协会）采纳。

# 2 用法

HTML 中的脚本必须位于 <script> 与 </script> 标签之间。

脚本可被放置在 HTML 页面的 <body> 和 <head> 部分中。

## 2.1 \<script\> 标签

如需在 HTML 页面中插入 JavaScript，请使用 <script> 标签。

<script> 和 </script> 会告诉 JavaScript 在何处开始和结束。

<script> 和 </script> 之间的代码行包含了 JavaScript:

```html
<script>
alert("我的第一个 JavaScript");
</script>
```

您无需理解上面的代码。只需明白，浏览器会解释并执行位于 \<script> 和 \</script>之间的 JavaScript 代码 

>那些老旧的实例可能会在 <script> 标签中使用 type="text/javascript"。现在已经不必这样做了。JavaScript 是所有现代浏览器以及 HTML5 中的默认脚本语言。

## 2.2 \<body> 中的 JavaScript

在本例中，JavaScript 会在页面加载时向 HTML 的\<body> 写文本：

**实例：**

```html
<!DOCTYPE html>
<html>
<body>
.
.
<script>
document.write("<h1>这是一个标题</h1>");
document.write("<p>这是一个段落</p>");
</script>
.
.
</body>
</html>
```

运行结果：

![image-20220310212115145](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203102121193.png)

## 2.3 JavaScript 函数和事件

上面例子中的 JavaScript 语句，会在页面加载时执行。

通常，我们需要在某个事件发生时执行代码，比如当用户点击按钮时。

如果我们**把 JavaScript 代码放入函数中**，就可以**在事件发生时调用该函数。**

## 2.4 在\<head> 或者 \<body> 的JavaScript

您可以在 HTML 文档中放入不限数量的脚本。

脚本可位于 HTML 的 <body> 或 <head> 部分中，或者同时存在于两个部分中。

通常的做法是把函数**放入 <head> 部分中**，**或者放在页面底部**。这样就可以把它们安置到同一处位置，不会干扰页面的内容。

## 2.5  \<head> 中的 JavaScript 函数

在本例中，我们把一个 JavaScript 函数放置到 HTML 页面的\<head> 部分。

该函数会在点击按钮时被调用：

```html
<!DOCTYPE html>
<html>
<head>
<script>
function myFunction()
{
    document.getElementById("demo").innerHTML="我的第一个 JavaScript 函数";
}
</script>
</head>
<body>
<h1>我的 Web 页面</h1>
<p id="demo">一个段落</p>
<button type="button" onclick="myFunction()">尝试一下</button>
</body>
</html>
```

在本例中，我们把一个 JavaScript 函数放置到 HTML 页面的 <body> 部分。

该函数会在点击按钮时被调用：

```html
<!DOCTYPE html>
<html>
<body>
<h1>我的 Web 页面</h1>
<p id="demo">一个段落</p>
<button type="button" onclick="myFunction()">尝试一下</button>
<script>
function myFunction()
{
    document.getElementById("demo").innerHTML="我的第一个 JavaScript 函数";
}
</script>
</body>
</html>
```

## 2.6 外部的 JavaScript

也可以把脚本保存到外部文件中。外部文件通常包含被多个网页使用的代码。

外部 JavaScript 文件的文件扩展名是 .js。

==如需使用外部文件，请在\<script> 标签的 "src" 属性中设置该 .js 文件：==

```html
<!DOCTYPE html>
<html>
<body>
<script src="myScript.js"></script>
</body>
</html>
```

你可以将脚本放置于 \<head> 或\<body>中，放\<script> 标签中的脚本与外部引用的脚本运行效果完全一致。

myScript.js 文件代码如下：

```javascript
function myFunction()
{
    document.getElementById("demo").innerHTML="我的第一个 JavaScript 函数";
}
```

> 注：外部脚本不能包含 <script> 标签。

# 3 Chrome 浏览器中执行 JavaScrip

## 3.1 Console 窗口调试 JavaScript 代码

打开开发者工具后，我们可以在 Console 窗口调试 JavaScript代码，如下图：

![img](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203102138268.jpeg)

上图中我们在 **>** 符号后输入我们要执行的代码 **console.log("runoob")**，按回车后执行。

我们也可以在其他地方复制一段代码过来执行，比如复制以下代码到 Console 窗口，按回车执行：

```javascript
console.log("runoob-1")
console.log("runoob-2")
```

![img](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203102138750.jpeg)

清空 Console 窗口到内容可以按以下按钮：

![img](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203102139736.jpeg)

## 3.2 Chrome snippets 小脚本

我们也可以在 Chrome 浏览器中创建一个脚本来执行，在开发者工具中点击 Sources 面板，选择 Snippets 选项卡，在导航器中右击鼠标，然后选择 Create new snippet 来新建一个脚本文件：

![img](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203111224652.jpeg)



如果你没看到 Snippets ，可以点下面板上到 **>>** 就能看到了。

![img](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203111224167.jpeg)

点击 Create new snippet 后，会自动创建一个文件，你只需在右侧窗口输入以下代码，然后按 Command+S（Mac）或 Ctrl+S（Windows 和 Linux）保存更改即可。

```javascript
console.log("runoob-1")
console.log("runoob-2")
```

保存后，右击文件名，选择 "Run" 执行代码：

![img](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203111225800.jpeg)

# 4 参考链接

1. https://www.runoob.com/js/js-tutorial.html

