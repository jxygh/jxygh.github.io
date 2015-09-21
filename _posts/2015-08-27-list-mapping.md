---
layout: article
title: 利用列表实现图像映射
codedemo: true
resdir: /blogres/2015-08-27-list-mapping
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
  &lt;title>利用列表实现图像映射&lt;/title>
  &lt;style>
    .mapping{
      position: relative;
    }
    .mapping ul{
      margin: 0;
      padding: 0;
      list-style-type: none;
    }
    .mapping ul li{
      display: none;
      position: absolute;
      width: 50px;
      height: 60px;
      border: 1px solid #fff;
      background-image: url(noimage.png);/*防止li鼠标穿透*/
    }
    .mapping:hover li{
      display: block;
    }
    .mapping a{
      position: absolute;
      bottom: -25px;
      left: -20px;
      display: none;
      width: 90px;
      padding: 2px 0;
      text-align: center;
      text-decoration: none;
      white-space: nowrap;
      background-color: #fff;
    }
    .mapping li:hover a{
      display: block;
      z-index: 2;/*防止li遮盖*/
    }
    .mapping .cathy{
      top: 155px;
      left: 65px;
    }
    .mapping .richard{
      top: 50px;
      left: 80px;
    }
    .mapping .james{
      top: 140px;
      left: 145px;
    }
    .mapping .sophie{
      top: 90px;
      left: 200px;
    }
    .mapping .pual{
      top: 165px;
      left: 245px;
    }
  &lt;/style>
&lt;/head>
&lt;body>
  &lt;div class="mapping">
    &lt;img src="nerdcore.jpg" alt="">
    &lt;ul>
      &lt;li class="cathy">&lt;a href="javascript:;">Cathy Jones&lt;/a>&lt;/li>
      &lt;li class="richard">&lt;a href="javascript:;">Richard Rutter&lt;/a>&lt;/li>
      &lt;li class="james">&lt;a href="javascript:;">James Box&lt;/a>&lt;/li>
      &lt;li class="sophie">&lt;a href="javascript:;">Sophie Barrett&lt;/a>&lt;/li>
      &lt;li class="pual">&lt;a href="javascript:;">Pual Annett&lt;/a>&lt;/li>
    &lt;/ul>
  &lt;/div>
&lt;/body>
&lt;/html>
</pre>

效果图片：<br>
![自己的实现效果]({{page.resdir}}/list-mapping.png)

可查看[测试页面]({{page.resdir}}/list-mapping.html)。

##《精通CSS》中的实现

可直接参照[测试页]({{page.resdir}}/flickr-rollovers.htm)。

查看书中代码后，意识到自己犯了一份非常大的错误，图像映射应该是可点击的。
但我的实现里用li元素框住了头像，而不是用a元素，这就使得头像不可点击。

##参考

1. 《精通CSS：高级WEB标准解决方案（第二版）》 p114

{{page.date|date_to_string}}