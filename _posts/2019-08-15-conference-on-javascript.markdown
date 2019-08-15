---
layout: post
title: JS入门之运算符
date: 2019-08-15 20:00:00 +0300
description: 每个语言都有运算符，它们长的一样，用发却时同时而不同。让我们一起看看JS中运算符吧~. # Add post description (optional)
img: js-1.png # Add image post (optional)
tags: [Js, 运算符] # add tag
---
每个语言都有运算符，它们长的一样，用发却时同时而不同。让我们一起看看JS中运算符吧。

# JS操作运算符
    运算操作符  + 、-、*、 /、 %、 =、 ()、 ++、 --、 +=、 -=、 *=、%=

## 例
>算数运算符

    var a = 'b'+ 'c' 字符串连接
	var a = 1 + 2 数字相加   任何数据类型加字符串都等于字符串 
    %意思是取余 优先级 '='最弱，"()"优先级较高
	var a = 10;
	a = a + 1; 
    a= a + 1;可简化为a++   a--同理a++  
    ++a 先计算后赋值，a++先赋值，后计算 --a同理。
	a = a + 10可简化成 a += 10
	var a = (10 * 3 -4 / 2 + 1) % 2,
		b = 3;
	b %= a+3;
	document.write(a++);
	document.write("<br>");
	document.write(--b);
	var a = 123;
	var b = 234;
	var c = a;
	a = b;
	b = c;
	document.write(a);
	document.write("<br>");
	document.write(b);

>比较运算符  > < == >= <= !=     

    比较返回结果为boolean值	
    被认定为flase的值 undefined null NaN "" 0 false 
	
    运算结果为真实的值

	所有值中唯有NaN不等于NaN

	1 / 0 = Infinity  属于Number

	NaN 非数 也属于number
		先看第一表达式转换成布尔值得结果，如果结果为真，那么它会看第二个表达式转换为布尔值得结果，如果只有两个表达式的话，只要看到第二个表达式就可以返回该表达式的值了。
    字符串之间比较是比ASCII码的值的大小

>逻辑运算符 &amp;&amp;||！

	值为flase的 undefined null NaN "" 0 false

	与 或  非

	var a = 0 && 2 + 1;   
    与运算找假，没有假打印最后一个表达式的值  
    或运算找真，遇到假看后一个表达式是否为真
    与运算符碰到假就停，或运算符碰到真就停。
	document.write(a);
	var a = 1 || 3;
	document.write(a);
	