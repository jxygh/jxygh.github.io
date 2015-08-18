---
layout: default
title: img图片出现下边距的解决办法
---

#{{page.title}}
今天在制作图片投影效果时，发现img图片的下方出现了下边距。将img设置为`margin:0; padding:0;`时，下边距仍不消失。如下方的示例所示：
{% highlight html %}
<!doctype html>
<html>
 <head>
  <meta charset="UTF-8">
  <title>图片下边距</title>
  <style>
    div,img{
      margin: 0;
      padding: 0;
    }
    div{
      border: 1px solid black;
    }
  </style>
 </head>
 <body>
  <div>
    <img src="http://placehold.it/150x150" alt="示例图片">
  </div>
 </body>
</html>
{% endhighlight %}

效果图片：
![出现了下边距图片](/blogres/2015-08-17-img-bottom-margin/has-margin.png)

##出现原因
根据[img图片下面出现莫名的下边距](http://blog.csdn.net/nx8823520/article/details/6283339)的描述：出现这一现象的原因是：

>图片底部的空隙实际上涉及行内元素的布局模型，图片默认的垂直对齐方式是基线，而基线的位置是与字体相关的。所以在某些时候，图片底部的空隙可能是 2px，而有时可能是 4px 或更多。不同的 font-size 应该也会影响到这个空隙的大小。

##解决办法
解决该问题的办法有多个：

1. `div img{display: block}`
2. `div img{vertical-align: top|bottom}`。*推荐*
3. `div{font-size: 0}`

##参考

1. [img图片下面出现莫名的下边距](http://blog.csdn.net/nx8823520/article/details/6283339)
2. [IMG图片下面出现下边距的解决办法](http://blog.csdn.net/yourlin/article/details/42024665)

{{page.date|date_to_string}}