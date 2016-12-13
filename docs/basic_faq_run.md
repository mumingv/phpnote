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




