# 包安装使用

## gd


## exif


## redis

### Yum安装

```
# yum install php-redis
```

说明：php-redis其实就是php-pecl-redis，如下所示。

```
# yum list installed | grep redis
php-pecl-redis.x86_64              2.2.8-1.el7                         @epel  
```

查看redis扩展是否安装成功。

```
$ php -m | grep redis
redis
```


## xml-rpc


