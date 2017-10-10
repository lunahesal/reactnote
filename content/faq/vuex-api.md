本节来用 vuex 的 action 读取 api 获得数据。

### 何时需要读取 API ？

情况很多，最基本的就是 comment 模块中的最初的 comment 内容，肯定不是写到代码中的，而是通过 API 的形式从服务器上读取的。

### 用 json-server 搭建 API

```
npm i -g json-server
atom db.json
json-server --watch db.json -p 3008
```

db.json 内容

```
{
  "comments": [
    { "id": "1",
      "text": "fooo"
    },
    { "id": "2",
      "text": "barr"
    }
  ]
}
```


commit: json-server

### created 生命周期函数

vue 和 react 一样，也有[生命周期函数](https://cn.vuejs.org/v2/guide/instance.html#生命周期图示) 。我们这里可以用 created 这个函数来自动触发加载 API 的操作。

### 书写 mutation

要修改 store 中的数据一定是要有 mutaion 的。

```
'LOAD_COMMENTS' (state, { comments }) {
  this.state.all = comments
}
```

如果数据不需要通过 API 获得，那么我们就可以直接在 created 生命周期中，执行 commit 来调用 mutation 了。

```
this.$store.commit('LOAD_COMMENTS', { comments })
```

### 触发 Action

但是，Mutaion 要求必须是同步函数，当我们要发 API 的时候，需要涉及到异步请求，就要来写 action 来完成。

Action 类似于 mutation，不同在于：

- Action 提交的是 mutation，而不是直接变更状态。
- Action 可以包含任意异步操作。

参考：https://vuex.vuejs.org/zh-cn/actions.html


先来写一个基本的 action:

```js
'FETCH_COMMENTS' ({ commit }) {
  commit('LOAD_COMMENTS', { comments })
}
```

可见，action 最核心的功能之一就是来触发 mutation 。

但是上面的 comments 数据从哪里来呢？答案就是 actions 之中可以直接写异步请求语句来从 json-sever 中获取到 comments 。


### 代码

commit: actions
