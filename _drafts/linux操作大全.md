#### 修改系统环境变量

```shell
//先找到.profile文件,再修改.profile
vim ~/.profile

在文件的末尾添加
export 环境变量名=路径（Linux是一个相对路径）windows的环境变量是绝对路径
//修改完之后，该环境变量不能立马生效，需要执行如下命令
source ~/.profile

```

### node全局模块找不到的问题解决

```shell
//查看全局模块的安装路径,prefix即为全局安装模块的路径
npm config ls 
//修改全局路径
npm config set prefix 指定路径
//修改环境变量
vim ~/.profile
//在文件末尾加上NOED_PATH环境变量
export NODE_PATH=路径(Node的这个路径很特殊，一定要找到node_modules的那一级目录)
//查看文件的目录的命令 pwd
//让修改立即生效
source ~/.profile
```



