现在登录或者注册之后，基本上就是直接重定向到 /mine 页面，然后把表单关闭。本节来设置 currentUser 管理登录态，并且实现退出登录的功能。

### currentUser

这个应该是注册/登录成功之后自动设置的，通过它来判断到底有没有用户登录进来。

首先要做的一点就是，用户一旦登录/注册成功，直接就可以设置这个 currentUser 值了，那么跳转到 /mine 页面之后，可以判断一下 store 中有没有这个值，有的话就不用重新发 axios 请求了。


https://github.com/happypeter/petpetgo/commits/master

commits:

- set currentUser after signup/login

### 退出登录

首先判断有 currentUser ，才显示退出按钮。

- authString
