## **TypeScript:**

**_TypeScript 中文网： https://www.tslang.cn
TypeScript 入门教程：https://ts.xcatliu.com/introduction/what-is-typescript.html_**
![](https://imgkr2.cn-bj.ufileos.com/8bc029f2-abe4-4582-a2fc-e60c47cfd526.png?UCloudPublicKey=TOKEN_8d8b72be-579a-4e83-bfd0-5f6ce1546f13&Signature=0RTEv094RL7bFCpPytABn%252BaAEKA%253D&Expires=1597565240)

\*图片摘自于 https://juejin.im/post/6844904182843965453#heading-0

## **TypeScript 是什么:**

```
// 根据官网翻译成中文是：
// TypeScript 是 JavaScript 的类型的超集，它可以编译成纯 JavaScript。编译出来的 JavaScript 可以运行在任何浏览器上。TypeScript 编译工具可以运行在任何服务器和任何系统上。TypeScript 是开源的。
```

## **为什么选择 TypeScript:**

```
// TypeScript 增加了代码的可读性和可维护性
// 类型系统实际上是最好的文档，大部分的函数看看类型的定义就可以知道如何使用了
// 可以在编译阶段就发现大部分错误，这总比在运行时候出错好
// 增强了编辑器和 IDE 的功能，包括代码补全、接口提示、跳转到定义、代码重构等

// TypeScript 非常包容
// TypeScript 是 JavaScript 的超集，.js 文件可以直接重命名为 .ts 即可
// 即使不显式的定义类型，也能够自动做出类型推论

// TypeScript 的类型系统是图灵完备的，可以定义从简单到复杂的几乎一切类型
// 即使 TypeScript 编译报错，也可以生成 JavaScript 文件

// 兼容第三方库，即使第三方库不是用 TypeScript 写的，也可以编写单独的类型文件供 TypeScript 读取
// TypeScript 拥有活跃的社区

// 大部分第三方库都有提供给 TypeScript 的类型定义文件

// Angular、Vue、VS Code、Ant Design 等等耳熟能详的项目都是使用 TypeScript 编写的

// TypeScript 拥抱了 ES6 规范，支持 ESNext 草案中处于第三阶状态（Stage 3）的特性

// *TypeScript 的缺点:
// 任何事物都是有两面性的，我认为 TypeScript 的弊端在于：
// 有一定的学习成本，需要理解接口（Interfaces）、泛型（Generics）、类（Classes）、枚举类型（Enums）等前端  工程师可能不是很熟悉的概念
// 短期可能会增加一些开发成本， 毕竟要多写一些类型的定义，不过对于一个需要长期维护的项目，TypeScript 能够减少其维护成本
// 集成到构建流程需要一些工作量
// 可能和一些库结合的不是很完美

                                                      ---   内容摘自https://ts.xcatliu.com/introduction/what-is-typescript.html
```

## **安装 TypeScrip:**

```
// TypeScript 的命令行工具安装方法如下：
npm install -g typescript

// 以上命令会在全局环境下安装 tsc 命令，安装完成之后，我们就可以在任何地方执行 tsc 命令了。

// 查看 TypeScript 的版本信息：
tsc -v
```

## **编译 TypeScript:**

```
// 编译一个 TypeScript 文件很简单：
// 新建 一个ts文件（例如:index.ts，将代码复制到此文件中）:
function sayHello(person: string) {
// 在 TypeScript 中，我们使用 : 指定变量的类型，: 的前后有没有空格都可以。
    return 'Hello, ' + person;
}
let user = 'Tom';
console.log(sayHello(user));

// 然后运行命令：tsc index.ts: 这时候会生成一个编译好的文件 index.js：
function sayHello(person) {
    return 'Hello, ' + person;
}
var user = 'Tom';
console.log(sayHello(user));

// 我们约定使用 TypeScript 编写的文件以 .ts 为后缀，用 TypeScript 编写 React 时，以 .tsx 为后缀。
```

![](https://imgkr2.cn-bj.ufileos.com/aa88b1c1-4e60-46f8-b9cd-3a2131998d46.png?UCloudPublicKey=TOKEN_8d8b72be-579a-4e83-bfd0-5f6ce1546f13&Signature=n0HM67GHE0UkgZoJi52F9FFwJBs%253D&Expires=1597569865)

```
// 上述例子中，我们用 : 指定 person 参数类型为 string。但是编译为 js 之后，并没有什么检查的代码被插入进来。

// 这是因为 TypeScript 只会在编译时对类型进行静态检查，如果发现有错误，编译的时候就会报错。而在运行时，与普通的 JavaScript 文件一样，不会对类型进行检查。

// 如果我们需要保证运行时的参数类型，还是得手动对类型进行判断：
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
// 在 TypeScript 中，可以使用 null 和 undefined 来定义这两个原始数据类型：
let u: undefined = undefined;
let n: null = null;
// 与void的区别是，undefined 和 null 是所有类型的子类型，也就是说 undefined 类型的变量，可以赋值给 number类型的变量
// 这样不会报错
let num:number = undefined;
// 这样也不会报错
let u: undefined;
let num:number = u;

// 而 void 类型的变量不能赋值给 number 类型的变量：
let u: void;
let num: number = u;

// Type 'void' is not assignable to type 'number'

// 空值
JavaScript 没有空值（Void）的概念，在 TypeScript 中，可以用 void 表示没有任何返回值的函数：
function alertName(): void {
    alert('My name is Tom');
}
// 声明一个 void 类型的变量没有什么用，因为你只能将它赋值为 undefined 和 null：
let unusable: void = undefined;
```

## **TypeScript 任意值:**

```
// 任意值（Any）用来表示允许赋值为任意类型。
let myFavoriteNumber: any = 'seven';
myFavoriteNumber = 7;

// 如果是一个普通类型，在赋值过程中改变类型是不被允许的：
let myFavoriteNumber:string = "seven";
myFavoriteNumber = 8
// index.ts(2,1): error TS2322: Type 'number' is not assignable to type 'string'

// 任意值的属性和方法 在任意值上访问任何属性都是允许的：
let anyThing:any = "hello";
console.log(anyThing.myName)

// 也允许调用任何方法：
let anyThing:any = "MrBai"
anyThing.setName('Jerry')
anyThing.setName('Jerry').sayHello();
anyThing.myName.setFirstName('Cat');
// 可以认为，声明一个变量为任意值之后，对它的任何操作，返回的内容的类型都是任意值。

// 未声明类型的变量:变量如果在声明的时候，未指定其类型，那么它会被识别为任意值类型：
let something;
something = "MrBai";
something = 8
something.setName("Cherry")
等价于
let something:any;
something = "MrBai";
something = 9;
something.setName("Cherry")
```

## **类型推论:**

// 如果没有明确的指定类型，那么 TypeScript 会依照类型推论（Type Inference）的规则推断出一个类型。

```
// 以下代码虽然没有指定类型，但是会在编译的时候报错：
let myFavoriteNumber = 'Cherry';
myFavoriteNumber = 8;
// index.ts(2,1): error TS2322: Type 'number' is not assignable to type 'string'.

// 事实上，它等价于：
let myFavoriteNumber: string = 'Cherry';
myFavoriteNumber = 8;
// index.ts(2,1): error TS2322: Type 'number' is not assignable to type 'string'.

// TypeScript 会在没有明确的指定类型的时候推测出一个类型，这就是类型推论。

// 如果定义的时候没有赋值，不管之后有没有赋值，都会被推断成 any 类型而完全不被类型检查：
let myFavoriteNumber;
myFavoriteNumber = 'Cherry';
myFavoriteNumber = 7;
```

## **联合类型:**

联合类型（Union Types）表示取值可以为多种类型中的一种。

```
// 联合类型使用 | 分隔每个类型。
// 这里的 let myFavoriteNumber: string | number 的含义是，允许 myFavoriteNumber 的类型是 string 或者 number，但是不能是其他类型。
let myFavoriteNumber: string | number;
myFavoriteNumber = 'Cherry';
myFavoriteNumber = 8;

myFavoriteNumber = tue;   // 报错
// index.ts(2,1): error TS2322: Type 'boolean' is not assignable to type 'string | number'.
// Type 'boolean' is not assignable to type 'number'.

// 访问联合类型的属性或方法
// 当 TypeScript 不确定一个联合类型的变量到底是哪个类型的时候，我们只能访问此联合类型的所有类型里共有的属性或方法：
function getLength(something:string | number):number{
    return something.length;
}
// index.ts(2,22): error TS2339: Property 'length' does not exist on type 'string | number'.
// Property 'length' does not exist on type 'number'.
// 上例中，length 不是 string 和 number 的共有属性，所以会报错。

// 访问 string 和 number 的共有属性是没问题的：
function getString(something:string | number):string{
     return something.toString()
}
// 联合类型的变量在被赋值的时候，会根据类型推论的规则推断出一个类型：
let myFavoriteNumber: string | number;
myFavoriteNumber = 'cherry';
console.log(myFavoriteNumber.length); // 6
myFavoriteNumber = 8;
console.log(myFavoriteNumber.length); // 编译时报错
// index.ts(5,30): error TS2339: Property 'length' does not exist on type 'number'.
// 上例中，第二行的 myFavoriteNumber 被推断成了 string，访问它的 length 属性不会报错。
// 而第四行的 myFavoriteNumber 被推断成了 number，访问它的 length 属性时就报错了。
```

## **对象的类型——接口:**

在 TypeScript 中，我们使用接口（Interfaces）来定义对象的类型。

```
什么是接口:
// 在面向对象语言中，接口（Interfaces）是一个很重要的概念，它是对行为的抽象，而具体如何行动需要由类（classes）去实现（implement）。

TypeScript 中的接口是一个非常灵活的概念，除了可用于对类的一部分行为进行抽象以外，也常用于对「对象的形状（Shape）」进行描述。

// 简单的例子:
interface Person {
    name: string;
    age: number;
};
let tom: Person = {
    name: 'Tom',
    age: 25
};
上面的例子中，我们定义了一个接口 Person，接着定义了一个变量 tom，它的类型是 Person。这样，我们就约束了 tom 的形状必须和接口 Person 一致。

接口一般首字母大写。有的编程语言中会建议接口的名称加上 I 前缀。

定义的变量比接口少了一些属性是不允许的：
interface Person {
    name: string;
    age: number;
};
let tom: Person = {
    name: 'Tom'
};
// index.ts(6,5): error TS2322: Type '{ name: string; }' is not assignable to type 'Person'.
//   Property 'age' is missing in type '{ name: string; }'.

多一些属性也是不允许的：
interface Person {
    name: string;
    age: number;
};
let tom: Person = {
    name: 'Tom',
    age: 25,
    gender: 'male'
};
// index.ts(9,5): error TS2322: Type '{ name: string; age: number; gender: string; }' is not assignable to type 'Person'.
//   Object literal may only specify known properties, and 'gender' does not exist in type 'Person'.
```

**可见，赋值的时候，变量的形状必须和接口的形状保持一致。**

```
可选属性:有时我们希望不要完全匹配一个形状，那么可以用可选属性：
interface Person{
    name:string;
    age?:number
};
let tom: Person = {
    name: 'Tom'
};
interface Person {
    name: string;
    age?: number;
}
let tom: Person = {
    name: 'Tom',
    age: 25
};
可选属性的含义是该属性可以不存在。
这时仍然不允许添加未定义的属性：

interface Person {
    name: string;
    age?: number;
}

let tom: Person = {
    name: 'Tom',
    age: 25,
    gender: 'male'
};

// examples/playground/index.ts(9,5): error TS2322: Type '{ name: string; age: number; gender: string; }' is not assignable to type 'Person'.
//   Object literal may only specify known properties, and 'gender' does not exist in type 'Person'.
````
````
任意属性:有时候我们希望一个接口允许有任意的属性，可以使用如下方式：
interface Person {
    name:string;
    age?:number;
    [propName:string]:any;
};
let tom: Person = {
    name: 'Tom',
    gender: 'male'
};
使用 [propName: string] 定义了任意属性取 string 类型的值。

一个接口中只能定义一个任意属性。如果接口中有多个类型的属性，则可以在任意属性中使用联合类型：
interface Person {
    name: string;
    age?: number;
    [propName: string]: string | number;
};
let tom: Person = {
    name: 'Tom',
    age: 25,
    gender: 'male'
};
````
**需要注意的是，一旦定义了任意属性，那么确定属性和可选属性的类型都必须是它的类型的子集：**
````
interface Person {
    name: string;
    age?: number;
    [propName: string]: string;
};
let tom: Person = {
    name: 'Tom',
    age: 25,
    gender: 'male'
};
// index.ts(3,5): error TS2411: Property 'age' of type 'number' is not assignable to string index type 'string'.
// index.ts(7,5): error TS2322: Type '{ [x: string]: string | number; name: string; age: number; gender: string; }' is not assignable to type 'Person'.
//   Index signatures are incompatible.
//     Type 'string | number' is not assignable to type 'string'.
//       Type 'number' is not assignable to type 'string'.

上例中，任意属性的值允许是 string，但是可选属性 age 的值却是 number，number 不是 string 的子属性，所以报错了。
另外，在报错信息中可以看出，此时 { name: 'Tom', age: 25, gender: 'male' } 的类型被推断成了 { [x: string]: string | number; name: string; age: number; gender: string; }，这是联合类型和接口的结合。
````
**只读属性:有时候我们希望对象中的一些字段只能在创建的时候被赋值，那么可以用 readonly 定义只读属性：**
````
interface Person {
    readonly id: number;
    name: string;
    age?: number;
    [propName: string]: any;
};
let tom: Person = {
    id: 89757,
    name: 'Tom',
    gender: 'male'
};
tom.id = 9527;
// index.ts(14,5): error TS2540: Cannot assign to 'id' because it is a constant or a read-only property.
上例中，使用 readonly 定义的属性 id 初始化后，又被赋值了，所以报错了。

注意，只读的约束存在于第一次给对象赋值的时候，而不是第一次给只读属性赋值的时候：

interface Person {
    readonly id: number;
    name: string;
    age?: number;
    [propName: string]: any;
}

let tom: Person = {
    name: 'Tom',
    gender: 'male'
};

tom.id = 89757;

// index.ts(8,5): error TS2322: Type '{ name: string; gender: string; }' is not assignable to type 'Person'.
//   Property 'id' is missing in type '{ name: string; gender: string; }'.
// index.ts(13,5): error TS2540: Cannot assign to 'id' because it is a constant or a read-only property.
上例中，报错信息有两处，第一处是在对 tom 进行赋值的时候，没有给 id 赋值。
第二处是在给 tom.id 赋值的时候，由于它是只读属性，所以报错了。
````
