---
layout: post
title: JS入门之预编译
date: 2019-08-17 18:40:20 +0000
description: JS的类型转换. # Add post description (optional)
img: js-1.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [预编译]
---
JavaScript (usually abbreviated as JS) is an advanced, interpreted programming language. JavaScript is a prototype-based, function-first language, a multi-paradigm language that supports object-oriented programming, imperative programming, and functional programming.Today we learn about Precompiled
# 预编译
        先通篇扫描      称为语法分析
		预编译
		解释执行
		imply global 暗示全局变量：即任何变量，如果变量未经声明就赋值，此变量就为全局对象所有。
		全局对象为Window。
		如：a = 123;      var a = b = 123;
		一切声明的全局变量，全是window的属性。   windoe就是全局的域。
		如：var a = 123;===> window.a = 123;

		function test(){
			var b = 123;
		}
		test();
		console.log(window.b);

函数作用域不受除函数外的任何因素影响

全局预编译 GO    函数执行完只销毁映向AO的链接，并不是销毁AO，函数[[scope]]并回到被定义时的执行器上下文集合状态

函数(局部预编译)预编译四部曲

1.创建AO(Activation Object(活跃对象))对象(执行期上下文) GO去掉找形参和第三步操作即可

2.找形参和变量声明，将变量名和形参名作为AO属性名，值为undefined。

3.将实参值和形参统一。

4.在函数体里面找到函数声明，值赋予函数体。  if中不可定义函数

## 作用域 执行期上下文
		   运行期上下文：当函数执行的前一刻，会创建一个称为执行期上下文的内部对象。
		   一个执行器上下文定义了一个函数执行时的环境，函数每次执行时对应的执行上下文都是独一无二的，
		   所以多次调用一个函数会导致创建多个执行上下文，当函数执行完毕，它所产生的执行器上下文被销毁。
		   查找变量：从作用域的顶端一次向下查找。
		   [[scope]]：每个JavaScript函数都是一个对象，对象中有些属性我们可以访问，但有些不可以，这些属性仅供JavaScript引擎存取，[[scope]]就是其中一个
					[[scope]]指的就是我们所说的作用域，其中存储了运行期上下文集合
		   作用域链：[[scope]]中所存储的执行期上下文对象的集合，这个集合呈链式链接,我们把它叫作用域链，但是我们不可访问，仅供JavaScript引擎访问
				