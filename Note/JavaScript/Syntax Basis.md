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
            // 控制台中绿色样式输出，自己之后会有n
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



#### 类型检查

大整数类型不能和其他数据类型做运算，JS发展过程中后添加的，会报错。

typeof运算符，所以可以不用加括号，和C中sizeof类似。

由于JS中变量没有类型，typeof返回的是变量中值的类型。



#### 字符串

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
        	let a = 'hello';

            console.log(a);

            // 转义字符
            console.log('aaaa\"');
            console.log('\\');
            console.log('\\\\');
            console.log('a\tb'); // 制表符
            console.log('a\nb');

            // 模板字符串
            a = `shuahiu
            shuiidhui
            siidhohiod`; // 跨行，换行空格都会被保存

            console.log(a);

            // 模板字符串中可以嵌入变量 类似于f字符串
            let name = 'Peter';
            let str = `Hello, ${name}`;

            console.log(str);

            let b = 10;

            console.log(`b = ${b}`);
            
        </script>
    </head>

    <body>
            
    </body>
</html>
```

typeof 检查字符串返回字符串string（typeof的返回值都是字符串）。

#### 其他数据类型

##### 布尔值boolean

用于进行逻辑判断，仅有两个值true、false。

##### 空值null

表示空对象。

##### 未定义undefined

变量进行了声明却未赋值。也是早期JS不报错核心思想的产物。

自己表示空尽量使用null。

##### 符号Symbol

用来创建唯一的标识。

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
        	let a = true;

            console.log(a);  // 蓝色显示，底层也是数字
            console.log(typeof a);

            let b = null;

            console.log(b);  // 灰色输出
            console.log(typeof b);  // 返回object 空值表示空对象

            let c;

            console.log(c);
            console.log(typeof c);

            let d = Symbol();

            console.log(d);
            console.log(typeof d);
            
        </script>
    </head>

    <body>
            
    </body>
</html>
```

**所有原始值数据都是不可变数据类型，变量赋值修改的是引用。**



### 类型转化

类型转换指将某种数据类型转化为其他类型。

#### 字符串

```js
console.log(a, typeof a);  // 是支持的，和print类似
```

两种方式：

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

            console.log(a.toString());
            // toSting方法，返回值是字符串，原数据类型不修改

            a = true;

            console.log(a.toString());
            // true

            a = 11n;
            console.log(a.toString());
            // 11

            console.log(null.toString());
            // Cannot read properties of null

            console.log(undefined.toString());
            // Cannot read properties of undefined

            // undefined和null没有toSting方法

            console.log(String(undefined));
            // undefined

            console.log(String(null));
            // null

            // String函数同样的不会对原数据做修改，而是返回转化的结果

        </script>
    </head>

    <body>
            
    </body>
</html>
```

对于用于toString方法的类型，调用toSting和使用Sting函数没有区别；对于null和undefined直接转化为对应字符串。两种方式都是强制（显式）类型转化。

#### 数值

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

            console.log(Number('123'));
            // 只有Number函数一种方式

            console.log(Number('abc'));
            // NaN 不是纯数字字符串

            console.log(Number('12.345'));
            // 12.345

            console.log(Number(''));
            // 字符串为空串或纯空格，转化为0

            console.log(Number(true), Number(false));
            // 1 0

            console.log(Number(null));
            // 0

            console.log(Number(undefined));
            // NaN

            console.log(parseInt('123', 8));
            // 可以指定进制

            console.log(parseInt('123px'));
            // 从字符串左边开始解析整数字符串

            console.log(parseFloat('12.3'));

            // 当传入的参数是数字而不是字符串时，先会将数字转化为字符串，可以利用这一性质进行取整

            let num = 12.345;

            console.log(parseInt(num));
            // 12
            // 性能较差，但是可以使用
        </script>
    </head>

    <body>
            
    </body>
</html>
```

#### 布尔值

有且仅有一种方式，Boolean函数。

对于数字，非0和Infinity转化为true，0、NaN转化为false；对于字符串，空串转化为false，其余均为true；null和undefined都转化为false；对象一般都会为转化为true。



## 运算符

operator，又可以叫做操作符。

### 算数运算符

```
+ - * / **(幂运算) %
```

**JavaScript的除法不是整除法**

除0的返回值是Infinity，并不会报错。

JS的幂并不要求指数是整数，如：

```js
9 ** 0.5 = 3;
```



JS是一门弱类型语言，运算时会进行自动类型转化，如数字和其他类型进行算数运算，会先将其他类型通过Number函数转化为数字，再进行计算。如果转化的NaN，最终得到的结果也是NaN。

除了与字符串的加法外，一般JS中的算术运算自动数据类型转化都是转成Number，而在与字符串做加法时，则是将其他类型的数据通过String函数转化为字符串，再做拼接。**因此，加法是个特例。**

以上两种都称作隐式类型转化。

我们可以利用隐式类型转化把其他类型的数据转化为字符串，如：

```js
a = a + ''  // 与调用String函数相同
```

### 赋值运算符

```
= += -= *= /= %= **=
```

= 是把右边的内容赋值给等式左边的变量。

```js
let  a = 10;
let b = a;

// a再做修改也并不会影响b的引用
```

a = a + 5 等价于 a += 5

JS中还有一个赋值：??= 空赋值，只有变量**只有为null或undefined**才会执行赋值语句。

### 一元的正负

一元即操作对象为1。

一元的+表示正号，-表示负号（符号位取反）。

这里主要涉及一个新的隐式类型转化，若对非数值进行正负的运算，会先将数据类型转化为Number再计算正负。

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
            let a = '123';

            a = +a;  // 与调用Number函数无异

            console.log(a);  // 数字的123
        </script>
    </head>

    <body>
            
    </body>
</html>
```

### 自增和自减

```
++ --
```

执行规则和C语言完全相同，也区分前缀（先使用后计算）和后缀（先计算后使用）使用。

```js
let n = 5;
let result = n++ + ++n + n;
// 结果为19
```

### 逻辑运算符

#### 非

!: 逻辑取反，对bool值进行取反操作。

对非布尔值进行取反，先将其他类型的数据转化为布尔值，再取反。

因此可以借助这个隐式类型转化做这样的操作：

```js
let a = 1;
a = !!a;  // 与调用Boolean函数相同
```

#### 与 或

与非不同，是二元运算符。

与运算存在逻辑惰性，如果第一个结果已经是false，后面的内容不会执行。

```js
true && alert('hello');

false && alert('123');
```

非布尔值进行与运算，转化为布尔进行运算，但返回原值：

```js
1 && 2  // 2
1 && 0  // 0
2 && 1  // 1
0 && NaN  // 0
2 && 'a'  // 'a'
```

或运算存在逻辑短路，只要第一个为true，就不会看运算符后面的内容。

非布尔值进行或运算，转化为布尔值进行计算，但返回原值。

```js
NaN || null  // null
```

### 关系运算符

比较两个值之间的关系是否成立，返回值为bool值。

```
> < >= <= 
```

对于非数值进行关系运算，会先将其转化为数字再比较；但字符串与字符串的比较就是比较再Unicode编码中的**字典序**。



实验得到：NaN小于任何数值。

```js
12 > 'px'  // true
```

JS中不支持：

```js
10 < a < 12
a > 10 && a < 12  // 和C相同
```

### 相等运算符

```
==(相等) ===（全等） != (==的取反, 自动类型转化) !== (===的取反，不进行自动类型转化) 
```

相等运算符比较两个不同类型，会将其转化为相同类型（一般是数值）再进行比较。

```js
1 == '1'

null == undefined  // true
NaN == NaN  // false
```

NaN和任何值都不相等，包括自身。



全等运算符不会做类型转化，只要类型不同一定是false。

```js
null === undefined  // false，不存在类型转化了 相等不全等
```

### 条件运算符

也就是C中的三目运算符。

```js
true ? alert('a'): alert('b');  // 除了赋值，也可以通过执行的角度理解
```

### 优先级

https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Operator_Precedence

优先级不确定时，使用小括号来保证执行顺序是希望的。



## 流程控制

### 代码块

使用{}创建代码块，代码块可以对代码进行分组。同一个代码块中的代码如果执行就都执行，若不执行都不执行。



let和var的区别：

- let声明的变量无法在代码块外使用
- var声明的变量可以在代码块外使用

```html
<!DOCTYPE html>

<html lang="en">

<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">

        <script type="text/javascript">
            // {
            //     let a = 10;
            // }

            // console.log(a);  // Uncaught ReferenceError: a is not defined

            {
                var b = 10;
            }

            console.log(b);  // 10
        </script>
        <title>Title</title>
    </head>

    <body>
    	
    </body>
</html>
```

### 条件判断语句

#### if语句

和C相同，如果只有一条语句，无需大括号，若存在多条语句需要大括号。书写习惯上，左大括号不换行写：

```js
if(a > 10) {
    aleart(`a比10大`);
}
```

若if条件后不是布尔值，会自动转化为布尔值。

#### if-else语句

总会执行一部分代码，条件满足了执行if后的，若没有满足就执行else后的代码。总会存在二选一执行的代码块。

若希望更多的选择，可以使用else if，最终也可以没有else，如果有else至少会执行一个代码块。

一旦条件成立，执行了这个代码块，下方的条件都不再继续判断。可以借助合适的条件编写顺序简化代码。

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
        	let age = 78;

        	if(age > 100) {
        		alert('你真是应该长寿的人');
        	}
        	else if(age >= 60) {
        		alert('你已经退休了');
        	}
        	else if(age >= 18) {
        		alert('你已经成年了');
        	}
        	else {
        		alert('你还是个孩子');
        	}

        	
        </script>
    </head>

    <body>
            
    </body>
</html>
```

补充一个知识点（JS中的输入函数）：

```js
prompt('输入提示');   // 返回字符串

num = +prompt('输入一个数字');
```



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
        	let num;

        	num = +prompt('请输入一个数字');

        	// NaN不与任何值相等，额外提供了函数
        	if(isNaN(num)) {
        		alert('这不是一个数字');
        	} 
        	else if(num % 1 != 0) {
        		// 判断是否为小数的简单办法
        		alert('输入的是是一个小数');
        	}
        	else {
        		if(num % 2 == 1) {
        			console.log('是一个奇数');
        		} 
        		else {
        			console.log('是一个偶数');
        		}
        	}
        	
        </script>
    </head>

    <body>
            
    </body>
</html>
```

检查多个数值中是否存在NaN，可以直接用下方的关系运算：

```js
isNaN(a + b + c);
```

#### switch语句

```js
switch(表达式) {
    case 表达式: 代码;
    case 表达式: 代码;
    default: 代码;  // 若出现，总会执行一段代码
}
```

执行流程就是将switch后的表达式和case后的表达式进行全等比较，如果满足全等就执行相应case后的代码。

需要注意的是，如果没有break，则自当前case处开始执行代码。如果不希望这样，可以通过添加break实现。

```js
switch(表达式) {
    case 表达式: 代码; break;
    case 表达式: 代码; break;
    default: 代码;  // 若出现，总会执行一段代码  else的作用
}
```

default不写在最后也是最后执行。

与if-else的区别就是在多个全等判断时可以使结构更加清晰。

### 循环语句

循环语句可以使指定的代码反复执行。

#### while语句

```js
while(condition) {
    code;
}  // 注意循环变量的修改
```

当一个循环的条件恒为true时，循环就为死循环。

循环的三个要点：

1. 初始化表达式（初始化循环变量）；
2. 设置条件表达式；
3. 更新表达式（修改循环变量）。

#### do while语句

```js
do {
    code;
} while(condition);
```

相较于while，至少会执行一次。

#### for语句

```js
for(初始化变量; 循环条件; 更新表达式) {
    代码;
}
```

初始化表达式在整个循环的声明周期中只会执行一次。三个表达式可以选择性的省略。



*注意for中的内容都属于一个代码块：

```js
for(let i = 0; i < 10; i++) {
    ;
}

console.log(i);  // Undefined
```

也就是i只能在循环内部使用，var就可以在外部使用。



创建死循环的方式：

```js
while(true) {
    
}

do {
    
} while(true);

for(;true;) {
    
}
```



题目水下花束可以利用索引获取字符串字符，再利用类型转化，实现数字各位的获取。
