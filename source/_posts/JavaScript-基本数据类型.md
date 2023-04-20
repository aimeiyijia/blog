---
title: JavaScript-基本数据类型
comments: false
abbrlink: c0cf83fa
date: 2023-04-20 14:29:44
tags:
categories:
keywords:
description:
top_img:
cover:
---

## 基本数据类型

js 中共有六种基本数据类型(简单数据类型，原始数据类型)：**undefined**、**boolean**、**number**、**bigint**、**string**、**null**、**symbol**
其余均为引用类型(复杂数据类型，特殊数据类型，合成类型)，比较常用的有 Array, Date,也叫内置对象

### null

代表**无**、**空**的特殊值，变量未指向任何对象，对象的值未设置，从原型链（继承链）上来说就是找不到它的创建者（不知道是那种类型创建了它）

不是一个对**不存在的 Object 的引用**或者 **null 指针**。

### undefined

变量已被声明，但未赋值，一个函数如果没有使用 return 语句指定值，就会返回一个 undefined 值。

{% note info no-icon %}

null 与 undefined 的比较

相同点：

1. 都是基本类型中的特殊值
2. 在布尔运算中都是 [falsy](https://developer.mozilla.org/zh-CN/docs/Glossary/Falsy)(假值、虚值)

不同点：

1. **null** 表示一个值被定义了，定义为“空值”；**undefined** 表示根本不存在定义。所以把一个值设为 **null** 是合理的，如 `let obj = null`。但设置一个值为 **undefined** 是不合理的
2. **undefined**是全局作用域（在浏览器环境下全局对象为[window](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/window)）中的一个值，**null**不是。
3. **undefined**的初始值就是**undefined**，**null**没有初始值

推荐阅读[undefined 与 null 的区别](https://www.ruanyifeng.com/blog/2014/03/undefined-vs-null.html)
{% endnote %}

### number

数字(值)类型，最大、小值为 +、-(2<sup>53</sup> - 1)

### bigint

bigint：大数，表示任意大的数，一个整数字面量后面加 n 的方式定义一个 bigInt

{% note warning no-icon %}
不能使用用[Math](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math)中的方法

bigint 类型的数字不能与 number 类型的数字做数学运算，bigint 型转 number 会降低精度
{% endnote %}

### string

string：字符串 必须包含在单引号/双引号内，或反引号(模板字符串) `haha${变量}`

### boolean

boolean：布尔值，两个值 true, false。

### symbol

symbol 用于唯一的标识符，独一无二的。基本上用于定义对象的唯一属性名，

## 基本类型通用语法

以 Boolean 为例：Boolean(expression) 名叫布尔函数、布尔构造器，将简单地将表达式转换为布尔型，而 new Boolean(expression) 将围绕转换后的布尔值创建一个包装对象，以一个数字值为参数调用 Number 构造器（对象包装器）来创建数字对象。由此产生的对象包含一个值为此数字值的内部属性。

```js
// 严格相等
new Boolean("true") === true // false
Boolean("true") === true // true
// 非严格相等 会执行一次隐形类型转换
Boolean("true") == new Boolean("true") // true

typeof new Boolean("true") // "object"
typeof Boolean("true") // "boolean"

var b = new Boolean(true)
b.relatedMessage = "this should be true initially"
console.log(b.relatedMessage) // will work

var b = true
b.relatedMessage = "this should be true initially"
console.log(b.relatedMessage) // undefined
```

其它基本类型如上用法，对应关系如下表

| 基本类型 | 构造器(对象包装器)环境下      | 非构造器环境下(如没有 new 操作符)     |
| -------- | ----------------------------- | ------------------------------------- |
| number   | new Number() 返回一个包装对象 | Number() 执行类型转换返回一个基本类型 |
| bigint   | 无                            | BigInt()                              |
| string   | new String()                  | String()                              |
| boolean  | new Boolean()                 | Boolean()                             |
| symbol   | 无                            | Symbol()                              |
