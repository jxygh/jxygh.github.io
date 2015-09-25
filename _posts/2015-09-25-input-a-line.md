---
layout: article
title: input元素与a元素在同一行内水平对齐
codedemo: true
resdir: /blogres/2015-09-25-input-a-line
---

#{{page.title}}
问题：要求在以下结构中实现input元素和a元素在同一行内水平对齐

这个问题是在实现一个搜索框的过程中遇到的，搜索框的样式为：<br>
![搜索框]({{page.resdir}}/target.png)

搜索框的基本结构为：

<pre class="brush:html">
  &lt;div>
    &lt;input type="text">&lt;a href="javascript:;">&lt;/a>
  &lt;/div>
</pre>

添加基本的css后，表现为：

<pre class="brush:css">
input{
  height: 26px;
  margin: 0;
  padding: 0 0 0 26px;
  border: 0;
  background: url(search-bg.gif) no-repeat;
}
a{
  display: inline-block;
  width: 41px;
  height: 26px;
  background: url(search-go.gif) no-repeat;
}
</pre>

效果图片：<br>
![搜索框]({{page.resdir}}/problem.png)

由图中可以看出，input元素很明显的下沉了。

##input下沉的处理方法
这个问题出现的最主要原因是a元素内没有内容，只要为a元素添加上内容就可以了，比如空格，注意，空格必须为`&nbsp;`。
a元素会默认为内容添加下划线，别忘了取消掉。

<pre class="brush:html">
&lt;input type="text">&lt;a href="javascript:;">&amp;nbsp;&lt;/a>
</pre>

<pre class="brush:css">
a{
  display: inline-block;
  width: 41px;
  height: 26px;
  text-decoration: none;
  background: url(search-go.gif) no-repeat;
}
</pre>

添加上后的效果：<br>
![搜索框]({{page.resdir}}/problem2.png)

观察到input元素与a元素还是存在对齐问题。

##解决对齐问题
这一问题是由于input元素与a元素的`vertical-align`的方式有关，两个元素默认以baseline方式对齐，将两个元素的对齐方式设置为middle即可。
<pre class="brush:css">
    input{
      height: 26px;
      margin: 0;
      padding: 0 0 0 26px;
      vertical-align: middle;
      border: 0;
      background: url(search-bg.gif) no-repeat;
    }
    a{
      display: inline-block;
      width: 41px;
      height: 26px;
      vertical-align: middle;
      text-decoration: none;
      background: url(search-go.gif) no-repeat;
    }
</pre>

效果图片：<br>
![搜索框]({{page.resdir}}/problem3.png)

input和a元素的对齐问题已经解决了，但又出现了另一个问题，input元素内的文字太偏上了。在输入文字后，效果如下：<br>
![搜索框]({{page.resdir}}/problem4.png)

##input文字垂直居中
这个问题的解决方式就很简单了，只要将input元素的`line-height`设置的与`height`一致就可以。
<pre class="brush:css">
    input{
      height: 26px;
      margin: 0;
      padding: 0 0 0 26px;
      vertical-align: middle;
      line-height: 26px;
      border: 0;
      background: url(search-bg.gif) no-repeat;
    }
    a{
      display: inline-block;
      width: 41px;
      height: 26px;
      vertical-align: middle;
      text-decoration: none;
      background: url(search-go.gif) no-repeat;
    }
</pre>

效果如下：<br>
![搜索框]({{page.resdir}}/problem5.png)

这样搜索框看着就比较清爽了。
[测试页面]({{page.resdir}}/problem.html)

##参考

1. [设为inline-block的标签和input并排放置为何会错位](http://www.zhihu.com/question/26778887)
2. [CSS中并列的display:inline-block的a元素如果内容为空就错位的问题](http://zhidao.baidu.com/link?url=vtI41ZJ2REkDxBZMF0Ip9lKA3V_f0aA8NSXGv_R2SOuViXVhvKB7Hita8TYXrM15rVgvna5L7DylHn9iqZO3FpZu-ZMjMuSFzaXngHTGxI_ )
3. [使用vertical-align实现input和img对齐](http://www.ynpxrz.com/n787766c2022.aspx)

{{page.date|date_to_string}}