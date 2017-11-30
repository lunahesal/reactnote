基本思路：首先做注册，然后登录后拿到 userId 保存到 localStorage 中，然后页面每次刷新都拿 userId 去服务器上换 username ，这样就可以维持登录态了。

### 先来制作表单

发起注册相关的 axios 请求也不难，也在这一部分完成了

https://github.com/happypeter/petpetgo/commits/master

commits:

- signup back
- show signup form
- add signup/login Link
- control BottomList

### 注册成功之后自动跳转到个人主页

涉及到 react router 的使用了

```
npm i --save react-router-dom
```

- redirect to mine


### 引入 redux

目前的问题是 BottomList 中包裹  SignUp 表单，每次关闭 BottomList 的时候要保证把表单的开管 state 值也设置一下，涉及到父子操作比较多了，所以还是引入 redux 比较方便。

```
npm i --save redux react-redux redux-thunk
```


### 独立路由页面还是当前页面的弹出

独立路由页面有很多方便之处，但是如果用注册/登录表单弹出页面的形式，未来就不涉及到重定向回 referrer 的操作了，也是非常方便的。


### 跳转到“我的”页面

先保存 userId 到 localStorage 中，然后如果页面刷新，可以自动去服务器端取用户名。

https://github.com/happypeter/petpetgo/commits/master

commits:

- redirect to mine and save userId
- fetchUser

### 添加 Login 页面

SignUp 功能基本完善了，现在作 Login 页面

https://github.com/happypeter/petpetgo/commits/master

commits:

- login works
