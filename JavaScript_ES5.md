
## **《JavaScript高级程序设计（第3版）》**

---

### **目录**

### <a href="#ch3">第3章 基本概念</a>
- *3.1 语法*
  - <a href="#3.1.1">3.1.1 区分大小写</a>
  - <a href="#3.1.2">3.1.2 标识符)</a>
  -  *3.1.3 注释*
  - <a href="#3.1.4">3.1.4 严格模式</a>
  -  *3.1.5 语句*
- <a href="#3.2">3.2 关键字和保留字</a>
- <a href="#3.3">3.3 变量</a>
- <a href="#3.4">3.4 数据类型</a>
  - <a href="#3.4.1">3.4.1 `typeof` 操作符</a>
  - <a href="#3.4.2">3.4.2 `undefined` 类型</a>
  - <a href="#3.4.3">3.4.3 `null`</a>
  - <a href="#3.4.4">3.4.4 `boolean` 类型</a>
  - <a href="#3.4.5">3.4.5 `number` 类型</a> : <a href="#isNaN()">`isNaN()`</a>, <a href="#parseInt()">`parseInt()`</a>, <a href="#parseFloat()">`parseFloat()`</a>
  - <a href="#3.4.6">3.4.6 `string` 类型</a>
  - <a href="#3.4.7">3.4.7 `object` 类型</a>
- *3.5 操纵符*
  - <a href="#3.5.1">3.5.1 一元操作符</a>
  - <a href="#3.5.2">3.5.2 位操作符</a>
  - <a href="#3.5.3">3.5.3 布尔操作符</a>
  - <a href="#3.5.4、5">3.5.4 乘性操作符、3.5.5 加性操作符</a>
  - <a href="#3.5.6、7">3.5.6 关系操作符、3.5.7 相等操作符</a>
  - *3.5.8 条件操作符*
  - <a href="#3.5.9">3.5.9 赋值操作符</a>
  - <a href="#3.5.10">3.5.10 逗号操作符</a>

---
---


### 第1章 JavaScript 简介

---

### 第2章 JavaScript 简介

---

### <a id="ch3">第3章 基本概念</a>

<br>

> > #### <a id="3.1.1">3.1.1 区分大小写</a>

- 标识符命名区分大小写。

<br>

> > #### <a id="3.1.2">3.1.2 标识符</a>

- 第一个字符必须是字母、下划线或美元符号（$）
- 其它字符可以是字母、下划线、美元符号和数字

 按照惯例，采用首字母小写的驼峰大小写命名方式

<br>

> > #### <a id="3.1.4">3.1.4 严格模式</a>

- **在脚本文件顶部** 或者 **函数体顶部** 添加：`"use strict;"`
- 在node命令行里启用严格模式：`$ node --use_strict xxx.js`

<br>

> #### <a id="3.2">3.2 关键字和保留字</a>

```js
// 以下是部分关键字（带*是ES 5新增的关键字），不可用作标识符名：

instanceof  typeof      in      with
in          this        new     delete
eval        arguments
debugger*   let*        yield*
```

- **关键字和保留字虽不能作为标识符名字，但可作为对象的属性名（不建议）**

<br>

> #### <a id="3.3">3.3 变量</a>

- ES的变量是松散类型。
- 在函数体内定义的变量是局部变量。

```js
// 声明的技巧
var msg = "hi",
    found = false,
    age = 29;
```

<br>

> #### <a id="3.4">3.4 数据类型</a>

- 数据类型：`undefined, boolean, number, string, object(包括null), function`

<br>

> > #### <a id="3.4.1">3.4.1 `typeof` 操作符</a>

```js
// typeof是操作符，其操作数可以是变量也可是字面量，可以加括号也可不加括号进行调用:

typeof null;  // => "object"
typeof(/^666/);  // => "object"
```

- `function`其实也是一种`object`，但由于函数有一些特殊的属性，所以`typeof`操作符对`function`进行了区别。

<br>

> > #### <a id="3.4.2">3.4.2 `undefined` 类型</a>

```js
// 未定义的变量在进行判断时会被视为undefined，但它与定义为undefined的标量是有区别的：

var message;  // 等同于 var message = undefined;  定义了变量但未赋值，其值为undefined
// var age;  // 这个变量未声明

typeof message; // "undefined"
typeof age; // "undefined"

console.log(message); // "undefined"
console.log(age);     // error
```

<br>

> > #### <a id="3.4.3">3.4.3 `null` 类型</a>

- 实际上`undefined`继承于`null`，因此它们的相等性测试(==)返回true。

<br>

> > #### <a id="3.4.4">3.4.4 `boolean` 类型</a>

 <a id="Boolean()">**`Boolean(x)` 转换函数（默认的转换函数）的行为：**</a>
数据类型 | 转为true | 转为false
:------: | :------: | :------:
undefined | *n/a*     | undefined
boolean  |   true   | false
number | 除0和NaN以外的数值 | 0或NaN
string | 非空字符串 | 空字符串
object | 任何非null对象 | null

- 布尔判断会自动对变量自动调用 `Boolean(x)` 进行转型。

<br>

> > #### <a id="3.4.5">3.4.5 `number` 类型</a>

```js
var n1 = 56,  // 十进制整数
    n2 = 070,  // 八进制的56，严格模式不支持八进制
    n3 = 0x1f;  // 十六进制
```

- `-0`, `0`和`+0`相互是全等。

- 虽然都是`number`类型，但是存放浮点数会占用64位，存放整数占用32位；在允许的情况下，ES会将浮点数转换为整数存放。

```js
Number.MIN_VALUE  // 5e-324
Number.MAX_VALUE  // 1.7976931348623157e+308

// 若计算结果超界，则会被自动转换为Infinity或-Infinity,
// 切该值无法参与下一次计算
Infinity === Number.POSITIVE_INFINITY  // true
-Infinity === Number.NEGATIVE_INFINITY  // true

isFinite(n);  // 是否位于负无穷大与正无穷大之间
```
<br>

<a id="isNaN()">`isNaN` 函数:</a>

```js
/*
NaN表示一个不是有效数值的数值（Not a Number）：
1）任何涉及到NaN的操作结果都是NaN
2）NaN与任何值都不相等，包括它自身
//*/
isNaN(n);  // 判断是否 非数值；会尝试转换为数值
isNaN(NaN);  // true
isNaN("10.0");  // false
isNaN("blue");  // true
isNaN(true);  // false, true可被转换为1

/*
若 isNaN 的实参为对象，则：
1）调用对象的 valueOf 方法，确定返回值是否可以转换为数值，若不能则执行下一步
2）调用上一步的返回值的 toString 方法，再测试返回值能否转换为数值。
//*/
```

 <a id="Number()">**`Number(x)` 转换函数（默认的转换函数）的行为：**</a>
- 若是`undefined`，则为NaN
- 若是`boolean`类型，则`true`和`false`分别转换为1和0
- 若是`number`类型，则为自身
- 若是字符串，则遵循下列规则：
  - 若是空字符串，则转换为0
  - 若字符串只包含数字（包括正负号、小数点、0x|0X前缀），则转换为十进制数值（前导的0会被忽略）
  - 其它情况，转换为NaN
- 若是对象：
  1. 若是`null`，则转换为0
  2. 调用 `valueOf` 方法，然后按照前面的规则来尝试转换返回的值，若为NaN则进行下一步
  3. 调用对象的 `toString` 方法，然后按照前面的规则来尝试转换返回的值

<br>

<a id="parseInt()">**`parseInt(s: string, radix?: number)` 将字符串转换为整数：**</a>
- 从字符串的第一个非空格字符开始解析，直至解析完所有的字符或遇到了非数字字符：
  - `"  1234abc" => 1234; "0xA" => 10;`
  - `"+123.4" => 123; " -123.4" => -123; 22.5 => 22;`
  - `parseInt("070") => 70` (ES5中此函数不能直接解析八进制，但可以设置radix为8)
  - `parseInt("070", 8) => 56`
- 空字符串转换为NaN："" => NaN

<br>

<a id="parseFloat()">**`parseFloat(s: string)` 将字符串转换为浮点数：**</a>
- 行为与 parseInt 函数类似，支持解析浮点数，但只能解析十进制：
  - `"  22.34.5" => 22.34; "1234abc" => 1234; "3.125e7" => 31250000;`
  - `"0xA" => 0; "0908.5" => 908.5;`
- 空字符串转换为NaN："" => NaN

<br>

> > #### <a id="3.4.6">3.4.6 `string` 类型</a>

字符是16位的Unicode

一些特殊字面量    | 含义
------ | ------
\b | 空格
\f | 禁止
\xnn | 以十六进制代码nn表示的一个字符。例如：\x41表示'A'
\unnnn | 以十六进制代码nnnn表示的一个字符。例如：\u03a3表示一个希腊求和字符

- 字符串的 `length`属性返回的是包含的16位字符的个数，但若有双字节字符，那么`length`就不会返回正确的字符数量。
- 字符串是不可变的

<br>

- 除了undefine和null，其余都能调用 `toString()` 方法转换为字符串
- 在调用数值的 `toString()` 方法时，还可以传递基数
  - `var n = 10; n.toString(8); // => 10`

<br>

**转型函数 `String(x)` 的规则：**
  1. 若不是`undefined`和`null`，则调用`toString()`方法并返回相应结果
  2. 否则返回 "undefined" 或 "null"

<br>

> > #### <a id="3.4.7">3.4.7 `object` 类型</a>

`var o = new Object(); <==> var o = new Object;  // 若无参数则可省略圆括号`

 ES中所有的对象都是`Object`的实例，都具有以下属性和方法：
  - `Constructor`属性：指向创建当前对象的构造函数。
  - `hasOwnProperty(propName)`方法：检查在当前的实例中（不是在实例的原型中）是否有指定的属性。
  - `isPrototypeOf(obj)`方法：判断此实例是否是传入的对象的原型
  - `propertyIsEnumerable(propName)`方法：判断指定的属性能否使用`for-in`进行枚举
  - `valueOf()`：返回对象的布尔值、数值或字符串表示。一般与`toString()`的返回值相同
  - `toString()`：返回对象的字符串表示
  - `toLocaleString()`：返回对象与执行环境的的地区对应的字符串表示


宿主对象（如BOM和DOM）是由宿主实现提供的，而ECMA-262不负责定义宿主对象，所以宿主对象不一定继承`Object`。

<br>

> > #### <a id="3.5.1">3.5.1 一元操作符</a>

`++`、`--`、一元`+` 和 一元`-` 会对非数值类型的操作数使用 <a href="#Number()">*`Number(x)`*</a> 函数进行转换后再运算。

<br>

> > #### <a id="3.5.2">3.5.2 位操作符</a>

位操作符不能直接操作64位的值，而是先将64位的值转成32位的整数，然后执行操作。<br>
因此对于开发人员来说整个过程像是只存在32位的整数一样。

ES中的整数都是有符号的，负数用二进制补码表示，且位操作符也会操作符号位。<br>
**位操作符** 会对非数值类型的操作数使用 <a href="#Number()">*`Number(x)`*</a> 函数进行转换后再操作。<br>
`NaN` 和 `Infinity` 在进行位操作时，会被当成0来处理。<br>

```js
~b;  // 按位非
a & b;  // 按位与
a | b;  // 按位或
a ^ b;  // 按位异或
a << n;  // 左移，n = [0, 31]
a >> n;  // 有符号右移，用符号位来填充左侧的空位，n = [0, 31]
a >>> n; // 无符号右移，用0填充左侧的空位，n = [0, 31]
```
<br>

> > #### <a id="3.5.3">3.5.3 布尔操作符</a>

`!  &&  ||` 会对非布尔类型的操作数使用 <a href="#Boolean()">*`Boolean(x)`*</a> 函数进行转换后再操作。<br>
`&&` 和 `||` 都是短路操作。

<br>

> > #### <a id="3.5.4、5">3.5.4 乘性操作符、3.5.5 加性操作符</a>

```js
// 牢记一点：[-]Infinite 只是一个标记，而不是一个具体的数，
Infinite + -Infinite; => NaN
Infinite * 0; // => NaN
Infinite / Infinite;  // => NaN
0 / 0;  // NaN
Infinite / 0;  // => Infinite
Infinite / -0;  // => -Infinite

Infinite % num;  // NaN
num % Infinite;  // num
5 % Infinite, 5 % -Infinite;  // 5
-5 % Infinite, -5 % -Infinite;  // -5

-0 + -0;  // -0
+0 + -0;  // 0

true + null;  // 1
             
1+2+"+"+3+"="+1+2+3;  // "3+3=123"。在加法操作符中，若有操作数是`string`类型，
                      // 则会将另一个操作数转换为`string`类型，然后进行拼接。
1+2+"+"+3+"="+(1+2+3);  // "3+3=6"
```
<br>

> > #### <a id="3.5.6、7">3.5.6 关系操作符、3.5.7 相等操作符</a>

**`<  <=  >  >=` 关系操作符遵循以下流程对操作数进行转换：**
- 若有一个操作数是布尔值，则先将其转换为数值，然后进行比较
- 若有一个操作数是数值，则将另一个操作数转换为数值，再进行比较
- 若两个操作数都是字符串，则比较它们对应的字符编码值
- 若有一个是对象：
  1. 若有`valueOf()`方法，则调用此方法用返回的结果按照前面的规则执行比较。
  2. 调用`toString()`方法，并用返回的结果按照前面的规则执行比较。

```js
"a" < 3; // false，a被转换为了NaN
NaN >= 3;  // false，NaN与任何操作数进行关系比较都是false
```
<br>

**`==  !=` 关系操作符遵循以下流程对操作数进行转换：**
- `undefined` 和` null` 不会做转换，且 `undefined == null`
- 若有一个操作数是布尔值，则先将其转换为数值，然后进行比较
- 若有一个操作数是数值，则将另一个操作数转换为数值，再进行比较
- 若两个操作数都是对象，则比较它们是否是同一个对象(引用/指针)
- 若只有一个是对象（非`null`），调用 `valueOf()`方法，则调用此方法用返回的结果按照前面的规则执行比较。

```js
0 == null, 0 == undefined;  // false, false
null == undefined;  // true
0 == false;  // true
NaN != NaN;  // true
"5" == 5;  // true
```

**`===  !==` 不会对操作数做转换，即只有当两个操作数是相同类型且相同值才是全等**

<br>

> > #### <a id="3.5.9">3.5.9 赋值操作符</a>

每个主要的算术操作符（以及个别的其它操作符）都有对应的复合赋值操作符：
`+=  -=  *=  /=  %=  <<=  >>=  >>>=`

> > #### <a id="3.5.10">3.5.10 逗号操作符</a>

```js
// 声明多个变量
var n1 = 1, n2 = 2, n3 = 3;
// 赋值时，逗号操作符总是返回表达式中的最后一项
var n = (5, 1, 4, 8, 6);  // n=>6
```
<br>

> #### <a id="3.6">3.6 语句</a>



---

#### 第4章 JavaScript 简介



