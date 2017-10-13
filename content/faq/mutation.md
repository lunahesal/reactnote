本节来修改 store 中的数据。


### 添加 mutation

Vue 修改 store 中的数据，也是通过一个函数来完成的，这个函数要放到 store 中的对应数据模块（ modules/comment.js )的 mutations （中文意思：修改）对象中。

逻辑如下：

```
mutations {
  'MUTATION_NAME' (state, data) {
    return newState
  }
}
```

### 呼叫 mutations

这个就是到对应组件中，由用户去触发了。

```
this.$store.commit('MUTATION_NAME', data)
```

### 代码

commit: mutations

### 视频

http://digicity-1253322599.costj.myqcloud.com/mutations.mp4
