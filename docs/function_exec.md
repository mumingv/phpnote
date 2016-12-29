# [程序执行](https://github.com/mumingv/php/tree/master/func/exec)

## exec 执行一个外部程序

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.exec.php)。

```php
string exec ( string $command [, array &$output [, int &$return_var ]] )
```

### 示例：执行一个外部程序

```php
echo exec('whoami');
```
```php
work
```































