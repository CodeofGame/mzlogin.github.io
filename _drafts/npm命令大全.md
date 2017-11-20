```shell
//创建一个package.json文件
npm init 
```

```shell
npm install 
npm install 
```

```shell
//查看某个库的详细信息
npm info koa2
//查看koa的所有可用版本
npm view koa versions 
//查看koa的最新版本
npm view koa version
```

```shell
//在当前目录下安装最新版本的koa
npm install koa
//全局安装
npm install koa -g
//安装指定版本的koa
npm install koa@2.3.0
//根据package.json安装所有依赖的包
npm install 
```

```shell
//查看npm的一些配置
npm config ls
//输出信息为
; cli configs
metrics-registry = "https://registry.npmjs.org/"
scope = ""
user-agent = "npm/5.0.3 node/v8.1.2 win32 x64"

; builtin config undefined
//全局路径，这里有时会有错误，全局安装的模块会到这个地方，这个路径应该是node的安装目录
prefix = "C:\\Users\\HouHanBin\\AppData\\Roaming\\npm"
//修改prefix的值
npm config set prefix "node包安装的路径"

; node bin location = E:\someSoftWare\node\node.exe
; cwd = F:\
; HOME = C:\Users\HouHanBin
; "npm config ls -l" to show all defaults.
```

**注意**:修改完npm的config设置后，会在C://用户//账户//.npmrc,这个文件会引起你的任何npm命令都无反应，这种情况，删除这个.npmrc文件。

```shell
//查看全局安装过的包
npm list --depth=0
```

