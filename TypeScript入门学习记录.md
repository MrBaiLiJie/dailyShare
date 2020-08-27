## **TypeScript:**

**_TypeScript 中文网： https://www.tslang.cn
TypeScript 入门教程：https://ts.xcatliu.com/introduction/what-is-typescript.html_**
![](https://imgkr2.cn-bj.ufileos.com/8bc029f2-abe4-4582-a2fc-e60c47cfd526.png?UCloudPublicKey=TOKEN_8d8b72be-579a-4e83-bfd0-5f6ce1546f13&Signature=0RTEv094RL7bFCpPytABn%252BaAEKA%253D&Expires=1597565240)

\*图片摘自于 https://juejin.im/post/6844904182843965453#heading-0

## **TypeScript 是什么:**

```
根据官网翻译成中文是：
TypeScript 是 JavaScript 的类型的超集，它可以编译成纯 JavaScript。编译出来的 JavaScript 可以运行在任何浏览器上。TypeScript 编译工具可以运行在任何服务器和任何系统上。TypeScript 是开源的。
```

## **为什么选择 TypeScript:**

```
TypeScript 增加了代码的可读性和可维护性§
类型系统实际上是最好的文档，大部分的函数看看类型的定义就可以知道如何使用了
可以在编译阶段就发现大部分错误，这总比在运行时候出错好
增强了编辑器和 IDE 的功能，包括代码补全、接口提示、跳转到定义、代码重构等

TypeScript 非常包容§

TypeScript 是 JavaScript 的超集，.js 文件可以直接重命名为 .ts 即可
即使不显式的定义类型，也能够自动做出类型推论

TypeScript 的类型系统是图灵完备的，可以定义从简单到复杂的几乎一切类型
即使 TypeScript 编译报错，也可以生成 JavaScript 文件

兼容第三方库，即使第三方库不是用 TypeScript 写的，也可以编写单独的类型文件供 TypeScript 读取
TypeScript 拥有活跃的社区§

大部分第三方库都有提供给 TypeScript 的类型定义文件

Angular、Vue、VS Code、Ant Design 等等耳熟能详的项目都是使用 TypeScript 编写的

TypeScript 拥抱了 ES6 规范，支持 ESNext 草案中处于第三阶状态（Stage 3）的特性

TypeScript 的缺点§

任何事物都是有两面性的，我认为 TypeScript 的弊端在于：
有一定的学习成本，需要理解接口（Interfaces）、泛型（Generics）、类（Classes）、枚举类型（Enums）等前端工程师可能不是很熟悉的概念
短期可能会增加一些开发成本，毕竟要多写一些类型的定义，不过对于一个需要长期维护的项目，TypeScript 能够减少其维护成本
集成到构建流程需要一些工作量
可能和一些库结合的不是很完美

                                                      ---   内容摘自https://ts.xcatliu.com/introduction/what-is-typescript.html
```

## **安装 TypeScrip:**

```
TypeScript 的命令行工具安装方法如下：

npm install -g typescript
以上命令会在全局环境下安装 tsc 命令，安装完成之后，我们就可以在任何地方执行 tsc 命令了。

查看 TypeScript 的版本信息：
tsc -v
```

## **编译 TypeScript:**

```
编译一个 TypeScript 文件很简单：
新建 一个ts文件（例如:index.ts，将代码复制到此文件中）:
function sayHello(person: string) {  // 在 TypeScript 中，我们使用 : 指定变量的类型，: 的前后有没有空格都可以。
    return 'Hello, ' + person;
}
let user = 'Tom';
console.log(sayHello(user));

然后运行命令：tsc index.ts
这时候会生成一个编译好的文件 index.js：
function sayHello(person) {
    return 'Hello, ' + person;
}
var user = 'Tom';
console.log(sayHello(user));

我们约定使用 TypeScript 编写的文件以 .ts 为后缀，用 TypeScript 编写 React 时，以 .tsx 为后缀。
```

![](https://imgkr2.cn-bj.ufileos.com/aa88b1c1-4e60-46f8-b9cd-3a2131998d46.png?UCloudPublicKey=TOKEN_8d8b72be-579a-4e83-bfd0-5f6ce1546f13&Signature=n0HM67GHE0UkgZoJi52F9FFwJBs%253D&Expires=1597569865)

```
上述例子中，我们用 : 指定 person 参数类型为 string。但是编译为 js 之后，并没有什么检查的代码被插入进来。

这是因为 TypeScript 只会在编译时对类型进行静态检查，如果发现有错误，编译的时候就会报错。而在运行时，与普通的 JavaScript 文件一样，不会对类型进行检查。

如果我们需要保证运行时的参数类型，还是得手动对类型进行判断：
function sayHello(person: string) {
    if (typeof person === 'string') {
        return 'Hello, ' + person;
    } else {
        throw new Error('person is not a string');
    }
}

let user = 'Tom';
console.log(sayHello(user));
```

## **TypeScript 基础类型:**

```
// Boolean 类型
let isDone: boolean = false;
// ES5：var isDone = false;
// Number 类型
let count: number = 10;
// ES5：var count = 10;
// String 类型
let count: string = 'MrBai';
// ES5：var count = 'MrBai';
// Array 类型
let list: number[] = [1, 2, 3];
// ES5：var list = [1,2,3];
let list: Array<number> = [1, 2, 3]; // Array<number>泛型语法
// ES5：var list = [1,2,3];
// Null 和 Undefined
在 TypeScript 中，可以使用 null 和 undefined 来定义这两个原始数据类型：
let u: undefined = undefined;
let n: null = null;
```
