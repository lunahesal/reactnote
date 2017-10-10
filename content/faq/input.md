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

### 提交评论

接下来我们要实现的效果：input 中输入评论内容，点一下按钮，评论显示到页面上。

commit: input

### 使用 v-model

如果 input 使用 v-model

```
<input v-model="text" />
```

那么 handleClick 就可以写成下面这样：

```
handleClick: function () {
    const input = document.getElementById('addComment')
    this.comments.push({ text: this.text })
    this.text = ''
  }
```

### 计算属性

https://cn.vuejs.org/v2/guide/computed.html


如果写成这样：

```
computed: {
  reversedComments: function () {
    return this.comments.reverse()
  }
},
```

那么使用 reversedComments 的时候就会表现诡异。原因就是
执行 reverse() 的时候，this.comments 会被改变。

原因就是 this.comments.push 会永远把新元素添加到数组尾巴上，如果 comments 本身逆序了，那么添加后的结果肯定不是我们需要的。

解决方法：不要对 comments 变量本身执行 reverse() ，而要对 comments 的拷贝进行 reverse() 。

实现对数组的拷贝可以用 slice() 。

```
const commentsCopy = this.comments.slice(0)
return commentsCopy.reverse()
```

或者直接简写为

```
return this.comments.slice().reverse()
```
