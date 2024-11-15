环境配置参考如下
https://docs.net9.org/frontend/react/prepare/


https://zh-hans.react.dev/learn

熟悉React项目的文件结构
https://www.bilibili.com/video/BV1K44y1A7vv/?buvid=XU7698479DC76FEDD68386AEE069029A71C15&from_spmid=united.player-video-detail.drama-float.0&is_story_h5=false&mid=dQ%2F2MHdeEwN7sEfnPuLi8w%3D%3D&p=1&plat_id=116&share_from=ugc&share_medium=android&share_plat=android&share_session_id=c7aa83c6-0819-43b4-b6d9-21e41bf3dfd4&share_source=QQ&share_tag=s_i&spmid=united.player-video-detail.0.0&timestamp=1725180077&unique_k=nsn4unQ&up_id=588598994&vd_source=fb42ad7665ae70e7e966d013226b0a96

讲义：
https://summer24.net9.org/frontend/react/handout/





### 组件（Component）

React 应用程序是由 **组件** 组成的。一个组件是 UI（用户界面）的一部分，它拥有自己的逻辑和外观。组件可以小到一个按钮，也可以大到整个页面。

然后react将这些组建打包成应用程序，自动化渲染进一个固定格式的html中，实现网页效果
### 属性（Props）


类似 HTML 规定标签属性语法，你可以通过通过 `props` 实现父组件对子组件的控制。具体而言，`props` 会包装成一个对象传入函数组件的参数之中。

实际上，`props` 是一个对象，它包含了组件的所有属性。


### 状态（State）
函数组件之中需要使用 Hooks，形而上地写成 `const [state, setState] = useState(initState);`，状态是组件自我管理的数据，不需要依赖父组件的控制。


需要注意的是，我们应该将组件的状态视为只读的，不能直接进行赋值，也就是不允许 mutation。在上面的例子中，`setTargetId(targetId + 1)`是正确的写法，而`targetId = targetId + 1`则是错误的写法，换言之，如果你想要改变组件状态，你需要创建一个新对象并把它传递给 state 的设置函数。

**State 是隔离且私有的**，换句话说，State 是屏幕上组件实例内部的状态，如果你渲染同一个组件两次，每个副本都会有**完全隔离的 state**，改变其中一个不会影响另一个。


State的更新不是及时的
### 副作用（Effect）
函数组件的主作用是渲染，所有其他的操作都是副作用
所有的副作用都应当写成回调函数使用 `useEffect` Hook 裹住

最常见的副作用：网络请求

副作用的依赖列表
	列表为undifined时默认每次渲染后都触发
	空置('[]')时默认在渲染第一次页面后执行依次
	依赖存在时在依赖值改变时执行


副作用的清除
### 反向数据流


### Next.js 路由

app router

采用文件系统作为路由，项目文件目录即可作为路由路径

需要编写 next.config.mjs 以设定路由的域名地址(及后端服务器/代理地址)