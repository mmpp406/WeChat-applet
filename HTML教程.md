# 1 简介

超文本标记语言（英语：HyperText Markup Language，简称：HTML）是一种用于**创建网页**的标准标记语言。

您可以使用 HTML 来建立自己的 WEB 站点，HTML 运行在浏览器上，由**浏览器**来解析。

- HTML 指的是超文本标记语言: **H**yper**T**ext **M**arkup **L**anguage
- HTML 不是一种编程语言，而是一种**标记**语言
- 标记语言是一套**标记标签** (markup tag)
- HTML 使用标记标签来**描述**网页
- HTML 文档包含了HTML ==**标签**==及==**文本**==内容
- HTML文档也叫做 **web 页面**

## 1.1 HTML实例

```html
<!DOCTYPE html>  <!-- 声明为HTML5文档 -->
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>
    <h1>我的第一个标题</h1>
    <p>我的第一个段落。</p>
</body>
</html>
```

实例解析：

![img](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203092256694.jpeg)

- **<!DOCTYPE html>** ==声明为 HTML5 文档==
- **<html>**==元素是 HTML 页面的根元素==
- **<head>** 元素==包含了文档的元（meta）数据==，如 **<meta charset="utf-8">** 定义网页编码格式为 **utf-8**。
- **<title>** 元素==描述了文档的标题==
- **<body>** 元素==包含了可见的页面内容==
- **<h1>** 元素定义一个==大标题==
- **<p>** 元素定义一个==段落==

**注：**在浏览器的页面上使用键盘上的**F12** 按键开启调试模式，就可以看到组成标签。

## 1.2 HTML文档的后缀名

- .html
- .htm

以上两种后缀名没有区别，都可以使用。

## 1.3 HTML标签

HTML 标记标签通常被称为 HTML 标签 (**HTML tag)**。

- HTML 标签是由***尖括号***包围的关键词，比如 <html>
- HTML 标签通常是***成对出现***的，比如 \<b> 和 \</b>
- 标签对中的*第一个标签是*==开始标签==*，第二个标签是*==结束标签==
- 开始和结束标签也被称为==*开放标签*和*闭合标签*==

```html
<标签>内容</标签>
```

## 1.4 HTML元素

"HTML 标签" 和 "HTML 元素" 通常都是描述同样的意思.

但是严格来讲, 一个 HTML 元素包含了开始标签与结束标签，如下实例:

**HTML元素: **

```html
<p>这是一个段落。</p>
```

## 1.5 Web浏览器

Web浏览器（如谷歌浏览器，Internet Explorer，Firefox，Safari）是用于**读取HTML文件，并将其作为网页显示。**

浏览器并不是直接显示的HTML标签，但可以**使用标签来决定如何展现HTML页面的内容给用户**

## 1.6 HTML网页结构

下面是一个可视化的HTML页面结构：

```html
<html>

<head>

<title>页面标题</title>

</head>

<body>

<h1>这是一个标题</h1>

<p>这是一个段落。</p>

<p>这是另外一个段落。</p>

</body>

</html>
```

> 只有 <body> 区域才会在浏览器中显示。

## 1.7 <!DOCTYPE> 声明

\<!DOCTYPE>声明有助于浏览器中**正确显示网页**

网络上有很多不同的文件，如果能够正确声明HTML的版本，浏览器就能正确显示网页内容。

doctype 声明是不区分大小写的，以下方式均可：

```html
<!DOCTYPE html>

<!DOCTYPE HTML>

<!doctype html>

<!Doctype Html>
```

## 1.8 中文编码

目前在大部分浏览器中，直接输出中文会出现中文乱码的情况，这时候我们就需要在==头部==**将字符声明为 UTF-8 或 GBK。**

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>
页面标题</title>
</head>
<body>
 
<h1>我的第一个标题</h1>
 
<p>我的第一个段落。</p>
 
</body>
</html>
```

# 2 HTML 样式-CSS

CSS (Cascading Style Sheets) **用于渲染HTML元素标签的样式。**

![image-20220310190436289](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203101904360.png)

## 2.1 如何使用CSS

CSS 是在 HTML 4 开始使用的,是为了更好的渲染HTML元素而引入的.

CSS 可以通过以下方式添加到HTML中:

- **内联样式**- 在HTML元素中使用"style" **属性**
- **内部样式表** -在HTML文档头部 <head> 区域使用<style> **元素** 来包含CSS
- **外部引用** - 使用外部 CSS **文件**

> 最好的方式是通过外部引用CSS文件

## 2.2 内联样式

当特殊的样式需要==应用到个别元素==时，就可以==使用内联样式==。 使用内联样式的方法是在相关的标签中使用样式属性。样式属性可以包含任何 CSS 属性。以下实例显示出如何改变段落的颜色和左外边距

```html
<p style="color:blue;margin-left:20px;">这是一个段落。</p>
```

## 2.3 内部样式表

当==单个文件需要特别样式==时，就可以==使用内部样式表==。你可以在<head> 部分通过 <style>标签定义内部样式表:

```html
<head>
<style type="text/css">
body {background-color:yellow;}
p {color:blue;}
</style>
</head>
```

## 2.4 外部样式表

==当样式需要被应用到很多页面的==时候，==外部样式表将是理想的选择==。使用外部样式表，你就可以通过更改一个文件来改变整个站点的外观。

````html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
````

## 2.5 HTML样式标签

![image-20220310191736914](https://gitee.com/China_Tencent/typora_images/raw/master/img/202203101917935.png)

# 3 学习链接

1. https://www.runoob.com/html/html-intro.html

2. HTML 样式- CSS：https://www.runoob.com/html/html-css.html

