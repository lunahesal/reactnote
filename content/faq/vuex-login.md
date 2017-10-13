实现一个只有前端的登录效果（页面刷新后会失效）。配合 vuex 来做。

达成的功能：

- 用户输入用户名之后，点保存按钮，LoginForm 的文字就变成了“我是 XXX”
- 不要退出按钮
- store 中保存 isAuthenticated （是否已授权，值为 true 或者 false ），还有 currentUser （当前用户，值为用户名字符串）
- 上面两个变量的 module 名为 auth.js （ auth 的意思就会认证）


### 引入 vuex

把 vuex 先引入进来

```
npm i vuex
```

main.js 中导入

```diff
  import Vue from 'vue'
  import App from './App'
+import store from './store'

 Vue.config.productionTip = false

 /* eslint-disable no-new */
 new Vue({
   el: '#app',
   router,
+  store,
   template: '<App/>',
   components: { App }
 })
```

store/index.js 内容：

```js
import Vue from 'vue'
import Vuex from 'vuex'
import auth from './modules/auth'

Vue.use(Vuex)

export default new Vuex.Store({
  modules: {
    auth
  }
})
```

store/modules/auth.js 的内容：

```js
const state = {
  isAuthenticated: false,
  currentUser: ''
}

export default {   
  state
}
```

有了上面的内容，就可以到 LoginForm.js 中使用 store 中的数据了

```js
  computed: {
    isAuthenticated: function () {
      return this.$store.state.auth.isAuthenticated
    },
    currentUser: function () {
      return this.$store.state.auth.currentUser
    }
  }
```

### 修改 store

LoginForm 中添加

```js
<input v-model="username" />
<button @click="saveUser" >
  保存
</button>
...
methods: {
  saveUser: function () {
    this.$store.commit('login', { username: this.username })
    this.username = ''
  }
},
data: function () {
  return {
    username: ''
  }
},
```

store/modules/auth.js

```js
const mutations = {
  login (state, { username }) {
    console.log('mutations', username)
    state.currentUser = username
    state.isAuthenticated = true
  }
}
...
export default {
  ...
  mutations
}
```

### 使用 v-if 条件显示

```js
<template>
  <div class='login-form'>
    <div v-if="!isAuthenticated">
      你是
      <input v-model="username" />
      <button @click="saveUser" >
        保存
      </button>
    </div>
    <div v-else>
      我是 {{ currentUser }}
    </div>
  </div>
</template>
```

### 视频

http://digicity-1253322599.costj.myqcloud.com/voteup-vuex-login.mp4
