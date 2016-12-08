# [字符串函数](https://github.com/mumingv/php/tree/master/func/strings)

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




