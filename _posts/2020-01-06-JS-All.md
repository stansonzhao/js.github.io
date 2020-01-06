---
layout: post
title: 成哥(姬成)讲JS(全)
date: 2020-01-6 12:25:20 +0000
description: JS笔记. # Add post description (optional)
img: js-1.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [笔记大全,JS]
---
```js
 原始值 stack  栈   原始值存在栈里

		 Number string  boolean  undefined  null
		 错误分成两种
		 1.低级错误（语法解析错误）    SyntaxError 语法解析错误

		 2.逻辑错误（标准错误，情有可原） ReferenceError逻辑错误



		 引用值 heap  堆     引用值存在堆里
		 array Object function date RegExp

		 运算操作符  + - * / % = () ++ -- += -= *= %=
		 var a = 'b'+ 'c' 字符串链接
		 var a = 1 + 2 数字相加   任何数据类型加字符串都等于字符串    %意思是取余 优先级 '='最弱，"()"优先级较高
		
		 var a = 10;
		 a = a + 1;  'a= a + 1'可简化为a ++   a--同理a++                  ++a 先计算后赋值，a++先赋值，后计算。
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
		 字符串之间比较是比ASCII码的值的大小
		比较运算符  > < == >= <= !=  逻辑运算符 && || ！    被认定为flase的值 undefined null NaN "" 0 false
		比较结果为boolean的值			运算结果为真实的值
		 所有值中唯有NaN不等于NaN
		 1 / 0 Infinity  属于Number
		 NaN 非数 也属于number
		
		 先看第一表达式转换成布尔值得结果，如果结果为真，那么它会看第二个表达式转换为布尔值得结果，如果只有两个表达式的话，
		 只要看到第二个表达式就可以返回该表达式的值了。
		
		 逻辑运算符 && || ！					值为flase的 undefined null NaN "" 0 false
		 与 或  非
		 var a = 0 && 2 + 1;   与运算找假，没有假打印最后一个表达式的值   或运算找真，遇到假看后一个表达式是否为真
		 document.write(a);
		 var a = 1 || 3;
		 document.write(a);
		 与运算符碰到假就停，或运算符碰到真就停。
			    if语句的应用
			var score = parseInt(window.prompt('输入'))
			if(score > 90 && score <= 100) {
				document.write('阿里巴巴');
			}else	if(score > 80 && score <= 90) {
				document.write('腾讯');
			}else   if(score > 70 && score <= 80) {
				document.write('百度');
			}else   if(score > 60 && score<= 70) {
				document.write('蘑菇街');
			}else   if(score < 60){
				document.write('自学的吧？？');
			}else {
				document.write('error');
			}



		 for循环   先执行一遍(1) 判断(2) 执行执行语句 再执行(3) 接下来再判断(2) 执行执行语句 再执行(3)
		 	(1)		   (2)	   (3)
		 for(var i = 0; i < 10; i++){
		 	document.write('a');
		 }
			1. var i = 0;
			2.if(i < 10){
				document.write('a');
			}
			3.i++
			4.if(i < 10){
				document.write('a');
			}
			5.i++
			 if(i < 10){
				document.wriye('a');
			 }

			
		 var i = 1;
		 var count = 0;
		 for(; i;){
		 	document.write('a');
		 	count ++;
		 	if(count == 10){
		 		i = 0;
		 	}
		 }

		 var count = 0;
		 var i = 100;
		 for(;i--;){
		 	document.write(i);
		 }
		 计算2的n次幂
		 var n = parseInt (window.prompt('输入'));
		 var num = 1;
		 for(var i =0; i < n;i++){
		 	num *= 2;
		 }
		 document.write(num);
		计算阶乘
		 for(var i =1 ; i <= n;i++){
		 	num *= i ;
		 }
		 document.write(num);

		裴多纳契数列
			var a = 1,
				b = 1,
				c;
				if(n > 2){
				for(var i = 0;i < n-2; i++){
					c = a + b;
				a = b;
				b = c;
				}document.write(c);
			}else
				document.write(1);
			
		 var a = parseInt(window.prompt('输入a')),
		 b = parseInt(window.prompt('输入b')),
		 c = parseInt(window.prompt('输入c'));
		 if(a<b){
		 	if(b<c){
		 		document.write(c  +' '+  b  +' '+  a);
		 	}else if(a<c){
		 		document.write(b +' '+ c +' '+ a);
		 	}else{
		 		document.write(b +' '+ a +' '+ c);
		 	}
		 }else if(a>b){
		 	if(b>c){
		 		document.write(a+' '+b+' '+c);
		 	}else if(a > c){
		 		document.write(a+' ' + c + ' ' + b );
		 	}else{
		 		document.write(c+' ' + a + ' ' + b );
		 	}
		 }
		 for(var i = 0; i < 100; i++){
		 	if(i % 3 == 0 || i % 5 == 0 || i % 7 == 0)
		 }
		 i = 100;
		 for(;i--;){
		 	document.write(i + ' ');
		 }

		 while 循环，去掉for循环头和尾
		 	格式
		 var i = 0;
		 while(i < 100){
		 	if(i % 7 == 0 || i % 10 ==7) {
		 		document.write(i + ' ');
		 	}
		 	i ++;
		 }
		
				计算2的N次幂
		var n = parseInt(window.prompt('输入'));
		mul = 1;
		for(var i = 0; i < n; i++){
			mul *= 2;
		}
			document.write(mul);

		 计算阶乘
			var n = parseInt(window.prompt('输入'));
			var mul = 1;
			for(var i = 1; i <= n; i++){
				mul *= i;
			}
			document.write(mul);


		 1 * 2
		 1 * 2 * 2
		 1 * 2 * 2 * 2
			var mul = 1;
			for(i = 0; i < n; i++){
				mul *= 2;
			}
				document.write(mul);
			
		选出三个数中最大的一位
		 var a = parseFloat(window.prompt('输入第一个数'));
		 var b = parseFloat(window.prompt('输入第二个数'));
		 var c = parseFloat(window.prompt('输入第三个数'));
		if(a > b && a >c){
			 document.write(a);
		}else if(b > a && b>c){
			 document.write(b);
		}else if (c > a && c > b){
			 document.write(c);
		}

		三目运算进行大小筛选
		 var max = a > b ? (a > c ? a : c) : (b > c ? b : c);
		 alert(max);

		 if(a > b){
		 	if(a > c){
		 		document.write(a);
		 	}else{
		 		document.write(c);
		 	}
		 }else if(b > c){
		 		document.write(b);
		 }else{
		 		document.write(c);
		 }
		  输入456，输出654
			 var a = 456;
		var num = a % 10;
		var	 num1 = a - num;
		 document.write(num1);
		var	 num2 =  num1 % 100;
		 document.write(num2);
		var	 num3 = num1 - num2;
		 document.write(num3);
		var	 num4 = num3 / 100;
		 num *= 100;
			 document.write(num +  num2 +  num4);


		裴多那切数列
		 var n = parseFloat(window.prompt('输入计算数'));
		 var f = 1,
		 	 s = 1,
		 	 t;
		 	if(n > 2){
			 for(i = 0; i < n-2; i++){
		 	 	t = f + s;
		 	 	f = s;
		 	 	s = t;
		 	 }
		 	 document.write(t);
		 	}else{
		 		document.write(1);
		 	}


		计算任意数的二次幂
			 var mul = 1;
			  for(i = 0; i < n; i++){
					 mul *= 2;
			  }
			  document.write(mul);
		算任意数的阶乘
		 var mul = 1;
		 for(i = 1; i <= n; i++){
				mul *= i;
		 }
		 document.write(mul);


		 var a =  document.
		 列出100以内的质数
			var count = 0;
			for (var i = 1; i <= 100; i++) { 轮流取出i

				for (var j = 1; j <= i; j++) {  进行模计算
					if (i % j == 0) {
						 console.log(i)
						count++;
					}
				}
				if (count == 2) {  满足条件则输出
					document.write(i + ' ');

				}
				count = 0;   清空计数器

			}
			
		开方数求质数
		 var count = 0;
		 for (var i = 2; i <= 100; i++) { 轮流取出i

		 	for (var j = 1; j <= Math.sqrt(i); j++) {  进行模计算 Math.sqrt()意思是求一个数的开方数
		 		if (i % j == 0) {
		 			 console.log(i)
		 			count++;
		 		}
		 	}
		 	if (count == 1) {  满足条件则输出 此时只能被整除一次，被1整除
		 		document.write(i + ' ');

		 	}
		 	count = 0;   清空计数器

		 }

		条件判断语句
			 var n = 1;
			 switch(n){
					case 1:
						  console.log('a');
						  break;
					case 2:
						  console.log('b');
						  break;
					case 3:
						  console.log('c');
						  break;
			 }

		
		var count = 0;
		for(var i = 2;i<=100;i++){
		   for(var j = 1;j<=Math.sqrt(i);j++){
			   if(i % j == 0){
				   count++;
			   }
		   }if(count == 1){
			   document.write(i + ' ');
		   }
		   count = 0;
		}

		break是终止循环,必须放在循环里面
		 var i = 0;
		 while(1){
				i ++;
				console.log(i);
				if(i >= 100){
					  break;
				}
		 }


		  不通过break终止循环
		  var sum = 0;
		  for(var i = 0;sum < 100;i++){
		 	 sum += i;
		 	 console.log(i);
		  }
		var i = 0;
		var sum = 0;
		for(var i = 0; i < 100; i ++){
			   sum += i;
			   console.log(i);
			   if(sum > 100){
					 break;
			   }
		}
		列出不能被7整除的数
		 for(var i = 0; i < 100; i ++){
				if(i % 7 == 0 || i % 10 ==7){
					  continue;终止本次循环，进行下次循环。
			  }
			  console.log(i);
		 }






		数组 arr
		var arr = [1,2,3,4,5,6,7,8,9,10];
		 arr[0] = 10;
		for(var i = 0; i < arr.length; i ++){
			  arr[i] += 1
			  console.log(arr[i]);
		}





		对象 object
		var deng = {
			  lastName : 'Deng',
			  age : 40,
			  sex : undefined,
			  wife : 'xiaoliu',
			  father : 'dengdaye',
			  son : 'xiaodeng',
			  handsome : false,
		}
		console.log(deng.lastName);
		deng.age = '50';
		console.log(deng.age);


		typeof类型显示    typeof可以显示未定义的东西而不报错
		六种数据类型
		number，string，boolean,undefined,object([]、null都属于object),function
		数字    字符串  布尔值   未定义    对象    函数
		
		var num = 3;
		console.log(typeof(num)); || console.log(typeof num);
		类型转换
		分为两种，一、显示类型转换，二、隐示类型转换




		 Number(mix)类型转换     undefined转换为Number类型值是NaN,false值是0，true值是1，
								null值是0，字母值是NaN,数字加字母值是NaN,符号值是NaN
		var demo = NaN;
		var num = Number(demo);
		console.log(typeof(num) + ':' + num);




		parseInt(string,radix(radix取值范围为2~32))类型转换 只能数字转换数字，其它类型转换都是NaN,数字加字母转换，从数字位开始读，到最近的非数位截至
		  var demo = '10ab1';
		  var num = parseInt(demo);
		  console.log(typeof(num) + ':' + num);
		var demo = '10';
		var num = parseInt(demo,16) 意思是把10当成16进制数，转换成10进制数
		var demo = null;
		var num = String(demo);			tostring用法 var num = demo.toString()
		console.log(typeof(num) + ':' + num);
		var demo = '123abc';
		var num = parseInt(demo);
		console.log(typeof(num) + ':' + num);



		parseFolt(string)类型转换，读取第一个小数点到非数字位停止
		var demo = '123.23px';
		var num = parseFloat(demo);
		console.log(typeof(num) + ':' + num);
		string(mix)类型转换，可以把任意类型变为字符串类型，并显示本身，
			var demo = NaN;
			var num = String(demo);
			console.log(typeof(num) + ':' + num);


		Boolean()类型转换，致力于转换为Boolean类型  这六个值转换必为false： false、0、''、null、undefined、NaN。
		
		var demo = 123;
		var num = Boolean(demo);
		console.log(typeof(num) + ':' + num); 


		toString(radix)类型转换，致力于转为字符串类型  undefined和null不可用toString。将demo里的数转换成radix中填的进制数。
			var demo = 10000;
			 var test = parseInt(demo,2);把二进制的数转换成十进制数
			 console.log(test.toString(16));把十进制数转换成16禁止

		隐示类型转换
		 isNaN 通过Number进行转换
		 console.log(isNaN(NaN));

		++ --  +正 -负  通过number进行隐示转换
		+  两边有一个是字符串，就用string进行转换，没有则用number

		- * / %  用number进行转换

		 < > <= >= 是通过Boolean来转换，结果为true或false。

		不发生类型转换的
		=== 全等于！== 不等于
		var a = 123123.3456789;       toFixed(X),只显示至小数点后X位截至，如果保留数的最后一位的后一位会进行四舍五入
		alert(a.toFixed(3));


		函数
		函数声明
		 function test(){
				var a = 1;
				var b = 2;
				var c = a + b;
				document.write(c);
		 }
		 test();

		 函数表达式
		 1. 命名函数表达式    如果是，会完整读一遍强调
		 var test = function theFirstName(){
				document.write('a');
		 }
			   test();
		 2. 匿名函数表达式   行业简称函数表达式
		 					形式参数---形参
			var demo = function (a,c){
				   var b = a + c;
				   document.write(b);
			 }
				    实际参数---实参            arguments -- [放的实参]  实参列表
			 demo(34,78);

		var demo = function(a,b){
			  if(a > 10){
				  document.write(a - b);
			  }else if(a < 10){
				  document.write(a + b);
			  }else{
				  document.write(10);
			  }
		}
		demo(11,2);

			function demo(a){
				   console.log(demo.legnth);
				    形参长度
				   console.log(arguments);
				    实参数组
				   console.log(arguments.length);
				    实参长度
				   for(i = 0;i < arguments.length; i++){
					   console.log(arguments[i]);
				   }
			 }
			 demo(10,9,6,7,8);


		function  test(a,b,c,d,){
				  if(test.length > arguments.length){
					  console.log('形参多');
				  }else if(test.length < arguments.length){
					  console.log('实参多');
				  }else{
					  console.log('相等');
				  }
		}
		test(1,2,3,4,5);

		 求任意数的和
			function sum(a){
				var result = 0;
				for(i = 0;i < arguments.length;i++){
					result += arguments[i];
				}
				console.log(result);
				console.log(arguments.length);
			}
			sum(1,2,3,4,5,6,7,8,9,10);
		
				function myNumber(target){
					return +target;
				}
				var num = myNumber('123');
				console.log(typeof(num) + ' ' + num);

		加法计数器
		function sum(){
			var result = 0
			for(i = 0; i < arguments.length;i++){
				result += arguments[i];
			}
			console.log(result);
		}
		sum(1,2,3);


		计算阶乘
		function mul (){
			var n = parseInt(window.prompt('输入'));
			var ji = 1;
			for(i = 1;i <= n;i++){
				ji *= i;
			}
			console.log(ji);
		}
		mul();





		计算裴多那切数列
			function demo(){
				var n = parseInt(window.prompt('输入'));
				var f = 1;
				var s = 1;
				var c;
				if(n > 2){
					for(i = 0;i < n-2;i++){
							c = f+s;
							f = s;
							s = c;
							}
						console.log(c);
					}else{
						console.log(1);
				}
			}
			demo();


		输入动物名称，跳出动物叫声
		var n = window.prompt('输入');
		function demo(){
		switch(n){
			case '猫':
				console.log('喵喵喵');
				break;
			case '狗':
				console.log('汪汪汪');
				break;
			case '曹旭鹏':
				console.log('hahaha');
				break;
			case '羊':
				console.log('咩咩咩');
				break;
			}
		}
		demo();

		
		输入数字，逆转并输出汉字  str.charAt[i]  拿出字符串数组的第i位
		var arr = [' ','拾','佰','仟','萬','亿'];
		var num = window.prompt('input');
		var str = '';
		var jian = num.length;
		for (var i = 0; i < num.length; i++) {
			str += transfer(num[i]);
		}
		 document.write(str);
		万位以下转换
		if(num.length < 5){
		for( var j = 0;j < str.length;j++){
			if(jian > 0){
				jian--;
				document.write(str[j] + arr[jian]);
			}
		}
	}else if(num.length >= 5){

	}


		function transfer(target) {
			switch (target) {
				case '0':
					return '零';
				case '1':
					return '壹';
				case '2':
					return '贰';
				case '3':
					return '叁';
				case '4':
					return '肆';
				case '5':
					return '伍';
				case '6':
					return '陆';
				case '7':
					return '柒';
				case '8':
					return '捌';
				case '9':
					return '玖';
			}
		}


		




		 1、找规律
		 2、找出口
		
				function mul(n) {
					n的阶乘
					var num = 1;
					for(var i = 1;i <= n;i++){
						num *=i;
					}
					if (n == 1) {
						return 1;
					}
					return n * mul(n - 1);
				}
		裴多纳契数列
		 var f = 1,
		 	s = 1,
		 	t;
		 var n = parseInt(window.prompt('输入'));
		 if (n > 2) {
		 	for (var i = 1; i <= n - 2; i++) {
		 		t = f + s;
		 		f = s;
		 		s = t;
		 	}
		 	console.log(t);
		 } else if(n<=2 && n >=0) {
		 	console.log(1);
		 }else{
		 	console.log('无法计算');
		 }



		递归来写裴多那切数列
		function fb(n){
			if(n == 1 || n == 2){
				return 1;
			}
			return fb(n-1) + fb(n-2);
			}
		console.log(fb(n));*





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
			a = 100;
			fuction demo(e){
				function e(){}
				arguments[0] = 2;
				console.log(e);2
				if(a){
					var b = 123;
					function c(){
						猪都不如
				}
			}
			var c;
			a = 10;
			var a;
			console.log(b);und
			f = 123;
			console.log(c);und fn
			console.log(a);10
		}
		var a;
		demo(1);
		console.log(a);100
		console.log(f);123
		分析
		GO {
			a : 100,
			demo : function(){},
			f : 123
		}
		AO {
			e : 2,
			b : undefined,
			c : function(){}
			a : 10
		}



		function a(){
			var a = b = 123;
			console.log(a);
		}


		function fn(a){
			console.log(a); function a(){}

			var a = 123;

			console.log(a);123

			function a(){}

			console.log(a);123

			var b = function(){}

			console.log(b);function(){}

			function d(){}
		}
		fn(1);

		console.log(test);
		function test(test){
			console.log(test);
			var test = 234;
			console.log(test);
			function test(){
			}
		}
		test(1);
		var test = 123;


		global = 100;
		function fn(){
			console.log(global);undefined
			global = 200;
			console.log(global);200
			var  global = 300;
		}
		fn();
		var global;





		 GO{
		 	a : undefined
		 	test : function test(){}
		 }


		function test (){
			console.log(b);undefined
			if(a) {
				var b = 100;
			}
			c = 234;
			console.log(c);234
		}
		var a;
		 AO{
		 	b : undefined
		 }

		test();
		a = 10;
		console.log(c);234

		百度13年笔试题
		1.
		function bar(){
			return foo;
			foo = 10;
			function foo(){

			}
			var foo = 11;
		}
		console.log(bar());
		2.
		console.log(bar());
 			function bar(){
 				foo = 10;
 				function foo(){

 				}
 				var foo = 11;
 				return foo;
 			}

		求值 (window.foo || (window.foo = 'bar'));    值为'bar'
		
		   运行期上下文：当函数执行的前一刻，会创建一个称为执行期上下文的内部对象。
		   一个执行器上下文定义了一个函数执行时的环境，函数每次执行时对应的执行上下文都是独一无二的，
		   所以多次调用一个函数会导致创建多个执行上下文，当函数执行完毕，它所产生的执行器上下文被销毁。
		   查找变量：从作用域的顶端一次向下查找。
		   [[scope]]：每个JavaScript函数都是一个对象，对象中有些属性我们可以访问，但有些不可以，这些属性仅供JavaScript引擎存取，[[scope]]就是其中一个
						   [[scope]]指的就是我们所说的作用域，其中存储了运行期上下文集合
		   作用域链：[[scope]]中所存储的执行期上下文对象的集合，这个集合呈链式链接,我们把它叫作用域链，但是我们不可访问，仅供JavaScript引擎访问
				
		function a(){    a刚出生时存所在环境的执行期上下文

			function b(){

				function c(){

				}
				c();
			}
			b();
		}
		a();

		a defined a.[[scope]] --> 0 : GO    a定义

		a doing   a.[[scope]] --> 0 : aAO	a执行
								  1 : GO

		b defing  b.[[scope]] --> 0 : aAO	b定义
								  1 : GO

		b doing   b.[[scope]] --> 0 : bAO	b执行
								  1 : aAO
								  2 : GO

		c defined c.[[scope]] --> 0 : bAO	c定义
								  1 : aAO
								  2 : GO

		c doing   c.[[scope]] --> 0 : cAO	c执行 bAO是指向b函数的AO，只是引用
								  1 : bAO
								  2 : aAO
								  3 : GO

		闭包典型案例   但凡是内部的函数被保存在了外部，一定产生闭包
			function a(){
				function b(){
					var bbb = 234;
					console.log(aaa);
				}
				var  aaa = 123;
				return b;
			}
			var glob = 100;
			var demo = a();
			demo();
			function a(){     GO{demo : un,a : func }AO{num : 100, b : func}
				var num = 100;
				function b(){
					num ++;
					console.log(num);
				}
				return b;
			}
			var demo = a();
		案例
			function test(){
				var num = 100;
				function a(){
					num ++;
					console.log(num);
				}
				function b(){
					num --;
					console.log(num);
				}
				return [a,b];
			}
			var myArr = test();
			myArr[0]();
			myArr[1]();
		缓存结构
		function eater(){
			var food = '';
			var obj = {
				eat : function (){
					console.log('i am eating' + food);
					food = '';
				},
				push : function(myFood){
					food = myFood;
				}
			}
			return obj;
		}
		var eater1 = eater();
			eater1.push(' apple');
			eater1.eat();
		立即执行函数 也有返回值，
		定义：此类函数没有声明，在一次执行过后既释放。适合做初始化工作。
		格式：( function () {} () ) W3C建议第一种
		格式：(function () {} ) ()



		var num = (function (c, d, f){
			var a = 123;
			var b = 234;
			console.log(a + b + c * 2 + d * 3 + f * 4);
			d = a + b + c * 2 + d * 3 + f * 4;
			return d
		}(1, 2, 3))



		能被函数表达式执行的函数，函数名将自动忽略
		只有表达式才能被执行符号执行   加正负符号或运算符，与运算符，!号后可变为表达式，可被执行
		+ function test(){
			console.log('a');
		}();
		
		function test(){
			var arr = [];
			for(var i = 0; i < 10; i++){

				(function (j){
				arr[j] = function (){
					document.write(j + ' ');
					}

				}(i));
			}
			return arr;
		}

		var myArr = test();
		for(var j = 0; j < 10; j++){
			myArr[j]();
		}

		
		function test(){
			var arr = [];
			for(var i = 0;i<10;i++){
				arr[i] = function(){
					document.write(i + ' ');
				}
			}
			return arr;
		}
		var myArr = test();
			for(var j = 0;j<10;j++){
				myArr[j]();
			}



		闭包精细版
		内存泄漏是指可用内存变少。
		闭包的作用
		实现公有变量
		如 函数累加器
		可以做缓存（存储结构）
		如 eater
		可以实现封装，属性私有化
		如 Person();
		模块化开发，防止污染全局变量
		
			快速判断闭包：三点
				1、嵌套函数
				2、内层函数，一定操作了外层函数的局部变量
				3、外层函数一定将内层函数返回到外部保存在一个全局变量中；

				判断闭包的执行结果：
				1、外层函数被调用几次，就有几个受保护的局部变量的副本
				2、来自一个闭包的函数被调用几次，受保护的局部变量就变化几次
				3、用闭包解决闭包
		

		函数累加器
		function add(){
			var num = 0;
			function a() {
				console.log(++num);
			}
			return a;
		}
		var myAdd = add();
		myAdd();
		myAdd();
		myAdd();



		var demo;
		function test(){
			var abc = 100;
			function a () {
				console.log(abc);
			}
			demo = a;
		}
		test();
		demo();

		缓存结构
		function test() {
			var food = 'apple';
			var obj = {
				eatFood : function() {
					if(food != '') {
						console.log('I am eating + food');
						food = '';
					}else{
						console.log('There is nothing! empty!');
					}
				},
				pushFood : function (myFood){
					food = myFood;
				}
			}
			return obj;
		}

		var person = test();

		person.eatFood();
		person.eatFood();
		person.pushFood('banana');
		person.eatFood();


		案列
		function test(){
			var arr = [];
			for(var i = 0;i < 10; i++){
				+function(j){
				arr[j] = function(){
					document.write(j + ' ');
				}
				}(i);
			}
			return arr;
		}
		var myArr = test();
		for(var j = 0; j < 10; j++){
			myArr[j]();
		}


		var num = 100;
		function a (){
			console.log(num);
		}
		var num = 200;
		a();

		新立即执行函数语句
		var demo = function(){
			console.log('a');
		}(); 加上执行符后就不代表定义函数


		求字符串的字节长度
		
					function retByteslen(target){
						var count = 0;
						for(var i = 0; i < target.length; i++){
							if(target.charCodeAt(i) <= 255){
								count ++;
							}else if(target.charCodeAt(i) > 255){
								count += 2;
							}
						}
						console.log(count);
					}
		优化版
			function retByteslen (target){
				var count,
					len,
					count = len = target.length;
				for(var i = 0;i < len;i++){
					if(target.charCodeAt(i) > 255){
						count ++;
					}
				}console.log(count);
			}

		var f = (
			function f(){
				return '1';
				},	逗号计算符，先看前面表达式，如果前面表达式就计算，计算好后再看后面表达式，需要执行就执行后面表达式，执行完后并返回后一位
			function g(){
				return 2;
				}
			)();
			console.log(typeof(f));

		经典  因为function外加了括号，因此变成了函数表达式，此时函数名已销毁，因此f是undefined
		var x = 1;
		if(function f(){}){
			x += typeof f;
		}

		console.log(x);x为 1undefined  类型为字符串





		对象
		增： mrDeng.属性 = '属性值'
		删： delete mrDeng.属性
		改： mrDeng.属性 = '属性值'
		查： mrDeng.属性
		var mrDeng = {
			name : 'MrDeng',
			age : 40,
			sex : 'male',
			health : 100,
			smoke : function(){
				console.log('i think smoking! is cool!!!');
				this.health --;
			},
			drink : function(){
				console.log('drink is good');
				this.health ++;
			}
		}

		 var deng = {
			prepareWife : 'xiaowang',
			name : 'laodeng',
			sex : 'male',
			gf : '',
			wife : '',
			divorce : function () {
				delete this.wife;
				this.prepareWife = this.gf;
			},
			getMarried : function() {
				 this.wife = this.prepareWife;
			 delete this.prepareWife;
			 delete this.gf;
			},
			findGf : function(someone) {
				this.gf = someone;
			this.prepareWife = someone;
			}
		} 


		对象的创建方法
		1. var obj = {}		plainObject 对象字面量/对象直接量
		2.构造函数
				1) 系统自带的构造函数 new Object() 创建的对象一摸一样，但相互独立
				2) 自定义
		  通过系统自带函数构造生成	JS与其它语言区别，JS的对象是最灵活的，java和C++需要构造一个类，
		  通过类来批量生产对象，他们生产的对象都是死的，生成后对象里的东西都不可再变
			系统自带的构造函数： 必须要加new才能变为构造函数
			new Number();		var obj = new Object();
			new Boolean();		obj.name = 'test';
			new String();		obj.age = '0';
				构造函数用大驼峰式命名规则 TheFirstName	函数声明用小驼峰式命名规则theFirstName
				用于命名构造函数，构造函数唯一特点就是大驼峰式命名


		自定义构造函数 必须要加new才能变为构造函数 结构上和函数没有任何区别 例
		 founction Car(color){
			有了new后就会在函数逻辑最顶端隐式生成var this = this{}（空对象）
			this.color = color;  颜色通过外部参数更改
			this.name = 'BMW';
			this.height = '1400';
			this.lang = '4900';
			this.weight = 1000;
			this.health = 100;
			this.run = function(){
				this.health --;
			}
			return this 并在最后一步隐式的return this出去
		}

		var car = new Car('red'); 由此传颜色参数
		var car1 = new Car('green'); 
		 function student(name, age, sex){

		 	this.name = name;
		 	this.age = age;
		 	this.sex = sex;
		 	this.grade = 2017;

		 }

		 var student = new student('zhangsan', 18, 'male')

		构造函数内部原理（调用new去执行构造函数时）
		1、在函数体最前面隐式的加上this = {}
		2、执行this.XXX = XXX;
		3、隐式返回this;
		
		function Person(name,height){
			隐式创建名为this的空对象 var this = {_proto_ : Person.prototype} 对象中有系统默认创建的属性-->_proto_，里面存的原型，把prototype.Person给_proto_相当于连接的关系
			例如查找person.name时，会在自己的里面先找，找不到就按照_proto_的指向去prototype.Person里找
			_属性名_，这个意思是创建私有变量，告诉别人能不改就不改
			this.name = name;
			this.height = height;
			this.say = function(){
				console.log(this.say);
			}
			隐式返回this对象 return this; 注！return可以填引用值进行导出值的恶意更改捣乱，但填原始值无效
 		}
		var peleor = new Person('zhao',180); 一定要加new将函数声明转换成构造函数，才会隐式声明this和return值出去，并且return值为引用值才会对其返回值产生影响
		 console.log(new Person('zhao',180).name);


				模拟构造函数执行和隐式调用，不推荐这样，因为有的东西模拟不了如prototype对象__proto__对象，Object.proto
				function Preson(name,height){
					var that = {}; 自己创建任意名的空对象
					that.name = name;
					that.height = height;
					return that;把对象返回出去
				}
				 var people = Preson('zhao',180);
				 console.log(Preson('zhao',180).height);

		包装类  原始值没有属性和方法，只有对象（Object、function、Array都属对象）有属性和方法
		数字对象能参与运算，但是运算后会变成原始值数字
		原始值的数字才是原始值
		包装类
		new Number();
		new String();
		new Boolean();
		
		var num = 4;
			num.len = 3;
			new Number(4).len = 3; delete 因为num为原始值，不能有属性，读到这的时候系统隐式的new了Number对象,并放入num.len属性 属性值为3。做完后立刻删除Number对象

			console.log(num.len);因为num为原始值，不能有属性，读到这的时候系统隐式的new了Number对象,并放入num.len属性，没有属性值，所以打印出的结果为undefined
			new Number(4).len;  
		
		var arr = [1,2,3,4,];
			arr.length = 2;这样操作数组长度是可以的，叫数组截断，只保留前两位
		var str = 'abcd';
			str.length = 2;str没有length属性，是系统new String('abcd').length
			系统识别str里没有length属性，就自动new String('abcd').length=2，并马上delete
			这样操作str是不可以的
		
		var str = 'abc';
			str += 1;
			var test = typeof str;
			if(test.length == 6){
				console.log(test.sign = 'typrof的返回结果可能为String');
				new String(test).sign = 'XXX'; delete
			}new String(test).sign;
			console.log(test.sign);
		
	function Person(name,age,sex){
		var a = 0;
		this.name = name;
		this.age = age;
		this.sex = sex;
		function sss(){ 此处生成了闭包
			a++;
			console.log(a);
		}
		this.say = sss;
	}
	var oPerson = new Person();将Person转为了构造函数，并return出对象
		oPerson.say();此时执行这个函数会触发闭包，对PersonAO里的a进行修改
		oPerson.say();基于上次修改的a继续修改
	var	oPerson1 = new Person();此时又重新构造了函数对象，此时的构造函数和上次构造函数相互独立
		oPerson1.say();基于初始a继续修改
		




		
			GO{
				x : undefined-->1,
				y : undefined-->0,
				z : undefined-->0,
				add : undefined-->function add(n){return n = n + 1}
				 -->function add(n){return n = n + 3},
			}
		
		此题考点是预编译后，函数覆盖问题，因为两个函数为同一个函数，所以AO里的同名函数必定被最后一个函数覆盖
		
		var x = 1,y = z = 0;
		function add(n){
			return n = n + 1;
		}
		y = add(x);
		function add(n){
			return n = n + 3;
		}
		z = add(x);




		
				将输入的内容转化成ascll码
				function transform(){
					var a = window.prompt('请输入');
					var conut,
					count = a.length;
					for (var i = 0;i< count;i++){
						if(a.charCodeAt(i) > 255){
							count ++;
						}
						document.write(a.charCodeAt(i) + ' ');

					}
					return count;
				}
				var num = transform();
				alert(num); 




		
			1、定义：原型是function对象的一个属性，它定义了构造函数制造出的对象的公共祖先。
			通过该构造函数产生的对象，可以继承该原型的属性和方法。
			原型也是对象。
			2、利用原型特点和概念，可以提取共有属性。
			3、对象如何查看原型-->隐式属性__proto__
			4、对象如何查看对象的构造函数-->constructor(构造器的意思)，存在于原型对象里，是系统自己创的属性，
				用来查找对象是由哪个构造函数产出的（浅粉色字体代表是系统自己创建）
		
		一个中文字符占两个字节


		 prototype是函数自带的 -->原型，在函数刚出生时就被定义好了
		 Person.prototype = {__proto__系统自带的属性} 默认就有的空对象 是祖先。是构造函数构造出对象的公有祖先
		构造函数构造出的对象都可用以下基于原型的属性，正常的对象都可以调用自身和原型的属性
		通过调用new Person();并赋给不同的变量，生成相似且独立的对象
		
		Person.prototype.LastName = 'hehe';
		Person.prototype.say = function (){
			console.log('hehe');
		}
		function Person(name,age,sex){
			this.name = name; 诺自身有与原型中属性名一样的属性名，则调用自身的属性名的属性值
			this.age = age;
			this.sex = sex;
		}
		var person = new Person('zhao',20,'male'); person本身是空对象，但可以从原型里拿它没有的属性
		var person1 = new Person();
		




		
		 原型的应用,将共有变量放入原型中，这样声明一次就好，能避免代码冗余,因为Car.prototype是空对象，所以可以如下缩写
		Car.prototype = {
			height : 1900;
			lang : 4900;
			carName : 'BMW';
		}
		Car.prototype.height = 1900;
		Car.prototype.lang = 4900;
		Car.prototype.carName = 'BMW';
		function Car(){
			var this = {}var this = {__proto__ : Person.prototype} 对象中有系统默认创建的属性-->__proto__，里面存的原型，把prototype.Person给_proto_相当于连接的关系
			例如查找person.name时，会在自己的里面先找，找不到就按照__proto__的指向去Person.prototype里找
			__属性名__，这个__ __是创建私有变量，告诉别人能不改就不改
			this.owner = owner;
			this.color = color;
			 this.carName = 'BMW'; 因为属性值固定，并不需修改，所以可以放入原型内，避免每次都重复调用
			 this.height = 1900;
			 this.lang = 4900;
		}
		

		
			 原型的属性增删改查 只能通过Person.prototype+属性来修改 构造函数函数名+.prototype.+属性名
			Person.prototype.name = 'zhao';
			 obj.prototype.lastName = 'ju';
			function Person(){
				 this.name = 'wenqiang';
			}
			var obj = {
				name : 'ju'
			}
			var person = new Person();通过后代是无法更改原型的属性值的，delele person.属性（对象的属性可有可无），都不会报错，返回true
			person.lastName = 'ju',这样是不可以修改原型属性的值的，这样属于在person对象中添加lastName属性
			只能Person.prototype.lastName = XXX，XXX为另一个对象名，这样才可以修改
			原型(Person.prototype)也可更改指向，person.__proto__ = obj;此时person的原型被指向了obj的原型

		constructor(构造器)存在与原型（prototype）中，是它的一种属性，存在于原型对象里，是系统自己创的属性，
					用来查找对象是由哪个构造函数产出的（浅粉色字体代表是系统自己创建）可以手动更改指向的构造函数
		比如person.constructor 意思是查找person对象的构造函数时谁,可以更改对象的构造函数目标
					function Car(){

			}
			var car = new Car();
			function Car1(){

			}

			var car1 = new Car1();
			Car1.prototype.constructor = Car;此时car1的构造函数已指向了Car这个构造函数
			




		
		Test.prototype.name = 'mmm';
		function Test(){
			var this = {__proto__ : Test.prototype} __proto__存储了这个构造函数的原型 __proto__和Test.prototype指向同一个空间，共用属性和属性值
		}
		var test = new Test();test.name在查name是会在自己的属性里先找，找不到就按照__proto__的指向去找，在Test.prototype中找
		Test.prototype.name = 'a';在同一个空间内更改属性值，此时还是指向的同一个空间 同一个属性，换句话说只是改了容器里的东西没有改容器
		Test.prototype = { 更改成不同的空间，此时test.prototype变，但是__proto__指向的空间不变，test1查属性只在__proto__中查。这个连容器也改了
			name : 'b'
		}
		




		__proto__这个属性默认指向 Person.prototype对象，person对象在查找属性时现在自己的属性里找，找不到按照__proto__的指向去找
		
		Person.prototype.name = 'abc'; Person这个构造函数构造出的对象的原型未必非得指向Person这个构造函数，可以被修改
		function Person(){

		}
		var obj = {
			name : 'mmm'
		}
		var person = new Person();(prototype是原型，Person.prototype意思时Person这个构造函数的原型)
		person.__proto__ = obj;此时person的__proto__属性指向的对象不再是Person.prototype对象,而是指向了obj这个对象
		



		
		prototype的赋值在执行函数上下是有区别的，
		Test.prototype.name = 'mmm';
		function Test(){
			var this = {__proto__ : Test.prototype} 隐式增加this是在执行了构造函数的转换后。
		}
		Test.prototype = { 这是把Test的原型给改成了另一个对象
			name : 'zhao';
		}
		var test = new Test();执行到这一行才进行this的添加，此时Test.prototype的值为{name : 'zhao'}
		





		原型链的连接点是__proto__
		 Grand.prototype.__proto__ 的原型是 object.prototype   object.prototype这个是所有对象的最终原型
		
		Grand.prototype.lastName = 'zhao';
		function Grand(){		__proto__  = Grand.prototype{
										Object.prototype{
										}
									}

		}
		var grand = new Grand();

		Father.prototype = grand; 继承了grand的原型   Father.prototype = grand = Grand.prototype
		function Father(){
			this.name = 'xuming';
		}

		var father = new Father();

		Son.prototype = father;继承了father（包含grand）的原型   Son.prototype = Father.prototype = grand = Grand.prototype = Object.prototype
		function Son(){
			this.hobbit = 'smoke';
		}
		var son = new Son();
		
		 原型链的 增 删 改 查
		增 删 改只能由需修改的原型的本身来操作，向下继承的原型没有权限，引用值除外，继承的构造函数可以修改父级构造函数的引用值内容
		如父级构造函数father中有this.furtune = {card : 'No1'},子级构造函数可以直接son.furtune.card1 = 'No2'
		 比如要修改Grand.prototype.lastName的值，只能由Grand修改，不可以以father.prototype.lastName形式修改
		
		function Furtune(){
			this.card = {		父级建一个card对象
				card1 : 'mmm',
				card2 : 'yyy'
			};
			this.name = 'xm' ;
			this.num = 100;
		}
		var furtune = new Furtune(); 通过构造函数生成对象furtune
		Son.prototype = furtune; 把Son.prototype的内容替换成funtune的对象
		function Son(){

		}
		var son = new Son();
		son.num ++;注意这里改的是son的，在son这个对象里先创建个num的属性，再++，
		son.card.card3 = 'ccc';这是一种调用赋值的修改，因为父级构造函数中card是对象,是引用值，所以son可以对card这个对象的内容进行增 删 改 查
		son的card属性里添加card3变量，值为‘ccc’
		





		
		*	a.sayName(),里面的this.name指向是谁调用这个方法this就指向谁
		*
		*
		Person.prototype = {
			name : 'a',
			sayName : function (){
				console.log(this.name);
			}
		}
		function Person(){
			this.name = 'b'
		}
		var person = new Person();

		
		Person.prototype = {
			height : 100
		}
		function Person(){
			this.eat = function(){
				this.height ++;
			}
		}
		var person = new Person();
		person.eat();
		 person.__proto__ 这句意思是查找person对象的原型
		 person.__proto__.__proto__ 这句意思是查找person对象的原型的原型就是最终原型Object.prototype
		 Person.prototype 这句意思是查找Person构造函数的原型
		 Person.prototype.__proto__ 这句意思是查找Person构造函数的原型的原型就是最终原型Object.prototype
		因为是person调用的这个方法，所以在person这个对象里进行修改，
		 因为没有height，所以向父级取了height值，并在自身创建了height属性，值为父级所取值，再执行eat方法，对自身height进行++
		对象字面量的写法和构造函数的写法造出来的对象都一样，最好用对象字面量的写法去写对象


		
		Object.create(放入对象); 也是一种对象创建方法如
			var obj = {name : 'sunny',age : 123};
			var obj1 = Object.create(obj); 意思是创建一个名为obj1Definitel的对象，该对象原型为obj

		Person.prototype.name = 'sunny';
		function Person(){

		}
		var person = Object.create(Person.prototype);此时person原型为Person.prototype
		

		 绝大多数对象最终都会继承自Object.prototype。 Object.create();除外 括号内可填null或者对象，填null就没有Object.prototype


		
				toString()用法

				true.toString(); boolean类型转字符串，返回字符串true

				 123.toString();报错,因为数字加点会被认为是浮点型，后面的toString被当成了数字

				var num = 123; 数字只有这样才能进行toString转换
				 num.toString(); --> new Number(num).toString;
				Number.prototype.toString = function(){} 这个叫方法重写，与原型里的某个方法不同功能同一个名字
				Number.prototype.__proto__ = Object.prototype,没有调用最终原型的Object.prototype.toString方法

				var obj = {};
				obj.toString() 返回"[object Object]"
		

		
		方法重写
		Person.prototype = {
			toString: function () {	近路截断
				return '老邓身体好';
			}
		}
		function Person() {

		}
		var person = new Person();

		都是方法重写
		 Object.prototype.toString
		 Number.prototype.toString
		 Array.prototype.toString
		 Boolean.prototype.toString
		 String.prototype.toString
		

		 var obj = Object.create(null);
		 	obj.toString = function(){
		 		return '321'
		 	}

		
			var obj = Object.create(null);
				obj.toString = function(){
					return '233'
				}
		document.write(obj);调用的toString方法
		

		
		向上取整
		Math.ceil(123.321);不管后面小数位是什么，直接向个位数加一
		向下取整
		Math.floor(123.999);不管后面小数是什么，直接舍弃，只取整数
		 Math.random生成随机数0到一百的随机数


		解决精度问题
		
		for(var i = 0;i < 10;i ++){
			var num = Math.random();
			var num1 = num;
			num = Math.floor(num * 100);
			console.log(num1);
			 num1 = Math.floor(num1.toFixed(2) * 100);
			console.log(num + ' ' + num1);
		}
		

		 JavaScript可正常计算的范围是小数点前16位后16位

		 function test(){}  test();实际是test.call();这样来执行，没有任何区别




		 call和apply，借用别人的方法，实现自己的功能,两者指向位只要填以定义的变量都可以执行
		call
		
		function Person(name,age,sex){
			this.name = name;此时this是obj
			this.age = age;此时this是obj
			this.sex = sex;
		}如果直接执行Person();此时this直接指向Window
		var person = new Person('chen',10);
		var obj ={};
		 Person.call(obj,'deng',100);第一个参数改变this指向，第二个参数对应第一个形参，第二个对应第二个形参
		function Student(name,age,sex,tel,grade){
			执行new Student()时隐式创建了this={}
			Person.call(this,name,age,sex);此时把Person指向改为了this,此时this是指Stundet
			this.tel = tel;
			this.grade = grade;
		}
		var student = new Student('sunny',23,'male',123,155);
		


		
		call改变指向
		function Wheel(wheelSize,style){
			this.wheelSize = wheelSize;
			this.style = style
		}
		function Sit(c,sitColor){
			this.c = c;
			this.sitColor = sitColor;
		}
		function Model(height,width,len){
			this.height = height;
			this.width = width;
			this.len = len;
		}
		function Car(wheelSize,style,c,sitColor,height,width,len){
			 Wheel.call(this,wheelSize,style);
			Wheel.apply(this,[wheelSize,style]);apply改变指向
			 Sit.call(this,c,sitColor);
			Sit.apply(this,[c,sitColor]);apply改变指向
			 Model.call(this,height,width,len);
			Model.apply(this,[height,len,width]);apply改变指向
			call和apply作用是改变this指向，区别是传参列表不同，第一位都要传对象。call需要把实参按照形参顺序传进去，逗号隔开。
			 apply要传个arguments，数组只包含参数，不含重指定的对象里面参数顺序无所谓
		}
		var car = new Car(300,'花里胡哨','舒服极了','骚红',1600,1400,4900);
		





		
				继承发展史   继承的英文（extend、inherit）inherit也是CSS的font-size值 意思是我没有就继承上级的
		1、传统形式-->原型链
			过多的继承了没用的属性
			案例：
				Grand.prototype.lastName = 'zhao';
				function Grand(){

				}
				var grand = new Grand();

				Father.prototype = grand; 继承了grand的原型   Father.prototype = grand = Grand.prototype
				function Father(){
					this.name = 'xuming';
				}

				var father = new Father();

				Son.prototype = father;继承了father（包含grand）的原型   Son.prototype = Father.prototype = grand = Grand.prototype = Object.prototype
				function Son(){
					this.hobbit = 'smoke';
				}
				var son = new Son();
	2、	借用构造函数
			不能继承借用构造函数的原型
			每次构造函数都要多走一个函数
			案例：
				function Wheel(wheelSize,style){
					this.wheelSize = wheelSize;
					this.style = style
				}
				function Sit(c,sitColor){
					this.c = c;
					this.sitColor = sitColor;
				}
				function Model(height,width,len){
					this.height = height;
					this.width = width;
					this.len = len;
				}
				function Car(wheelSize,style,c,sitColor,height,width,len){
					Wheel.call(this,wheelSize,style);
					Wheel.apply(this,[wheelSize,style]);apply改变指向
					Sit.call(this,c,sitColor);
					Sit.apply(this,[c,sitColor]);apply改变指向
					Model.call(this,height,width,len);
					Model.apply(this,[height,len,width]);apply改变指向
					call和apply作用是改变this指向，区别是传参列表不同，第一位都要传对象。call需要把实参按照形参顺序传进去，逗号隔开。
					 apply要传个arguments，数组只包含参数，不含重指定的对象里面参数顺序无所谓
				}
				var car = new Car(300,'花里胡哨','舒服极了','真皮',1600,1400,4900);
	3、	共享原型
			不能随便改动自己的原型
			案例：
				Father.prototype.lastName = 'deng'
				function Father(){

				}
				function Son(){

				}
				Son.prototype = Father.prototype; Son的原型从Father的原型继承
				var son = new Son();
				var father = new Father();
			案例优化:
				function Ferther(){}
				function Son(){}
				function inherit(Traget,Origin){Target.prototype = Origin.prototype;}构造函数原型继承方法
				inherit(Son,Father);继承要在生成对象前面
				var son = new Son();
			缺点 Son的原型不能加自己仅有的属性，因为Son和Father都是指向同一个对象空间，无论谁操作，都是更改的这个空间内的东西
	4、	圣杯模式 功能丰满的继承模式
			案例：
				function inherit(Target,Origin){
					function F(){}
					F.prototypr = Origin.prototype;把被继承的构造函数的原型赋给F的原型
					Target.prototype = new F();把F的原型给要继承的构造函数的原型
					Target.prototype.constuctor = Target;把Target函数来源改为自己
					Target.prototype.uber = Origin.prototype;定义个最终继承自谁的属性
				}
				Father.prototype.lastName = 'deng';
				function Father(){}
				function Son(){}
				inherit(Son,Father);
				var son = new Son();
				var father = new Father();
				圣杯模式--雅虎版本
				var inherit = (function(){
					var F = function (){};
					return function (Target,Origin){ 此处生成闭包   Target是要继承的，Origin是被继承的
						F.prototype = Origin.prototype;
						Target.prototype = new F();
						Target.prototype.constuctor = Target;    定义由自己构造
						Target.prototype.uber = Origin.prototype; 定义真正继承自谁
					}
				}());
				


		 Father.prototype.lastName = 'deng';
		 function Father() { }
		  function F(){}
		  F.prototype = Father.prototype;
		 function Son() { }
		 Son.prototype = new Father();
		  Son.prototype = new F();
		 var son = new Son();
		 var father = new Father();


		命名空间


		 变量私有化应用 模块化开发
		解决污染全局变量问题 方法一：命名空间；方法二：闭包；
				var a = 10;
				var test = (function(){
					var a = 0;
					function add(){
						if(a <300){
						for(var i = 0;i <= 50;i++){
							a ++;
							}
						}
					}
					function mo(){
						if(a < 300){
							a *= 2;
						}
					}
					return function(){
						add(a);
						mo(a);
						console.log(a);
					}
				}())



		零碎小知识点
			1.对象的连续调用
			var deng = {
				smoke : function (){
					console.log('smoking.....cool!!!');
					return this
				},
				drink : function (){
					console.log('drinking.....cool!!!');
					return this
				},
				perm : function (){
					console.log('perming.....cool!!!');
					return this
				}
			}
			
		 2.按序号打印出内容
		
		var deng = {
			wife1 : {name:'xiaoliu'},
			wife2 : {name:'xiaozhang'},
			wife3 : {name:'mazi'},
			wife4 : {name:'xiaowang'},
			sayWife : function(num){
				return this['wife' + num];
			}
		}





		对象枚举/遍历(enumeration)
		就是依次拿出来
		 普通for循环遍历		
			var arr = [1,2,3,4,5,6,7,8,9];
			for(var i = 0;i < arr.length;i++){
				  console.log(arr[i]);
			   }
		专门变例对象的for循环   通过对象属性的个数来控制循环圈数 
		  test就是要遍历的对象 er是个存放属性名的变量 遍历出的er值是字符串类型
		test.name执行时会被隐式转换成 --> 这种test['name']形式其中值为字符串，改为test[name],这样访问的就是变量了 
		test.hasOwnProPerty(name)这个属性就是用来判断属性是否为对象自己的,查询到Object.prototype 原型链的最顶端截至
		只要是自己设置的属性，不管设在对象的哪个地方，都可以被查到，
		
		for in 专门用来遍历对象的for循环
		var test = {
			name : 'qwe',
			age : 12,
			sex : 'male',
			height : 123,
			weight : 321,
		}
		判断是否是该对象的属性，并进行操作
		for(var er in test){
			if(test.hasOwnProperty(er)){
			console.log(test[er]);
			}
		}


		in操作符，专门用来查看对象里有没有这个属性
		 例：
		 'height' in test  查看height属性是否在test这个对象里，存在则会返回true 不存在则返回false，注意属性是字符串形式，
		in和hasOwnProperty的区别是，in是只判断对象能不能访问到这个属性，能就返回true。hasOwnProperty是必须直属于审核的对象(属性只能存在于被审核对象中)，


		 A instanceof B
		判断对象A是不是构造函数B构造出来的
		看A的原型链上有没有B的原型
		 例
		 function Person(){

		 }
		 var person = new Person();
		  person instanceof Person;  判断对象person是不是构造函数Person构造出来的



		 区别数组和对象的三种方法
		 var arr = [];
		 var obj = {};
		1. constructor
			arr.constructor 返回结果为 function Array(){}
			obj.constructor 返回结果为 function Object(){}
		
		2.instanceof
			arr instanceof Array   返回结果为 true
			arr instanceof Object   返回结果为 true
			obj instanceof Object  返回结果为true
			obj instanceof Array  返回结果为false
		
		3.toString/call
			Object.prototype.toString.call(arr)  返回结果为 "[object Array]"
			Object.prototype.toString.call(obj)  返回结果为 "[object Object]
		


		this
		
			1.函数预编译过程中this指向window
			function test (c){
				var a = 123;
				function b(){}
			}
			test(1);  如果是new test(); this会这样创建 this= Object.create(test.prototype)
				AO{
					arguments : [1],
					this : window,会隐式创个this对象
					c : 1,
					a : undefined,
					b : function(){}
				}
			2.全局作用域里this指向window
			3.call/apply路由改变函数运行时this指向
			4.obj.func();func()里的this指向obj

			this指向
			全局环境中this指向全局对象
			函数中的this，由调用函数的方式来决定
				如果函数是独立调用，在严格模式下禁止this指向全局，此时this是undefined，非严格模式下指向Window
				如果函数是被某个对象调用。那么this指向被调用的这个对象
			构造函数和原型中的this指向生成的实例对象，因为new的原因
		



		
		测试this理解程度
		var name = '222';
		var a = {
			name : '111',
			say : function(){
				console.log(this.name);
				console.log(this);打印出每次调用的谁的name
			}
		}
		var fun = a.say;
		fun();  输出'222'   上一步把a.say函数体赋给了fun,而fun是在全局环境下执行的，所以this指向是window
		a.say();  输出'111' 这个虽然是在全局环境下执行，但是前面有调用者，所以此时say函数里的this指向调用者就是a对象
		var b = {
			name : '333',
			say : function(fun){
				fun();
			}
		}
		b.say(a.say); 输出'222'   此时是把a.say的函数体当成实参传到b.say的形参fun里，
				 	 然后执行形参fun，因为没有人调用fun()，所以fun执行走预编译环节，此时this指向window
		b.say = a.say;  把a.say的函数体赋给了b.say,
		b.say();  输出'333'   执行b对象里的say，因为上一步做了b.say的赋值，
				   所以此时b.say的函数体是a.say的函数体，此时this指向指向b对象
		



		 arguments.callee指向函数自身引用  arguments上只有callee和length属性
		 例
			var num = (function(n){
				if(n == 1){
					return 1;
				}return n * arguments.callee(n-1);  此处用来代替自身
			}(5))
		caller 调用的人的h环境
		
			function test(){
				demo();
			}
			function demo(){
				console.log(demo.caller)
			}
			test();
		
		 var foo = 123;
		 function print(){
		 	this.foo = 234;
		 	console.log(foo);
		 }
		 new print();




		 var a = 5;
		 function test(){
		 	a = 0;
		 	alert(a);
		 	alert(this.a);
		 	var a ;
		 	alert(a);
		 }
		  test();
		 new test();




		圣杯模式继承
		 var inherit = (function(){
		 	var F = function (){}
		 	return function(traget,origin){
		 		F.prototype = origin.prototyoe;
		 		target.prototyoe = new F();
		 		target.prototyoe.constuctor = target;
		 		target.prototyoe.uber = origin.prototyoe;
		 	}
		 }());





		深度克隆
		 遍历对象和数组(for (var prop in Array/Object))
		1、判断是不是原始值      typeof()判断是引用值还是原始值
		2、判断是数组还是对象    toString/constructor/instanceof   用toString判断最合适
		3、建立相应的数组或对象	
		4、递归判断属性值里是否嵌套了数组或对象
			var obj = {													通过对象字面量的方式创建个需要被复制的对象
				name : 123,
				wife : {
					card : ['123','312',['456']],
					son : {
						name : 'xiao',
						height : 123,
					}
				}
			};
		 var obj1 = {};												通过对象字面量的方式创建个接受复制内容的对象
		
		function deepClone(origin,target){  		 	 			创建个转换函数，形参origin是需要复制的对象 复制其内容到形参target
			var target = target || {},      		   	  			做容错方法，如果没有传入接收复制内容的对象，则自动创建接收对象
				toStr = Object.prototype.toString,		  			把辨别对象或数组的方法传给一个变量接受
				arrStr = "[object Array]";     			  			把数组类型赋给arrStr
			for(var prop in origin){        			  			把origin对象里的属性都拿出来
				if(origin.hasOwnProperty(prop)){      	  			判断对象里的属性是否为原型的属性
					if(origin[prop] !== "null" && typeof(origin[prop]) == 'object'){ 			判断取出的属性是不是对象类型

						if(toStr.call(origin[prop]) == arrStr){		把取出的origin属性放在原型的toString方法里执行
							target[prop] = [];						是数组类型则给该属性赋值为数组
					}else{
						target[prop] = {};							否则给该属性赋值为对象
					}
					deepClone(origin[prop],target[prop]);			如果是对象或者数组，将它们放入判断对象或数组的方法里再继续运行，直到遇到原始值为止
					}else{
						target[prop] = origin[prop];  				是原始值则直接赋值
					}
				}
			}
			return target;											返回复制好的对象
		}



		测试
		 function deepClone(target,origin){
		 	var target = target || {},
		 		toStr = Object.prototype.toString,
		 		arrStr = "[object Array]";
		 	for(var prop in origin){
		 		if(origin.hasOwnProperty(prop)){
		 			if(origin[prop] !== 'null' && typeof(origin[prop]) == 'object'){
		 				if(toStr.call(origin[prop]) == arrStr){
		 					target[prop] = [];
		 				}else{
		 					target[prop] = {};
		 				}
		 				target[prop] = toStr.call(origin[prop]) == arrStr ? [] : {};  三目运算版判断
		 				deepClone(target[prop],origin[prop]);
		 			}else{
		 				target[prop] = origin[prop];
		 			}
		 		}
		 	}
		 	return target;
		 }



		三目运算符      条件？满足执行冒号前面，返回结果且不看冒号后面的内容 ：不满足条件则看冒号后面的内容，并且返回值
		 例				问号比较的是Boolean值，为真则执行冒号前面，并返回值为假则执行冒号后面，并返回值
		 var num = '' ? 2 + 2 : 1 + 1;
		 var num = 1 > 0 ? ('10' > '9' ? 1 : 0) : 2;     num结果为0，先算括号内的



		数组生成方法  所有方法都来自于Array.prototype
		1、对象字面量创建  var arr = [,];  只写一个逗号会有一个值为undefined的位置，写逗号叫稀松数组
		2、数组构造函数创建  var arr = new Array();   new Array(10),意思是创一个长度为10的稀松数组，当只有一个数时当作数组长度来创建
		如果new Array(10.2);这样会报错，构造函数数组第一位不能写小数

		 数组读和写
		 arr[num]不可以溢出读   结果是undefined
		 arr[num] = xxx;可以溢出写 

		数组的常用方法(用的es3.0方法)  es3.0 es5.0 es6.0     JS分为三部分： ECMAScrip DOM BOM
		改变原数组 在原数组的基础上进行改变
		 push,pop,shift,unshift,sort,reverse
		 push 在数组最后一位添加数据，可以同时添加多位     pop是把数组的最后一位剪切出来，并可以赋给变量，执行时不传参
		unshift()是在数组最前面加内容，可以同时添加多位   shift是在减去数组的第零位内容         
		reverse() arr.reverse意思是把原数组内容排序给反过来
		手写改动Array原型里的push方法									
		 var arr = [1,2,3];
		 Array.prototype.push = function(){
		 	for(var i = 0;i < arguments.length;i++){
		 		this[this.length] = arguments[i];
		 	}
		 	return this.length;
		 }

		 sort()方法  数组内容诺是无序排列，则自动给数组排序，排序顺序是按ascii码大小从小到大排。从大到小排可以arr.sort().reverse()。sort内可以写函数或函数引用
		 var arr = [1,2,3,3,34,54,12,45,35];
		function test (){..}
		 arr.sort(test);
		 arr.sort(function(x,y){..})第一次调用时，形参第一位和第二位分别写数组的第0位和第1位  
		函数规则1、必须写两个形参
			   	 2、看函数返回值 1）当函数返回值为负数时，那么前面的数放在前面
							   2）为正数时 那么后位的数在前位，前位的数放在后位
							   3）为零时  	不动
		 arr.sort(function(x,y){
		 	return x - y;  是升序排列
		 	return y - x;   是降序排列

		 })	

		把一组有序数组无序排列
		 var arr = [1,2,3,4,5,6,7,8];
		 arr.sort(function(){return Math.random() -0.5;})   

		
		把一组对象按年龄降序排列
		var chen = {
			name : 'chen',
			age : 23
		},
			deng = {
				name : 'deng',
				age : 30
		},
			zhang = {
				name : 'zhang',
				age : 23
		};
		var arr = [zhang,deng,chen];
		arr.sort(function(x,y){ return y.age - x.age});
		

		把一组数组按字节大小排列
		var arr = ['qwe','qwwe','asd','qswef','qefdfrg','qwsdgreg'];
		 arr.sort(function(x,y){return x.length - y.length}); 把数组内容按长度排列
		function retbyte(str){  计算字节长度
			var num = str.length;
			for(var i = 0;i < str.length;i++){
				if(str.charCodeAt(i) > 255){
					num ++;
				}
			}return num;

		}
		arr.sort(function(x,y){  按照字节来排序
			return retbyte(x) - retbyte(y);
		});



		 splice
		arr.splice(从第几位开始，截取多少长度，在切入口添加新数据)
		var arr = [1,2,3,4,5,7];
		arr.splice(5,0,6)意思是在第五位处切进去，不截取内容，在切口处添加个6
		arr.splice(-1,1) -1是倒数第一位，截取长度位1



		不改变原数组
		concat,join-->split,toString,slice
		concat是把两个数组连接起来
		 例
		
		var arr = [1,2,3,4,5];
		var arr1 = [6,7,8,9];
		arr.concat(arr1);

		var newarr = slice(从该位开始截取，截取到该位); 因为不改变原数组，因此要拿个东西来接受复制出的东西
		可以填负数，填负数时 负数加数组长度，就是开始的位数，不写就是整个数组复制并赋值给变量

		join是用传入的符号把数组内容连接起来,并生成字符串，必须填字符串
		 例
		
			var arr = [1,2,3,4,5,6]
			arr.join('~');
		
		split 和join方法是可逆的   join是按括号内的字符串来组合数组内容成字符串，split是按照括号(括号内填字符串)内的来拆分字符串，并生成数组
		 按什么拆就把括号内的数当作截取符
		 例
		
		var arr = [1,2,3,4,5];
		arr.join('~');   把数组内容按照~来组合
		arr.split('~');  把字符串按照~来拆分，并组合成数组


		把一堆字符串连在一起，因为字符串是原始值，存在栈里，调用很折腾，把他们放入数组里调用就很简单，数组是散列存储结构
		
		var  str = '123e',
			str1 = '12wd',
			str2 = 'sdkbjvf',
			str3 = 'slbe',
			str4 = 'skjb';
		var arr = [str,str1,str2,str3,str4]; 叫散列结构
			console.log(arr.join(''));


		类数组
		好处：把数组和对象的特性拼在一起，不是所有数组方法都能用
		 如：arguments ,长的像数组，但没有数组的属性
		
		var obj = {  这就是类数组，必须加上length属性，push最好加上没有length不叫类数组。加上splice方法，就完全和数组张的一样了
			'0' : 'a',
			'1' : 'b',
			'2' : 'c',
			'length' : 3,
			'push' : Array.prototype.push,
			'splice' : Array.prototype.splice
		}

		阿里面试题
		 var obj = {
		 	'1' : 'a',
		 	'2' : 'b',
		 	'3' : 'c',
		 	'length' : 3,
		 	'push' : Array.prototype.push
		 }
		 obj.push('f');
		 obj.push('g');
		 结果为
		 obj = {
		 	'1' : 'a',
		 	'2' : 'b',
		 	'3' : 'f',
		 	'4' : 'g',
		 	'length' : 3,
		 	'push' : Array.prototype.push
		 }  因为是根据数组的push方法来运算，所以懂push原理就可以理解

		 Array.prototype.push = function (target){简化版仿写push方法
		 	this[this.length] = target;
		 	this.length ++;
		 }

		 var obj = {
		 	'1' : 'a',
		 	'2' : 'b',
		 	'3' : 'c',
		 	length : 3,
		 	name : 'xf',
		 	age : 18,
		 	splice : Array.prototype.splice
		 }

		手写type判断类型，并能细判断Object类型
		
		var type1 = {
			'[object Number]' : 'number-object',
			'[object Boolean]' : 'boolean-object',
			'[object String]' : 'string-object',
			'[object Array]' : 'array',
			'[object Object]' : 'object'

		}
		function type (target){
			if(target == null){
				return 'null';
			}
			if(typeof(target) == 'object'){
				var str = Object.prototype.toString.call(target);
				return type1[str]
			}else{
				return typeof(target);
			}
		}

		数组去重
		将数组每一位拿出，如果对象中没有这个属性，则放入对象中存储 有则忽略,并将其添加到数组中
			var arr = [1,2,3,2,3,1,4,3,5,34,45,34];
			Array.prototype.unique = function (){
				var temp = {},
					arr = [],
					len = this.length;
				for(var i = 0;i < len;i++){ 取出数组每一位
					if(!temp[this[i]]){     放入对象中查询，没有则进行下一步操作
						temp[this[i]] = 'abe';  给对象赋值并添加到对象中
						arr.push(this[i]);   将该数放入数组中
					}
				}return arr;
			}






		复习
			原始值和引用值区别：1、存储地址不同，原始值存在栈内存中，引用值存在堆内存中。原始值不可以有属性和方法，引用值有属性和方法
			var str = 'abc';字符串是原始值，却能调用length属性，
			new String('abc').length;是因为系统隐式的调用了String包装类，将str的值放入括号中，执行后原地返回个{}在其中加入了length属性，值为3，然后查看length属性，并将结果返回给str.length
			console.log(str.length);打印出结果为3，看似执行的str.length,实际执行的是new String('abc').length,然后将结果返回给str.length,这个过程叫包装类
			叫包装类是因为new String()的括号包住了str
			var num = 123;
			num.abc = 'abe';因为原始值没有属性和方法，此时系统防止报错，隐式的加上了new Number();把num值放入包装类，生成了对象123，并给123这个对象加上abc这个属性，并赋值123。
							但是因为仅仅是赋值，系统不会保存对象123，在赋完值后立刻删除了
			console.log(num.abc);执行到这的时候，系统还会隐式创建对象，然后查看abc这个属性的值，但是因为并没有创这个属性，所以是结果是undefined

		原型
			Persen.prototype.lastName = 'test';
			function Person (){

			}
			var person = new Person ();
		Object.create()    Object.create(prototype,definedproperty)  第一个属性填将被作为原型的对象，第二个填特性
			var demo = {
				name : 123,
				age : 456
			}
			var obj = Object.create(demo); 括号中必须要放入要创建对象的原型，此原型一定要是对象。此时obj的__proto__原型对象内容是demo对象的内容
		 可配置属性和不可配置属性
				var num = 123;
				一旦经过var的操作，所得出的属性，window对象没有删除权，这种属性叫做不可配置属性
				此时num这个属性虽然归window对象所有，但是window并没有删除权，delete不掉
				没有经过var的属性可以删除，如window.num = 123;此时delete window.num是可以的
		this指向
			function test(){
				var num = 123;
				console.log(this);此时this指向window
				function a (){

				}
			}
			test(); --->AO{
							arguments : {},
							this : window,
							a : function(){}
							num : 123,
						}
			1、预编译时this指向window
			2、谁调用的this就指向谁
			3、call apply()中参数第一个填的谁就指向谁
			4、全局模式下this指向window
			var obj = {
					name : 123,
					age : 321
				}
			function test(){
				var num = 123;
				console.log(this);此时this指向window
				function a (){

				}
			}test.call(obj);此时函数的this环境改成了obj，此时括号中参数的第一位就是函数this指向,可以填任何东西，因为只是打印this环境

			var name = 'window'
			var obj = {
				name: 'name',
				age: 321,
				say : function(){
				console.log(this.name);
				}
			}
			var fun = obj.say;把obj中的say函数体赋给fun
			fun();此时fun是自调用，没有call和apply改变指向，所以走预编译环节，此时this指向window，
				  所以执行结果为调用window下的name变量，所以结果为'window'
			fun.call(obj);此时调用了call，将fun函数的this指向改为了obj对象，所以结果为'name'

		

		 function test() {
		 	var num = 123;
		 	this.abc= 123;此时this指向window
		 	console.log(num);
		 	console.log(typeof(num));
		 	function a() {

		 	}
		 } test.call();此时函数的this环境改成了obj
		 var a = window.prompt('输入a'),
		 b = window.prompt('输入b'),
		 c = window.prompt('输入c'),
		 d = window.prompt('输入d');

		 var str = [a,b,c,d];
		  str.sort(
		 	function ty(x ,y){
		 		return x -y;
		 	}
		 )
		 console.log(str.join(' '));

		(function (x){
		 	delete x; 删不掉，因为x是形参，相当于隐式的var个x，var后的变量没有删除权
		 	return x;还是返回1
		 }(1))


		 function test(){
		 	typeof(arguments);  打印结果为Object
		 }
		 test();

		 var x =1;
		 if(function f(){}){   f因为加了括号变为了立即执行函数，所以函数名没有，因为function不为false，所以能执行到主体部分
		 	x+=typeof f;    此时f没有了，所以最终值为1undefined
		 }
		 x;

		字符串去重
		
		var test = (function () {
			var temp = {};
			var str1 = '';
			return function (str) {
				for (var prop in str) {
					if (!temp[str.charCodeAt(prop)]) {
						temp[str.charCodeAt(prop)] = 'test';
						str1 += str[prop];
					}
				}
				return str1;
			}
		}());

		 var str = 'asadqqqqqqqqef';
		 var len = str.length;
		 var temp = {};
		 var str1 = '';
		 for (var i = 0; i < len; i++) {
		 	if (!temp[str.charCodeAt(i)]) {
		 		temp[str.charCodeAt(i)] = 'abc';
		 		str1 += str[i];
		 	}
		 }















		  排错   当try{}里有错时，不抛出错误，try里的后续代码也不执行，跳过try整体执行后面的代码
		try {

		} catch (error) {error是对象，里面存有message和name属性
						执行完catch里的代码会执行catch外面的代码
		}
		
		Error.name的六种值对应的信息：
			1、EvalError:eval()的使用与定义不一致
			2、RangeErrot:数值越界
			3、ReferenceError:非法或不能识别的引用数值
			4、SyntaxError:发生语法解析错误
			5、TypeError:操作数类型错误
			6、URIError:URI处理函数使用不当
		
		 try{
		 	console.log('1');
		 	console.log(a);
		 }catch(e){
		 	console.log(e.message + '~~~~' + e.name);
		 }


			"use strict"
				不再兼容ES3的一些不规则语法。使用全新的ES5规范
				两种用法：
					全局严格模式  写在JS页面最顶端
					局部函数内严格模式(推荐)   写在函数最顶端
				就是一行字符串，不会对不兼容严格模式 浏览器产生影响
				不支持with,argumrnts.callee,func.caller。变量赋值前必须声明，局部this必须被赋
				(Person.call(null/undefined)赋值什么就是什么)，拒绝重复属性和参数
		
		 ES5严格模式
		 目前浏览器用的方法基于ES3.0+ES5.0新增的方法，如果有冲突则用ES3.0的方法
		ES3.0和ES5.0产生中途的部分
		ES5.0严格模式  那么ES3.0火绒ES5.0产生冲突的部分人你就是用ES5.0，否则会用ES3.0
		必须启用ES5.0严格模式才能完全使用ES5.0的方法--在JS部分最顶端加上"use strict";这叫全局严格模式
		写在函数最顶端就叫局部严格模式

		 with可以改变函数作用域链
		
		var obj = {
			name : 'obj',
			age : 234
		}
		var name = 'window';
		function test(){
			var age = 123;
			var name = 'scope';
			with(obj){with改变了console.log代码执行时的作用域，在作用域最顶端加上了obj这个对象
				console.log(name);
			}
		}
		test();
		执行结果为obj
		

		 严格模式下不可以用with

		
		function test(){
			'use strict' 进入严格模式，此时this不再指向window
			console.log(this); 此时this无值，打印为undefined
		}
		new test();new 后把test函数this指向改为了函数本身
		
		严格模式下全局模式下this还是指向window
		eval('console.log(a)');把字符串当代码来执行
		eval在ES3.0下不可以使用，必须在ES5.0严格模式下使用











		DOM  文档对象模型 document object mode
		DOM定义了表示和修改文档所需的方法。DOM对象即为宿主对象，由
		浏览器厂商定义，用来操作html和xml功能的一类对象的集合。也有人称DOM
		是对HTML和XML的标准编程接口
		可以操作HTML标签的行间样式间接修改CSS，但不可以直接修改样式表

		
			1、对节点的增删改查
				查
					查看元素节点
						document代表整个文档
						document.getElementById()元素id在Ie8以下的浏览器，不区分id大小写，
						而且也返回匹配name属性的元素
						getElementByTaName()标签名
						get.ElementByName()需注意，只有部分标签name可生效（表单，表单元素，img，iframe）
						getElementByClassName()类名->ie8和ie以下的ie版本中没有，可以多个class一起
						querySelector()css选择器，在ie7及以下版本没有
						querySelectorAll()css选择器，在ie7及以下版本没有
		

		DOM对象
		var div = document.getElementsByTagName('div')[0];通过document下的getElementByTargetName方法获取到页面的div标签，并生成类数组
			div.style.width = '100px';
			div.style.height = '100px';
			div.style.backgroundColor  = 'red';	因为JS中写-报错，所以带-的属性都用小驼峰式写法
		var count = 0;
		div.onclick = function(){
			count ++;
			if(count % 2 == 1){
				this.style.backgroundColor = 'red';
			}else{
				this.style.backgroundColor = 'blue';
			}

		}
		
		var btn = document.getElementsByTagName('button');
		var div = document.getElementsByTagName('div');

		for(var i = 0;i < btn.length;i++){
			(function(n){
				btn[n].onclick = function(){
				for(var j = 0;j < btn.length;j++){
					btn[j].className = '';
					div[j].className = 'warrp';
				}
				this.className = 'act';
				div[n].className = ' ';
			}
		}(i))
		}

		
		var div = document.createElement('div');创建一个组div
		document.body.appendChild(div);把div插入到页面中
		div.style.height = '100px'; 设置该div的高
		div.style.width = '100px';设置该div的宽
		div.style.backgroundColor = 'red';设置该div的背景色
		div.style.position = 'absolute';设置该div的定位
		div.style.left = '0px';设置该div的离左边的距离
		div.style.top = '0px';设置该div离上边的距离
		
			让方块加速运动
			var speed = 1;
			var timer =	setInterval(function (){
				speed += speed;
				div.style.left = parseInt(div.style.left) + speed + 'px'; 每隔50毫秒让div离左边距离加两像素
				div.style.top = parseInt(div.style.top) + speed + 'px'; 每隔五十毫秒让div离上边距离加两像素
				if(parseInt(div.style.left) > 900 && parseInt(div.style.top) > 900){
					clearInterval(timer);清除定时器
				}
			},50)每五十毫秒执行一次这个函数
			
		 用上下左右键操控小方块
		document.onkeydown = function (e) {
			switch (e.which) {
				case 38:
					div.style.top = parseInt(div.style.top) - 5 + 'px';
					break;
				case 40:
					div.style.top = parseInt(div.style.top) + 5 + 'px';
					break;
				case 37:
					div.style.left = parseInt(div.style.left) - 5 + 'px';
					break;
				case 39:
					div.style.left = parseInt(div.style.left) + 5 + 'px';
					break;
			}
		}
		



		
		<div>
			<span>
				<strong id='str' class='cool'></strong>
			</span>
		</div>
		
		 var div = document.getElementById('str');id选择器,直接填入id名就好,填入name属性值也可以选中要选的东西,选出的是一个
		 var target = document.getElementsByTagName('strong')[0];标签选择器，不加中括号以类数组的方式呈现，加中括号和位，则显示对应位的选中内容,0代表html中第一个
		 var cla = document.getElementsByClassName('cool')[0];类名选择器,不加中括号以类数组的方式呈现,加中括号和位,则显示对应位的选中内容,0代表html中第一个
		 var qu = document.querySelector('div > span > strong');css选择器,可以按css中选择元素那样写
		 var qus = document.querySelectorAll('div > span > strong');这两个query查询方法不是实时更新,只是拷贝个副本,如果源标签更改,它选中的元素不实时更改	
		 var newDiv = document.createElement('div');添加新div;
		 document.body.appendChild('newDiv');将新建的div作为子元素放入body标签中
		 var ta = document.getElementsByName('');只有部分有name的标签能生效，如(表单，img，iframe);
		遍历节点树 不管什么类型的节点都遍历一遍  parentNode，childNodes,fistChild,lastChild
		 body父级是html，HTML父级是document,document没有父级   parentNode——查询该标签父级，如body.parentNode 打印出父级为HTML，span.parentNode——父级为div
		 XXX.childNodes XXX的子节点们，XXX.firstChild XXX第一个子节点，XXX.lastChild XXX最后一个子节点，
		 XXX.nextSibling XXX的最后一个子节点，XXX.previousSibling XXX前一个兄弟节点
		 节点类型
		元素节点——1
		属性节点——2
		文本节点——3
		注释节点——8
		document——9
		documentEragment——11
		

		
		基于元素节点树的遍历  只遍历元素节点
			XXX.parentElement 返回当前元素XXX的父元素节点(IE不兼容)
			XXX.children 值返回当前元素XXX的元素子节点
			XXX.node.childElementCount  === node.children.length 当前元素XXX节点的子元素个数等于元素子节点数组长度
			XXX.firstElementChild 返回的是XXX第一个元素节点(IE不兼容)
			XXX.lastElementChild 返回的是XXX最后一个元素节点(IE不兼容)
			XXX.nextElementSibling/previousElementSibling 返回XXX后一个或前一个兄弟元素
		

		
		节点的四个属性
			nodeName
				元素的标签名，以大写形式表示，只读
			nodeValue
				Text节点或者Comment(注释)节点的文本内容，可读写，只有这两个节点有
			nodeType
				该节点的类型，只读
			attributes
				元素节点的属性集合，可以结合.valus更改属性值
		节点的一个方法
			Node.hasChildNodes();
				看元素节点上有没有它的子节点
		





		
			 拿出一个元素的所有子元素节点
			<div>
				<strong></strong>
				<em><em>
				<h1></h1>
				<i></i>
			</div>
			function retchild(node){
				var temp = {
					length : 0,
					push : Array.prototype.push,
					splice : Array.prototype.splice
					},
					child = node.childNodes,
					len = child.length;
				for(var i = 0;i < len;i++){
					if(child[i].nodeType === 1){
						temp.push(child[i]);
					}
				}
				return temp;
			}
			console.log(retchild(div));
			

		 DOM继承树
								Node
		Document(文档)     	 CharacterData   		Element(文档中的元素)			Attr
		HTMLDocument		Text Comment		HTMLElement
												{HTMLHeadElement
												HTMLBodyElement
												HTMLTitleElement
												HTMLParagraphElement
												HTMLLInputElement
												HTMLTableElement
													...etc.}
		 Document是构造函数，但是我们不能用它去构造对象
		 document对象是由HTMLDocument构造出的
		
		在原型链上编写查找子元素节点树的方法
		var div = document.getElementsByTagName('div')[0];
		var arr = [];
		Element.prototype.childrenNodes = function () {
			var child = this.childNodes;
			var len = child.length;
			for (var i = 0; i < len; i++) {
				if (child[i].nodeType == 1) {
					arr.push(child[i]);
					child[i].childrenNodes();
				}
			}
		 return arr;
		}
		

		封装函数，返回元素e的第n层祖先元素节点
		
		function rePar(elem,n){
			while(elem && n){
				elem = elem.parentElement;
				n --;
			}
			return elem;
		}
		var i = document.getElementsByTagName('i')[0];
		rePar(i,3);
		

		
		 手动封装children函数
		var div = document.getElementsByTagName('div')[0];
		function mychild(){
			var child = this.childNodes;
			var len = child.length;
			var arr = [];
			for(var i = 0;i < len;i++){
				if(child[i].nodeType == 1){
					arr.push(child[i]);
				}
			}
			return arr;
		}
		

		
		 手动封装hasChildren函数
		var div = document.getElementsByTagName('div')[0];
		function mychild(){
			var child = this.childNodes;
			var len = child.length;
			var arr = [];
			for(var i = 0;i < len;i++){
				if(child[i].nodeType == 1){
					return true;
				}else{
					return false;
				}
			}
			return arr;
		}
		

		
		 当n为正数时求e得上一个节点，为负时求下一个节点，为0返回自己
		var strong = document.getElementsBytagetName('strong')[0];
		function retSibling(e,n){
			while(e && n){
				if(n > 0 && e){
					e = e.nextElementSibling;下一个节点
					n --;
				}else{
					e = e.previousElementSibling;上一个节点
					n ++;
				}
			}
			return e;
		}
		retSibling(strong,2);
		
		优化版
		vr strong = document.getElementsByTagName('strong')[0];
		function retSibling(e,n){
			while(e && n){
				if(n > 0 ){
					if(e.nextElementSibling){
						e = e.nextElementSibling;
					}else{
						for(e = e.nextSibling;e && e.nodeType != 1;e = e.nextSibling);
					}
					n --;
				}else{
					if( e.previousElementSibling){
						e = e.previousElementSibling;
					}else{
						for(e = e.previousSibling; e && e.nodeType != 1;e = e.previousSibling);
					}
					n ++;
				}
			}
			return e;
		}
		




		 DOM操作
		 var div = document.createElement('div');
		 var span = document.createElement('span');
		 var i = document.createElement('i');
		 var strong = document.createElement('strong');
		 var p = document.createElement('p');
		 document.body.appendChild(div);
		 div.appendChild(span);
		 div.appendChild(i);
		 div.insertBefore(strong,i);
		 增
		var div = document.createElement('div');  	JS中增加元素节点
		 var text = document.createTextNode(' 123'); JS中增加文本节点
		 var comment = document.createComment('这是注释'); JS中增加注释节点
		 var do = document.createDocumentFragment('');JS中创建文档碎片节点
		document.body.appendChild(div);将div标签放入HTML文档中
		div.innerHTML = 1234; 对HTML文档中的选中的div进行内容修改

		 插入 parentNode意思是父节点
		 parentNode.appendChild(); 在元素中最后面插入东西，把页面中有的节点，插入到另一个位置时，原先的就没了，被剪切到要插入的位置了
		 如div.appendChild(text);在div最后面中插入文本节点
		 XXX.insertBefor(a,b);
		 如 XXX.insertbefor(span,p); 在XXX父级元素内 插入span在p标签的前面

		 删除
		 parentNode.removeChild(); 父节点删除自己的子节点，操作是剪切走，可以赋值给其它变量
		 child.remove(); 子节点自己删除自己，是直接删除如 i.remove();


		 替换
		 parentNode.replaceChild(new , origin); 父节点把子节点的origin(老的)替换成new(新的)，剪切的手法进行替换的
		 如 div.replaceChild(p,strong);

		 Element的属性
		 		innerHTML  获取的是元素的内容，div.innerHTML = '123'; 对内容进行覆盖，div.innerHTML += '456';在123后面添加456,+=只能作用在可读可写的内容里
				innerText(老版火狐不兼容/textContent(老版IE不好用))  获取的是元素内的文本内容，div.inneerText = 123; 内容是全覆盖的，如果div内还有其它元素，不要使用，如果里面只有文本可以使用

		 Element的方法
				div.setAttribute('class','demo'); 给div的行间样式加个class类，类名为demo
				div.getAttribute('id');获取div的id属性值


		给div下的所有子元素添加this-name属性，属性值为该元素的元素名
		var div = document.getElementsByTagName('div')[0];
		var c =  div.children;
		var len = c.length;
		for(var i = 0 ;i < len ;i++){
			console.log(c[i]);
			c[i].setAttribute('this-name',c[i].nodeName);
		}
		


		手写insertAfter方法
		 	var div = document.getElementsByTagName('div')[0];
		 	var p = document.createElement('p');
		 	var span = document.getElementsByTagName('span')[0];
		 	var b = document.getElementsByTagName('b')[0];
		 Element.prototype.insertAfter =	function (targetNode , afterNode){
		 		var beforNode  = afterNode.nextElementSibling;
		 		if(beforNode == null){
		 			this.appendChild(targetNode);
		 		}else{
		 			this.insertBefore(targetNode,beforNode);
		 		}

		 	}


		将元素倒序排列
		
		var div = document.createElement('div');
		var p = document.createElement('p');
		var span = document.createElement('span');
		var i = document.createElement('i');
		var em = document.createElement('em');
		document.body.appendChild(div);
		div.appendChild(p);
		div.appendChild(span);
		div.appendChild(i);
		div.appendChild(em);
		var all = document.getElementsByTagName('div')[1];
		var alle = all.childNodes;
		var len = all.children.length;
		for(var i = len-1;i >=0;i--){
			all.appendChild(alle[i]);
		}
		



		 日期对象 Date();  系统提供好的
		 var date = new Date();
		date.getDate();指打印出今天是这个月的第几天
		date.getDay();指打印出今天是这周的第几天 从0(星期天)开始计数，
		date.getMouth();指打印出当前月份是第几个月 从0开始计数
		 date.getFullYear();年份以四位数来展示，getYear()已经不用了，它是两位数来展示的
		 date.getHours();获取当前小时数
		 date.getMinutes();获取当前分钟数
		 date.getSeconds();获取当前秒数
		 date.getMilliseconds();返回毫秒(0~999)
		date.getTime();获取自1970年1月1日起到现在的毫秒数


		打印当前时间
		 setInterval(function get(){
		 	var date = new Date();
		 	console.log(date.getFullYear() + '年 ' + date.getMonth() + '月 '  + date.getDate() + '日 ' + ca()  +' ' + date.getHours() + ' 点' + date.getMinutes() + ' 分' + date.getSeconds() +' 秒')
		 },1000)
		 function ca(){
		 	switch(new Date().getDay()){
		 		case 0: return '星期日';
		 		break;
		 		case 1: return'星期一';
		 		break;
		 		case 2: return'星期二';
		 		break;
		 		case 3: return'星期三';
		 		break;
		 		case 4: return'星期四';
		 		break;
		 		case 5: return'星期五';
		 		break;
		 		case 6: return'星期六';
		 		break;
		 	}
		 }


		 setInterval(function(){},time)定时器,第一个写函数，第二个写时间，定时器不准
		clearInterval(); 清除定时器
		例如
		 var i = 0;
		 var timer = setInterval(function(){
		 	console.log(i++);
		 	if(i >10){
		 		clearInterval(timer);
		 	}
		 },1000)
		 setTimeout(); 计时器
		计时器
		var inputs = document.createElement('input');
		var inputm = document.createElement('input');
		var body = document.getElementsByTagName('body')[0];
		document.body.appendChild(inputm);
		document.body.appendChild(inputs);
		inputs.value = 0;
		inputm.value = 0;
		var text  = document.createTextNode(' secound:');
		var text2  = document.createTextNode('minutes:');
		inputs.style.textAlign = 'right';
		inputm.style.textAlign = 'right';
		body.insertBefore(text,inputs);
		body.insertBefore(text2,inputm);
		var jishi = setInterval(ji,1000);
		function ji(){
			inputs.value ++;
			if(inputs.value == 60){
				inputm.value ++;
				inputs.value = 0;
			}
			if(inputm.value == 3){
				clearInterval(jishi);
			}
		}

		 BOM基本操作
		 查看滚动条滚动距离
		 window.pageXOffset查看页面X轴滚动距离
		 window.pageYOffset查看页面Y轴滚动距离
		 IE8及以下不兼容
		 IE8及以下用
		 document.body.scrollLeft 取X轴滚动条滚动距离
		 document.documentElement.scrollLeft 取X轴滚动条滚动距离
		 document.body.scrollTop 取Y轴滚动条滚动距离
		 document.documentElement.scrollTop取Y轴滚动条滚动距离
		 兼容IE8及以下浏览器就用如下方法
		 document.body.scrollLeft + document.documentElement.scrollLeft  求IE8及以下浏览器X轴滚动距离
		 document.body.scrollTop + document.documentElement.scrollTop    求IE8及以下浏览器Y轴滚动距离

		求x y轴页面大小
		 function getscrolloffset(){
		 	if(window.pageYOffset){
		 		return {y : window.pageYOffset,
		 				x : window.pageXOffset
		 		}
		 	}else{
		 		return{
		 			y : document.body.scrollTop + document.documentElement.scrollTop,
		 			x : document.body.scrollLeft + document.documentElement.scrollLeft
		 		}
		 	}
		 }
		 混杂模式和标准模式
		 混杂模式下浏览器以以前版本的语法标准来渲染页面
		 标准模式以浏览器目前最新语法标准来渲染页面
		 <!DOCTYPE html> 文档格式是html格式 DOCTYPE是DocumentType,文档类型

		 document.compatMode  查看当前浏览器模式

		 查看客户端页面高度(标准模式)
		 document.documentElement.clientHeight
		查看客户端页面高度(怪异模式)
		 document.body.clientHeight
		 查看客户端页面的宽度(标准模式)
		 document.documentElement.clientWidth
		查看客户端页面宽度(怪异模式)
		 document.body.clientWidth


		求客户端窗口大小兼容多版本浏览器
		 function getClientView(){
		 	if(window.innerHeight){
		 		return {
		 			w : window.innerWidth,
		 			h : window.innerHeight
		 		}
		 	}else{
		 		if(document.compatMode === "BackCompat"){
		 			return {
		 				w : document.body.clientWidth,
		 				h : document.body.clientHeight
		 			}
		 		}else{
		 			return {
		 				w : document.documentElement.clientWidth,
		 				h : document.documentElement.clientHeight
		 			}
		 		}
		 	}
		 }
		 查看元素几何尺寸的方法
		 domEle.getBoundingClientRect();将返回个对象内涵这个元素各个点相对页面左顶点的距离
		 但是老版IE未实现height和width，我们可以通过right-left得出width，bottom-top得出heigth
		返回结果并不是实时的

		 查看元素尺寸方便方法，如果父级有定位，则是求距父级的距离，如果父级没有定位，则求该元素至文档的距离
		 dom.offsetHeight; 查看元素视觉上的高，看起来多高就多高
		dom.offsetWidth; 查看元素视觉上的宽，看起来多宽就多宽
		dom.offsetTop; 查看元素顶端离页面顶端距离
		dom.offsetLeft; 查看元素离左边距离页面左边缘距离
		 dom.offsetParent返回最近的有定位的父级，如果没有就返回body，body.offsetParent是最后一级父级返回值为null
		让滚动条滚动
		 window.scroll(x,y);第一个值代表X轴滚动距离，第二个值代表Y轴滚动距离，Window.scrollTo(x,y)和scroll一样效果
		 window.scrollBy(x,y);把滚动距离累加起来，执行都基于目前滚动条距离

		自动阅读
		 var star = document.getElementsByTagName('div')[0];
		 var stop = document.getElementsByTagName('div')[1];
		 var timer = 0;
		 var key = true;
		 star.onclick = function(){
		 	if(key){
		 		setInterval(function(){
		 		window.scrollBy(0,10);
		 		key = false;
		 	},100)
		 	}
		 }
		 stop.onclick = function(){
		 	clearInterval(timer);
		 	key = true;
		 }


		 读写元素的CSS属性
		 dom.style.prop   获取行间样式,行间没写的属性就没有
		 可读写行间样式，没有兼容性问题，碰到float这样的保留属性，前面应该加css  cssFloat
		 复合属性(border,拆解成borderWidth,borderColor等等)和组合单词必须拆写成小驼峰式写法
		 写入的值必须是字符串形式
		查询css属性(都是只读样式,只能获取)
		window.getComputedStyle(ele,null)[style],如window.getComputedStyle(div,null).width,第二个值填伪元素,用不到就填nullIE8及以下不兼容
		返回的值都是绝对值,是经过转换的,如window.getComputedStyle(div,null).color的返回值为rgb(..,..,..)
		 获取伪元素宽高 window.getComputedStyle(div,"after").width,获取div这个元素的伪元素的宽

		ele.currentStyle[prop],如div.currentStyle.width.IE独有的属性
		返回的值是未经计算的值

		 封装获取元素样式的有兼容的方法
		 function getStyle(ele,prop){
		 	if(window.getComputedStyle){
		 		return window.getComputedStyle(ele,null)[prop];
		 	}else{
		 		return ele.currentStyle[prop];
		 	}
		 }


		 事件
		 ele.on + 事件 = function(){};
		 兼容性很好,但是一个元素的同一个事件上只能绑定一个处理程序,基本等同于写在HTML行间上
		 ele.addEventListener("事件",函数,false);false改成true将触发事件捕获
		 IE9以下不兼容,可以为一个事件绑定多个处理程序
		 ele.attachEvent("on + 事件",处理函数);
		IE独有,可以为一个事件绑定多个处理程序

		给li绑定事件
		 var li = document.getElementsByTagName('li');
		 for (var i = 0; i < li.length; i++) {
		 	(function(j){
		 		li[j].addEventListener('click',function(){console.log(j)},false) 
		 	})(i)	
		 }

		
		事件处理程序的运行环境
			1、ele.onXXX = function(event){}
				程序this指向是dom元素本身
			2、ele.addEventListener('type',fn,false)
				程序this指向是dom元素本身
			2、ele.attachEvent('on'+type,fn);
				程序this指向window
		

		 事件绑定函数，要求兼容性
		function addEvent(ele,type,handle){
			if(ele.add.addEventListener){
				ele.addEventListener('type',handle,false);
			}else if(ele.attachEvent){
				ele.attachEvent('on' + type,function(){handle.call(ele)})
			}else{
				ele['on'+type] = handle;
			}

		}

		 接触事件处理程序
		 ele.onclick = false/''/nul
		 ele.removeEventListener('type',fn,false)
		 ele.detachEvent('on'+type,fn)
		 !!绑定匿名函数无法清除

		 事件处理模型——事件冒泡、捕获
			事件冒泡
				结构上(非视觉上)嵌套关系的元素，会存在事件冒泡功能，即同一事件，自子元素冒泡向父元素。(自底而上)
			事件捕获
				结构上(非视觉上)嵌套关系的元素，会存在事件捕获功能，即同一事件，自父元素捕获至子元素(事件源元素)。(自顶向下)
				IE没有捕获事件
				ele.addEventListener('type',fn.true),true代表开启事件捕获
			触发顺序，先捕获再冒泡
				focus,blur,change,submit,reset,select等事件不冒泡
			同一元素绑定了冒泡和捕获，谁先绑定谁就先执行
		


		 var div = document.getElementsByTagName('div');
		 div[0].style.width = '200px';
		 div[0].style.height = '200px';
		 div[0].style.backgroundColor = 'red';
		 div[1].style.width = '100px';
		 div[1].style.height = '100px';
		 div[1].style.backgroundColor = 'green';
		 div[2].style.width = '50px';
		 div[2].style.height = '50px';
		 div[2].style.backgroundColor = 'yellow';
		 div[0].addEventListener('click',function(){console.log('warrper')},false);
		 div[1].addEventListener('click',function(){console.log('content')},false);
		 div[2].addEventListener('click',function(){console.log('box')},false)

		 取消冒泡
			W3C标准 event.stopPropagation();但不支持ie9以下版本
			IE独有(谷歌也可以用) event.cancelBubble = true;
			function stopBubble(event){
				if(event.stopPropagation){
					event.stopPropagation();
				}else{
					event.cancelBubble = true;
				}
			}
		

		阻止默认事件
			默认事件——表单提交，a标签跳转，右键菜单等
			1、return false;
			2、event.preventDefault();W3C标准，IE9以下不兼容
			3、event.returnValue = false;兼容IE
			 取消默认事件函数
			function cancelhander(event){
				if(event.preventDefault){
					event.preventDefault();
				}else{
					event.returnValue = false;
				}
			}
		
		 浏览器右击事件  contextmenu  ele.oncontextmenu = function(){return false}
		例 document.oncontextmenu = function(){
		 	return false;
		 }

		 取消a标签默认事件
		 <a href= "javascript:void(false)"></a>javascript:可以接着后面写JS代码，void(0/false)意思是返回值为false
		 var div = document.getElementsByTagName('div');
		 div[0].onclick = function(e){ 形参只能写一个，虽然我们无法填入实参，但是系统会自动填入，填入事件对象
		  var event = e || window.event;
		 	console.log(event);
		 }
		 事件对象
		 event || window.event(用于IE)
		 事件源对象
		 event.target 火狐只有这个
		 event.srcElement IE只有这个
		 chrome这两个属性都有

		 事件委托
		 利用事件冒泡和事件源对象进行处理
		 优点：
		 1、性能 不需要循环所有的元素一个一个绑定事件
		 2、灵活 当有新的子元素的时候不用再绑定事件
		事件委托 例
		 var ul = document.getElementsByTagName('ul')[0];
		 ul.onclick = function(e){
		 	var event = e || window.event;
		 	var target = event.target || event.srcElement;
		 	console.log(target.innerText);
		 }


		 拖拽
		 var div = document.getElementsByTagName('div')[0];
		 	var divx;
		 	var divy;
		 	div.onmousedown = function (e) {
		 		divx = e.pageX - parseInt(div.style.left);
		 		divy = e.pageY - parseInt(div.style.top);
		 		document.onmousemove = function (e) {
		 			var event = e;
		 			div.style.left = e.pageX - divx + 'px';
		 			div.style.top = e.pageY - divy + 'px';
		 		}
		 		document.onmouseup = function(){
		 			div.onmousemove = null;
		 		}
		 	}
			 div.setCapture();开启div监听全局事件
			 div.releaseCapture();关闭监听
		 鼠标事件
		 	click,mousedown,mousemove,mouseup,contextmenu,mouseover,mouseout,Mouseenter
		 	mouseleave
		 用button来区分鼠标的按键,0/1/2.左键是0,右键是2,滚轮是1 能区分的点击事件只有mousedown,mouseup
		 DOM3标准规定:click事件只能监听左键,只能通过mousedown,mouseup来判断鼠标键
		 判断左右键
		 document.onmousedown = function (e){
		 	if(e.button == 0){
		 		console.log('left');
		 	}else if(e.button == 2){
		 		console.log('right');
		 	}
		 }
			 var key = false;
			 var ft = 0,
			 	lt =0,
			 	divx,
			 	divy;
			 div.onmousedown = function (e){
			 	 ft = new Date().getTime();
			 	divx = e.pageX - parseInt(div.style.left);
			 	divy = e.pageY - parseInt(div.style.top);
			 	 console.log(divy);
			 	div.onmousemove = function(e){
			 		var cont = e.event || window.event;
			 		console.log(cont);
			 		div.style.left = e.pageX - divx + 'px';
			 		div.style.top = e.pageY - divy + 'px';
			 	}
			 }
			 div.onmouseup = function (){
			 	 lt = new Date().getTime();
			 	if(lt - ft < 300){
			 		key = true;
			 	}
			 	div.onmousemove = null;
			 }
			 div.onclick = function(){
			 	if(key){
			 		console.log('click');
			 		key = false;
			 	}
			 }

			随即移动方快
			 var px,py;
			 div.onmouseover = function(e){
			 	px = e.pageX;
			 	py = e.pageY;
			 	div.style.left = Math.floor(Math.random() * 600)  +'px' ;
			 	div.style.top = Math.floor(Math.random() * 600)  +'px' ;
			 	if(px  > 800 || py > 800){
			 		div.style.left = Math.floor(Math.random() *10) + 'px';
			 		div.style.top = Math.floor(Math.random() *10) + 'px';
			 		console.log(px);
			 	console.log(py);
			 	}
			 }

			 移动端事件
			 touchstart touchmove touchend 效果等同于mousedown mousemove mouseup

			 键盘事件 
			 keydown keyup keypress
			keydown > keypress > keyup
			keydown和keyup是一组合
			 keydown和keypress的区别
				 keydown可以响应任意键盘按键，keypress只能响应字符类键盘按键
				 keypress返回ASCII码，可以转换成相应字符 
				 例如
				 document.onkeypress = function(e){console.log(String.fromCharCode(e.charCode))}
				 将ASCII码转换成对应字符

			 document.onkeydown = function(){
			 	console.log('keydown');
			 }
			 document.onkeyup = function(){
			 	console.log('keyup');
			 }
			 document.onkeypress = function(){
			 	console.log('keypress');
			 }


			 input事件  实时监听输入框的值(password类型输入框也可监听数据值)
				 var input = document.getElementsByTagName('input')[0];
				 input.oninput = function(){
				 	console.log(this.value);
				 }

			change事件  对比聚焦和失去焦点两个状态有没有发生改变，发生改变就打印，没有发生改变就不触发
			 var input = document.getElementsByTagName('input')[0];
			 	input.onchange = function(){
			 		console.log(this.value);
			 	}

			 focus(聚焦)  blur(失去焦点)

			 窗体操作类(Window上的事件)
			 scroll load load事件执行是在整个页面加载完成时才执行load事件


			 domTree(dom树)    cssTree(css树)
				 renderTree(渲染树)形成后按照renderTree渲染页面




				 JSON
			 将普通对象变为字符串传给后端   JSON.stringify();   string ————> JSON
			 将后端传的字符串变为普通对象	  JOSN.parse();			JSON —————> string


			 异步加载


			 生成DOM树的过程叫DOM节点解析，
			 浏览器解析节点的时候按深度优先来解析，不会等图片节点加载好图片资源后再把图片节点挂在DOM树上，这就是异步加载，节点解析中不会等资源加载完再继续解析
			 DOM树节点的解析完并不代表所有DOM节点的加载完毕，


			 DOMTree +CSSTree = randerTree    randerTree形成之后浏览器才会真正的配置页面

			 重新构建DOMtree或者CSSTree就会reflow(重排)    DOM节点的删除，增加，宽高的更改，位置的更改
														 offsetwidth   offsetLeft 会让randertree重新构建，重排页面，去获取实时页面宽高
			 repaint 重绘   更改CSS字体颜色，背景图片等 就会进行重绘，效率浪费比较少


			 JS文档加载是单线程，不会并行去解析HTML和CSS，因为JS会动态去更改元素节点和CSS，

			 如何让JS异步加载
			 1、defer="defer"    (属性名和属性值相等可以直接写属性名就好)，defer只有IE能用，可以把代码写在内部并且在等DOM文档全部解析完后才执行
			 2、async异步加载，加载完后就执行，async只能加载外部脚本，不能把JS写在scrip标签内
			 3、在script标签中预生成scrip标签，并插入页面中 如：
		<script>
			var script = document.createElement('script');
			script.type = "type/javascript";
			script.src = "./dome.js";
			兼容IE
			if(script.readyState){
			script.onreadystatechange = function(){
				if(script.readystate == "complete" || script.readyState == "loaded"){
						函数执行
				}
			}
			}else{
				script.onload = function(){函数执行}
			}
			document.head.appedchild(script);
		<script>
		

		 满足一定条件才执行得叫回调函数，callback指回调函数

		 封装异步加载函数
		function load(url,callback){
			var script = document.createElement('script');
				script.type = 'type/javascript';
			if(script.readyState){
				if(script.readyState  == "complete" || script.readyState == "loaded"){
					callback();
				}
			}else{
				script.onload = function(){
					callback();
				}
			}
			script.url = url;
			document.head.appendChild(script);
		}
		调用方法 load('test.js',function(){test();})
		



		 JS加载时间线
		
		1、创建Document对象，开始解析web页面。解析HTML元素和他们的文本内容后添加ELEMENT对象和Text节点到文档中。
		这个阶段document.readyState = "loading"
		2、遇到link外部CSS，创建线程加载，并继续解析文档。
		3、遇到script外部JS，并没有设置async、defer，浏览器加载，并阻塞，等待JS加载完成并执行该脚本，
		然后继续解析文档
		4、遇到script外部JS，并且设置有async、defer，浏览器继续创建线程加载，并继续解析文档。
		对于async属性的脚本，脚本加载完成后立即执行。(异步禁止使用document.write())
		5、遇到img等，先正常解析dom结构，然后浏览器异步加载src，并继续解析文档
		6、当文档解析完成，document.readyState = "interactive"。
		7、文档解析完成后，所有设置有defer的脚本会按照顺序执行。(注意与async的不同，但依同样也禁止使用document.write())
		8、document对象触发DOMContentLoaded事件，这也让标志着程序执行从同步脚本执行阶段，转化为事件驱动阶段。
		9、当所有async的脚本加载完成并执行后、img等src资源加载好后，document.readyState = "complete"，window对象触发load事件
		10、从此，异步响应式处理用户输入、网络事件等
		
		 documunt.readyState 展示文档当前执行状态
		 文档开始创建Document对象，开始解析web页面，document.readyState = "loading"
		 页面解析中，document.readyState = "interactive"
		 页面解析完成，document.readyState = "complete";
		 console.log(document.readyState);
		 document.onreadystatechange = function(){
		 	console.log(document.readyState);
		 }
		 document.addEventListener('DOMContentLoaded',function(){},false);  等页面解析完就执行
		 window.onload是等到解析好并资源全部加载好再执行
		 $(document).ready(function(){});  这个是等文档解析完就执行


				 正则表达式 RegExp
 
		 1、转意符号 \    将双引号以文本形式插入
		 var str = "abcdefghij\"klmnopquvwxyz";  \"字符串中插入文本引号
		 var str = "apoewofiwefjslfwe\np2fj2p3"; \n字符串中插入换行	
		 \r代表行结束  \n代表行换行  \t代表table(制表符) 缩进，一般一个tab代表四个空格。
		

		 正则表达式作用:匹配特殊字符或有特殊搭配原则的字符的最佳选择
		两种创建方式:
						 直接量; 直接写进行创建
						var reg = /abc/;
						var str = "abc";
						reg.test(str);

						 new RegExp(); 构造函数创建
						 var reg = new RegExp("abc"); 创建正则表达式
						 var str = "abc"; 创建字符串
						 reg.test(str); 进行对比
		
		 reg.test();判断字符串有没有符合正则表达式规则的片段，返回结果只有true和false
		 str.match();匹配字符串中符合的片段并返回

		 正则表达式属性 i(ignoreCase)忽视大小写,g执行全局匹配,m执行多行匹配
		 直接量创建
		 var reg = /abc/;
		 var str = "abcd";
		 console.log(reg.test(str));

		构造函数创建
		 var reg = new RegExp("abc","mgi");
		 var str = "abc";
		 console.log(reg.test(str));
		
		 转义符 \
		 var reg =  /abc/i;
		var reg1 = new RegExp(reg); 构造函数方式创建可以写入其它正则,虽然样子一样，但却互相独立

		 如果把new RegExp的new去掉,此时的reg1和reg指向同一个内存，只是引用不一样
		 var reg =  /abc/i;
		 var reg1 = RegExp(reg);
		 验证  		var reg =  /abc/i;
						var reg1 = RegExp(reg);
		 				reg.abc = 123; 此时reg1.abc也等于123;都指向同一个地址

		
		 /abc/g;会匹配所有相同字段

		 var reg = /abc/;
		 var str =  "abcabcabcabcabc";
		 str.match(reg); string的方法，将相匹配的字段取出，仅取出第一次出现的字符，后面还有不会再取出

		 var reg = /abc/g;
		 var str = "abcabcabcabcabcabc";
		str.match(reg); 将str下所有匹配正则表达式规则的字段取出，不仅仅取出第一次出现的，后面还有任然取出

		 ^ 例 ^a 匹配以a开头的字符串，单行出现多个a但不在开头没用,m执行多行匹配
		 var str = "abc\naabc\nbahcb";
		 var reg = /^a/gm;
		 var str = "abcaklnwovabcqofoifioabc";
		 var reg = /abc/;

		 var str = "123bjbk123uj123d/.e@qq.comwhflwie080upoj;l/o";
		 var reg = /\w@?/g;
		
		 方括号形式表达式
			 var str = "qfwg1abs";
			 var reg = /[0-9][ab][bsd]/g;

		 var reg = /[^q]/;^放在正则表达式的中括号内，代表非。匹配^后面跟的范围之外的任意字符
		 var str = "ab1cd";
		 var reg = /[^a][^b]/g;

		 | 正则表达式中的或,满足表达式任意一条件即可
		 var reg = /(abc|bcd)/;
		 var str = "abc";
		
		

		 元字符

		 \w 范围是[0-9A-z_];
		 \W 范围是[^w]
		 var reg = /\Wbj1/g;
		 var str = "a*bj1";

		 \d 范围是0-9
		 \D范围是^\d
		 var str = "123";
		 var reg = /\d\d\d/g;

		 \s范围是[/t/r/f/n/v ]
		 \S范围是[^\s]

		 \b ===单词边界
		 \B === 非单词边界
		 var reg = /\bcbd\B/g;
		 var str = "abc cbdefc";

		 \t \r \n \v \f  只能匹配对应内容字符\t \r \n \v \f
		 var str = "abc\tcbd";
		 var reg = /\tc/g;
		 var str = "ehhh@  qwdji09789dq hhhhh1&o31.,=-'";
		 var reg = /[\d]/g;

		 .除了换行和行结束符，都能匹配


		 正则表达式执行贪婪匹配原则，非贪婪匹配如 reg = /n+?/g; /n{1,3}?/g; /n??/g;意思是匹配n时能取0就不取1；
		 量词
		 n 为变量
		 n+ {1-Infinity}
		 n* {0-Infinity}  会匹配字符串逻辑最后一位，在原先匹配基础上再返回个空串,
		 n? {0-1}  能匹配的值为0到1，最后返回值会加空串
		n{X} X为数字，按X个为一组来匹配，
		n{X,Y} X和Y之间形成区间
		n{x, } 从X个到正无穷
		n$ 匹配以n结尾的字符
		^n 必须以n作为字符串开头

		 var reg = /\w{2,5}/g;
		 var str = "abc123giu权威的贵de";


		 var reg = /^\d|\d$/判断字符串头或尾是否有数字
		 var reg = /^\d[\s\S]*\d$/; 判断字符串首尾是否都有数字
		 var str = "1ej2";

		reg.test(str);判断字符串中是否有符合正则表达式的片段，有返回true 没有返回false;

		reg.exec(str);匹配字符串符合正则的部分，不加g不会全局匹配

		reg.lastindex exce每匹配一次，都会把lastindex改为末尾的数的索引，索引可以手动更改，exce在匹配时会从设置的索引开始

		 ()在正则中算子表达式
		  \1反向引用，
		 reg = /(\w)\1/;引用第一个子表达式的里面的内容

		匹配出字符串内连续的四个一样的字符
		 var reg = /(\w)\1\1\1/g;
		 var str = "aaaabbbbcccc";

		str.serach(reg); 匹配出与正则表达式相匹配的值，并返回其位置，不受lastindex影响，

		str.split(reg); 按照正则表达式的规则拆分字符串
		 var str  = "aaewifo;hqouwgddwqowgdggqwiodoo";
		 var reg = /(\w)\1/g;

		str.replace("a","b");将字符串的第一个a替换成b,因为replace只能访问字符串的第一个，没有访问全局的能力，
		 第一个可以填写正则表达式，如果正则表达式没有填写g那也是只能匹配第一个字符，不能全局访问
		第二个可以填写function，系统自动调用，并传入值，第一个值是正则表达式匹配的结果，第二个值是第一个子表达式的内容，第三个值是第二个子表达式的内容
		 var str = "bibbfwjnfbbb";
		 str.replace("b","a");
		 console.log(str);

		 var str = "aabbcc";
		 var reg = /(\w)\1(\w)\2(\w)\3/g;
		 console.log(str.replace(reg,"$3$3$2$2$1$1"));

		把XYXY替换成YXYX
		 var str = "cfcfcf";
		 var reg = /(\w)(\w)/g;
		 console.log(str.replace(reg,"$2$1"));



		 改变字符串的大小写
		 str.toUpperCase();  把字符串变大写
		 str.toLowerCase();	把字符串变小写

		把str内容变为小驼峰式写法
		 var str = "the-first-name";
		 var reg = /-(\w)/g;
		 console.log(str.replace(reg,function($,$1){
			 return $1.toUpperCase();
		 }));
			 var str = "aaaabbbb";
			 var reg = /(\w)\1\1\1(\w)\2\2\2/g;
			 console.log(str.replace(reg,"$2$2$2$2$1$1$1$1$1"));
			 var str1 = "my-first-name";
			 var reg1 = /-(\w)/g;
			 console.log(str1.replace(reg1,function($,$1){
			 	return $1.toUpperCase();
			 }))



		正则方法字符串去重
		 var str = "qqeerrddsafe3r333";
		 var reg = /(\w)\1+/g;
		 console.log(str.match(reg));
		 console.log(str.replace(reg,"$1"));



		正向预查 正向断言  n(?=x);  把x当成寻找n的特征，意思是n后面跟着x  n(?!b); 寻找n后面没有跟着b的n
		 var str = "abaaa";
		 var reg = /a(?=b)/g;
		 console.log(str.match(reg));


		 var str = "100000000000000";
		 var reg = /(?=(\B)(\d{3})+$)/g;
		 console.log(str.replace(reg,","));


		 var reg = /\b\w/g;
		 var str = "abc def rfg";
		 console.log(str.replace(reg,function(th){
			 return th.toUpperCase();
		 }));
```
