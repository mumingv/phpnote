# [PCRE函数](https://github.com/mumingv/php/tree/master/func/pcre)

## preg_match 正则表达式匹配

函数原型：

```php
int preg_match ( string $pattern , string $subject [, array &$matches [, int $flags = 0 [, int $offset = 0 ]]] )
```

返回值：正常返回匹配次数(0或1)；异常返回false。

<font color="red">
说明：preg_match只匹配第一个，preg_match_all匹配全部。
</font>

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


## preg_match_all 全局正则表达式匹配

函数原型：

```php
int preg_match_all ( string $pattern , string $subject [, array &$matches [, int $flags = PREG_PATTERN_ORDER [, int $offset = 0 ]]] )
```

返回值：正常返回匹配次数(0、1...)；异常返回false。

<font color="red">
说明：preg_match只匹配第一个，preg_match_all匹配全部。
</font>

### 示例: 查找文本字符串

```php
if (preg_match_all("/php/i", "PHP is the web scripting language of choice. PHP is the best language.", $matches)) {
    echo "A match was found.\n";
} else {
    echo "A match was not found.\n";
}
var_dump($matches);
```
```php
A match was found.
array(1) {
  [0]=>
  array(2) {
    [0]=>
    string(3) "PHP"
    [1]=>
    string(3) "PHP"
  }
}
```


### 示例：查找匹配的HTML标签（贪婪）

1. $flags参数取默认值: PREG_PATTERN_ORDER，行为和preg_match一致，从完整模式到子组进行排列。

```php
// 说明：\\2是一个后向引用的示例. 这会告诉pcre它必须匹配正则表达式中第二个圆括号(这里是([\w]+))，匹配到的结果. 这里使用两个反斜线是因为这里使用了双引号.
$html = "<b>bold text</b><a href=howdy.html>click me</a>";
preg_match_all("/(<([\w]+)[^>]*>)(.*?)(<\/\\2>)/", $html, $matches);
var_dump($matches);
```
```php
array(5) {
  [0]=>
  array(2) {
    [0]=>
    string(16) "<b>bold text</b>"
    [1]=>
    string(31) "<a href=howdy.html>click me</a>"
  }
  [1]=>
  array(2) {
    [0]=>
    string(3) "<b>"
    [1]=>
    string(19) "<a href=howdy.html>"
  }
  [2]=>
  array(2) {
    [0]=>
    string(1) "b"
    [1]=>
    string(1) "a"
  }
  [3]=>
  array(2) {
    [0]=>
    string(9) "bold text"
    [1]=>
    string(8) "click me"
  }
  [4]=>
  array(2) {
    [0]=>
    string(4) "</b>"
    [1]=>
    string(4) "</a>"
  }
}
```

2. $flags参数取值: PREG_SET_ORDER，以匹配次数进行排列。

```php
$html = "<b>bold text</b><a href=howdy.html>click me</a>";
preg_match_all("/(<([\w]+)[^>]*>)(.*?)(<\/\\2>)/", $html, $matches, PREG_SET_ORDER);
var_dump($matches);
```
```php
array(2) {
  [0]=>
  array(5) {
    [0]=>
    string(16) "<b>bold text</b>"
    [1]=>
    string(3) "<b>"
    [2]=>
    string(1) "b"
    [3]=>
    string(9) "bold text"
    [4]=>
    string(4) "</b>"
  }
  [1]=>
  array(5) {
    [0]=>
    string(31) "<a href=howdy.html>click me</a>"
    [1]=>
    string(19) "<a href=howdy.html>"
    [2]=>
    string(1) "a"
    [3]=>
    string(8) "click me"
    [4]=>
    string(4) "</a>"
  }
}
```


## preg_replace 正则表达式搜索和替换

函数原型：

```php
mixed preg_replace ( mixed $pattern , mixed $replacement , mixed $subject [, int $limit = -1 [, int &$count ]] )
```

返回值：正常返回匹配次数(0、1...)；异常返回false。

<font color="red">
说明：参数replacement中可以使用后向引用，格式为 \\n 或者 $n 或者 ${n}。对于反斜线的处理，需要经过PHP的处理然后再经过正则引擎的处理；所以如果想输出一个字面意义的反斜线的话，需要表示成'\\\\'。
}
</font>

### 示例：日期格式调整

```php
$string = 'April 15, 2003';
$pattern = '/(\w+) (\d+), (\d+)/i';
$replacement = '\\1,${3}';
$result = preg_replace($pattern, $replacement, $string);
var_dump($result);
```
```php
string(11) "April,20032"
```


### 示例：去除空白字符

```php
$str = 'foo   o';
$str = preg_replace('/\s\s+/', ' ', $str);
var_dump($str);
```
```php
string(5) "foo o"
```


