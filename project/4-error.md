前面的 login/signup 只是考虑到了正确的情况，对于报错信息无法正确显示，这集来控制一下。


### 用户注册不成功

一般就是用户名重复，会返回

```
  return res.status(403).json({msg: '用户名重复，请重新注册'})
```


采用 flash 的形式来显示：

- add flash


### 用户登录错误


- login error handled
