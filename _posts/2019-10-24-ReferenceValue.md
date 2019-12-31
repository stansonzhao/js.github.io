---
layout: post
title: JS入门-引用值
date: 2019-10-24 12:40:20 +0000
description: JS引用值. # Add post description (optional)
img: js-1.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [引用值,JS]
---
# 引用类型

    原始类型 引用类型(对象、函数)

**原始类型的变量，存放的是具体的值**

**引用类型的变量，存放的是内存地址**

**凡是出现对象字面量，都一定在内存中出现一个新的对象**

> 扩展知识:JS中的垃圾回收
> JS引擎中的垃圾回收器,会定期的发现内存中无法访问到的对象，该对象称之为垃圾，JS引擎会在合适的时间将其占用的内存释放。

