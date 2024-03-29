---
title: TypeScript-函数定义
comments: false
abbrlink: 155208f2
date: 2023-03-25 22:03:34
tags:
categories:
keywords:
description:
top_img:
cover:
---

## 函数

### 函数声明式

#### 常用定义方法

```typescript
function say(person: string, content: string): boolean {
  if (person === "" || content === "") return false
  console.log(`${person}say:${content}`)
  return true
}
```

#### 泛型函数

泛型的使用为了方便复用函数——复用不同类型输入，但是行为和操作逻辑一致的函数。

```typescript
function say<T>(operate: T, person: string, content: string): boolean {
  if (person === "" || content === "") return false
  console.log(`${person} ${operate}:${content}`)
  return true
}
```

### 函数表达式

#### 常用

```typescript
const say = function (person: string, content: string): boolean {
  if (person === "" || content === "") return false
  console.log(`${person}say:${content}`)
  return true
}
```

#### 泛型

```typescript
const say = function <T>(person: string, content: string, operate: T): boolean {
  if (person === "" || content === "") return false
  console.log(`${person}${operate}:${content}`)
  return true
}
```

#### 利用 type 声明函数

```typescript
type sayType = (person: string, content: string) => boolean
var say: sayType = function (person, content) {
  if (person === "" || content === "") return false
  console.log(`${person}say:${content}`)
  return true
}
```

#### type 声明加泛型

```typescript
type sayType = <T>(operate: T, person: string, content: string) => boolean
var say: sayType = function (operate, person, content) {
  if (person === "" || content === "") return false
  console.log(`${person} ${operate}:${content}`)
  return true
}
```

#### 利用接口

```typescript
interface Say {
  (person: string, content: string): boolean
}
const say: Say = function (person, content) {
  if (person === "" || content === "") return false
  console.log(`${person}say:${content}`)
  return true
}
```

#### 泛型加接口

```typescript
type sayWhileSimiling = "gegege" | "hhhh"
interface Say<T> {
  (operate: T, person: string, content: string): boolean
}
const say: Say<sayWhileSimiling> = function (operate, person, content) {
  if (person === "" || content === "") return false
  console.log(`${person}${operate}:${content}`)
  return true
}
```

```typescript
interface Say {
  <T>(operate: T, person: string, content: string): boolean
}
const say: Say = function (operate, person, content) {
  if (person === "" || content === "") return false
  console.log(`${person}${operate}:${content}`)
  return true
}
```

### 箭头函数

#### 常用

```typescript
const say = (person: string, content: string): boolean => {
  if (person === "" || content === "") return false
  console.log(`${person}say:${content}`)
  return true
}
```

#### 泛型

```typescript
const say = <T>(operate: T, person: string, content: string): boolean => {
  if (person === "" || content === "") return false
  console.log(`${person}${operate}:${content}`)
  return true
}
```

### js 函数参数的三种用法的 ts 实现

#### 可选参数

```typescript
// 需求: 要求定义一个函数可以实现2个数或者3个数的加法

function add(x: number, y: number, z?: number): number {
  return x + y + (z ? z : 0)
}

let res = add(10, 20)

let res = add(10, 20, 30)
```

{% note warning no-icon %}

可选参数可以是一个或多个

```typescript
function add(x: number, y?: number, z?: number): number {}
```

可选参数后面只能跟可选参数

```typescript
function add(x: number, y?: number, z: number): number {} //报错
```

{% endnote %}

#### 默认参数

```typescript
function add(x: number, y: number = 10): number {
  return x + y
}

let res = add(10)

let res = add(10, 30)
```

#### 剩余参数

```typescript
function add(x: number, ...ags: number[]) {
  console.log(x)

  console.log(ags)
}

add(10, 20, 30, 40, 50)
```
