## Git指南

### 自己跟自己玩

#####创建仓库

```shell
git init
```

##### 查看仓库状态

```shell
//列出当前目录还没有被git管理的文件或者已经被git管理，但是还未提交的文件，查看文件的状态：新增，修改，删除，冲突。
git status
```




#### 分支相关操作

```shell
//查看当前仓库的所有分支，不带任何参数
git branch
//所有的仓库都有一个默认的分支，名为master不可修改
//创建一个名为分支，如果一个新仓库还没有任何commit操作，责无法commit
git branch test
//切换到test分支
git checkout test
//上面两条命令可以合为一个命令
git checkout -b test //生成test分支并跳转到test分支
//查看各个版本最后一次提交的信息
git branch -v
```

###### 合并分支

```shell
//首先切换到master分支
git checkout master
//接着合并分支,将test的分支同步到master分支上
git merage test
//合并之后会有两种情况
//1.成功（Fast-forward：快进）
//	直接祖先是相同的，所以这种合并是没问题的
//2.失败（Automatic merge failed; fix conflicts and then commit the result.）
//直接祖先不相同，合并有问题，merge之后会把分支的内容，同步到目标分支上，所以merge之后，test分支也没
//用了，可以直接删除。
失败之后，可以手动修改，修改完之后使用git add命令，将冲突的文件标记为已解决状态。
//解决冲突的可视化工具
git mergetool
```

###### 删除分支

```shell
//分支上的内容合并到主分支上，，就可以删除多余的分支了
git branch -d test
```





### 多人协作

##### 管理远程仓库相关

> 

```shell
//查看当前已存在的远程仓库
git remote
//查看当前远程仓库的详细信息,查看远程仓库的地址
git remote -v
//新建远程仓库
git remote add 仓库名称 远程仓库的url

```

### 通用的功能

##### 修改一些全局配置

> 在一个机器上初次使用git，一般要做一些配置，使用git config命令来配置

```shell
//配置使用者的用户名和邮箱，每次 Git 提交时都会引用这两条信息
git config [--system/--global] user.name 用户名
git config [--system/--global] user.email 邮箱
注：参数说明 
--system 对所有用户都适用的配置
--global 对当前用户适用的配置
不加参数时 对当前git工作目录有效

//查看配置信息
git config --list
注：会看到很多重复的配置，说明来自不同的配置文件，但是git只会获取最后一条

//查看某个特定的信息
git config user.name //以此为例
```

### 在GitHub与他人协作开发

- 首先找到要参与的项目，然后fork该项目

- 使用git clone将项目克隆到本地

- 修改完文件之后，commit，并上传到远程仓库

- 登录我们自己的github，在Code页签下有一个Pull Request的按钮，进去以后能看到我们的修改

- 点击Create Pull Request 再写一些备注就会给项目作者发送

- 如果项目的原作者在你fork之后，又更新了文件，这是你就要做fork的同步（fork sync）

（官方地址：https://help.github.com/articles/syncing-a-fork/）

​	首先配置远程指向Git中上游存储库，以便将您在分支中进行的更改与原始存储库同步。 这也使您能够将原始存储库中所做的更改与叉同步，具体操作如下：

```shell
//查看我项目的远程仓库
git remote -v
//执行该项目的原始地址 upstream（上游），指定该项目的远程上游库，同步fork的内容
git remote add upstream https://github.com/ORIGINAL_OWNER{原始作者}/ORIGINAL_REPOSITORY{原始库}.git
//再看下远程仓库
git remote -v 
```

​	配置好远程上游仓库后，就可以同步项目了

```shell
//从远程上游库抓取数据，将新加的内容存储在本地的分支
git fetch upstream
//检出本地的master分支
git checkout master
//同步远程的master分支内容到你本地的master分支，不会删除你修改的内容
git merge upstream/master
注：If your local branch didn't have any unique commits, Git will instead perform a "fast-forward":（如果你的本地分支没有任何独特的提交，那么Git将执行“快进”：）
```

