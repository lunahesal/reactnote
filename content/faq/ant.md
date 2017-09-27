对于像后台系统这样的对界面风格要求不高的应用，我们可以使用现成的**组件库**，来完成开发，好处是：

- 开发效率可以提高百倍
- css 兼容和用户体验都是一流的


### 蚂蚁设计简介

ant.design 。是一套 UI 设计语言，是阿里巴巴对自己公司中后台系统开发的一套经验总结。是一套开源在 github.com 之上的开源组件库。

### 如何在 create-react-app 中使用？

https://ant.design/docs/react/use-with-create-react-app-cn

视频：
http://digicity-1253322599.costj.myqcloud.com/ant-1-hello.mp4


### 创建登录页面

使用 ant-design 的 Form https://ant.design/components/form-cn/。

视频：
http://digicity-1253322599.costj.myqcloud.com/ant-2-login-form.mp4


### 使用 styled-components 来写 CSS

https://www.styled-components.com/ 。

视频：

http://digicity-1253322599.costj.myqcloud.com/ant-3-styled.mp4


### 实现登录跳转功能


```js
login = (data) => {
  console.log('axios.post %s', data)
  this.props.history.push('/dashboard')
}

render() {
  return (
    <Home onLogin={this.login} />
  )
}
```

视频：
http://digicity-1253322599.costj.myqcloud.com/ant-4-redirect.mp4


### 添加配置文件

视频：
http://digicity-1253322599.costj.myqcloud.com/ant-5-settings.mp4


### 登录报错信息

视频:
http://digicity-1253322599.costj.myqcloud.com/ant-6-error.mp4


### 操作盘界面布局

视频：
http://digicity-1253322599.costj.myqcloud.com/ant-7-dash-layout.mp4

### 退出登录

视频：
http://digicity-1253322599.costj.myqcloud.com/ant-8-logout.mp4


### withRouter 解决 history 对象找不到的问题

https://reacttraining.com/react-router/web/api/withRouter

视频：

http://digicity-1253322599.costj.myqcloud.com/ant-9-withrouter.mp4

### 添加导航栏

视频：

http://digicity-1253322599.costj.myqcloud.com/ant-10-navbar.mp4

```
Navigated to http://localhost:3000/
manifest.json:1 Manifest: Line: 1, column: 1, Unexpected token.
```

解决方法：把 manifest.json 添加进来即可

```
➜  public git:(master) ✗ mv manifest.json ~/Desktop/dj-stuff/dj-demos/ant-demo/public
```

### 页面跳转

视频：ant-11-link

http://digicity-1253322599.costj.myqcloud.com/ant-11-link.mp4

### selected-keys

保证页面刷新后，导航栏的高亮可以保持。

视频：ant-12-selected
http://digicity-1253322599.costj.myqcloud.com/ant-12-selected.mp4

### 更多 selected-keys 相关

视频 ant-13-selected-more

http://digicity-1253322599.costj.myqcloud.com/ant-13-selected-more.mp4

### 404

视频： ant-14-404

http://digicity-1253322599.costj.myqcloud.com/ant-14-404.mp4

### table

视频：ant-15-table

http://digicity-1253322599.costj.myqcloud.com/ant-15-table.mp4

### 数据保存到数据库

视频：ant-16-json-server

http://digicity-1253322599.costj.myqcloud.com/ant-16-json-server.mp4

### 删除一条美食

视频：ant-17-delete

http://digicity-1253322599.costj.myqcloud.com/ant-17-delete.mp4

### 使用 form

使用 form 来添加新甜点，
这个视频先把表单基本用法介绍一下。

- this.props.form.getFieldsValue()
  - getFieldsValue 读取表单字段的值
-  { getFieldDecorator }
  - 读取字段修饰符

视频：ant-18-form

http://digicity-1253322599.costj.myqcloud.com/ant-18-form.mp4

### 提交新甜点

视频：ant-19-submit

http://digicity-1253322599.costj.myqcloud.com/ant-19-submit.mp4


### 全局 state 和 redux

很多时候，兄弟组件间互相通信，只需要把要共用的 state 放到他们的父组件中即可，但是类似我们现在面临的 sidebar 高亮问题，就不那么好办了。

当然方法不是没有：

https://medium.com/@blairanderson/you-probably-dont-need-redux-1b404204a07f

但是后续我们会引入 redux 来解决这个问题。

视频 ant-20-share

http://digicity-1253322599.costj.myqcloud.com/ant-20-share.mp4


### 订单

视频：ant-21-orders

http://digicity-1253322599.costj.myqcloud.com/ant-21-orders.mp4

视频：ant-22-orders-more

http://digicity-1253322599.costj.myqcloud.com/ant-22-orders-more.mp4

### 用户系统

视频：ant-23-user

http://digicity-1253322599.costj.myqcloud.com/ant-23-user.mp4

### 引入 redux store

视频： ant-24-redux-store
http://digicity-1253322599.costj.myqcloud.com/ant-24-redux-store.mp4

### redux 修改 state

视频：ant-25-redux-reducer
http://digicity-1253322599.costj.myqcloud.com/ant-25-redux-reducer.mp4

### 组件通信

视频：ant-26-redux-update
http://digicity-1253322599.costj.myqcloud.com/ant-26-redux-update.mp4

### 订阅数据修改

视频：ant-27-redux-subscribe

http://digicity-1253322599.costj.myqcloud.com/ant-27-redux-subscribe.mp4
