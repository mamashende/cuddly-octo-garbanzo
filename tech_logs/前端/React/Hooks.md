## hook是什么？

大概就是一种等待对应事件发生并给出相应的操作的东西
就像在钓鱼，鱼上钩了，就会触发

在数据库中有名叫“触发器”的组件，大概实现的功能相似


在react框架中内置的hook
//可以自定义hook

在 React 中，`useState` 以及任何其他以“`use`”开头的函数都被称为 **Hook**。

Hook 是特殊的函数，只在 React [渲染](https://zh-hans.react.dev/learn/render-and-commit#step-1-trigger-a-render)时有效
# 最常用的两种hook
## State Hook
https://zh-hans.react.dev/reference/react/useState
状态帮助组件 [“记住”用户输入的信息](https://zh-hans.react.dev/learn/state-a-components-memory)。例如，一个表单组件可以使用状态存储输入值，而一个图像库组件可以使用状态存储所选的图像索引。

## Effect Hook

https://zh-hans.react.dev/reference/react/useEffect
Effect 允许组件 [连接到外部系统并与之同步](https://zh-hans.react.dev/learn/synchronizing-with-effects)。这包括处理网络、浏览器、DOM、动画、使用不同 UI 库编写的小部件以及其他非 React 代码。
用于处理非渲染任务，主要是网络请求





## 用法 [](https://zh-hans.react.dev/reference/react/useEffect#usage "Link for 用法")

### 连接到外部系统 [](https://zh-hans.react.dev/reference/react/useEffect#connecting-to-an-external-system "Link for 连接到外部系统")

有些组件需要与网络、某些浏览器 API 或第三方库保持连接，当它们显示在页面上时。这些系统不受 React 控制，所以称为外部系统。

要 [将组件连接到某个外部系统](https://zh-hans.react.dev/learn/synchronizing-with-effects)，请在组件的顶层调用 `useEffect`：


```ts
import { useEffect } from 'react';
import { createConnection } from './chat.js';

function ChatRoom({ roomId }) {
  const [serverUrl, setServerUrl] = useState('https://localhost:1234');

  useEffect(() => {
  	const connection = createConnection(serverUrl, roomId);
    connection.connect();
  	return () => {
      connection.disconnect();
  	};
  }, [serverUrl, roomId]);
  // ...
}
```


你需要向 `useEffect` 传递两个参数：

1. 一个 **setup 函数** ，其 setup 代码 用来连接到该系统。
    - 它应该返回一个 **清理函数**（cleanup），其 cleanup 代码 用来与该系统断开连接。
2. 一个 依赖项列表，包括这些函数使用的每个组件内的值。

**React 在必要时会调用 setup 和 cleanup，这可能会发生多次**：

1. 将组件挂载到页面时，将运行 setup 代码。
2. 重新渲染 依赖项 变更的组件后：
    - 首先，使用旧的 props 和 state 运行 cleanup 代码。
    - 然后，使用新的 props 和 state 运行 setup 代码。
3. 当组件从页面卸载后，cleanup 代码 将运行最后一次。



### Effect与事件处理的区别
https://zh-hans.react.dev/learn/separating-events-from-effects

事件处理函数只有在你再次执行同样的交互时才会重新运行。Effect 和事件处理函数不一样，它只有在读取的 props 或 state 值和上一次渲染不一样时才会重新同步。


### 事件处理函数只在响应特定的交互操作时运行 

### 每当需要同步，Effect 就会运行
