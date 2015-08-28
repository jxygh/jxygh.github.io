---
layout: article
title: 变量提升
codedemo: true
resdir: /blogres/2015-08-28-variable-hoisting
---

#{{page.title}}

## 简单示例

在JavaScript中，当变量被声明时，声明会提升至所在函数的顶部，并被赋予undefined值。如果在函数声明位置前调用变量，则会得到undefined值。
如果一个变量从未在函数内声明，则调用该变量会出现错误。

<pre class="brush: js;">
    function fn1(){
      alert("在声明位置前调用变量:"+v1);
      alert("调用未声明变量："+v2);

      var v1 = 3;
    }
    fn1();
</pre>

请直接查看[测试页面]({{page.resdir}}/variable-hoisting.html)。

## 引发的隐秘bug

有以下代码，请思考下，执行结果什么？

<pre class="brush: js;">
    var v1 = 1;
    function fn1(){
      alert(v1);

      var v1 = 3;
    }
    fn1();
</pre>

点击查看[测试页面]({{page.resdir}}/variable-hoisting-bug.html)。

执行结果是：undefined。从直觉来说，调用v1时，已经在全局为v1赋过值了，并且尚未在局部变量中覆盖定义v1，此时结果应该为1。
但结合前面变量提升的知识，在函数fn1中存在v1的定义，v1属于fn1的局部变量，在函数执行时，已经把v1的变量提升至了函数顶部，并且为其赋予了undefined值。
实际上，上述代码与以下代码是等价的。

<pre class="brush: js;">
    var v1 = 1;
    function fn1(){
      var v1;
      alert(v1);

      v1 = 3;
    }
    fn1();
</pre>

##参考

1. 《单页Web应用 javaScript从前端到后端》 p27-p28

{{page.date|date_to_string}}
