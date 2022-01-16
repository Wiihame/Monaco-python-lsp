# Monaco Editor LSP

该项目是基于 monaco-editor 以及 python-languageserver 开发的带有 intellisense、auto-complete 等 LSP 能力（language server protocol）的编辑器。

项目分为 client 和 server 两端：

- client：基于 express 运行的 nodejs 服务，提供编辑器页面
- server：基于 tornado 的 python web server，通过 pyls-jsonrpc 提供 LSP 服务

client 和 server 之间的连接方式是 websocket，通过 typefox 的 monaco-languageclient 包向 server 发送补全求情，在收到补全信息后，monaco-languageclient 会在 monaco 内展示补全内容。

---

本地调试开发教程：

1. 安装 python 依赖(python 3.4+)

```
pip install tornado python-jsonrpc-server
```
>| 安装依赖的时候使用python-jsonrpc-server，调用的时候用pyls_jsonrpc的包名  （[出处](https://github.com/palantir/python-language-server/issues/643)）

2. 运行脚本

```
python python-server/langserver_ext.py
```

3. 访问`http://localhost:3001/python`（默认启动端口，可自己修改），若有"Can "Upgrade" only to "WebSocket"."的文字提示，即服务其成功启动

4. 启动 expres

安装依赖

```
yarn
```

编译 ts 代码

```
yarn prepare
```

启动 express

```
yarn start:ext
```

5. 访问`http://localhost:3002/`（默认启动端口，可自己修改）,能看到带语法高亮、输入 python 代码有自动补全，即运行成功
