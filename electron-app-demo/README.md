# Electron-app-demo

> electron使用样例

## 安装electron

1. 使用`yarn`安装`electron`,`yarn add electron --dev`,提示网络连接异常,开发环境使用shadowsockts,可能为代理异常问题,错误提示内容:
    - `RequestError: connect ETIMEDOUT 13.250.177.223:443`
    - `at ClientRequest.<anonymous> (E:\home\nodejs\electron-app-demo\node_modules\got\source\request-as-event-emitter.js:178:14)`
2. 使用全局代理模式,网络依然有问题,错误提示内容:
    - `RequestError: read ECONNRESET`
    - `at ClientRequest.<anonymous> (E:\home\nodejs\electron-app-demo\node_modules\got\source\request-as-event-emitter.js:178:14)`
3. 将代理服务使用npx添加到命令后安装成功,命令详情为:
    - `npx cross-env ELECTRON_GET_USE_PROXY=true GLOBAL_AGENT_HTTPS_PROXY=http://127.0.0.1:1080 yarn add electron --dev`

> 参考: https://stackoverflow.com/questions/60054531/how-can-i-solve-the-connection-problem-during-npm-install-behind-a-proxy


## 初始开发并启动demo

1. 初始化项目,`yarn init -y`,生成`package.json`文件;
2. 按照官方文档,分别编写`main.js,index.html,preload.js`文件,修改`package.json`文件
3. 启动项目,`yarn start`,包裹`index.html`的主窗口启动

> 参考: https://www.electronjs.org/docs/tutorial/quick-start