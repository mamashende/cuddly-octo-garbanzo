TypeScript 是 JavaScript 的超集
TypeScript 最大的特点就是引入了类型系统，这样就可以在编译为 JavaScript 代码之前由编译器进行类型检查。
https://www.typescriptlang.org/zh/docs/handbook/typescript-in-5-minutes.html

### 支持类型标注
```ts

let sast_yyds: boolean = true;

any

let aws : any = 114514;

```
`any` 类型是目前 TypeScript 语言之中具有较大争议的一个设计，因为理论上我们可以将所有的变量声明为 `any` 从而绕过类型检查，这个时候 TypeScript 实际上退化为 JavaScript。

但是考虑到目前 Web 前端项目会引用大量的第三方库，开发者很多时候无法完全把握某些变量的信息，所以 `any` 类型是必要的。不过我们需要注意其使用，对于能够给定类型的变量则尽量不标记为 `any`。

### 支持联合类型

```ts
type All = number | string | boolean;

```

### 泛型

```typescript
type StringArray = Array<string>;  
type NumberArray = Array<number>;  
type ObjectWithNameArray = Array<{ name: string }>;   

```


#### 自定义泛型

```ts
interface Backpack<Type> {

add: (obj: Type) => void;

get: () => Type;

}

// 这一行是一个简写，可以告诉 TypeScript 有一个常量，叫做`backpack`，并且不用担心它是从哪

// 里来的。

declare const backpack: Backpack<string>;

// 对象是一个字符串，因为我们在上面声明了它作为 Backpack 的变量部分。

const object = backpack.get();

// 因为 backpack 变量是一个字符串，不能将数字传递给 add 函数。

backpack.add(23);
```


### 结构化的类型系统

TypeScript 的一个核心原则是类型检查基于对象的属性和行为（type checking focuses on the _shape_ that values have）。这有时被叫做“鸭子类型”或“结构类型”（structural typing）。

在结构化的类型系统当中，如果两个对象具有相同的结构，则认为它们是相同类型的。无论这个对象是否申明为某个类型名称

类和对象确定结构的方式没有区别：
```ts
interface Point {

x: number;

y: number;

}

function logPoint(p: Point) {

console.log(`${p.x}, ${p.y}`);

}

// ---分割线---

class VirtualPoint {

x: number;

y: number;

constructor(x: number, y: number) {

this.x = x;

this.y = y;

}

}

const newVPoint = new VirtualPoint(13, 56);

logPoint(newVPoint); // 此处实现了处理Point对象的方法去处理VirtualPoint对象，可见被视为同一类型，实现打印 "13, 56"
```
如果对象或类具有所有必需的属性，则 TypeScript 将表示是它们匹配的，而不关注其实现细节。