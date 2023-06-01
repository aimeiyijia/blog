---
title: javascript-模块规范及实现
comments: false
abbrlink: 9c4c10b
date: 2023-05-31 11:00:44
tags:
categories:
keywords:
description:
top_img:
cover:
---

## script 标签

普通版：一个 js 文件就是一个模块，没有独立作用域，模块之间互相影响

升级版：使用一个立即执行的函数，将 js 代码单独包裹在一个文件里面，然后通过 script 标签将其进行引入，这样就能使得各自文件的 js 代码在各自的局部作用域执行，避免相互影响。

#### 立即执行函数

立即执行函数（Immediately Invoked Function Expression，IIFE）是一种常见的 JavaScript 设计模式，也被称为自执行匿名函数，它可以创建一个局部作用域，并在定义后立即执行该函数。通常用于创建私有变量和方法，以及避免全局命名空间的污染。

IIFE 的语法主要由两部分组成
第一部分是一个具有词法作用域的匿名函数，并且用圆括号运算符 () 运算符闭合起来。这样不但阻止了外界访问 IIFE 中的变量，而且不会污染全局作用域。
第二部分创建了一个立即执行函数表达式 ()，通过它，JavaScript 引擎将立即执行该函数。

```
(function() {
  // 函数体
})();

(() => {
  // 函数体
})();

(async () => {
  // 函数体
})();
```

接收参数，例如：

```
(function (name) {
   console.log('我是' + name + '!');
})('刘小凡');
```

在这个示例中，我们定义了一个接受一个参数 name 的匿名函数，并在定义后立即执行该函数，并传入参数 'Alice'。执行结果会输出 'Hello, Alice!'。

IIFE 还可以返回一个值，例如：

```
var result = (function() {
  var x = 1;
  var y = 2;
  return x + y;
})();
console.log(result); // 输出 3
```

在这个示例中，我们定义了一个匿名函数，其中定义了两个变量 x 和 y，并返回它们的和。然后我们在函数定义后立即执行该函数，并将返回值赋给变量 result。执行结果会输出 3。

## Commonjs

CommonJS 是一种服务器端模块规范，它定义了模块的导入和导出方式，使得 JavaScript 代码可以在服务器端运行。它主要用于 Node.js 环境中。

在 CommonJS 规范中，每个模块都是一个单独的文件，模块内部的变量和函数都是私有的，只有通过导出才能被其他模块使用。导出可以通过 module.exports 或者 exports 对象实现，导入可以通过 require 函数实现。

#### 导入模块

```javascript
const moduleName = require("modulePath")
const { export1, export2 } = require("modulePath")
```

这里的 `moduleName` 是导入模块的默认值，`export1` 和 `export2` 是导入模块内的成员。

#### 导出模块

```javascript
module.exports = value
exports.export1 = value1
exports.export2 = value2
```

这里的 `value` 是默认导出的值，`export1` 和 `export2` 是具名导出的值。

在浏览器端使用 CommonJS 规范需要使用工具将 CommonJS 模块转换为 ESModule 模块。



#### exports 与 module.exports的区别

`exports` 对象是 `module` 对象的一个属性,在初始时 `module.exports` 和 `exports` 指向同一块内存区域

模块导出的是 `module.exports` , `exports` 只是对它的引用,在不改变`exports` 内存的情况下,修改`exports` 的值可以改变 `module.exports` 的值

## AMD

AMD（Asynchronous Module Definition）规范是另一种 JavaScript 模块化规范，它是 CommonJS 规范的一个异步模块定义的变体。与 CommonJS 不同的是，AMD 规范支持异步加载模块，这意味着模块可以在需要时动态加载，而不是在应用程序启动时一次性加载所有模块。

AMD 规范的核心思想是定义一个模块，并在需要时异步加载它。一个 AMD 模块可以通过 define 函数来定义，该函数有三个参数：模块名称、依赖模块列表和模块定义函数。在模块定义函数中，我们可以定义模块的行为，并返回一个模块对象。

#### 定义模块

```javascript
define('myModule', ['dep1', 'dep2'], function(dep1, dep2) {
  // 模块代码
  return {
    foo: function() {
      // ...
    },
    bar: function() {
      // ...
    }
  };
});
```


在这个示例中，我们定义了一个名为 myModule 的模块，它依赖于 dep1 和 dep2 两个模块。在模块定义函数中，我们可以基于 dep1 和 dep2 来实现myModule模块的功能，并返回一个包含 foo 和 bar 两个方法的模块对象。

在 AMD 规范中，使用 `require` 函数来加载模块。`require` 函数接受一个数组作为参数，该数组包含了当前模块所依赖的其他模块的路径。在加载完所有依赖的模块之后，`require` 函数会执行一个回调函数，回调函数中的参数是当前模块所依赖的其他模块的输出值，按照顺序对应数组中的路径。

#### 加载模板

```javascript
require(['module1', 'module2'], function(module1, module2) {
  // 模块加载完成后执行的代码
});
```

- `require` 函数用于加载模块。第一个参数是一个数组，包含了当前模块所依赖的其他模块的路径。第二个参数是一个回调函数，用于在所有依赖的模块加载完成之后执行。
- `module1` 和 `module2` 是当前模块所依赖的其他模块的输出值，按照顺序对应第一个参数中的路径。

需要注意的是，在 AMD 规范中，模块的加载和执行是异步的，因此需要在回调函数中处理模块的输出值。

使用 AMD 规范编写的模块可以被用于浏览器环境和 Node.js 环境。在浏览器环境中，我们可以使用 RequireJS 等加载器来加载和管理模块。在 Node.js 环境中，我们可以使用 AMD 兼容的加载器（如 curl-loader）来加载和管理模块。

## CMD

CMD（Common Module Definition）是另一种模块定义规范，与 AMD 类似，都是为了解决 JavaScript 中模块化开发的问题。CMD 规范是由国内的开发者玉伯提出并实现的，主要应用于 [Sea.js](https://github.com/seajs/seajs/issues/266) 模块加载器中。

CMD 规范与 AMD 规范的区别在于，CMD 规范是延迟执行模块代码，只有在真正使用时才会执行，而 AMD 规范是提前执行模块代码，不管是否使用都会执行。因此，CMD 规范更加适合大型的模块化项目，可以有效地降低模块之间的耦合度。

#### 定义模块

```javascript
define(function (require, exports, module) {
  // 加载依赖模块
  var $ = require("jquery")
  var util = require("./util")

  // 定义模块
  var myModule = {
    init: function () {
      // 使用依赖模块
      $("body").append("<p>" + util.formatDate(new Date()) + "</p>")
    },
  }

  // 导出模块
  module.exports = myModule
})
```

#### 加载模块

```javascript
// 加载一个模块
seajs.use("./a")

// 加载一个模块，在加载完成时，执行回调
seajs.use("./a", function (a) {
  a.doSomething()
})

// 加载多个模块，在加载完成时，执行回调
seajs.use(["./a", "./b"], function (a, b) {
  a.doSomething()
  b.doSomething()
})
```

在上面的代码中，我们使用 define 函数定义了一个模块，该模块依赖于 jQuery 和 util 模块。在模块代码中，我们使用 require 函数加载了 jQuery 和 util 模块，然后定义了一个 myModule 对象，并将其导出。

使用 CMD 规范定义模块时，需要遵循以下几点：

1. 使用 define 函数定义模块；
2. 在 define 函数中使用 require 函数加载依赖模块；
3. 在模块代码中使用 require 函数引入依赖模块；
4. 使用 exports 对象或 module.exports 导出模块。

## ESModule

ESModule 是 ECMAScript 6（ES6）中引入的一种模块规范，它也被称为 ES6 模块。与 CommonJS 相比，ESModule 更加简洁、易用和安全。在 ESModule 中，每个模块都是一个单独的文件，并且模块内部的变量和函数默认是私有的，只有通过导出才能被其他模块使用。导出可以通过 export 关键字实现，导入可以通过 import 关键字实现。ESModule 还支持动态导入，可以在运行时根据需要导入模块。ESModule 是浏览器原生支持的模块规范，也是未来 JavaScript 开发的趋势。

ESModule 是 ECMAScript 6 中引入的一种模块规范，它使用 `import` 和 `export` 关键字来导入和导出模块。下面是一些常见的 ESModule 语法：

#### 导入模块：

```javascript
import moduleName from "modulePath"
import { export1, export2 } from "modulePath"
import * as moduleAlias from "modulePath"
```

这里的 `moduleName` 是导出模块的默认值，`export1` 和 `export2` 是导出模块的具名值，`moduleAlias` 是导出模块的所有值的别名。

#### 导出模块：

```javascript
const value = 1
function export1(){}
function export2(){}
export default value
export { export1, export2 }
```

这里的 `value` 是默认导出的值，`export1` 和 `export2` 是具名导出的值。

#### 动态导入模块：

```javascript
import(modulePath).then((module) => {
  // 模块加载完成后的回调函数
})
```

这里的 `modulePath` 是需要动态导入的模块路径，`then` 方法是在模块加载完成后执行的回调函数。

以上是 ESModule 的一些基本语法，它们可以帮助你更好地管理和组织你的代码。

#### export 与 export default区别

`export` 和 `export default` 都是 ES6 中用于导出模块内容的关键字。

`export` 用于导出一个或多个变量、函数或类，可以使用大括号 `{}` 包裹多个导出项，例如：

```javascript
export const name = 'John';
export function sayHello() {
  console.log('Hello');
}
export class Person {
  constructor(name) {
    this.name = name;
  }
}
```

`export default` 用于导出一个默认的变量、函数或类，一个模块只能有一个默认导出，例如：

```javascript
const name = 'John';
function sayHello() {
  console.log('Hello');
}
class Person {
  constructor(name) {
    this.name = name;
  }
}
export default Person;
```

在导入时，使用 `import` 关键字来引入模块，可以使用大括号 `{}` 包裹多个导入项，例如：

```javascript
import { name, sayHello } from './module';
import Person from './module';
```

注意，使用 `export default` 导出的默认值，在导入时可以使用任意名称进行重命名，例如：

```javascript
import MyPerson from './module';
```

## UMD

UMD（Universal Module Definition）是一种通用的模块定义规范，可以让你的代码同时支持在浏览器和 Node.js 环境下使用。下面是一个简单的 UMD 模块示例：

```javascript
;(function (root, factory) {
  if (typeof define === "function" && define.amd) {
    // AMD. Register as an anonymous module.
    define(["jquery"], factory)
  } else if (typeof exports === "object") {
    // Node. Does not work with strict CommonJS, but
    // only CommonJS-like environments that support module.exports,
    // like Node.
    module.exports = factory(require("jquery"))
  } else {
    // Browser globals (root is window)
    root.myModule = factory(root.jQuery)
  }
})(typeof self !== "undefined" ? self : this, function ($) {
  // Use $ here...
  var myModule = {}

  // ...

  return myModule
})
```

这个 UMD 模块定义了一个名为 `myModule` 的模块，它可以在浏览器和 Node.js 环境下使用。在浏览器环境下，它会将模块暴露为全局变量 `myModule`，在 Node.js 环境下，它会将模块导出为 CommonJS 模块。

[从github umdjs/umd项目中的templates文件夹中可查看规范的不同实现](https://github.com/umdjs/umd)

具体来说，这个 UMD 模块定义包含以下几个部分：

1. 一个立即执行函数表达式，它接受两个参数：`root` 和 `factory`。`root` 表示全局对象，`factory` 表示模块的工厂函数。
2. 通过检测 `define` 和 `exports` 是否存在来判断当前环境是 AMD、CommonJS 还是浏览器环境。如果是 AMD 环境，就使用 `define` 函数来定义模块；如果是 CommonJS 环境，就使用 `module.exports` 来导出模块；否则就将模块暴露为全局变量。
3. 在模块工厂函数中，通过传入的 `$` 参数来使用 jQuery 库，并返回一个包含模块代码的对象。
