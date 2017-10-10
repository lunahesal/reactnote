comments 数据，是 CommentBox 组件生成的，但是因为已经保存到了 vuex store 中，所以共享数据就变得非常容易。现在我们想要在 PostBody 组件中拿到评论数。

### 思路

直接在 PostBody 中读取 store 数据即可，跟在 CommentBox 中的读取语句完全一样。

```js
computed: {
  commentNo: function () {
    return this.comments.length
  },
  comments: function () {
     return this.$store.state.comment.all
  }
}
```


### 代码

commit: read store
