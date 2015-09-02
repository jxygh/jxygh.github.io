---
layout: article
title: 定制列表元素li项目符号的两种方法
codedemo: true
resdir: /blogres/2015-08-27-list-style
---

#{{page.title}}
浏览器默认的列表符号是小圆点，在网页中，我们也可以使用图片替换掉小圆点。有两种方式：

##设置列表图片-list-style-image

<pre class="brush:html">
&lt;!doctype html>
&lt;html>
 &lt;head>
  &lt;meta charset="UTF-8">
  &lt;title>使用list-style-image设置列表项目图片&lt;/title>
  &lt;style>
    li{
      list-style-image:url(arrow.gif);
    }
  &lt;/style>
 &lt;/head>
 &lt;body>
  &lt;ul>
    &lt;li>苹果&lt;/li>
    &lt;li>菠萝&lt;/li>
    &lt;li>香蕉&lt;/li>
  &lt;/ul>
 &lt;/body>
&lt;/html>
</pre>

效果图片：<br>
![使用list-style-image设置列表项目图片]({{page.resdir}}/list-style-image.png)

可查看[测试页面]({{page.resdir}}/list-style-image.html)。

这种方式存在三个问题：

1. 图片位置无法控制，当图片过小时，很明显可以看出图片位置偏下（如以上测试）。
2. 当浮动时，图片位置会与其他内容重合。可参见[测试页面]({{page.resdir}}/list-style-image-float.html)。
3. 需要ul存在左内边距，当ul不存在左内边距时，项目图片会与ul左侧元素重合。

一般来讲，建议使用背景图片的方式实现项目图片。

##背景图片方式-background-image

使用背景图片的方式在于为li设置左内边距，然后使用一张图片作为li的背景图片，注意，背景图片不能设置重复。代码如下：

<pre class="brush:html">
&lt;!doctype html>
&lt;html>
 &lt;head>
  &lt;meta charset="UTF-8">
  &lt;title>使用background-image设置列表项目图片&lt;/title>
  &lt;style>
    li{
      padding-left: 10px;
      list-style-type: none;
      background: url(arrow.gif) no-repeat left center;
    }
  &lt;/style>
 &lt;/head>
 &lt;body>
  &lt;ul>
    &lt;li>苹果&lt;/li>
    &lt;li>菠萝&lt;/li>
    &lt;li>香蕉&lt;/li>
  &lt;/ul>
 &lt;/body>
&lt;/html>
</pre>

可查看[测试页面]({{page.resdir}}/background-image.html)。

这种方式也存在一些不足，表现在项目列表图片占用了li的背景图片，li无法再设置其他背景图片。
如果要为li设置背景图片，可将项目列表图片与背景图片合为一个；也可以通过`before`为li设置项目图片，可参考[测试页面]({{page.resdir}}/before-background-image.html)。

##参考

1. 《精通CSS：高级WEB标准解决方案（第二版）》 p102

{{page.date|date_to_string}}