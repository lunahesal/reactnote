# 属性传入

### 静态属性

方式非常简单，父组件中这样写

```
<post-body title="Git 技巧"></post-body>
```

然后到 post-body 组件内部声明一下

```
props: ['title'],
```

### 动态属性

上面的方式，只能传入固定值，而实际中，我们经常需要传变量。

这样，我们就需要用到 v-bind 指令了。

基本方式如下:

```
<post-body v-bind:title="title"></post-body>
```

但是，v-bind 还支持简写形式：https://cn.vuejs.org/v2/guide/syntax.html#v-bind-缩写

也就是写成这样：

```
<post-body :title="title"></post-body>
```

然后定义 title 这个 state 值，使用即可。

commit: props

### 视频

http://digicity-1253322599.costj.myqcloud.com/props.mp4
