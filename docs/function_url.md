# [URL函数](https://github.com/mumingv/php/tree/master/func/url)

## rawurlencode 按照 RFC 3986 对 URL 进行编码

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.rawurlencode.php)

```php
string rawurlencode ( string $str )
```

编码规则：[RFC 3986 - Uniform Resource Identifier (URI): Generic Syntax](http://www.faqs.org/rfcs/rfc3986.html)。


## urlencode 编码 URL 字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.urlencode.php)

```php
string urlencode ( string $str )
```

示例：字母、数字和 -_. 这三个字符不会编码

```php
$userinput = 'abc-def_ghi.123';
echo '<a href="mycgi?foo=', urlencode($userinput), '">', "\n";
```
```php
<a href="mycgi?foo=abc-def_ghi.123">
```

示例：其他会编码的英文字符，如：空格、#、!等等

```php
$userinput = 'abc def#123!';
echo '<a href="mycgi?foo=', urlencode($userinput), '">', "\n";
```
```php
<a href="mycgi?foo=abc+def%23123%21">
```

示例：中文字符编码

```php
$userinput = '大王派我来巡山！';
echo '<a href="mycgi?foo=', urlencode($userinput), '">', "\n";
echo '<a href="mycgi?foo=', urlencode(urlencode($userinput)), '">';
```
```php
<a href="mycgi?foo=%E5%A4%A7%E7%8E%8B%E6%B4%BE%E6%88%91%E6%9D%A5%E5%B7%A1%E5%B1%B1%EF%BC%81">
<a href="mycgi?foo=%25E5%25A4%25A7%25E7%258E%258B%25E6%25B4%25BE%25E6%2588%2591%25E6%259D%25A5%25E5%25B7%25A1%25E5%25B1%25B1%25EF%25BC%2581">
```


## urldecode 解码已编码的 URL 字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.urldecode.php)。

```php
string urldecode ( string $str )
```

示例：字母、数字和 -_. 这三个字符不会编码

```php
$userinput = 'abc-def_ghi.123';
$useroutput = urlencode($userinput);
echo urldecode($useroutput).PHP_EOL;  // abc-def_ghi.123
```

示例：其他会编码的英文字符，如：空格、#、!等等

```php
$userinput = 'abc def#123!';
$useroutput = urlencode($userinput);
echo urldecode($useroutput).PHP_EOL;  // abc def#123!
```

示例：中文字符编码

```php
$userinput = '大王派我来巡山！';
$useroutput = urlencode($userinput);
echo urldecode($useroutput).PHP_EOL;  // 大王派我来巡山！
```





