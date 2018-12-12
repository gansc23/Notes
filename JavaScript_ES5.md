

# **《JavaScript高级程序设计（第3版）》**


### **目录**

### [第3章 基本概念](#第3章-基本概念)
- 3.1 语法
  - [3.1.1 区分大小写](#区分大小写)
  - [3.1.2 标识符](#3.1.2-标识符)
  -  3.1.3 注释
  - [3.1.4 严格模式](#3.1.4-严格模式)
  -  3.1.5 语句
- [3.2 关键字和保留字](#3.2-关键字和保留字)
- [3.3 变量](#3.3-变量)
- [3.4 数据类型](#3.4-数据类型)
  - [3.4.1 typeof 操作符](#3.4.1-typeof-操作符)
  - [3.4.2 undefined 类型](#3.4.2-undefined-类型)
  - [3.4.3 null 类型](#3.4.3-null-类型)
  - [3.4.4 boolean 类型](#3.4.4-boolean-类型)
  - [3.4.5 number 类型](#3.4.5-number-类型)
  - [3.4.6 string 类型](###3.4.6-string-type)
  - <a href="#3.4.6">`3.4.6 string 类型`</a>
---
---


## 第1章 JavaScript 简介

---

## 第2章 JavaScript 简介

---

## 第3章 基本概念

>> ### 3.1.1 区分大小写

标识符命名区分大小写

<br>

>> ### 3.1.2 标识符

- 第一个字符必须是字母、下划线或美元符号（$）
- 其它字符可以是字母、下划线、美元符号和数字

按照惯例，采用首字母小写的驼峰大小写命名方式

<br>

>> ### 3.1.4 严格模式

**在脚本文件顶部** 或者 **函数体顶部** 添加： 
```js
"use strict";
```

```js
// 在命令行中启用严格模式
$ node --use_strict main.js
```
<br>

> ### 3.2 关键字和保留字

**以下是部分关键字（带*是ES 5新增的关键字），不可用作标识符名* ：
```js
instanceof  typeof      in      with
in          this        new     delete
eval        arguments
debugger*   let*        yield*
```

**关键字和保留字虽不能作为标识符名字，但可作为对象的属性名（不建议）**

<br>

> ### 3.3 变量

- ES的变量是松散类型。
- 在函数体内定义的变量是局部变量。

```js
// 声明的技巧
var msg = "hi",
    found = false,
    age = 29;
```

<br>

> ### 3.4 数据类型

数据类型：undefined, boolean, number, string, object(包括null), function

<br>

>> ### 3.4.1 typeof 操作符

typeof是操作符，其操作数可以是变量也可是字面量，可以加括号也可不加括号进行调用。
```js
typeof null;  // => "object"
typeof(/^666/);  // => "object"
```

function其实也是一种object，但由于函数有一些特殊的属性，所以typeof操作符对function进行了区别。

<br>

>> ### 3.4.2 undefined 类型

未定义的变量在进行判断时会被视为undefined，但它与定义为undefined的标量是有区别的：
```js
var message;  // 等同于 var message = undefined;  定义了变量但未赋值，其值为undefined
// var age;  // 这个变量未声明

typeof message; // "undefined"
typeof age; // "undefined"

console.log(message); // "undefined"
console.log(age);     // error
```

<br>

>> ### 3.4.3 null 类型

实际上，undefined继承于null，因此它们的相等性测试(==)返回true。

<br>

>> ### 3.4.4 boolean 类型

**转型函数 Boolean(x) 的行为如下：**
数据类型 | 转为true | 转为false
:------: | :------: | :------:
undefined | *n/a*     | undefined
boolean  |   true   | false
number | 除0和NaN以外的数值 | 0或NaN
string | 非空字符串 | 空字符串
object | 任何非null对象 | null

**布尔判断会自动对变量自动调用 Boolean(x) 进行转型。**

<br>

>> ### 3.4.5 number 类型

>> ### 3.4.6 string type

>> ### <a id="3.4.6" /> 3.4.6 fsdfds

---

#### 第4章 JavaScript 简介

---

#### 第5章 JavaScript 简介

---

#### 第6章 JavaScript 简介

---

#### 第7章 JavaScript 简介

---

#### 第8章 JavaScript 简介

---

#### 第9章 JavaScript 简介

---

#### 第10章 JavaScript 简介

---

#### 第11章 JavaScript 简介

---

#### 第12章 JavaScript 简介

---

#### 第13章 JavaScript 简介

---

#### 第14章 JavaScript 简介

---

#### 第15章 JavaScript 简介

---

#### 第16章 JavaScript 简介

---

#### 第17章 JavaScript 简介

---

#### 第18章 JavaScript 简介

---

#### 第19章 JavaScript 简介

---

#### 第20章 JavaScript 简介

---

#### 第21章 JavaScript 简介

---

#### 第22章 JavaScript 简介

---

#### 第23章 JavaScript 简介

---

#### 第24章 JavaScript 简介

---

#### 第25章 JavaScript 简介

---

#### 附录A JavaScript 简介

---

#### 附录B JavaScript 简介

---

#### 附录C JavaScript 简介

---

#### 附录D JavaScript 简介









