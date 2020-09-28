## 1、const 命令

```
基本用法
const声明一个只读的常量。一旦声明，常量的值就不能改变。
const a = 3.1415;
console.log(a) // 3.1415
a = 3;
// TypeError: Assignment to constant variable.
上面代码表明改变常量的值会报错。
const声明的变量不得改变值，这意味着，const一旦声明变量，就必须立即初始化，不能留到以后赋值。

const foo;
// SyntaxError: Missing initializer in const declaration
上面代码表示，对于const来说，只声明不赋值，就会报错。

const的作用域与let命令相同：只在声明所在的块级作用域内有效。

if (true) {
  const MAX = 5;
}

MAX // Uncaught ReferenceError: MAX is not defined
```
