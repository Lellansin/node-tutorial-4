# 语句

本节无ES6新内容， 熟悉的可以跳过。

## 选择结构

* if () else
* switch () case

## 循环结构

* while () 循环
* do while () 循环
* for () 循环

## 终止循环：

* continue 终止该次循环
* break 终止该循环

## if else

```javascript
// 形式1
if(条件)
{ /*条件为真执行*/
    ...
}

// 形式2
if(条件)
{ /*条件为真执行*/
    ...
} else
{ /*条件为假执行*/
    ...
}

// 更多形式..
if(条件1)
{ /*条件1为真执行*/
    ...
} else if(条件2)
{ /*条件2为真执行*/
    ...
} else
{ /*条件1、2为假才执行*/
    ...
}
`
``

代码示例：

```
var salary = 2500;
var rent = 850;
var life_cost = 1000;

if( salary > (rent + life_cost) )
{
    console.log("还过的下去");
} else if( salary < (rent + life_cost) )
{
    console.log("活不下去了！");
} else
{
    console.log("你妹！");
}
```

## switch

```javascript
switch (变量) {
	case 情况1:
		...
		break;

	case 情况2:
		...
		break;

	case 情况3:
		...
		break;

	default:
		/* 默认情况 */
		...
}
```

代码示例

```javascript
var cmd;

console.log("确认要删除吗？");
cmd = 'Y';

switch (cmd) {
	case 'Y':
		console.log("文件正在删除\n");
		break;
	case 'N':
		console.log("取消删除\n");
		break;
		defualt:
			console.log("用户未响应，操作取消\n");
}
```
关于case穿透

```javascript
var score = 80;

switch (math / 10) {
	case 1:
	case 2:
	case 3:
	case 4:
	case 5:
		console.log("不及格\n");
	case 6:
	case 7:
	case 8:
		console.log("及格\n");
	case 9:
	case 10:
		console.log("满分\n");
}
```

## while 循环

```javascript
var i = 0;
while (i < 10) {
	console.log(i);
}
```

## do while 循环
安装 scanf 模块
```
npm install scanf
```

```javascript
var scanf = require("scanf");
var c;

do {
	console.log("请问你是⑨吗？(Y/N)\n");
	c = scanf("%c");
} while (c != 'Y');
```

## for 循环

```javascript
// 形式
for (初始值; 条件; 变化) {
	...
}
```

```javascript
var i;
for (i = 0; i < 5; i++) {
	console.log(i);
}
```

## continue 与 break

终止循环：
* continue 终止该次循环
* break 终止该循环

```javascript
var i;
for (i = 0; i < 5; i++) {
	if (i == 3)
		continue;
	console.log(i);
}
```
输出
```
1
2
4
5
```
```javascript
var i;
for (i = 0; i < 5; i++) {
	if (i == 3)
		break;
	console.log(i);
}
```
输出
```
1
2
```
