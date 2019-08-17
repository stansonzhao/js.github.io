---
layout: post
title: JS入门之堆、栈
date: 2019-08-15 16:32:20 +0300
description: JS的堆和栈. # Add post description (optional)
img: js-1.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [堆, 栈]
---
JavaScript (usually abbreviated as JS) is an advanced, interpreted programming language. JavaScript is a prototype-based, function-first language, a multi-paradigm language that supports object-oriented programming, imperative programming, and functional programming.Today we learn about 'stark'&'heap'
---
# 堆(stark) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 栈(heap)

## 了解堆和栈之前先了解一下JS数据类型
    JS中，数据分为两种类型值，原始值和引用值
    原始值:Number string  boolean  undefined  null
    引用值:array Object function date RegExp...
**原始值变量名存储的栈内存中，而其数据值存在堆内存地址之中**

> 原始值存储在栈内存中  
    
    栈内存存储方式[^先进后出，后进先出]。
        和我们向口袋里放取东西一样，最先放入的东西，想要取用，要把后放入的东西全部取出后才可取出最先放入的东西。而想取用最后放入的东西，可直接拿取。

>引用值存储在堆内存中

    堆内存存储方式[随用随取，与其它数据无关]
        类似于我们的书架，想用直接取出，不用挪动其它书本。

## **常见面试题**
```JS
    //原始值之间赋值
    var a = 20;
    var b = a;
    b = 40;
``` 
问此时a的值是多少？
    
    原始值之间赋值 新建个变量b，此时b值为空，继而获取a的堆内存的地址，查询到a的值，而后将a的值再赋给新建变量b，此时a和b互不关联。所以更改b的值后a的值并不会变，所以a的值仍为20。
```JS
    //引用值之间赋值
    var arr = [1,2,3,4];
    var arr1 = arr;
    arr1 = [233];
```

问此时arr的值是多少

    引用值之间赋值 引用值之间赋值只将数组的堆内存地址赋给arr1,arr1的堆内存地址仍然是arr的堆内存地址，也就是说arr和arr1都指向同一个堆内存地址，所以将arr1的值修改，arr的值也跟着更改了。

OVER