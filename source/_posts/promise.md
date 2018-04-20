---
title: promise
date: 2018-04-20 14:59:53
tags:
---
``` bash
$.get('/api/data')
.then(function(data) {
    console.log(data);
    return $.get('/api/user');
})
.then(function(user) {
    console.log(user);
    return $.get('/api/products');
})
.then(function(products) {
    console.log(products);
});
```