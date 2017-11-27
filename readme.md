### Redis
```
redis-server.exe redis.conf
```

```
redis-cli.exe -h 127.0.0.1 -p 6379
```


默认情况下 requirepass 参数是空的，你无需通过密码验证就可以连接到 redis 服务
```
CONFIG get requirepass
```

设置密码后，客户端连接 redis 服务就需要密码验证，否则无法执行命令
```
CONFIG set requirepass "123456"
```

Redis支持五种数据类型：string（字符串），hash（哈希），list（列表），set（集合）及zset(sorted set：有序集合)
SET 和 GET 命令

#### String
```
SET w3ckey redis

GET w3ckey

DEL w3ckey
```
#### Hash

设置 redis 的一些描述信息(name, description, likes, visitors) 到哈希表的 w3ckey 中
```
HMSET w3ckey name "redis tutorial" description "redis basic commands for caching" likes 20 visitors 23000
```
#### List

使用LPUSH(left push) 将三个值插入了名为 w3ckey 的列表当中
```
LPUSH w3ckey redis
LPUSH w3ckey mongodb
LPUSH w3ckey mysql
```
#### Set

通过 SADD 命令向名为 w3ckey 的集合插入的三个元素
```
SADD w3ckey redis

SADD w3ckey mongodb

SADD w3ckey mysql

SADD w3ckey mysql

SMEMBERS w3ckey
```
#### sorted set

通过命令 ZADD 向 redis 的有序集合中添加了三个值并关联上score

```
ZADD w3ckey 1 redis

ZADD w3ckey 2 mongodb
ZADD w3ckey 3 mysql

ZADD w3ckey 3 mysql
ZADD w3ckey 4 mysql

ZRANGE w3ckey 0 10 WITHSCORES
```
