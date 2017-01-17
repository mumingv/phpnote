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


## bin2hex 函数把包含数据的二进制字符串转换为十六进制值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.bin2hex.php)。

```php
string bin2hex ( string $str )
```

<font color="red">说明：该函数将字符串中的每个字符逐个转换成对应的ASCII码16进制表示。</font>

### 示例：转换成16进制字符串

```php
$binary = "11111001";
$hex = bin2hex($binary);
echo $hex, PHP_EOL; //3131313131303031
```
```php
echo bin2hex('abc'), PHP_EOL;  // 616263
```


## chop 删除字符串末端的空白字符（或者其他字符）(rtrim的别名)

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.chop.php)。

说明：该函数是rtrim的别名。


## chr 返回指定的字符

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.chr.php)。

```
string chr ( int $ascii )
```

<font color="red">说明：将整数ascii码转换成对应的字符。</font>

### 示例：将ascii码转成字符

```php
echo chr(65) . PHP_EOL; //A
echo chr(97) . PHP_EOL; //a
```


## chunk_split 将字符串分割成小块

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.chunk_split.php)。

```php
string chunk_split ( string $body [, int $chunklen = 76 [, string $end = "\r\n" ]] )
```

### 示例：将一个字符串拆分成多行

```php
$string = '1234'; 
echo chunk_split($string, 2);
```
```php
12
34
```

### 示例：将一个字符串使用冒号分隔

```php
$string = '1234'; 
echo chunk_split($string, 2, ':');
```
```php
12:34:
```


## convert_cyr_string 将字符由一种 Cyrillic 字符转换成另一种

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.convert_cyr_string.php)。

```php
string convert_cyr_string ( string $str , string $from , string $to )
```

### 示例：不会使用该函数，略。


## convert_uudecode 解码一个 uuencode 编码的字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.convert_uudecode.php)。

```php
string convert_uudecode ( string $data )
```

### 示例：解码使用uuencode算法进行编码的字符串

```php
echo convert_uudecode("0=&5S=`IT97AT('1E>'0-\"@``\n`");
```
```php
test
text text
```


## convert_uuencode 使用 uuencode 编码一个字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.convert_uuencode.php)。

```php
string convert_uuencode ( string $data )
```

### 示例：使用uuencode算法对字符串进行编码

```php
$some_string = "test\ntext text\r\n";
echo convert_uuencode($some_string);
/*
0=&5S=`IT97AT('1E>'0-"@``
`
```


## count_chars 返回字符串所用字符的信息

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.count_chars.php)。

```php
mixed count_chars ( string $string [, int $mode = 0 ] )
```

### 示例：统计字符传中各字符出现的次数, $mode为1表示只显示次数大于0的字符。返回的数组中，key为字母的ascii值。

```php
$data = "Two Ts and one F.";
print_r(count_chars($data, 1));
```
```php
Array
(
    [32] => 4
    [46] => 1
    [70] => 1
    [84] => 2
    [97] => 1
    [100] => 1
    [101] => 1
    [110] => 2
    [111] => 2
    [115] => 1
    [119] => 1
)
```


## crc32 计算一个字符串的 crc32 多项式

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.crc32.php)。

```php
int crc32 ( string $str )
```

### 示例：计算校验码

```php
$checksum = crc32("The quick brown fox jumped over the lazy dog.");
printf("%u\n", $checksum);
```
```php
2191738434
```


## crypt 单向字符串散列

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.crypt.php)。

```php
string crypt ( string $str [, string $salt ] )
```

### 示例：获取散列值，使用自动盐值

```php
$password = 'mypassword';
$hash = crypt($password, 'mm');
echo $hash."\n";
```
```php
mmqunkvQ77kH2
```


## echo 输出一个或多个字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.echo.php)。

```php
void echo ( string $arg1 [, string $... ] )
```

### 示例：单个参数，使不使用括号都可以

```php
echo("Hello world\n");
echo "Hello world\n";
```
```php
Hello world
Hello world
```


### 示例：多个参数，不能使用括号

```php
echo "Hello world. ", "I'm coming!\n";
```
```php
Hello world. I'm coming!
```


## explode 使用一个字符串分割另一个字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.explode.php)。

```php
array explode ( string $delimiter , string $string [, int $limit ] )
```

### 示例：使用空格拆分字符串

```php
$str = "I am a stutdent. Right?";
print_r (explode(" ",$str));  
```
```php
Array
(
    [0] => I
    [1] => am
    [2] => a
    [3] => stutdent.
    [4] => Right?
)
```


### 示例：使用空格拆分字符串

```php
$pizza  = "piece1 piece2 piece3 piece4 piece5 piece6";
$pieces = explode(" ", $pizza);
echo $pieces[0] . PHP_EOL; //piece1
echo $pieces[1] . PHP_EOL; //piece2
```


### 示例：使用冒号拆分字符串

```php
$data = "foo:*:1023:1000::/home/foo:/bin/sh";
list($user, $pass, $uid, $gid, $gecos, $home, $shell) = explode(":", $data);
echo $user . PHP_EOL; //foo
echo $pass . PHP_EOL; //*
echo $uid . PHP_EOL; //1023
echo $gid . PHP_EOL; //1000
echo $gecos . PHP_EOL; // 
echo $home . PHP_EOL; ///home/foo
echo $shell . PHP_EOL; ///bin/sh
```


### 示例：中文字符串分割

```php
$str = "我爱北京天安门，哈哈。你好啊！";  
print_r (explode("。",$str));  
```
```php
Array
(
    [0] => 我爱北京天安门，哈哈
    [1] => 你好啊！
)
```


## fprintf 将格式化后的字符串写入到流

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.fprintf.php)。

```php
int fprintf ( resource $handle , string $format [, mixed $args [, mixed $... ]] )
```

### 示例：格式化字符串并将其写入文件当中

```php
if (!($fp = fopen('date.txt', 'w'))) {
    return;
}
$year = "2017";
$month = "01";
$day = "17";
fprintf($fp, "%04d-%02d-%02d", $year, $month, $day);
```
```php
2017-01-17
```


## get_html_translation_table 返回使用 htmlspecialchars() 和 htmlentities() 后的转换表

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.get_html_translation_table.php)。

```php
array get_html_translation_table ([ int $table = HTML_SPECIALCHARS [, int $flags = ENT_COMPAT | ENT_HTML401 [, string $encoding = 'UTF-8' ]]] )
```

### 示例：查看转换表

```php
var_dump(get_html_translation_table(HTML_ENTITIES, ENT_QUOTES | ENT_HTML5));
```
```php
array(1511) {
  ["    "]=>
  string(5) "&Tab;"
  ["
"]=>
  string(9) "&NewLine;"
  ["!"]=>
  string(6) "&excl;"
  ["""]=>
  string(6) "&quot;"
  ["#"]=>
  string(5) "&num;"
  ["$"]=>
  string(8) "&dollar;"
  ["%"]=>
  string(8) "&percnt;"
  ["&"]=>
  string(5) "&amp;"
  ["'"]=>
...
}
```


## hebrev 将逻辑顺序希伯来文（logical-Hebrew）转换为视觉顺序希伯来文（visual-Hebrew）

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.hebrev.php)。

```php
string hebrev ( string $hebrew_text [, int $max_chars_per_line = 0 ] )
```

### 示例：不使用该函数，略。


## hebrevc 将逻辑顺序希伯来文（logical-Hebrew）转换为视觉顺序希伯来文（visual-Hebrew），并且转换换行符

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.hebrevc.php)。

```php
string hebrevc ( string $hebrew_text [, int $max_chars_per_line = 0 ] )
```

### 示例：不使用该函数，略。


## hex2bin 转换十六进制字符串为二进制字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.hex2bin.php)。

```php
string hex2bin ( string $data )
```

### 示例：

```php
$hex = hex2bin("6578616d706c65206865782064617461");
var_dump($hex);
```
```php
string(16) "example hex data"
```


## html_entity_decode Convert all HTML entities to their applicable characters

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.html_entity_decode.php)。

```php
string html_entity_decode ( string $string [, int $flags = ENT_COMPAT | ENT_HTML401 [, string $encoding = ini_get("default_charset") ]] )
```

### 示例

```php
$orig = "I'll \"walk\" the <b>dog</b> now";
$a = htmlentities($orig);
$b = html_entity_decode($a);
echo $a."\n"; // I'll &quot;walk&quot; the &lt;b&gt;dog&lt;/b&gt; now
echo $b."\n"; // I'll "walk" the <b>dog</b> now
```




























































































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




