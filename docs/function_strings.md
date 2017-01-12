# [字符串函数](https://github.com/mumingv/php/tree/master/func/strings)

## addcslashes 以 C 语言风格使用反斜线转义字符串中的字符

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.addcslashes.php)。

```php
string addcslashes ( string $str , string $charlist )
```

### 示例：转义a到z之间所有的字符

```php
echo addcslashes('foo[ ]', 'a..z')."\n";
```
```php
\f\o\o[ ]
```


### 示例：转义A到z之间所有的字符

```php
echo addcslashes('foo[ ]', 'A..z')."\n";
```
```php
\f\o\o\[ \]
```


## addslashes 使用反斜线引用字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.addslashes.php)。

```php
string addslashes ( string $str )
```

<font color="red">说明：转义的字符：单引号、双引号、反斜线（\）与 NUL（NULL 字符）。</font>




## htmlentities 将HTML页面中的特殊字符转换成HTML实体

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.htmlentities.php)。

```php
string htmlentities ( string $string [, int $flags = ENT_COMPAT | ENT_HTML401 [, string $encoding = ini_get("default_charset") [, bool $double_encode = true ]]] )
```


## nl2br 在字符串所有新行之前插入 HTML 换行标记

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.nl2br.php)。

```php
string nl2br ( string $string [, bool $is_xhtml = true ] )
```


## sprintf 返回格式化的字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.sprintf.php)。

```php
string sprintf ( string $format [, mixed $args [, mixed $... ]] )
```

<font color="red">各类格式化类型(如: %s)参考官方文档，大部分和C语言类似。</font>

示例：
```php
$num = 5;
$location = 'tree';
$format = 'There are %d monkeys in the %s';
echo sprintf($format, $num, $location)."\n";  // There are 5 monkeys in the tree
```


## strip_tags 从字符串中去除 HTML 和 PHP 标记

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.strip-tags.php)。

```php
string strip_tags ( string $str [, string $allowable_tags ] )
```

示例代码，请参考：[GitHub](https://github.com/mumingv/php/tree/master/func/strings/strip_tags.php)。

### 示例：去除所有HTML标记

```php
$text = 'This is <b>bold</b> and this is <i>italic</i>. What about this <a href="http://www.php.net/">link</a>?';
echo strip_tags($text).PHP_EOL;
```
```
This is bold and this is italic. What about this link?
```


### 示例：去除部分HTML标记

注：第二个参数用于指明要保留的标记。

```php
$text = 'This is <b>bold</b> and this is <i>italic</i>. What about this <a href="http://www.php.net/">link</a>?';
echo strip_tags($text, '<b><i>').PHP_EOL;
```
```
This is <b>bold</b> and this is <i>italic</i>. What about this link?
```


## vsprintf 返回格式化的字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.vsprintf.php)。

```php
string vsprintf ( string $format , array $args )
```

<font color="red">vsprintf和sprintf的区别在于，vsprintf的$args参数是个数组，sprintf的$args参数是个列表。</font>

示例：
```php
print vsprintf("%04d-%02d-%02d", explode('-', '1988-8-1'));  // 1988-08-01
```

示例：
```php
$arr = array('1988', '8', '1');
print vsprintf("%04s-%02s-%02s", $arr);  // 1988-08-01
```


## wordwrap 打断字符串为指定数量的字串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.wordwrap.php)。

```php
string wordwrap ( string $str [, int $width = 75 [, string $break = "\n" [, bool $cut = false ]]] )
```

示例代码，请参考：[GitHub](https://github.com/mumingv/php/tree/master/func/strings/wordwrap.php)。

### 示例：使用默认列宽和break字符

```php
$string = "This is a long sentence that will be cut at seventy-five characters automatically. Don't worry, no words will be broken up
.";
echo wordwrap($string).PHP_EOL;
```
```
This is a long sentence that will be cut at seventy-five characters
automatically. Don't worry, no words will be broken up.
```


### 示例：使用指定列宽和break字符

```php
$string = "This is a long sentence that will be cut at sixty characters automatically. Don't worry, no words will be broken up.";
echo wordwrap($string, 60, '<br />').PHP_EOL;
```
```
This is a long sentence that will be cut at sixty characters<br />automatically. Don't worry, no words will be broken up.
```




