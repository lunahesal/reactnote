此时，如果我们刷新页面，就会发现终端报错

```
Cannot read property 'title' of undefined"
```

显然这是由于在页面显示的第一时间，`this.post` 还未加载完成造成的。

解决这个问题的方式就是采用 v-if 。


应对初始数据为空

v-if 是正解：https://forum.vuejs.org/t/any-better-way-than-v-if-to-render-content-that-is-temporarily-undefined/5327


代码如下：

<div v-if="show">
...
computed:
  show: function () {
    return this.post
  },
```

### 视频

http://digicity-1253322599.costj.myqcloud.com/if.mp4
