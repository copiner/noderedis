### Redis

下载
```
wget http://download.redis.io/releases/redis-5.0.5.tar.gz
```
解压
```
tar -xzvf redis-5.0.5.tar.gz
```
编译安装
```
$ cd redis-5.0.5
$ make

$ cd src && make

# or

$ cd src
$ make test
$ make

$ make isntall
```

启动
```
$ cd redis-5.0.5
$ redis-server redis.config

```

客户端连接
```
$ cd redis-5.0.5
$ redis-cli
```
修改配置

Redis 的配置文件位于 Redis 安装目录下，文件名为 redis.conf，客户端可以通过 config 命令查看或设置配置项。

1. 使用 * 号获取所有配置项
```
config get *
```

2. 默认情况，redis服务不是在后台运行，需要将 redis 放在后台运行
```
$ vi redis.config

daemonize no --> yes
```

3. 已经启动的 redis服务，客户端通过命令行设置密码，可以使用 config set 属性 值 来更改配置，

```
config set requirepass yourPassword
```
这种方式是临时的，当服务器重启了密码必须重设，但在设置完以后，输入 config rewrite 命令，
可以将config set持久化到Redis配置文件中
```
config rewrite
```

默认情况下 requirepass 参数是空的，你无需通过密码验证就可以连接到 redis 服务
```
config get requirepass
```
