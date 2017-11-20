---
layout: post
title: Windows命令大全
categories: DOS
description: 学习DOS命令，提高工作效率，不定期更新
keywords: Windows,DOS,CMD
---
## windows命令大全

#### 查看一个命令的帮助

```shell
命令 /?
# 例如 mkdir /?
# copy /?
```

#### 创建文件夹（mkdir）

```shell
mkdir 文件名称
```

#### 创建文件（多种方法）

```shell
# 创建一个空的文件
type nul>a.txt
# 创建一个有内容的文件
echo ceshi>a.txt
# 使用copy命令
copy nul a.txt
# 使用cd命令
cd.>a.txt 
# 使用重定向
type a.txt>b.txt 生成文件b.txt内容与a.txt一致
```

####删除文件夹（rd命令）

```shell
# 删除文件夹，如果文件夹不为空则不能删除
rd  文件名
# 删除文件夹及文件夹内所有文件
rd /s /q 文件夹名
```

#### 删除文件（del命令）

```shell
# 删除指定文件夹下的文件（不包括子目录的文件，并且有是否删除的提示）
del 文件夹名
# 删除文件夹及其子目录中的文件
del /s 文件夹名
#强制删除文件
del /f 文件夹名
# 使用安静模式 /q quiet（安静），使用后不会有是否删除的提示
del /s /q 文件夹名
# 删除某一类文件,比如删除后缀名为*.js的文件,使用*这个通配符
del 文件夹名\*.js   匹配文件的 aa.js
del 文件夹名\a*.js  匹配文件的 ab.js
del 文件夹名\*a.js  匹配文件的 ba.js
del 文件夹名\a.*    匹配文件的 a.txt a.js a.html
del 文件夹名\*a.*   匹配文件的 baa.txt ca.js ta.html
```

*注* ：以上所有命令只会删除文件，不会删除文件夹

#### 复制文件命令（copy）

```shell
# 我把destination放在[]中是因为，destination是一个可选参数，destination代表目标目录，当用户指定该参数，文件将复制到该目录下，否则文件复制到当前命令行所在的目录
copy source [destination]
# 文件复制到目标目录下，有可能存在同名的文件，系统会提示是否覆盖，使用/y 关闭该提示，直接覆盖
copy /y source [destination]
```



#### 复制文件夹命令（xcopy）

> xcopy命令是copy命令的扩展，可以将文件目录连同文件一并

```shell
# 将源文件复制到目标文件夹中
xcopy source destination 


```



