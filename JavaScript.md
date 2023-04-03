# ch01. 初识JS

## 1. JavaScript历史

布兰登艾奇（Brendan Eich， 1961年～）。 神奇的大哥在1995年利用10天完成JavaScript设计。 网景公司最初命名为LiveScript ，后来在与Sun合作之后将其改名为JavaScript.

## 2. JavaScript是什么

- JavaScript是世界上最流行的语言之一，是一种运行在**客户端**的脚本语言（Script是脚本的意思）

- 脚本语言：不需要编译，运行过程中由js解释器（js引擎）逐行来进行解释并执行。 

- 现在也可以基于Node.js技术进行服务器端编程

HTML/CSS标记语言--描述类语言

JS脚本语言--编程类语言

## 3. JavaScript的作用

- 表单动态校验（密码强度检测） （ JS产生最初的目的）
- 网页特效
- 服务端开发（Node.js）
- 桌面程序（Electron）
- App(Cordova)
- 控制硬件—物联网（Ruff游戏F发(cocos2d-js)

## 4. 浏览器执行JS简介

浏览器分成两部分：**渲染引擎**和**JS引擎**

- 渲染引擎：用来解析HTML与CSS ，俗称<u>内核</u>，比如chrome浏览器的blink ，老版本的webkit
- JS引擎：也称为JS解释器。用来读取网页中的JavaScript代码，对其处理后运行，比如chrome浏览器的V8

浏览器本身并不会执行JS代码，而是通过内置JavaScript引擎（解释器）来执行JS代码。JS引擎执行代码时<u>逐行解释</u>每一句源码（转换为机器语言） ，然后由计算机去执行，所以JavaScript语言归为<u>脚本语言</u>，会逐行解释执行。

## 5. JS三大组成

- ECMAScript（JavaScript语法）
- DOM（页面文档对象模型）
- BOM（浏览器对象模型）

### 5.1 ECMAScript

ECMAScript是由ECMA国际（原欧洲计算机制造商协会）进行标准化的一门编程语言，这种语言在万维网上应用广泛，它往往被称为JavaScript或JScript ，但实际上后两者是ECMAScript语言的实现和扩展。

ECMAScript

- JavaScript 网景公司
- Jscript 微软公司

ECMAScript ： ECMAScript规定了JS的编程语法和基础核心知识，是所有浏览器厂商共同遵守的一套JS语法工业标准。

### 5.2 DOM—文档对象模型

文档对象模型（Document Object Model ，简称DOM ） ，是W3C组织推荐的处理可扩展标记语言的标准编程接口通过DOM提供的接口可以对页面上的各种元素进行操作（大小、位置、颜色等）。

### 5.3 BOM—浏览器对象模型

浏览器对象模型 （Browser Object Model ，简称BOM）是指浏览器对象模型，它提供了独立于内容的、可以与浏览器窗口进行互动的对象结构。通过BOM可以操作浏览器窗口，比如弹出框、控制浏览器跳转、获取分辨率等。

## 6. JS 初体验

JS有3种书写位置，分别为**行内**、**内嵌**和**外部**

1. 行内式JS

	```html
	<input type="button" value="click" onclick="alert('Hello, world!')">
	```

	- 可以将单行或少量JS代码写在HTML标签的事件属性中（以on开头的属性） ，如： onclick
	- 注意单双引号的使用：**在HTML中我们推荐使用双引号**，**JS中我们推荐使用单引号**。
	- 可读性差，在html中编写JS大量代码时，不方便阅读；引号易错，引号多层嵌套匹配时，非常容易弄混；
	- 特殊情况下使用

2. 内嵌式

	```html
	<script>
	alert("Hello world!");
	</script>
	```

	学习时常用。

3. 外部JS文件

```html
<script src="newFile.js"></script>
```

- 利于HTML页面代码结构化，把大段JS代码独立到HTML页面之外，既美观，也方便文件级别的复用
- <u>引用外部JS文件的script标签中间不可写代码</u>
- 适合于JS代码量比较大的情况

## 7. JS 注释

- 单行注释：

	```js
	// 单行注释 ctrl + /
	```

- 多行注释：

	```js
	/*
	多行注释 shift + alt + a
	*/
	```

## 8. JS输入输出语句

1. 输入框

	`prompt(info)`浏览器弹出输入框，用户可输入

	`prompt` 方法返回一个 `string` 类型。

```js
prompt('请输入你的名字：');
```

2. 警示框

	`alert(msg)`浏览器弹出警示框

```js
alert('你好');
```

3. 控制台打印

	`console.log(msg)` 在浏览器 检查 点console控制台

```js
console.log('我是程序员能看到的。');
```



# ch02. 变量

## 1. 变量的实质

变量是程序在内存中申请的一块用来存放数据的空间。

## 2. 变量的使用

1. 声明变量
2. 赋值

### 2.1 声明变量

```js
// 声明一个叫age的变量
var age;
let name;
const PI = 3.14;
```

- `var` 是一个JS关键字，用来声明变量（variable变量的意思），使用该关键字声明变量后，计算机会自动为变量分配内存空间，不需要程序员管
- `age` 是程序员定义的变量名，我们要通过变量名来访问内存中分配的空间

### 2.2 赋值

```javascript
age=10;
```

### 2.3 变量的初始化

```js
var age = 18;
```

初始化：声明并赋值

## 3. 变量语法扩展

### 3.1 更新赋值

一个变量可以被重复赋值，变量值也会更新。

```js
var age = 18;
age = 81;
```

### 3.2 同时声明多个变量

同时声明多个变量时，只需写一个var，多个变量名之间使用英文逗号隔开。

```js
var age = 18,
    url = 'https://mphy.top',
    myname = 'MurphyChen';
```

### 3.3 声明不赋值

```js
var sex;
console.log(sex);// undefined
```

### 3.4 不声明，不赋值，直接输出某个变量会报错

```js
console.log(tel);
// 报错
console.log(aaa);//Uncaught ReferenceError: aaa is not defined
```

### 3.5 不声明直接赋值

```js
qq = 12345;
console.log(qq);
// 12345 全局变量
```

## 4. 命名规范

- 由字母（A—Za—z）、数字（0—9）、下划线（_）、美元符号（$）组成，如： usrAge， num01， name
- 严格区分大小写。var app；和var App；是两个变量
- 不能以数字开头。18age是错误的
- 不能是关键字、保留字。例如： var， for， while
- 变量名必须有意义。MMD BBD nl— age
- 遵守驼峰命名法。首字母小写，后面单词的首字母需要大写。myFirstName推荐翻译网站：有道爱词霸
- 尽量不要使用 `name` 作为变量名



# ch03. 数据类型

## 1. 数据类型概述

### 1.1 为什么需要数据类型

在计算机中，不同的数据所需占用的存储空间是不同的，为了便于把数据分成所需内存大小不同的数据，充分利用存储空间，于是定义了不同的数据类型。

简单来说，数据类型就是数据的类别型号。比如姓名“张三” ，年龄18，这些数据的类型是不一样的。

### 1.2 变量的数据类型

变量是用来存储值的所在处，它们有名字和数据类型。变量的数据类型决定了如何将代表这些值的位存储到计算机的内存中。<u>JavaScript是一种弱类型或者说动态语言</u>。这意味着<u>不用提前声明变量的类型，在程序运行过程中，类型会被自动确定。</u>

```js
var num; //这里的num是不确定属于哪种数据类型的
var age = 10;//age属于数字型
```

在代码运行时，<u>变量的数据类型是由JS引擎根据=右边变量值的数据类型来判断的</u>，运行完毕之后，变量就确定了数据类型 JavaScript拥有动态类型，同时也意味着相同的变量可用作不同的类型：

```js
var x = 6;
// x为数字
var x = "Bill";
// x为字符串
```

## 2. 简单数据类型

- 简单数据类型（Number, String, Boolean, Undefined, Null）
- 复杂数据类型（Object）

### 2.1 简单数据类型（基本数据类型）

JavaScript中的简单数据类型及其说明如下：

| 简单数据类型 | 说明                                                   | 默认值      |
| ------------ | ------------------------------------------------------ | ----------- |
| Number       | 数字型，包含整值和浮点值，如21、0.21                   | `0`         |
| Boolean      | 布尔值类型，如true、 false，等价于1和0                 | `false`     |
| String       | 字符串类型，如“张三”注意js 里面，字符串都带引号        | `""`        |
| Undefined    | `var a;` 声明了变量a但是没有给值，此时a =undefinedNull | `undefined` |
| Null         | `var a = null;` 声明了变量a为空值                      | `null`      |

### 2.2 数字型 Number

#### 1. 数字型进制

常见：二进制、八进制、十进制、十六进制

- `0123`: `0` 开头表示八进制
- `0b11`: `0b` 开头表示二进制
- `0x11`: `0x` 开头表示十六进制
- 直接打印出来会转化为十进制

#### 2. 数字型范围

```javascript
console.log(Number.MAX_VALUE);
console.log(Number.MIN_VALUE);
```

#### 3. 特殊值

```js
console.log(Infinity);
console.log(-Infinity);
console.log(NaN);
```

- `Infinity`：无穷大
- `-Infinity`：无穷小
- `NaN`：Not a number，代表一个非数值。

#### 4. isNaN()

NaN: not a number

**`isNaN`** 方法用来判断一个变量和或者一个值是<u>非数字类型</u>，若<u>是数字类型则返回 `false`,不是数字返回 `true`</u>。

### 2.3 字符串型 String

#### 1. 定义

字符长型可以是引号中的任意文本，其语法为双引号 `""` 和单引号 `''`。

#### 2. 字符串引号嵌套

JS可以用单引号嵌套双引号，或者用双引号嵌套单引号（外双内单，外单内双）

```js
var strmsg= '我是"高帅富"程序员';
var strmsg= "我是'高帅富'程序员";
```

JS推荐使用单引号

#### 3. 字符串转义符

类似HTML里面的特殊字符，字符串中也有特殊字符，我们称之为转义符转义符都是\开头的，常用的转义符及其说明如下：

| 转义符 | 解释说明                    |
| ------ | --------------------------- |
| `\n`   | 换行符， n是 newline 的意思 |
| `\\`   | \                           |
| `\'`   | 单引号'                     |
| `\"`   | 双引号"                     |
| `\t`   | tab 缩进                    |
| `\b`   | 空格，b 是 blank 的意思     |

#### 4. 获取字符串长度 length

```js
var str = 'hello';
console.log(str.length);
```

#### 5. 字符串拼接

多个字符串之间可以使用 **+** 进行拼接，其拼接方式为 <u>字符串+任何类型=拼接之后的新字符串</u> 

拼接前会把与字符串相加的任何类型<u>转成字符串</u>，再拼接成一个新的字符串

```js
console.log(12+12); //24
console.log('12'+12);//1212 
```

数值相加，字符相连

#### 6. 字符串拼接加强

将字符串和变量相加，以后要更新最终的结果字符串，只需更新变量的值。

1. `+`拼接

2. ```js
	`${}`
	```

```js
var age = 18;
console.log('我' + age + '岁');
console.log(`我${age}岁`);
```

### 2.4 布尔型 Boolean

- 布尔型有两个值，`true` 和 `false`
- 布尔型（`true`，`false`）在参与加法时当作 `1` 和 `0` 使用

```js
console.log(true+1);
// 2
console.log(false+1);
// 1
```

### 2.5 Undefined

一个声明没有被赋值的变量会有一个默认值undefined（如果进行相连或者相加时，注意结果）

```js
console.log(undefined+1); // NaN
console.log(undefined+NaN); // NaN
console.log(undefined+true); // NaN
console.log(undefined+'aaa'); // undefinedaaa
console.log(undefined+undefined); // NaN
```

### 2.6 空值 Null

```js
console.log(null+1); // 1
console.log(null+undefined); // NaN
console.log(null+NaN); // NaN
console.log(null+true); // 1
console.log(null+'aaa'); // nullaaa
console.log(null+null); // 0
```

## 3. 获取变量数据类型

### 3.1 typeof 获取变量数据类型

`typeof variable` （`typeof(variable)`） 返回一个字符串，值为该变量的数据类型。

```js
console.log(typeof 1); // number
console.log(typeof false); // boolean
console.log(typeof 'aaa');    // string
console.log(typeof undefined);// undefined
console.log(typeof NaN); // number
console.log(typeof Infinity); // number
console.log(typeof null); // object

var age = prompt('请输入您的年龄');
console.log(age);//18
console.log(typeof typeof age); // string  相当于python input输入的也是字符串型的
```

### 3.2 字面量

字面量是在源代码中一个固定的表示法，通俗来说，就是字面量如何表达这个值。

- 数字字面量：`1`、`0`
- 字符串字面量：`mphy`、`aaa`
- 布尔字面量：`true`、`false`

## 4. 数据类型转换

### 4.1 什么是数据类型转换

使用<u>表单、prompt获取过来的数据默认是字符串类型</u>的，此时就不能直接简单的进行加法运算，而需要转换变量的数据类型。 通俗来说，就是把一种数据类型的变量转换成另外一种数据类型 我们通常会实现3种方式的转换：

- 转换为字符串类型
- 转换为数字型
- 转换为布尔型

### 4.2 转换成字符串的三种方法

一般用第三种方式，隐式转换。

- **`toString()`** 方法 `num.toString()`
- **`String()`** 方法 `String(num)`
- 加号 **`+`** 拼接字符串

```js
var num = 12;
console.log(num.toString());
console.log(String(num));
console.log(num + '');
```

引申：数字字符长转数字

```js
var str = '123'
console.log(str - '');
```

### 4.3 转换为数字型

| 方式                          | 说明                             | 案例                                  |
| ----------------------------- | -------------------------------- | ------------------------------------- |
| **`parseInt(string)`** 函数   | string->整数型                   | parseInt('10')                        |
| **`parseFloat(string)`** 函数 | string->浮点型                   | parseFloat('3.14')                    |
| **`Number()`** 强转换函数     | string->数字型                   | Number('12')                          |
| JS 隐式转换                   | 算术运算符隐式转换为数字型 - * / | `'12'-  0` 或 `'12' - ''` 或 `'12'*1` |

```js
console.log(parseInt('123')); // 123
console.log(parseFloat('3.14')); // 3.14
console.log('123' - 0); // 123
console.log('123' - ''); // 123
console.log(parseFloat('999')); // 999
console.log(parseInt('3.14159')); // 3
console.log(parseInt('120px')); // 120
console.log(Number('100')); // 100
console.log(Number('100.32')); // 100.32
console.log(parseFloat('120px'));//120
console.log(Number('100px')); // NaN
console.log('100px' - ''); // NaN
```

注意：

1. 数字字符串（`'12.3'`，`12`）之间进行加法运算实际上是字符串的拼接，结果还是字符串；而数字字符串之间的减法运算是算术运算，结果是数字型。
2. 一个数字字符和一个数字相乘，结果是算数运算结果，为数字型。

```js
console.log('10' + '2'); // 102
console.log('10' - '2'); // 8
console.log('10' + '3.2'); // 103.2
console.log('10' - '3.2'); // 6.8
console.log('12'*3); // 36
```

### 4.4 转换为布尔型

使用 **`Boolean()`** 函数转换。

- 转换值为 `false`：`''`, `0`, `NaN`, `null`, `undefined`（5个）
- 其他的转换值均为 `true`

```js
console.log(Boolean('')); // false
console.log(Boolean(0)); // false
console.log(Boolean(NaN)); // false
console.log(Boolean(null)); // false
console.log(Boolean(undefined)); // false
console.log(Boolean([])); // true
```

## 5. 标识符、关键字、保留字

### 5.1 标识符

标识（zhi）符：就是指开发人员为变量、属性、函数、参数取的名字。<u>标识符不能是关键字或保留字</u>。

### 5.2 关键字

关键字：是指JS本身已经使用了的字，不能再用它们充当变量名、方法名。

包括: break, case, catch, continue, default, delete, do, else, finally. for, function, if, in instanceof, new. return, switch, this, throw, try, typeof, var, void, while, with等。

### 5.3 保留字

保留字：实际上就是预留的“关键字” ，意思是现在虽然还不是关键字，但是未来可能会成为关键字，同样不能使用它们当变量名或方法名。

包括: boolean, byte, char, class, const, debugger, double, enum, export, extends fimal, float. goto, implements, import, int, interface, long, mative, package private, protected, public, short, static, super, synchronized, throws, transient volatile等。

## 6. 拓展：8 种基本数据类型

8 种基本数据类型中，前 7 种为基本数据类型，最后 1 种为<u>复杂数据类型（`object`）</u>。

- `number`：用于任何类型的数字：整数或浮点数，在 ±(253−1)±(253−1) 范围内的整数。
- `bigint`：用于任意长的整数。
- `string`：字符串，一个字符串可以包含 0 个或多个字符，没有单独的单字符类型。
- `boolean`：值为 `true` 或 `false`
- `null`：未知的值，只有一个 `null` 值的独立类型。
- `undefined`：未定义得值，只有一个 `undefined` 值的独立类型。
- `symbol`：用于唯一的标识符。
- `object`：用于更复杂的数据结构。

使用 `typeof` 运算符查看变量的数据类型：

- 两种形式：`typeof x` 或 `typeof(x)`
- 以字符串的形式返回类型名称：例如 `string`
- `typeof null` 会返回 `"object"` —— 这是 JavaScript 编程语言的一个错误，实际上它并不是一个 `object`。



# ch04. JS 运算符

**运算符（ operator ）**也被称为**操作符**，是用于实现赋值、比较和执行算数运算等功能的符号。 JavaScript常用的运算符有：

- 算术运算符
- 递增和递减运算符
- 比较运算符
- 逻辑运算符
- 赋值运算符

## 1. 算数运算符

- `+`
- `-`
- `*`
- `/`
- `%`

### 1.1 浮点数的精度问题

浮点数值的最高精度是17位小数，但在进行算术计算时其精确度远远不如整数。

```js
var result =0.1+0.2; //结果不是0.3,而是: 0.30000000000000004 
console.log(0.07 * 100); //结果不是7， 而是： 7.000000000000001
```

注意：

1. JS 中不要直接用浮点数之间进行运算，会产生精度误差。
2. 不要直接拿两个浮点数进行比较！

### 1.2 表达式和返回值

表达式：是由数字、运算符、变量等以能求得数值的有意义排列方法所得的组合 简单理解：是由数字、运算符、变量等组成的式子

表达式最终都会有一个结果，返回给我们，我们称为返回值

## 2. 递增递减运算符

### 2.1 递增和递减运算符概述

如果需要反复给数字变量添加或减去1，可以使用递增（++）和递减（-- ）运算符来完成。 在JavaScript 中，递增（++）和递减（-- ）既可以放在变量前面，也可以放在变量后面。放在变量前面时，

我们可以称为**前置递增（递减）运算符**，放在变量后面时，我们可以称为**后置递增（递减）运算符**。

注意：递增和递减运算符必须和变量配合使用。

- 后置递增运算符 `i++`
- 前置递增运算符 `++i`
- 后置递减运算符 `i--`
- 前置递减运算符 `--i`

### 2.2 前置递增和后置递增小结

- 前置递增和后置递增运算符可以简化代码的编写，让变量的值+ 1 比以前写法更简单
- 单独使用时，运行结果相同
- 与其他代码联用时，执行结果会不同
- 后置：先原值运算，后自加（先人后己）
- 前置：先自加，后运算（先已后人）
- 开发时，大多使用后置递增/减，并且代码独占一行，例如：num++; 或者num--;

## 3. 比较运算符

### 3.1 概述

概念：比较运算符（关系运算符）是两个数据进行比较时所使用的运算符，比较运算后，会返回一个布尔值 （true / false）作为比较运算的结果。

| 比较运算符 | 说明                                                        |
| ---------- | ----------------------------------------------------------- |
| `<`        | 小于                                                        |
| `>`        | 大于                                                        |
| `<=`       | 小于或等于                                                  |
| `>=`       | 大于或等于                                                  |
| `==`       | 判等于                                                      |
| `!=`       | 判不等                                                      |
| **`===`**  | 全等于。要求**值和数据类型**均一致，则返回 `true`           |
| **`!==`**  | 全不等于。要求**值和数据类型至少一个不一致**，则返回 `true` |

### 3.2 关于 == 与 ===

#### 3.2.1. 区别

需要注意的是 `==` 和 `===` 的区别。

- `==` 比较的时候只判断值，因为会进行<u>隐式转换</u>。**值相等则返回 `true`**
- `===` 比较判断的时同时需要<u>值相等和类型相同</u>，两者均满足则返回 `true`

#### 3.2.2 规律

结合以下例子体会。

- `''`、`0`、`false` 之间（或 `'1'`、`1`、`true`之间）进行 `==` 比较的结果为 `true`
- `NaN` 与其他任何数据类型之间 `==` 比较结果为 `false`
- `null` 只有在和自身以及 `undefined` 之间 `==` 比较时结果为 `true`
- `undefined` 只有在和自身以及 `null` 之间 `==` 比较时结果为 `true`
- 数字和数字字符串的值相等，则 `==` 比较的结果为 `true`
- 以上这些例子在全等比较 `===` 下的结果均为 `false`

```js
console.log('18' == 18); // true
console.log('' == false); // true
console.log('' == 0); // true
console.log(0 == false); // true
console.log('1' == 1 == true); // true

console.log('NaN与其他值比较:');
console.log(NaN == 0); // false
console.log(NaN == ''); // false
console.log(NaN == NaN); // false
console.log(NaN == null); // false
console.log(NaN == false); // false
console.log(NaN == undefined); // false

console.log('null与其他值：');
console.log(null == null); // true
console.log(null == undefined); // true
console.log(null == 0); // false
console.log(null == ''); // false
console.log(null == NaN); // false
console.log(null == false); // false

console.log('undefined与其他值比较:');
console.log(undefined == null);  // true
console.log(undefined == undefined);  // true
console.log(undefined == 0);  // false
console.log(undefined == '');  // false
console.log(undefined == NaN);  // false
console.log(undefined == false);  // falseCopy to clipboardErrorCopied
```

## 4. 逻辑运算符

### 4.1 概述

- 逻辑与 `&&`
- 逻辑或 `||`
- 逻辑非 `!`

### 4.2 逻辑中断（短路操作）

原理：多个表达式进行逻辑运算，当左边的表达式值可以确定最终结果时，不再继续运算右边其余的表达式。

#### 4.2.1 逻辑与 &&

- 语法：`expr1 && expr2 && ...`
- **若 `expr1` 为真，则返回 `expr2`**
- 若 `expr1` 为假，则返回 `expr1`

```js
console.log(123 && 456); // 456
console.log(false && 123); // false
console.log(1 && 2 && 3); // 3
console.log(1 && 1 && false && 2); // false
```

#### 4.2.2 逻辑或 ||

- 语法：`expr1 || expr2 || ...`
- **若 `expr1` 为假，则返回 `expr2`**
- 若 `expr1` 为真，则返回 `expr1`

```js
console.log(0 || 12); // 12
console.log(true ||  false || 2); // true
console.log(0 || false || true || -2); // true
```

## 5. 赋值运算符

- `+=`
- `-=`
- `*=`
- `/=`

## 6. 拓展：JS特殊运算符

### 6.1 数字转化：单目运算符 `+`

单目运算符 `+` 作用于数字无效，结果不变。但是可以用来转化非数字类型为数字，等效于 `Number()`。

```javascript
let x = false;
let y = "";
let z = "123.4";
console.log(+x); // 0
console.log(+y); // 0
console.log(+z); // 123.4
```

用于非数字型之间的数学运算，很简洁：

```javascript
let a = "12";
let b = "24";
console.log(+a + +b); // 36
```

### 6.2 逗号运算符 `,`

逗号运算符能让我们处理多个语句，使用 `,` 将它们分开。每个语句都运行了，**但是只有最后的语句的结果会被返回**。

```javascript
let a = (3 + 4, 5 + 6);
console.log(a); // 11
```

### 6.3 布尔值转换符 `!!`

两个相邻的非逻辑运算符组成的 **`!!`**，可以将一个值转换为对应的布尔值。等效于 **`Boolean()`**。

```javascript
console.log(!!"0"); // true
console.log(!!0); // false
console.log(!!undefined); //false
console.log(!!"aaa"); // true
```

### 6.4 空值合并运算符 `??`

我们将值既不是 `null` 也不是 `undefined` 的表达式定义为已定义的值（defined）。即：`??`。

`a ?? b` 结果为：

- 若 `a` 已定义，则结果为 `a`
- 若 `a` 不是已定义的，则结果为 `b`

等价于：

```javascript
(a !== null && a !== undefined) ? a : b;
```



# ch05. 流程控制

- 顺序结构
- 选择分支结构
- 循环结构

## 1. 顺序结构

## 2. 选择结构

- `if-else`
- `if-else if-else`
- `switch-case`

### 2.1 if-else

语法

```js
if (condition)
   statement1
[else
   statement2]
```

### 2.2 if-else

语法

```js
if (condition1)
  statement1
else if (condition2)
  statement2
else if (condition3)
  statement3
...
else
  statementNCopy to clipboardErrorCopied
```

### 2.3 switch-case

语法

```js
switch (expression) {
  case value1:
    //Statements executed when the
    //result of expression matches value1
    [break;]
  case value2:
    //Statements executed when the
    //result of expression matches value2
    [break;]
  ...
  case valueN:
    //Statements executed when the
    //result of expression matches valueN
    [break;]
  [default:
    //Statements executed when none of
    //the values match the value of the expression
    [break;]]
}
```

### 2.4 三元表达式

```js
条件表达式 ? 表达式1 : 表达式2
```

```js
var num = 10;
num > 5 ? 'Y' :'N';
```

## 3. 循环

### 3.1 概述

- `for`
- `while`
- `do...while`
- `label`
- `for...in`
- `for...of`

### 3.2 for 循环

语法

```js
for ([initExpr]; [condExpr]; [incExpr])
    statement
```

- initExpr: 变量初始化
- condExpr: 循环条件
- incExpr：增量表达式

例子

```js
for (let step = 0; step < 5; step++) {
  // Runs 5 times, with values of step 0 through 4.
  console.log('Walking east one step');
}
```

### 3.3 while 循环

语法

```js
while (condition) 
    statement
```

例子

```js
let n = 0;
let x = 0;
while (n < 3) {
    n++;
    x += n;
}
```

### 3.4 do...while

先执行一次，再判断执行，至少会执行一次循环体

语法

```js
do 
    statement
while (condition);
```

例子

```js
let n = 5
do {
    console.log('hello');
} while (--n)
```

### 3.5 label

语法：

```js
label:
statement
```

- `label`: 任何不属于保留关键字的 JavaScript 标识符。
- `statement`: JS 语句。

说明：

可使用一个标签来唯一标记一个循环，然后使用 break 或 continue 语句来指示程序是否中断循环或继续执行。

需要注意的是，JavaScript 没有 goto 语句，标记只能和 break 或 continue 一起使用。

在严格模式中，你不能使用 “let” 作为标签名称。它会抛出一个 SyntaxError（因为 let 是一个保留的标识符）。

例子：

```js
var str = ''
aLoop:  //label
for (let i = 0; i < 5; i++) {
    if (i == 2) {
        continue aLoop;
    }
    str += i;
}
console.log(str); // 0134
```

### 3.6 break 与 continue

- `break`：跳出当前循环（跳出一层循环），不再进行当前循环。
- `continue`：跳过本轮循环，进行当前循环的下一轮。
- `break` 与 `continue` 均可配合 `label` 语句使用来跳转循环。

### 3.7 for...in

语法：

```js
for (variable in object) {
    //statements
}
```

说明：

- `for...in` 语句用于对数组或者对象的属性进行循环操作。
- `for ... in` 循环中的代码每执行一次，就会对数组的元素或者对象的属性进行一次操作。

```js
var arr = new Array(1,2,3,4,5);
for (let i in arr) {
    console.log(i+'.');
}
```

### 3.8 for...of

语法：

```js
for (variable of iterable) {
    //statements
}
```

例子：

```js
let iterable = [10, 20, 30];
for (let value of iterable) {
    value += 1;
    console.log(value);
}
```

## 4. chrome 代码调试

- 断点调试：断点调试是指自己在程序的某一行设置一个断点，调试时，程序运行到这一行就会停住，然后你可以一步一步往下调试，调试过程中可以看各个变量当前的值，出错的话，调试到出错的代码行即显示错误，停下。
- 断点调试可以帮我们观察程序的运行过程
- 浏览器中按F12--> sources -->找到需要调试的文件-->在程序的某一行设置断点
- Watch: 监视，通过watch可以监视变量的值的变化，非常的常用。
- F11: 程序单步执行，让程序一行一行的执行，这个时候，观察watch中变量的值的变化。
- 代码调试的能力非常重要，只有学会了代码调试，才能学会自己解决bug的能力。初学者不要觉得调试代码麻烦就不去调试，
- 知识点花点功夫肯定学的会，但是代码调试这个东西，自己不去练，永远都学不会。
- 今天学的代码调试非常的简单，只要求同学们记住代码调试的这几个按钮的作用即可，后面还会学到很多的代码调试技巧。