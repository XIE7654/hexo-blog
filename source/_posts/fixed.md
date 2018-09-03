---
title: fixed
date: 2018-09-03 20:54:25
tags:
---


今天入了个小坑，底部元素设置position:fixed;没有效果的问题，查了很久才发现原来原因。

如果一个元素设置了position:fixed;其父元素设置了tansform属性的话，不管是scale()、rotate()、还是translate()，其fixed值都会失效，直接会使position:fixed;变成position:absolute;的效果。

所以，我们fixed的元素的父级有transform属性的话，fixed效果完全没有，

社么，解决办法？no way！解决办法就是fixed的元素不使用transform属性。
