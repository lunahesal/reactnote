下一步，我在 CommentBox 组件中，添加评论，希望能够实时的在 PostBody 中看到评论数。这个涉及到了组件间如何进行数据通信。在 Vue 框架下，是通过 [vuex](https://vuex.vuejs.org/zh-cn/) 来完成的。本节先来实现把数据搬家到 vuex 的 store 中。

### 装包

vuex 可以作为 npm 包进行安装。

```
npm i vuex
```

### 创建 store

就是创建一个 store/index.js

```js
import Vue from 'vue'
import Vuex from 'vuex'
import comment from './modules/comment'

Vue.use(Vuex)

export default new Vuex.Store({
  modules: {
    comment
  }
})
```

### 代码

commit: vuex read data from store
