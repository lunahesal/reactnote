本节来用 vuex 的 action 读取 api 获得数据。

### 何时需要读取 API ？

情况很多，最基本的就是 comment 模块中的最初的 comment 内容，肯定不是写到代码中的，而是通过 API 的形式从服务器上读取的。

### 用 json-server 搭建 API

```
npm i -g json-server
atom db.json
json-server --watch db.json -p 3008
```

db.json 内容

```
{
  "comments": [
    { "id": "1",
      "text": "fooo"
    },
    { "id": "2",
      "text": "barr"
    }
  ]
}
```



### 代码

commit: API

### 视频

http://digicity-1253322599.costj.myqcloud.com/api.mp4
