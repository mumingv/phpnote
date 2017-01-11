# 目录

## 安装配置

### 安装


### 在OSX上安装


### 在Windows上构建


### PHP会话处理


### 分布式Redis数组


## 类和函数

### Usage


### Connection


### Server


### Keys


### Strings

参考：[官方](https://github.com/phpredis/phpredis#keys-and-strings) & [木名](https://github.com/mumingv/php/tree/master/books/phpredis/func/string)

|类别       |函数           |功能                                   |
|-----------|---------------|---------------------------------------|
|设置       |set            |设置string                             |
|           |setex          |设置string，超时后自动删除(单位：秒)   |
|           |psetex         |设置string，超时后自动删除(单位：毫秒) |
|           |setnx          |设置string，key不存在则设置，key存在则不设置|
|           |setrange       |设置string，覆写string中的子串         |
|           |getset         |设置string，同时返回旧的string         |
|获取       |get            |获取string                             |
|           |getrange       |获取string中的子串                     |
|设置多个   |mset           |设置多个string                         |
|           |msetnx         |设置多个string，**所有**key不存在则设置，有key存在则不设置|
|获取多个   |mget           |获取多个string                         |
|           |getmultiple    |获取多个string，功能和mget完全一致     |
|位操作     |setbit         |位操作，将string中的某一个bit设置为0或者1|
|           |getbit         |位操作，获取string中的某一个bit的值|
|           |bitcount       |位操作，计算string中值为1的bit个数|
|           |bitop          |位操作，两个string进行位运算，将结果存入新的string|
|数学运算   |incr           |将string当作整数增加1                  |
|           |incrby         |将string当作整数增加指定的整数         |
|           |incrbyfloat    |将string当作浮点数增加指定的浮点数     |
|           |decr           |将string当作整数减去1                  |
|           |decrby         |将string当作整数减去指定的整数         |
|其他       |strlen         |获取string的长度                       |
|           |append         |将string附加到已有的string后面         |


### Hashes


### Lists


### Sets


### Sorted sets


### Geocoding


### Pub/sub


### Transactions


### Scripting


### Introspection


## FAQ

### connect和pconnect的区别是什么？

参考：http://blog.csdn.net/u013474436/article/details/53118475


### auth为什么认证不成功？


## 参考资料

- [Github of phpredis](https://github.com/phpredis/phpredis)


