# 路由器

如果在 vue-cli 创建项目的时候，选择了 vue-router ，那么基本的代码就有了，但是，我这里没有选择。所以先从装包开始做。

参考：https://router.vuejs.org/zh-cn/

### 安装

```
npm i vue-router
```

### 去掉路由中的 hash

```
mode: 'history',
```


### 使用链接

```
<router-link to="/post/888">Post</router-link>
```

### 读取链接参数

会涉及到前面讲的动态属性。

commit: router


### 视频

http://digicity-1253322599.costj.myqcloud.com/router.mp4
