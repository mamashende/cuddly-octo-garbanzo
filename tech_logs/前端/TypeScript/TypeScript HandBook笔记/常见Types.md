## 基本类型：`string`，`number`，和 `boolean`


## Arrays
you can use the syntax `number[]`，`string[]` is an array of strings, and so on.also written as `Array<number>`

Note that `[number]` is a different thing; refer to the section on _tuple types_.

```ts
let num: number[];
let str: string[];

const names: Array<string>;
```


## any
When a value is of type `any`, you can access any properties of it (which will in turn be of type `any`), call it like a function, assign it to (or from) a value of any type, or pretty much anything else that’s syntactically legal:

```ts
let obj: any = { x: 0 };

// None of the following lines of code will throw compiler errors.

// Using `any` disables all further type checking, and it is assumed

// you know the environment better than TypeScript.

obj.foo();

obj();

obj.bar = 100;

obj = "hello";

const n: number = obj;
```


### `noImplicitAny`

When you don’t specify a type, and TypeScript can’t infer it from context, the compiler will typically default to `any`.

You usually want to avoid this, though, because `any` isn’t type-checked. Use the compiler flag [`noImplicitAny`](https://www.typescriptlang.org/tsconfig#noImplicitAny) to flag any implicit `any` as an error.


## Type Annotations on Variables

```ts
let myName: string = "Alice";
let myName = "Alice";
```

类型注解需要在变量前加冒号':'
## Functions


### Parameter Type Annotations


```ts
// Parameter type annotation

function greet(name: string) {

console.log("Hello, " + name.toUpperCase() + "!!");

}
```

Even if you don’t have type annotations on your parameters, TypeScript will still check that you passed the right number of arguments.

### Return Type Annotations

```ts
function getFavoriteNumber(): number {

return 26;

}
```


### Anonymous Functions
匿名函数


### Object Types

### Union Types

### 类型别名
```ts
type ID = number | string;
```

### 接口

_接口声明_ 是命名对象类型的另一种方式：
```ts
interface Point {

x: number;

y: number;

}

function printCoord(pt: Point) {

console.log("The coordinate's x value is " + pt.x);

console.log("The coordinate's y value is " + pt.y);

}

printCoord({ x: 100, y: 100 });
```

 TypeScript 只关心我们传递给 `printCoord` 的值的结构 - 它只关心它是否具有预期的属性。 只关心类型的结构和功能，这就是为什么我们说 TypeScript 是一个 _结构化类型_ 的类型系统。

#### 类型别名和接口之间的区别

类型别名和接口非常相似，在大多数情况下你可以在它们之间自由选择。 几乎所有的 `interface` 功能都可以在 `type` 中使用，关键区别在于不能重新开放类型以添加新的属性，而接口始终是可扩展的。