---
layout: article
title: 简单表单样式
codedemo: true
resdir: /blogres/2015-09-22-simple-form
---

#{{page.title}}
本节的目标效果如图：<br>
![目标效果]({{page.resdir}}/target.png)

##直接参考图片实现

<pre class="brush:html">
&lt;!doctype html>
&lt;html>
 &lt;head>
  &lt;meta charset="UTF-8">
  &lt;title>Simple Form&lt;/title>
  &lt;style>
    fieldset{
      width: 25em;
      margin: 1em 0;
      padding: 1em;
      border: 1px solid #ccc;
    }
    legend{
      font-weight: bold;
    }
    label{
      display: block;
      cursor: pointer;
    }
    input[type="text"]{
      width: 20em;
    }
    textarea{
      width: 100%;
    }
    .required{
      font-size: 60%;
    }
    input[type="text"]:focus,
    textarea:focus{
      background-color: #FFFFCC;
    }
    label[for="remember-yes"],
    label[for="remember-no"]{
      display: inline;
    }
  &lt;/style>
 &lt;/head>
 &lt;body>
  &lt;form action="">
    &lt;fieldset>
      &lt;legend>Your Contact Details&lt;/legend>
      &lt;div>
        &lt;label for="author">Name:&lt;em class="required">(Required)&lt;/em>&lt;/label>
        &lt;input type="text" name="author" id="author">
      &lt;/div>
      &lt;div>
        &lt;label for="email">Email Address:&lt;/label>
        &lt;input type="text" name="email" id="email">
      &lt;/div>
      &lt;div>
        &lt;label for="url">Web Address:&lt;/label>
        &lt;input type="text" name="url" id="url">
      &lt;/div>
    &lt;/fieldset>
    &lt;fieldset>
      &lt;legend>Comments&lt;/legend>
      &lt;div>
        &lt;label for="message">Message:&lt;em class="required">(Required)&lt;/em>&lt;/label>
        &lt;textarea name="message" id="message" cols="30" rows="10">&lt;/textarea>
      &lt;/div>
    &lt;/fieldset>
    &lt;fieldset>
      &lt;legend>Remember Me&lt;/legend>
      &lt;div>
        &lt;input type="radio" name="remember" id="remember-yes">
        &lt;label for="remember-yes">Yes&lt;/label>
      &lt;/div>
      &lt;div>
        &lt;input type="radio" name="remember" id="remember-no">
        &lt;label for="remember-no">No&lt;/label>
      &lt;/div>
    &lt;/fieldset>
  &lt;/form>
 &lt;/body>
&lt;/html>
</pre>

效果图片：<br>
![自己的实现效果]({{page.resdir}}/mine.png)

可查看[测试页面]({{page.resdir}}/mine.html)。

##《精通CSS》中的实现

可直接参照[测试页]({{page.resdir}}/simple-form.htm)。

两个实现差别不大。

##要点
1. form的组织结构。（form fieldset input）
2. label换行。
3. label关联input的两种方式（显式、隐式）

##参考

1. 《精通CSS：高级WEB标准解决方案（第二版）》 p139

{{page.date|date_to_string}}