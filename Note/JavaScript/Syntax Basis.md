# JavaScript



## JavaScript简介

### 历史

最初的浏览器只能提供静态网页，希望一门脚本程序语言（逐行执行）可以直接嵌在浏览器中使用，JavaScript应运而生。

因为Chrome浏览器（V8引擎）的出现ES（EcmaScipt）标准开始稳定更新，作为标准准则。JS只是对ES标准的一种实现，还有很多类型的语言和解释器。

### 特点

#### 解释型

逐行解释脚本，不需要手动编译，由解释器逐行编译。浏览器中集成了JS解释器，也可以通过Node JS将程序直接运行在计算机上。

#### 函数式编程

在JS中函数是一等公民，可以像其他类型的值一样赋值给变量，也可以作为参数传递给其他函数。

#### 单线程

#### 面向对象

JS中的操作都是对于对象进行的。

#### 扩展ES

ES标准只提供了基础的内容，JS还提供了不同的扩展，以实现不同的功能。



## Hello World

```html
<!DOCTYPE html>

<html lang="en">

<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">

        <title>Title</title>

        <script type="text/javascript">
        	alert('Hello World!');  // 弹出警告框

        	console.log('Where am I?');  // 在控制台输出一个日志

        	document.write('Where am I?');  // 向文档（网页）写内容
        </script>
    </head>

    <body>
            
    </body>
</html>
```

实际开发使用console.log()较多。



## JS的编写位置

### 内嵌式

如Hello World中的代码，直接编写在script标签中。

### 外链式

```html
<!DOCTYPE html>

<html lang="en">

<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">

        <title>Title</title>

        <script type="text/javascript" src="./JS002.js"></script>
        // 标签内引入文件，不能再写内部代码

        // 若希望再编写JS代码，新建一个标签，代码自上向下执行
    </head>

    <body>
            
    </body>
</html>
```

```js
alert('Hello World!');
```

### 行内式

给HTML标签添加属性：

```html
<!DOCTYPE html>

<html lang="en">

<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">

        <title>Title</title>

<!--         <script type="text/javascript" src="./JS002.js"></script>
        // 标签内引入文件，不能再写内部代码

        // 若希望再编写JS代码，新建一个标签，代码自上向下执行 -->
    </head>

    <body>
        <button onclick="alert('anana');">Button！</button>

        <button onmousemove="console.log('111');">Button</button>
        <!-- 在这个区域内鼠标移动就会执行 -->

        <a href="javascript:alert('123');">sss</a>
        <!-- 超链接指向的内容直接输在地址栏中也是允许的 -->
    </body>
</html>
```



## 基本语法

### 注释

完全和C相同：

```js
// 单行注释

/*
	多行注释
*/
```

注释的内容会被解释器忽略，可以通过注释对于代码进行解释说明或注释不想执行的代码。

### 严格区分大小写

### 空格和换行会被忽略

可以利用这一特性格式化代码。

### 每条语句以分号结尾

JS中具有自动添加分号的机制，解释器会自动添加。



## 字面量和变量

### 字面量

通俗来说就是一个值，所代表的含义就是字面的意思，如：

```
1 2 "123" true null...
```

JS中字面量都可以直接使用，但直接使用字面量并不方便（幻数且不易修改）。

### 变量

用来”存储“字面量，并且变量存储的字面量可以随意修改。

```html
<!DOCTYPE html>

<html lang="en">

<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">

        <title>Title</title>

        <script type="text/javascript">
        	let x;

        	x = 80;
        	console.log(x);

        	x = "haha";
        	console.log(x);
        </script>
    </head>

    <body>
            
    </body>
</html>
```

变量需要进行声明，但可以对于字面量进行解释且方便修改。



变量存在声明和赋值两个步骤，如下方的代码：

```html
<!DOCTYPE html>

<html lang="en">

<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">

        <title>Title</title>

        <script type="text/javascript">
        	let a;
        	var b, c, d;  // 声明

        	console.log(a);  // undefined

        	a = 10;  // 赋值

        	console.log(a);  // 10
        </script>
    </head>

    <body>
            
    </body>
</html>
```

若只声明未赋值，变量内的值是undefined。

let是新的声明方式，具有块作用域；var则是旧的声明方式，作用域不是块，不推荐。



可以将声明和赋值同时进行：

```html
<!DOCTYPE html>

<html lang="en">

<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">

        <title>Title</title>

        <script type="text/javascript">
        	let a = 10;
        	let b = 9, c = 8, d = 7;  // 声明赋值同时进行

        	console.log(a);  // 10

        </script>
    </head>

    <body>
            
    </body>
</html>
```

**JS中变量本身没有类型。**



### 变量的内存结构

JS和Python类似，变量本身没有类型，因此变量名内存储的是地址，即变量名和引用等价。因此如果内存中有了5，并不会再开辟新的内存空间，而是多个变量去引用这个5。

变量的赋值语句就是更改变量的引用，变量不会直接存储值，存储的是内存地址。



### 常（变）量

不可变的变量或不希望修改的数据。

```html
<!DOCTYPE html>

<html lang="en">

<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">

        <title>Title</title>

        <script type="text/javascript">
        	const PI = 3.1415926;

        	PI = 10;
        	// Uncaught TypeError: Assignment to constant variable.
        </script>
    </head>

    <body>
            
    </body>
</html>
```

常变量不能重复赋值，命名习惯使用纯大写。

从内存角度理解，就是不能修改常变量的引用，但其组成成员的引用却仍可以修改。



## 标识符

所有可以由程序员自主命名的内容都可以认为是标识符，如函数名、变量名、类名等。

### 标识符命名规范

1. 只能含有字母、数字、下划线和$，且不能以数字开头；
2. 标识符不能是js的关键字和保留字，也不建议使用内置函数和类名；

```js
let alert = 2;
```

alert就不能再作为函数使用，此时其所指向的对象就是一个数字。

3. 通常会使用小驼峰命名法，类名使用大驼峰命名法，常量习惯使用纯大写。



## 数据类型

可以给变量赋值的类型。

### 原始值

#### 数值number

整数与浮点数都是number类型。

```html
<!DOCTYPE html>

<html lang="en">

<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">

        <title>Title</title>

        <script type="text/javascript">
        	let a = 10;

            console.log(a);
            // 控制台中以蓝色字样输出

            a = 10.5;

            console.log(a);

            a = 9999999999999999;
            // 10000000000000000

            console.log(a);

            a = 99999 ** 9999;
            // Infinity

            console.log(a);

            console.log(typeof(Infinity));
            // number

            a = 10 - 'a';
            // 一般的编程语言都会报错

            console.log(a);
            // JS为了不报错，定义了一个特殊的数值NaN
        </script>
    </head>

    <body>
            
    </body>
</html>
```

数值过大会显示近似值，并不总是准确的，再大会以科学计数法表示（JS支持科学计数法），大到无法计算时会返回**Infinity**（字面量），本身也是number类型。

**\*\*是JS中的的幂运算**。

小数位数同理，小数位数较小时，可以完全显示，数据位数再多，就需要近似表示。

编程语言浮点数计算总会存在不准确的情形，所以浮点数判定相等用差的绝对值小于某个值来判定。



早期JS的核心思想就是不报错，因此多出了NaN（not a number）和Infinity这样特殊的number的值。



#### 大整数bigint

用来表示一些比较大的整数，大整数的字面量使用n结尾，长度可以理解为无限大（内存为上限）。

```html
<!DOCTYPE html>

<html lang="en">

<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">

        <title>Title</title>

        <script type="text/javascript">
        	let a = 10000000000000n;

            console.log(a);
            // 控制台中绿色样式输出
            console.log(typeof(a));
            // bigint
        </script>
    </head>

    <body>
            
    </body>
</html>
```



#### 其他进制的数字

常见：二进制、八进制、十六进制。

```html
<!DOCTYPE html>

<html lang="en">

<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">

        <title>Title</title>

        <script type="text/javascript">
        	let a = 0b1010;

            console.log(a);
            // 输出统一为十进制
            
            a = 0o2345;
            console.log(a);

            a = 0x12A;
            console.log(a);
        </script>
    </head>

    <body>
            
    </body>
</html>
```

