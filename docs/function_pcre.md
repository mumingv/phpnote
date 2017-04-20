# [PCRE函数](https://github.com/mumingv/php/tree/master/func/pcre)

## preg_match 正则表达式匹配

函数原型：

```php
int preg_match ( string $pattern , string $subject [, array &$matches [, int $flags = 0 [, int $offset = 0 ]]] )
```

返回值：0不匹配，1匹配。

### 示例：查找文本字符串

```php
if (preg_match("/php/i", "PHP is the web scripting language of choice.")) {
    echo "A match was found.\n";
} else {
    echo "A match was not found.\n";
}
```
```
A match was found.
```


### 示例：获取URL中的域名

```php
// 从URL中获取主机名称
// 说明：这里的 @ 表示模式字符串的起止字符；[^/]+ 表示接下来的字符串一直到'/'截止。
preg_match('@^(?:http://)?([^/]+)@i',
    "http://www.php.net/index.html", $matches);
var_dump($matches);

// 获取主机名称的后面两部分
// 说明：[^.]+ 示接下来的字符串一直到'.'截止，'.'在方括号中表示字面意义；
$host = $matches[1];
preg_match('/[^.]+\.[^.]+$/', $host, $matches);
var_dump($matches);
```
```
array(2) {
  [0]=>
  string(18) "http://www.php.net"
  [1]=>
  string(11) "www.php.net"
}
array(1) {
  [0]=>
  string(7) "php.net"
}
```






