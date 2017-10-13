# 添加登录表单

### 前端开发环境

采用 [vue-cli](https://github.com/vuejs/vue-cli) 搭建。

```
vue init webpack voteup
```

Github 上创建项目 voteup ，代码随时上传到 Github。

### LoginForm 组件开发

首页内容放到 Home 组件中，LoginForm 组件只是 Home 组件的一部分。

开发的时候只考虑移动版上的使用体验，所以在 index.html 中添加：

```
<meta name="viewport" content="width=device-width, initial-scale=1" />
```

然后打开 chrome 开发者工具的移动调试进行界面开发。

### CSS 规范

全局 CSS 都写到 App.vue 的 style 部分。其他组件的 CSS 都限制作用域（使用 `<style scoped>`）。

### 视频

http://digicity-1253322599.costj.myqcloud.com/voteup-login-form.mp4
