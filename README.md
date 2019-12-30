# Monaco-python-lsp

**Support python lsp in monaco editor**

**在 monaco 编辑器内支持 python lsp（代码补全、高亮）**

### Dependencies

- [python-jsonrpc-server](https://github.com/palantir/python-jsonrpc-server)

- [monaco-languageclien](https://github.com/TypeFox/monaco-languageclient)

---

### 使用步骤

1. 安装 Python 运行环境及 lsp 支持包 python-jsonrpc-server

   `pip install -U python-jsonrpc-server`

2. 运行 server 目录下的 launcher.py 文件，在本地启动 lsp 服务。

   `ws://localhost:3000/python`

3. 启动本地 monaco editor。在 client 目录下执行

   `npm i`

   `npm run prepare`

   `npm run watch`

4. 查看支持 Python lsp 的 Monaco editor

   `localhost:3000`
