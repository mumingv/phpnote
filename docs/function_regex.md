# [POSIX扩展正则表达式函数](https://github.com/mumingv/php/tree/master/func/regex)

## ereg 正则表达式匹配

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.ereg.php)

### 匹配日期格式

```php
$date = 'The date is: 2016-05-04.';
$ret = ereg("([0-9]{4})-([0-9]{1,2})-([0-9]{1,2})", $date, $regs);
echo '$ret => '.$ret.PHP_EOL;
echo '$regs[0] => '.$regs[0].PHP_EOL;
if ($ret) {
           echo "$regs[3].$regs[2].$regs[1]", PHP_EOL; //04.05.2016
} else {
           echo "Invalid date format: $date", PHP_EOL;
} 
```
```php
$ret => 10
$regs[0] => 2016-05-04
04.05.2016
```

说明：`$[0]`表示正则表达式匹配上的完整的字符串；`$[1] ~ $[n]`和匹配的子串按顺序一一对应。


## eregi 正则表达式匹配，不区分大小写

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.eregi.php)


## ereg_replace 正则表达式替换

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.ereg-replace.php)


## eregi_replace 正则表达式替换，不区分大小写

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.eregi-replace.php)


## split 用正则表达式将字符串分割到数组中

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.split.php)


## spliti 用正则表达式将字符串分割到数组中，不区分大小写

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.spliti.php)


## sql_regcase 产生用于匹配的正则表达式，不区分大小写

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.sql-regcase.php)

### 生成字符串对应的正则表达式

```php
echo sql_regcase("Foo - bar.");
```
```php
[Ff][Oo][Oo] - [Bb][Aa][Rr].
```
说明：该函数仅仅将每个字母使用方括号`[]`表示，且不区分大小写。其他字符一律不变。

