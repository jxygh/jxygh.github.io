---
layout: article
title: 滑动门标签式导航
codedemo: true
resdir: /blogres/2015-08-27-sliding-doors-nav
---

#{{page.title}}
本节的目标效果如图：<br>
![目标效果]({{page.resdir}}/target.png)

##直接参考图片实现

<pre class="brush:html">
&lt;!doctype html>
&lt;html lang="en">
&lt;head>
  &lt;meta charset="UTF-8">
  &lt;title>滑动门标签式导航&lt;/title>
  &lt;style>
    .nav{
      margin: 0;
      padding: 0;
      list-style-type: none;
      word-spacing: -6px;/*移除li元素inline-block时的间距*/
    }
    .nav li{
      display: inline-block;
      word-spacing: 0;/*恢复间距*/
      background: url(tab-right.gif) no-repeat top right;
    }
    .nav a{
      display: inline-block;
      padding: 8px 20px;
      font-size: 14px;
      color: #fff;
      text-decoration: none;
      white-space: nowrap;/* 防止页面过小（如50像素）时，最后一个Tab折行 */
      background: url(tab-left.gif) no-repeat;
    }
    .nav a:hover{
      color: #000;
    }
  &lt;/style>
&lt;/head>
&lt;body>
    &lt;ul class="nav">
      &lt;li>&lt;a href="javascript:;">HOME&lt;/a>&lt;/li>
      &lt;li>&lt;a href="javascript:;">ABORT&lt;/a>&lt;/li>
      &lt;li>&lt;a href="javascript:;">NEWS&lt;/a>&lt;/li>
      &lt;li>&lt;a href="javascript:;">PRODUCTS&lt;/a>&lt;/li>
      &lt;li>&lt;a href="javascript:;">SERVICES&lt;/a>&lt;/li>
      &lt;li>&lt;a href="javascript:;">CLIENTS&lt;/a>&lt;/li>
      &lt;li>&lt;a href="javascript:;">CASE STUDIES&lt;/a>&lt;/li>
  &lt;/ul>
&lt;/body>
&lt;/html>
</pre>

效果图片：<br>
![自己的实现效果]({{page.resdir}}/sliding-doors-nav.png)

可查看[测试页面]({{page.resdir}}/sliding-doors-nav.html)。

##《精通CSS》中的实现
书中的实现类似，可直接参考书中示例：[{{page.resdir}}/sliding-doors-nav-book.html)

##参考

1. 《精通CSS：高级WEB标准解决方案（第二版）》 p110

{{page.date|date_to_string}}