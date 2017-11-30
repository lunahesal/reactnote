第一版的设计图上传到了：https://github.com/happypeter/shunzhi/issues/1


### login 项目

- https://github.com/happypeter/redux-react-login

先把上面的这个小案例讲完，然后真正的去做 shunzhi 项目。

### 介绍后台 API 工作原理

参考：https://haoqicat.com/express-love-api

真正使用 API 就用：https://github.com/happypeter/aa-journey-demo/tree/master/api 即可

### 前端开发过程

参考：https://github.com/happypeter/redux-react-login/commits/master


### SVG 制作成组件

有 def 和 use 的 SVG 不能用，会报出 `name.toLowercase` 的错误。




### 手机测试

不要忘记改 settings.host ，否则，登录注册都没反应。


### 侧边栏

关于 react-buger-menu 做出的 sidebar ，不能每个组件里面嵌入一个，也就是

Dashboard.js

```
<div className="dashboard">
  <Sidebar />
</div>
```

这样，在切换页面的时候，sidebar 会闪退，看不出过渡关闭的效果。


### this.props.dispatch

对于已经 connect 了的组件，可以不用导入 store 使用 `store.dispatch` 了，可以直接用

this.props.dispatch
