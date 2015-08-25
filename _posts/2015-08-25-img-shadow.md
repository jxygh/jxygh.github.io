---
layout: article
title: 图片投影
codedemo: true
resdir: /blogres/2015-08-25-img-shadow
---

#{{page.title}}

##利用负边距实现投影效果
这种方法需要一张投影的效果图片，将需要投影的图片img包裹在一个div中，div的背景图设为效果图片，然后将img想左上方偏移，即可达到投影效果。

<pre class="brush: html;">
&lt;!doctype html>
&lt;html>
 &lt;head>
  &lt;meta charset="UTF-8">
  &lt;title>Document&lt;/title>
  &lt;style>
    .img-wrapper{
      display: inline-block;
      background: url(shadow.gif) no-repeat bottom right;
    }
    .img-wrapper img{
      margin: -5px 5px 5px -5px;
      vertical-align: top;/*避免图片下方出现间隔 http://jxygh.github.io/2015/08/17/img-bottom-margin.html */
    }
  &lt;/style>
 &lt;/head>
 &lt;body>
  &lt;div class="img-wrapper">
    &lt;img src="/image/example/xiaoxiang-small.jpg" alt="">
  &lt;/div>
 &lt;/body>
&lt;/html>
</pre>

效果图片：<br>
![投影效果]({{page.resdir}}/margin-shadow.png)

也可直接查看[测试页面]({{page.resdir}}/margin-shadow.html)。

因为应用了负边距，在使用中，需要注意与其他元素的边距设置，防止与其他元素重叠。

##利用相对定位实现投影效果
这种方式与利用负边距类似，不同的是采用了相对定位的方法。

<pre class="brush: html;">
&lt;!doctype html>
&lt;html>
 &lt;head>
  &lt;meta charset="UTF-8">
  &lt;title>Document&lt;/title>
  &lt;style>
    .img-wrapper{
      display: inline-block;
      background: url(shadow.gif) no-repeat bottom right;
    }
    .img-wrapper img{
      position: relative;
      top: -5px;
      left: -5px;
      vertical-align: top;/*避免图片下方出现间隔 http://jxygh.github.io/2015/08/17/img-bottom-margin.html */
    }
  &lt;/style>
 &lt;/head>
 &lt;body>
  &lt;div class="img-wrapper">
    &lt;img src="/image/example/xiaoxiang-small.jpg" alt="">
  &lt;/div>
 &lt;/body>
&lt;/html>
</pre>

效果图片：<br>
![投影效果]({{page.resdir}}/relative-shadow.png)

查看[测试页面]({{page.resdir}}/relative-shadow.html)。

因为应用了相对定位，在使用中，需要注意与其他元素的边距设置，防止与其他元素重叠。

##CSS3实现投影效果
通过CSS3的`box-shadow`属性可轻易实现投影效果，不仅不再需要多余元素（如div元素），而且可定制投影大小、颜色等。
属性的具体解释见[box-shadow](http://css.doyoe.com/properties/border/border-radius.htm)。

<pre class="brush: html;">
&lt;!doctype html>
&lt;html>
 &lt;head>
  &lt;meta charset="UTF-8">
  &lt;title>Document&lt;/title>
  &lt;style>
    img{
      box-shadow:3px 3px 10px #666;
    }
  &lt;/style>
 &lt;/head>
 &lt;body>
    &lt;img src="/image/example/xiaoxiang-small.jpg" alt="">
 &lt;/body>
&lt;/html>
</pre>

效果图片：<br>
![投影效果]({{page.resdir}}/css3-shadow.png)

查看[测试页面]({{page.resdir}}/css3-shadow.html)

##参考

1. 《精通CSS：高级WEB标准解决方案（第二版）》 p67-p71

{{page.date|date_to_string}}
