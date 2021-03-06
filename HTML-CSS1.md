# 2017-8-12

## 完成情况

1. HTML的常用标签

## 相关知识点总结

1. 什么是HTMl?

答: 页面可以包含图片,音频,链接等非文本元素的超文本标记语言,主要用于描述文档的内容.

2. 如何正确理解后缀名?

答: 后缀名和文件没有什么直接联系,它只是决定了文件的打开方式,真正决定文件类型的是问价的内容.

3. HTML的基本结构以及基本结构里面标签的含义

```html
<!DOCTYPE>   ---->文档类型声明
<html></html> ---->整个文档页面
<meta/>      ---->设置页面编码格式，关键字，以及页面的描述
<title></title> --------->标题部分
<head></head>   ------>页面的头部分
<body></body>   ------>页面的主体部分
```

4. Doctype作用？严格模式与混杂模式如何区分？它们有何意义?

答:

Doctype的作用:位于整个文档的最前面,告知浏览器以什么规范解析整个文档,但是它不是一个HTML标签

严格模式:又称标准模式,是指浏览器按照 W3C 标准解析代码,

混杂模式: 又称兼容模式,是指浏览器用自己的方式解析代码

DTD:文档类型定义(Document Type Definition)是一套为了进行程序间的数据交换而建立的关于标记符的语法规则.

如何区分: 浏览器解析时到底使用严格模式还是混杂模式，与网页中的 DTD 直接相关.

***
1. 如果文档包含严格的 DOCTYPE ，那么它一般以严格模式呈现。（严格 DTD ——严格模式） 
2. 包含过渡 DTD 和 URI 的 DOCTYPE ，也以严格模式呈现，但有过渡 DTD 而没有 URI （统一资源标识符，就是声明最后的地址）会导致页面以混杂模式呈现。（有 URI 的过渡 DTD ——严格模式；没有 URI 的过渡 DTD ——混杂模式） 
3. DOCTYPE 不存在或形式不正确会导致文档以混杂模式呈现。（DTD不存在或者格式不正确——混杂模式）
4. HTML5 没有 DTD ，因此也就没有严格模式与混杂模式的区别，HTML5 有相对宽松的语法，实现时，已经尽可能大的实现了向后兼容。（ HTML5 没有严格和混杂之分）
***

意义:可以做到各个浏览器兼容

5. HTML5 为什么只需要写 <!DOCTYPE HTML>？

答:html5不基于SGML(标准通用标记语言),因此不需要对DTD进行引用，但是需要doctype来规范浏览器的行为（让浏览器按照他们应该的方式来运行）

   而HTML4.01基于SGML，所以需要对DTD进行引用，才能告知浏览器文档所使用的文档类型。

6. HTMl常用标签及分类

注释: <!--我是注释 --->

***
```
行内元素:<strong>、<b>、<em>、<i>、<del>、<s>、<ins>、<u>、<a>、<span>等，其中<span>标记最典型的行内元素。
```
1.  总在新行上开始，占据一整行
2. 默认情况下，其宽度自动填满其父元素宽度
3. 宽度始终是与浏览器宽度一样，与内容无关
4. 它可以容纳内联元素和其他块元素
5. display属性为block
6. 块级元素的垂直相邻外边距margin会合并。
***

***
块级元素:
```
<h1>~<h6>、<p>、<div>、<ul>、<ol>、<li>等，其中<div>标记是最典型的块元素。
```
1. 和其他元素都在一行上
2. 高，行高及外边距和内边距部分可改变
3. 宽度只与内容有关
4. 行内元素只能容纳文本或者其他行内元素
5. display属性为inline
6. 水平方向的padding-left、padding-right、margin-left、margin-right都产生边距效果，
   但竖直方向的padding-top、padding-bottom、margin-top、margin-bottom却不会产生边距效果。
   不可以设置宽高，其宽度随着内容增加，高度随字体大小而改变，内联元素可以设置外边界，但是外边界不对上下起作用，只能对左右起作用
***
***
空(void)元素: 

```
<img />,<br />,<hr />, <input />
```
1. 没有内容的 HTML 内容被称为空元素。空元素是在开始标签中关闭的。
2. <br /> 就是没有关闭标签的空元素（<br /> 标签定义换行）。
3. 在 XHTML、XML 以及未来版本的 HTML 中，所有元素必须被关闭。
4. 在开始标签中添加斜杠，比如 <br />，是关闭空元素的正确方法，HTML、XHTML 和 XML 都接受这种方式。即使 <br> 在所有浏览器中都是有效的，但使用 <br /> 其实是更长远的保障。
***
***
行内块元素:
```
<img />、<input />、<td>,可以对它们设置宽高和对齐属性，有些资料可能会称它们为行内块元素
```
***

7. 什么是语义化?为什么要用语义化的标签?

语义化是指用合理HTML标记以及其特有的属性去格式化文档内容。通俗地讲,语义化就是对数据和信息进行处理,使得机器可以理解.

***
1. 对搜索引擎友好,有助于爬虫抓取更多有效信息
2. 利于其他设备(如盲人阅读器)的解析,可以无障碍阅读.
3. 在没有CSS的样式情况下,清晰的显示文档结构,便于开发者阅读和写出优雅的代码
***
常用的语义化标签有:section，side，article，header，footer，nav,canvas,audio,video

如何在低版本上可以使用语义化标签:以hack的形式,添加补丁

```
  <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
      <script src="https://cdn.bootcss.com/html5shiv/3.7.3/html5shiv.min.js"></script>
      <script src="https://cdn.bootcss.com/respond.js/1.4.2/respond.min.js"></script>
    <![endif]-->
```
如何自定义一个标签可以使用:document.createElement创建标签，然后给对应标签一定CSS属性

8. a标签使用:

```html
<a href="" target="">链接</a>
target:_self和_blank
```
9. 如何创建一个锚点?

```html
<!-- 1. 给要跳转的位置设定一个id --->
<p id="k"></p>
<!-- a标签的href写#id名 --->
<a href="#k">跳转锚点</a>
```

10. meta标签的使用

[meta](https://segmentfault.com/a/1190000002407912)

```html
<meta  content="" http-equiv="" name=""/>
```
常见用途有:

(1) 设置编码格式

```html
<meta charset="UTF-8">
```
(2) 定时页面跳转和刷新(content中间用分号隔开)

```html
<meta http-equiv="refresh" content="5;url='http://www.baidu.com'" />
```

(3) 搜索引擎的检索方式(content中用逗号隔开)

```html
<meta name="robots" content="index,follow" />
<!-- all：文件将被检索，且页面上的链接可以被查询；
    none：文件将不被检索，且页面上的链接不可以被查询；
    index：文件将被检索；
    follow：页面上的链接可以被查询；
    noindex：文件将不被检索；
    nofollow：页面上的链接不可以被查询。
-->
```

(4) 移动设备viewport:如果不是响应式网站，不要使用initial-scale或者禁用缩放。

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0,maximum-scale=1.0, user-scalable=no"/>
<!-- `width=device-width` 会导致 iPhone 5 添加到主屏后以 WebApp 全屏模式打开页面时出现黑边  -->
```

11. 页面浏览器标题前的logo怎么设置?

```html
<head>
<link rel="icon" href="图片位置" type="image/x-icon"/ media='screen'>
</head>
```
