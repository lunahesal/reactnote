---
title: nodejs 安装
---

安装 node 的方式很多，这里推荐用 nvm 装 node。

### 准备工作

在 ubuntu/deepin 系统上，需要先安装 curl ，

```
sudo apt-get update
sudo apt-get install curl
```

### 安装 nvm

安装 nvm 可以直接到 github 上找到 [nvm](https://github.com/creationix/nvm#install-script) 这个仓库查看安装命令


```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash
```

直接装好，运行 nvm 会报错

```
nvm: command not found
```

解决方法：重新开启一个新的命令行窗口。

接下来就可以用nvm 去安装 nodejs 了

```bash
nvm ls-remote  # 查看可以选择安装的 node 版本
nvm install v7.4.0 # 安装 7.4.0 的 nodejs
```

安装完 node 之后，npm 一块跟着装好了。

```bash
node -v
npm -v
```

如何使用 npm 初始化一个 node 项目：

```
npm init 生成 package.json
npm install <package name> --save 安装的包会记录到 package.json 的 dependencies
npm install <package name> --save-dev 安装的包会记录到 package.json 的 devDependencies
npm install <package name> -g 安装到我们本地的电脑上
```
