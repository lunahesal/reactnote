# 处理用户输入

参考：

- https://cn.vuejs.org/v2/guide/#处理用户输入
- https://cn.vuejs.org/v2/guide/forms.html

### 事件监听

```
<button v-on:click="handleClick">触发事件函数</button>
```

那么，handleClick 函数应该如何定义呢？

还是要到 export default {} 内部去写。


```js
methods: {
  handleClick: function () {
    console.log('clicked!')
  }
}
```

https://github.com/happypeter/vue-hello/commits/master

commit: event

### 修改 State

修改 state 值在 vue 这里，比 React 要简单太多。就是

```
this.stateName = newValue
```

类似下面这样：

```js
  addComment: function () {
      this.comments = 'hello'
    }
```

### 使用 v-model

如果 input 使用 v-model

```
<input v-model="text" />
```

那么 handleClick 就可以写成下面这样：

```
handleClick: function () {
    this.comments.push({ text: this.text })
    this.text = ''
  }
```

### 视频

http://digicity-1253322599.costj.myqcloud.com/input.mp4

### commit

https://github.com/happypeter/vue-hello/commits/master

input
