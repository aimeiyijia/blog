---
title: JavaScript基本类型与引用类型
comments: false
abbrlink: ced2cb54
date: 2023-03-25 23:20:56
tags:
categories:
keywords:
description:
top_img:
cover:
---

## 基本类型

基本的数据类型有：`undefined，boolean，number，bigint，string，null， symbol`。基本类型的访问是按值访问的，就是说你可以操作保存在变量中的实际的值。 基本类型有以下几个特点：

### 基本类型的值是不可变的

自动装箱
基本类型本身和一个赋值为基本类型的变量的区别。变量会被赋予一个新值，而基本类型不能像数组、对象以及函数那样被改变

基本类型没有方法，但仍然表现得像有方法一样。当在基本类型上访问属性时，JavaScript 自动将值装入包装器对象中，并访问该对象上的属性。例如，"foo".includes("f") 隐式创建了一个 String 包装对象，并在该对象上调用 String.prototype.includes()。这种自动装箱行为在 JavaScript 代码中是无法观察到的，但却是各种行为的一个很好的心理模型——例如，为什么“改变”基本类型不起作用（因为 str.Foo = 1 不是赋值给 str 本身的 Foo 属性，而是赋值给了一个临时包装器对象）

任何方法都无法改变一个基本类型的值，比如一个字符串：

```js
let name = "ame"
name.toUpperCase() // 输出 'AME'
console.log(name) // 输出  'ame'
```

字符串类型 name 调用了 toUpperCase()方法后返回的是一个新的字符串，原始的 name 并未发生改变。

再来看个：

```js
let person = 'jozo';
person.age = 22;
person.method = function(){//...};

console.log(person.age); // undefined
console.log(person.method); // undefined
```

通过上面代码可知，不能给基本类型添加属性和方法，再次说明基本类型是不可变的；

### 基本类型的比较是值的比较

只有在它们的'值'相等的时候它们才相等。

但你可能会这样：

```js
let a = 1
let b = true
let c = 1
console.log(a == b) //true
console.log(a == c) //true
```

{% note info %}
隐形类型转换规则：如果有一个操作数是布尔值，则在比较相等性之前先将其转换为数值
{% endnote %}

用==比较两个不同类型的变量时会先进行一些隐形类型转换。像上面的比较先会把 true 转换为数字 1 再和数字 1 进行比较，结果就是 true 了。

### 基本类型的变量是存放在栈区的（栈区指内存里的栈内存）

假如有以下几个基本类型的变量：

```js
let name = "jozo"
let city = "guangzhou"
let age = 22
```

那么它的存储结构如下图：

![img](https://cdn.jsdelivr.net/gh/aimeiyijia/blog-images/img/javascript/基本类型存储结构.png)

栈区包括了 变量的标识符和变量的值。

### 基本类型赋值是'赋值'

在从一个变量向另一个变量赋值基本类型时，会在该变量上创建一个新值，然后再把该值复制到为新变量分配的位置上：

```js
var a = 10
var b = a

a++
console.log(a) // 11
console.log(b) // 10
```

此时，a 中保存的值为 10 ，当使用 a 来初始化 b 时，b 中保存的值也为 10，但 b 中的 10 与 a 中的是完全独立的，该值只是 a 中的值的一个副本，此后， 这两个变量可以参加任何操作而相互不受影响。

也就是说基本类型在赋值操作后，两个变量是相互不受影响的。

![img](https://cdn.jsdelivr.net/gh/aimeiyijia/blog-images/img/javascript/基本类型赋值.png)

## 引用类型

js 中除了上面的基本类型(number,string,boolean,null,undefined)之外就是引用类型了，也可以说是就是对象了。对象是属性和方法的集合。 也就是说引用类型可以拥有属性和方法，属性又可以包含基本类型和引用类型。来看看引用类型的一些特性：

### 引用类型的值是可变的

我们可为为引用类型添加属性和方法，也可以删除其属性和方法，如：

```js
var person = {} //创建个控对象 --引用类型
person.name = "jozo"
person.age = 22
person.sayName = function () {
  console.log(person.name)
}
person.sayName() // 'jozo'

delete person.name //删除person对象的name属性
person.sayName() // undefined
```

上面代码说明引用类型可以拥有属性和方法，并且是可以动态改变的。

### 引用类型的值是同时保存在栈内存和堆内存中的对象

javascript 和其他语言不同，其不允许直接访问内存中的位置，也就是说不能直接操作对象的内存空间，那我们操作啥呢？ 实际上，是操作对象的引用，

所以引用类型的值是按引用访问的。

准确地说，引用类型的存储需要内存的栈区和堆区（堆区是指内存里的堆内存）共同完成，栈区内存保存变量标识符和指向堆内存中该对象的指针，

也可以说是该对象在堆内存的地址。

假如有以下几个对象：

```js
var person1 = { name: "jozo" }
var person2 = { name: "xiaom" }
var person3 = { name: "xiaoq" }
```

则这三个对象的在内存中保存的情况如下图：

![img](https://cdn.jsdelivr.net/gh/aimeiyijia/blog-images/img/javascript/引用类型存储结构.png)

### 引用类型的比较是引用的比较

```js
var person1 = "{}"
var person2 = "{}"
console.log(person1 == person2) // true
```

上面讲基本类型的比较的时候提到了当两个比较值的类型相同的时候，相当于是用 === ，所以输出是 true 了。再看看：

```js
var person1 = {}
var person2 = {}
console.log(person1 == person2) // false
```

可能你已经看出破绽了，上面比较的是两个字符串，而下面比较的是两个对象，为什么长的一模一样的对象就不相等了呢？

别忘了，引用类型时按引用访问的，换句话说就是比较两个对象的堆内存中的地址是否相同，那很明显，person1 和 person2 在堆内存中地址是不同的：

![img](https://cdn.jsdelivr.net/gh/aimeiyijia/blog-images/img/javascript/引用类型比较.png)

所以这两个是完全不同的对象，所以返回 false;

### 引用类型赋值是'赋值对象地址'

当从一个变量向另一个变量赋值引用类型的值时，同样也会将存储在变量中的对象的值复制一份放到为新变量分配的空间中。前面讲引用类型的时候提到，

保存在变量中的是对象在堆内存中的地址，所以，与简单赋值不同，这个值的副本实际上是一个指针，而这个指针指向存储在堆内存的一个对象。那么赋值操作后，

两个变量都保存了同一个对象地址，则这两个变量指向了同一个对象。因此，改变其中任何一个变量，都会相互影响：

```js
var a = {} // a保存了一个空对象的实例
var b = a // a和b都指向了这个空对象

a.name = "jozo"
console.log(a.name) // 'jozo'
console.log(b.name) // 'jozo'

b.age = 22
console.log(b.age) // 22
console.log(a.age) // 22

console.log(a == b) // true
```

它们的关系如下图：

![img](https://cdn.jsdelivr.net/gh/aimeiyijia/blog-images/img/javascript/引用类型赋值.png)

因此，引用类型的赋值其实是对象保存在栈区地址指针的赋值，因此两个变量指向同一个对象，任何的操作都会相互影响。

## 传递参数时的区别

在 js 中，参数传递只有一种规则：'按值传递'，基于值的复制。原始类型复制的是值本身，所以这两份数据互不影响；引用类型复制的是引用值，所以形参和实参指向同一个对象，通过一个引用修改了对象，那么通过另外一个引用访问的对象就是修改后的对象。

```javascript
function abc(num) {
  num += 1
  return num
}
var i = 5
var result = abc(i)
console.log(i) // 5
console.log(result) // 6
```

看上面 demo 可以看出 参数传参（原始类型） 是值传递.。

```javascript
function hello(obj) {
  obj.name = "lucy"
  return obj
}
var person = new Object()
person.name = "lili"
var newPerson = hello(person)
console.log(hello.name) // lucy
console.log(newPerson.name) // lucy
```

上面 demo 可以看出 参数传参好像是引用传递。但是实际是传递了“指针”这个值。下面 demo 可以看出这一点。

```javascript
function hello(obj) {
  obj.name = "lucy"
  obj = new Object() // 新赋值了一个地址
  obj.name = "lili"
  return obj
}

var person = new Object()
person.name = "jon"
var newPerson = hello(person)
console.log(person.name) // lucy
console.log(newPerson.name) // lili
```

当我把 person 传进去的时候，实际是传递了“指针”(就是它的内存地址)这个值 ，并不是 person 本身。那么传进 hello 函数是 person 和 obj 拥有相同内存地址，因此改变了 obj,name 的值就是改变了 person.name 的值。当 obj 赋于一个新的内存地址的时候 ，obj 的内存地址就和 person 的内存地址不是同一个了，因此改变了 obj,name 的时候 person,name 是不会改变的。
