# 运行FAQ

## 运行出现错误：Call to undefined function mb_split()

执行[mb_split.php](https://github.com/mumingv/php/tree/master/func/mbstring/mb_split.php)，出现下面的错误：

```php
$ php mb_split.php
PHP Fatal error:  Call to undefined function mb_split() in /home/work/git/php/func/mbstring/mb_split.php on line 3
```

解决该问题需要安装`php-mbstring`扩展。

```php
# yum install php-mbstring
```


## 运行出现错误：Allowed memory size of 134217728 bytes exhausted

```php
$ php updateOds.php
[19-Aug-2016 11:59:56 PRC] PHP Fatal error:  Allowed memory size of 134217728 bytes exhausted (tried to allocate 72 bytes) in /home/work/orp/app/betui/script/updateOdds.php on line 36
```

原因：脚本使用的内存超出PHP的默认值(128M)。

解决方法：脚本开头设置内存上限值。

```php
ini_set('memory_limit', '1024M');
```


## [Redis]运行出现错误：Redis server went away

```php
$ php connect.php 
PHP Fatal error:  Uncaught exception 'RedisException' with message 'Redis server went away' in /home/work/git/php/demo/redis/connect.php:18
Stack trace:
#0 /home/work/git/php/demo/redis/connect.php(18): Redis->set('tutorial-name', 'Redis tutorial')
#1 {main}
  thrown in /home/work/git/php/demo/redis/connect.php on line 18
```

1. 检查redis-server是否启动，没有启动的话执行如下命令启动redis-server。

```bash
$ nohup redis-server &
```

2. 创建Redis实例后，需要执行connect函数进行连接。

```php
$redis = new Redis();
$redis->connect('127.0.0.1', 6379);
```


## [Redis]运行出现错误：Failed to AUTH connection

```php
PHP Fatal error:  Uncaught exception 'RedisException' with message 'Failed to AUTH connection' in /home/work/git/php/demo/redis/connect.php:18
Stack trace:
#0 /home/work/git/php/demo/redis/connect.php(18): Redis->set('tutorial-name', 'Redis tutorial')
#1 {main}
  thrown in /home/work/git/php/demo/redis/connect.php on line 18
```

执行如下命令，出现错误如下：

```bash
$ redis-cli
127.0.0.1:6379> KEYS *
(error) NOAUTH Authentication required.
```

重启redis-server后，问题解决。

```bash
$ redis-cli 
127.0.0.1:6379> KEYS *
(empty list or set)
```






