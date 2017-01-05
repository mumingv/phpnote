# [PHP 选项/信息 函数](https://github.com/mumingv/php/tree/master/func/info)

## get_defined_constants 返回所有常量的关联数组，键是常量名，值是常量值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.json-decode.php)。

### 示例：查询系统中的所有常量（包括各扩展的常量以及自定义的常量）

```php
define("MY_CONSTANT", 1);
print_r(get_defined_constants(true));
```
```php
Array
(
    [Core] => Array
        (
            [E_ERROR] => 1
            [E_RECOVERABLE_ERROR] => 4096
            [E_WARNING] => 2
            [E_PARSE] => 4
            ...
        )
    [user] => Array
        (
            [MY_CONSTANT] => 1
        )
)
```



