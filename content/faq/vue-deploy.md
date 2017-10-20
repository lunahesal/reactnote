### 首先要放弃 axios 请求

- 把数据都直接写到 store 中
- 删除所有的 loadXXX 相关的 action

### 放弃 json-server 的 ID 问题

使用 https://www.npmjs.com/package/shortid 来生成 ID 。

### 部署步骤

https://www.npmjs.com/package/vue-gh-pages

- 安装上面的包
- 按照上面的包的文档要求，添加 deploy 脚本，并运行 npm run deploy
- 这样，编译后的输出会保存到项目文件夹下的 doc/ 文件夹中的
- 接下来登录 https://github.com/happypeter/voteup/settings
- 到 "GitHub Pages" 一项，把 "Source"（源）设置为 `master branch /doc folder` （ master 分支的顶级位置的 doc 文件夹）
