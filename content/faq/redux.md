本节给出 redux 的最简单的使用方式。正如 redux 的作者 [dan 所说](https://medium.com/@dan_abramov/you-might-not-need-redux-be46360cf367)。

> You can use as little, or as much of Redux, as you like.

翻译：你可以根据自己需要使用一点点或者使用很多 redux 。

### redux 基本原理

redux 是一个中心化的数据容器，涉及到三大概念：

- store ，字面意思是，数据仓库，实际中扮演 redux 心脏的作用，统一协调 redux 各部分功能
- action，字面意思是，行为。实际就是一个 js 对象，其中包括，行为类型以及相关数据。
- reducer，名字来自于数组的 reduce 方法，reducer 就是一个函数，作用是用来修改 store 中的数据。

三大概念的执行流程：

- 用户触发页面事件，从而发出 （dispatch）一个 action
- action 会被 reducer 接收到
- reducer 就会修改 store 中的数据

视频： redux-1-intro
http://digicity-1253322599.costj.myqcloud.com/redux-1-intro.mp4

### 添加评论功能

视频：redux-2-comment
http://digicity-1253322599.costj.myqcloud.com/redux-2-comment.mp4

### 添加 css

视频： redux-3-css
http://digicity-1253322599.costj.myqcloud.com/redux-3-css.mp4

### 数据存入 store

视频： redux-4-store
http://digicity-1253322599.costj.myqcloud.com/redux-4-store.mp4

### 修改 store 中的数据

流程：先要在组件中发出一个 action ，一个 action 就长成下面这样

```
{ type: 'ADD_COMMENT', text: 'hello' }
```

action 发出后，reducer 会接收到，并根据 action.type 来决定要执行 reducer 函数中的哪一部分代码，同时结合 action 中携带过来的数据来真正修改原有 state 。

视频：redux-5-dispatch
http://digicity-1253322599.costj.myqcloud.com/redux-5-dispatch.mp4

### 订阅数据变化

视频：redux-6-subscribe
http://digicity-1253322599.costj.myqcloud.com/redux-6-subscribe.mp4
