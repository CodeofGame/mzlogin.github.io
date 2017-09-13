### 使用navicat远程连接mysql（linux ubuntu）



```shell
vim  /etc/mysql/my.cnf
```

修改my.cnf文件，将```bind-address = 127.0.0.1```改为```bind-address = 0.0.0.0```



重启mysql服务

```shell
/etc/init.d/mysql restart
```

