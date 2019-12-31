---
layout: post
title: JS入门-变量与对象
date: 2019-10-23 15:40:20 +0000
description: JS变量与对象. # Add post description (optional)
img: js-1.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [变量,对象,JS]
---
# 变量和对象

    原始类型: number string boolean undefined null

    引用类型: object function 

## 在变量中存放对象

1、通过变量读取对象中的某个数据

```js
    var user = {
    name:'我都会',
    age:23,
    id:'abc',
    pwd:'2333',
    sex:'男',
    isVip:true,
};
console.log(user.name, typeof user.name);
```

**当读取的属性不存在时会得到undefined**

**当读取属性的对象不存在时报错(undefined 或 null)**

2、通过变量更改对象中的某个属性值

**当赋值的属性不存在的时候，会添加属性**

```js
    var user = {
    name:'我都会',
    age:23,
    id:'abc',
    pwd:'2333',
    sex:'男',
    isVip:true,
};
    user.age = 18;
console.log(user.name, typeof user.name);
```


3、删除属性

```js
    delete 变量名.属性名
```

4、属性表达式

给属性赋值或读取属性时可以使用下面的格式操作

```js
    对象变量['属性名']
```

- 某些属性名中包含特殊字符

实际上，JS对属性名的而要求并不严格，属性可以是任何形式的名字。遇到特殊字符时，加上双引号变为字符串即可

属性的名字只能是字符串，如果你书写的时数字，那会自动转换为字符串

## 全局对象

JS大部分的宿主环境，都会提供一个特殊的对象，该对象可以直接在JS代码中访问，该对象叫做全局对象。

在浏览器环境中，全局对象为window，表示整个窗口

全局对象中的所有属性，可以直接使用，而不需要写上全局对象名

**开发者定义的所有变量实际上会成为window对象的属性**

**如果变量没有被赋值，则该变量不会覆盖window上的同名属性**

```js
    // name为特殊变量
    var name;
    console.log(name , typeof name);
    //输出值为空。类型string，

    name = undefined;
    console.log(name , typeof name);
      //输出值为字符串undefined。类型string
```