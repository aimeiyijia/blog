---
title: this的指向判断
comments: false
abbrlink: "70459417"
date: 2023-03-25 23:19:41
tags:
categories:
keywords:
description:
top_img:
cover:
---

`this` 不是编写时绑定，而是运行时绑定。它依赖于函数调用的上下文条件。`this` 绑定与函数声明的位置没有任何关系，而与函数被调用的方式紧密相连。

当一个函数被调用时，会建立一个称为执行环境的活动记录。这个记录包含函数是从何处（调用栈 —— call-stack）被调用的，函数是 _如何_ 被调用的，被传递了什么参数等信息。这个记录的属性之一，就是在函数执行期间将被使用的 `this` 引用。

`this` 实际上是在函数被调用时建立的一个绑定，它指向 _什么_ 是完全由函数被调用的调用点来决定的。

1. 函数是通过 `new` 被调用的吗（new 绑定）？如果是，`this` 就是新构建的对象。

   `var bar = new foo()`

2. 函数是通过 `call` 或 `apply` 被调用（明确绑定），甚至是隐藏在 `bind`_硬绑定_ 之中吗？如果是，`this` 就是那个被明确指定的对象。

   `var bar = foo.call( obj2 )`

3. 函数是通过环境对象（也称为拥有者或容器对象）被调用的吗（隐含绑定）？如果是，`this` 就是那个环境对象。

   `var bar = obj1.foo()`

4. 否则，使用默认的 `this`（默认绑定）。如果在 `strict mode` 下，就是 `undefined`，否则是 `global` 对象。

   `var bar = foo()`
