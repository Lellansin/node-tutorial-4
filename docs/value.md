# 第二讲 数值

在 Javascript 中有 6 中基本类型的值：number、string、boolean、object、function 和 undefined。

## 定义

在 js 中数值有4中定义方式：

1. 使用 var 定义变量
2. 使用 let 定义局部变量
3. 使用 const 定义常量
4. 直接写一个名称赋值

### var
```javascript
var a = 10;      // 定义变量a, 并初始化为10
var b, c = 'hello';   // 定义变量b 不初始化，定义变量c 并初始化为字符串 'hello'
```

使用 var 定义变量无需指定类型，变量的类型会在赋值的时候确定，节省了填写不同类型的时间。赋值为数字则变量类型为数字，赋值为字符串，则变量类型为字符串。如果没有初始化那么变量的值就是 undefined（未定义）。

```javascript
'use strict';    // 严格模式声明

let i = 10;      // 定义局部变量i, 并初始化为10
let j, k = 12;   // 定义局部变量j 不初始化，定义局部变量k 并初始化为 12
```

### let
使用 let 定义变量与使用 var 类型，区别在于 let 定义的是代码块（花括号抱起来的部分）中的局部变量。

例如
```javascript
'use strict';    // 严格模式声明

let a = 10;
{
	let a = 12;
}
console.log(a);
```
结果输出 a 为 10。如果使用 var 定义则结果为 12。因为 let 定义的变量只在当前花括号以内（含子花括号中）有效。

注：目前 node.js 4.0 中要在严格模式下才能使用 let 定变量。

### const
const 关键字用于定义常量。即不能被修改的值。

```javascript
const i = 8;
i = 12;
console.log(i);
```
输出结果还是 8，因为 i 是常量。如果开启严格模式的话在赋值的时候会报错，而普通情况对常量赋值的操作会被无视。

### 直接定义

```javascript
num = 12;
name = 'Alan'
```

上述方式定义的变量为全局变量，为了代码维护简单请避免这样定义变量。另外需要注意的是，这种定义方式需要赋值才会定义，如果你在计算过程中使用没有赋值过的变量名会报错的：

```javascript
var i = 5;
console.log(i + j);
```
会得到 `ReferenceError: j is not defined`


## 数字

不同于 C/C++、Java 等主流语言有区分整数（int）和小数（浮点数 float、double），javascript 中只有一个数字类型，即 Number 类型。

在主流语言中 `10 / 3 = 3` 因为整数与整数运算的结果还是整数，小数部分就被丢弃了。而 javascript 中不用担心这个问题因为 js 会自动处理整数和小数在 js 中计算 `10 / 3` 会得到 `3.3333..` 这样的小数。

```javascript
// 整数与小数计算会自动转成小数
var i = 10;          // 定义一个整数
var j = 2.333;       // 定义一个小数
console.log(i + j);  // 结果为 12.333

// 取绝对值
console.log(Math.abs(-2));      // 2

// 去除小数部分
console.log(Math.trunc(2.333)); // 2

// 判断是否为整数
console.log(Number.isInteger(i)); // true
console.log(Number.isInteger(j)); // false

// js 能准确表示-2的53次方到正2的53次方之间的整数
console.log(Number.MAX_SAFE_INTEGER); // 整数的安全上限
console.log(Number.MIN_SAFE_INTEGER); // 整数的安全下限

// 科学计数法 10的2次方
var meter = 1e2;

var big = 1 / 0; 
console.log(big); // Infinity  正无穷大

// 判断是否在数值是否有限（没到无穷大）
console.log(Number.isFinite(0));     // true
console.log(Number.isFinite(meter)); // true
console.log(Number.isFinite(2e64));  // true
console.log(Number.isFinite(big));   // false

// 如果使用数值与非数值计算会出现问题
var num = 10 * 'a';
console.log(num); // NaN   非数字（Not a Number）

// 判断数值不是一个数字
console.log(Number.isNaN(0));    // false
console.log(Number.isNaN(100));  // false
console.log(Number.isNaN(num));  // true
```

## 字符串


### 定义

在 Javascript 中，字符串可以使用

1.单引号（''）
2.双引号（""）
3.反引号（``）

三种方式来定义，可以包含 0 个火多个字符串。与主流语言类似使用 \ （反斜杠）作为转义字符的开始。

```javascript
var name1 = 'Alan';
var name2 = "Bob";
var name3 = `Jack`;
```

### 拼接

因为方式1 单引号与方式2 双引号类似：

```javascript
var name = 'Alan';
var age = 22;

var intro = 'Hi, my name is ' + name + ', I\'m ' + age + ' years old.';
console.log(intro);
```
输出：
```
Hi, my name is Alan, I'm 22 years old.
```
字符串与变量使用加号拼接，其中数字在于字符串相加的时候转换成了字符串的 22。

而是用反引号则可以写成：
```javascript
var name = 'Alan';
var age = 22;

var intro = `Hi, My name is ${name}, I'm ${age} years old.`;
console.log(intro);
```
${} 中的变量（或者表达式）的结果会被转成字符串拼接在其中。当然反引号的字符串也可以使用加号拼接，并且可以在其中进行计算：
```javascript
var name = 'Alan';
var age = 22;

var intro = `Hi, my name is ` + name +  `, I'm ${age + 3} years old.`;
console.log(intro);
```

使用引号和反引号出了以上，还有一个区别是
```javascript
// 引号中书写字符串书写多行需要转义
var str = 'hello \
world';

// 反引号中不需要
var str = `hello 
world`;
```


Javascript 使用 UTF8-16 的字符编码












# 索引
上一讲 [第一讲 hello world](https://github.com/Lellansin/node-tutorial-4/blob/master/docs/hello.md)
