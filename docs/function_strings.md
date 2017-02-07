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


## htmlentities Convert all applicable characters to HTML entities

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.htmlentities.php)。

```php
string htmlentities ( string $string [, int $flags = ENT_COMPAT | ENT_HTML401 [, string $encoding = ini_get("default_charset") [, bool $double_encode = true ]]] )
```

### 示例：转换html标记

```php
$str = "A 'quote' is <b>bold</b>";
echo htmlentities($str)."\n";
echo htmlentities($str, ENT_QUOTES)."\n";
```
```php
A 'quote' is &lt;b&gt;bold&lt;/b&gt;
A &#039;quote&#039; is &lt;b&gt;bold&lt;/b&gt;
```


## htmlspecialchars_decode 将特殊的 HTML 实体转换回普通字符

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.htmlspecialchars_decode.php)。

```php
string htmlspecialchars_decode ( string $string [, int $flags = ENT_COMPAT | ENT_HTML401 ] )
```

### 示例：转换html标记

```php
$str = "<p>this -&gt; &quot;</p>\n";
echo htmlspecialchars_decode($str)."\n";
echo htmlspecialchars_decode($str, ENT_NOQUOTES)."\n";
```
```php
<p>this -> "</p>
<p>this -> &quot;</p>
```


## htmlspecialchars Convert special characters to HTML entities

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.htmlspecialchars.php)。

```php
string htmlspecialchars ( string $string [, int $flags = ENT_COMPAT | ENT_HTML401 [, string $encoding = ini_get("default_charset") [, bool $double_encode = true ]]] )
```

### 示例：转换html标记

```php
$new = htmlspecialchars("<a href='test'>Test</a>", ENT_QUOTES);
echo $new."\n";
```
```php
&lt;a href=&#039;test&#039;&gt;Test&lt;/a&gt;
```


## implode 将一个一维数组的值转化为字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.implode.php)。

```php
string implode ( string $glue , array $pieces )
string implode ( array $pieces )
```

### 示例

```php
$array = array('lastname', 'email', 'phone');
$comma_separated = implode(",", $array);
echo $comma_separated."\n";
```
```php
lastname,email,phone
```


## join 将一个一维数组的值转化为字符串 (implode的别名)

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.join.php)。

```php
string join ( string $glue , array $pieces )
string join ( array $pieces )
```

### 示例

```php
$array = array('lastname', 'email', 'phone');
$comma_separated = join(",", $array);
echo $comma_separated."\n";
```
```php
lastname,email,phone
```


## lcfirst 使一个字符串的第一个字符小写

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.lcfirst.php)。

```php
string lcfirst ( string $str )
```

### 示例

```php
$foo = lcfirst("HelloWorld");
echo $foo."\n";
```
```php
helloWorld
```


## levenshtein 计算两个字符串之间的编辑距离

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.levenshtein.php)。

```php
int levenshtein ( string $str1 , string $str2 )
int levenshtein ( string $str1 , string $str2 , int $cost_ins , int $cost_rep , int $cost_del )
```

### 示例：找出与错误单词最接近的单词

```php
// 输入拼写错误的单词
$input = 'carrrot';

// 要检查的单词数组
$words  = array('apple','pineapple','banana','orange',
                'radish','carrot','pea','bean','potato');

// 目前没有找到最短距离
$shortest = -1;

// 遍历单词来找到最接近的
foreach ($words as $word) {

    // 计算输入单词与当前单词的距离
    $lev = levenshtein($input, $word);

    // 检查完全的匹配
    if ($lev == 0) {

        // 最接近的单词是这个（完全匹配）
        $closest = $word;
        $shortest = 0;

        // 退出循环；我们已经找到一个完全的匹配
        break;
    }

    // 如果此次距离比上次找到的要短
    // 或者还没找到接近的单词
    if ($lev <= $shortest || $shortest < 0) {
        // 设置最接近的匹配以及它的最短距离
        $closest  = $word;
        $shortest = $lev;
    }
}

echo "Input word: $input\n";
if ($shortest == 0) {
    echo "Exact match found: $closest\n";
} else {
    echo "Did you mean: $closest?\n";
}
```
```php
Input word: carrrot
Did you mean: carrot?
``` 


## localeconv Get numeric formatting information

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.localeconv.php)。

```php
array localeconv ( void )
```

### 示例：设置系统区域并获取数字格式信息

```php
if (false !== setlocale(LC_ALL, 'zh_CN.UTF-8')) {
    $locale_info = localeconv();
    print_r($locale_info);
}
```
```php
Array
(
    [decimal_point] => .
    [thousands_sep] => ,
    [int_curr_symbol] => CNY 
    [currency_symbol] => ￥
    [mon_decimal_point] => .
    [mon_thousands_sep] => ,
    [positive_sign] => 
    [negative_sign] => -
    [int_frac_digits] => 2
    [frac_digits] => 2
    [p_cs_precedes] => 1
    [p_sep_by_space] => 0
    [n_cs_precedes] => 1
    [n_sep_by_space] => 0
    [p_sign_posn] => 4
    [n_sign_posn] => 4
    [grouping] => Array
        (
            [0] => 3
        )

    [mon_grouping] => Array
        (
            [0] => 3
        )

)
```


## ltrim 删除字符串开头的空白字符（或其他字符）

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.ltrim.php)。

```php
string ltrim ( string $str [, string $character_mask ] )
```

### 示例：删除字符串开头的空白字符

```php
$string = "    Hello world!";
echo $string."\n";
echo ltrim($string)."\n";
```
```php
    Hello world!
Hello world!
```


## md5_file 计算指定文件的 MD5 散列值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.md5_file.php)。

```php
string md5_file ( string $filename [, bool $raw_output = false ] )
```

### 示例：删除字符串开头的空白字符

```php
echo md5_file("echo.php")."\n";  // 32211c00eb56055e8bbe528ce31fc1b5 (32字符的十六进制数字)
echo md5_file("echo.php", true)."\n";  // 2!.............. (16位二进制)
```


## md5 算字符串的 MD5 散列值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.md5.php)。

```php
string md5 ( string $str [, bool $raw_output = false ] )
```

### 示例

```php
// 非空字符串
$str = 'apple';
echo md5($str) . PHP_EOL; //1f3870be274f6c49b3e31a0c6728957f

// 空字符串
echo md5("") . PHP_EOL; //d41d8cd98f00b204e9800998ecf8427e

// 第二个参数为true, 打印结果中16个字符对应的ASCII码
$bin = md5($str, true);  
for ($i = 0; $i < strlen($bin); $i++){  
    echo ord($bin[$i]) . ','; //31,56,112,190,39,79,108,73,179,227,26,12,103,40,149,127,
}
echo PHP_EOL;
```


## metaphone Calculate the metaphone key of a string

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.metaphone.php)。

```php
string metaphone ( string $str [, int $phonemes = 0 ] )
```

### 示例：根据发音创建的metaphone键

```php
var_dump(metaphone('programming'));
var_dump(metaphone('programmer'));
```
```php
string(7) "PRKRMNK"
string(6) "PRKRMR"
```


## money_format 将数字格式化成货币字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.money_format.php)。

```php
string money_format ( string $format , float $number )
```

### 示例：根据发音创建的metaphone键

```php
$number = 1234.56;
// 国际化格式
setlocale(LC_MONETARY, 'en_US');
echo money_format('%i', $number) . "\n";
/*
USD 1,234.56
*/
// 中国的货币格式，带两位浮点小数
setlocale(LC_MONETARY, 'zh_CN');
echo money_format('%i', $number) . "\n";
/*
CNY1,234.56
*/
```


## nl_langinfo Query language and locale information

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.nl_langinfo.php)。

```php
string nl_langinfo ( int $item )
```

### 示例：一般不使用，略。


## nl2br 在字符串所有新行之前插入 HTML 换行标记

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.nl2br.php)。

```php
string nl2br ( string $string [, bool $is_xhtml = true ] )
```

### 示例：将换行替换成HTML换行标记

```php
echo nl2br("foo isn't\n bar");
/*
foo isn't<br />
 bar
*/
echo nl2br("This\r\nis\n\ra\nstring\r");
/*
This<br />
is<br />
a<br />
string<br />
*/
```


## number_format 以千位分隔符方式格式化一个数字

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.number_format.php)。

```php
string number_format ( float $number [, int $decimals = 0 ] )
string number_format ( float $number , int $decimals = 0 , string $dec_point = "." , string $thousands_sep = "," )
```

### 示例：1位参数

```php
$number = 1234.56;
$english_format_number = number_format($number);
echo $english_format_number.PHP_EOL;  // 1,235
```

### 示例：4位参数

```php
$number = 1234.5678;
$english_format_number = number_format($number, 2, '.', '');
echo $english_format_number.PHP_EOL;  // 1234.57
```


## ord 返回字符的 ASCII 码值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.ord.php)。

```php
int ord ( string $string )
```

<font color="red">
说明：返回字符串 string 第一个字符的 ASCII 码值。
</font>

### 示例：入参是一个字符

```php
$str = "A";
echo ord($str) . PHP_EOL; //65
```

### 示例：入参是一个字符串

```php
$str2 = "ABC";
echo ord($str2) . PHP_EOL; //65
```


## parse_str 将字符串解析成多个变量

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.parse_str.php)。

```php
void parse_str ( string $str [, array &$arr ] )
```

### 示例：

```php
$str = "first=value&arr[]=foo+bar&arr[]=baz";
parse_str($str);
echo $first."\n";  // value
echo $arr[0]."\n"; // foo bar
echo $arr[1]."\n"; // baz
```

```php
parse_str($str, $output);
echo $output['first']."\n";  // value
echo $output['arr'][0]."\n"; // foo bar
echo $output['arr'][1]."\n"; // baz
```


## print 输出字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.print.php)。

```php
int print ( string $arg )
```

### 示例：

```php
print("Hello World\n");
print "print() also works without parentheses.\n";
```


## printf 输出格式化字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.printf.php)。

```php
int printf ( string $format [, mixed $args [, mixed $... ]] )
```

### 示例: 整数字符串后面加一位小数，如：'2' -> '2.0'

```php
$num = '2';
$num = printf("%.1f", $num);  // 2.0 (直接打印到屏幕)
var_dump($num);  // int(3) (字符串长度)
```


## quoted_printable_decode  quoted-printable 字符串转换为 8-bit 字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.quoted_printable_decode.php)。

```php
string quoted_printable_decode ( string $str )
```

### 示例：不使用该函数，略。


## quoted_printable_encode  8-bit 字符串转换成 quoted-printable 字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.quoted_printable_encode.php)。

```php
tring quoted_printable_encode ( string $str )
```

### 示例：不使用该函数，略。


## quotemeta 转义元字符集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.quotemeta.php)。

```php
string quotemeta ( string $str )
```

### 示例：

```php
$str = "Hello world. (can you hear me?)";
echo quotemeta($str);
```
```php
Hello world\. \(can you hear me\?\)
```


##  rtrim 删除字符串末端的空白字符（或者其他字符）

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function..php)。

```php
string rtrim ( string $str [, string $character_mask ] )
```

### 示例：

```php
// 去除尾部空格
$string1 = "  Hello world!   ";
print_r("Before trim --> string1: [" . $string1 . "]\n");
print_r("After trim --> string1: [" . rtrim($string1) . "]\n");

// 去除尾部tab键
$string2 = "\tHello world!\t";
print_r("Before trim --> string2: [" . $string2 . "]\n");
print_r("After trim --> string2: [" . rtrim($string2) . "]\n");

// 去除尾部指定字符(本例中，END是三个单独的字符，不是一个字符串整体)
$string3 = "ENDHello world!NDE";
print_r("Before trim --> string3: [" . $string3 . "]\n");
print_r("After trim --> string3: [" . rtrim($string3, "END") . "]\n");
```


## setlocale 设置地区信息

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.setlocale.php)。

```php
string setlocale ( int $category , string $locale [, string $... ] )
string setlocale ( int $category , array $locale )
```

### 示例：略。


## sha1_file 计算文件的 sha1 散列值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.sha1_file.php)。

```php
string sha1_file ( string $filename [, bool $raw_output = false ] )
```

### 示例：计算目录下所有php文件的散列值

```php
foreach(glob('./*.php') as $ent)
{
    if(is_dir($ent))
    {
        continue;
    }
    echo $ent . ' (SHA1: ' . sha1_file($ent) . ')', PHP_EOL;
}
```
```php
./trim.php (SHA1: f3204ce956037d97c3cd6f285bb0c0ac4f4239f3)
./ucfirst.php (SHA1: 3e414bb27d2fb26a3affcb283d22134381a24f14)
./vsprintf.php (SHA1: e7c74513998adbb93f5735f403b164cc73082080)
./wordwrap.php (SHA1: 59017fe459a484edb879f2b0b7ed4c97bac4ef95)
```


## sha1 计算字符串的 sha1 散列值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.sha1.php)。

```php
string sha1 ( string $str [, bool $raw_output = false ] )
```

### 示例：计算字符串的散列值

```php
$str = 'apple';
echo sha1($str);  // d0be2dc421be4fcd0172e5afceea3970e2f3d940
```


## similar_text 计算两个字符串的相似度

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.similar_text.php)。

```php
int similar_text ( string $first , string $second [, float &$percent ] )
```

### 示例：计算字符串的相似度

```php
$var_1 = 'PHP IS GREAT'; 
$var_2 = 'WITH MYSQL'; 
similar_text($var_1, $var_2, $percent); 
echo $percent."\n";
similar_text($var_2, $var_1, $percent); 
echo $percent."\n";
```
```php
27.272727272727
18.181818181818
```


## soundex Calculate the soundex key of a string

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.soundex.php)。

```php
string soundex ( string $str )
```

### 示例：判断两个字符串读音的相似度，略。


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


## sscanf 根据指定格式解析输入的字符

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.sscanf.php)。

```php
mixed sscanf ( string $str , string $format [, mixed &$... ] )
```

### 示例：

```php
list($serial) = sscanf("SN/2350001", "SN/%d");
$mandate = "January 01 2000";
list($month, $day, $year) = sscanf($mandate, "%s %d %d");
echo "Item $serial was manufactured on: $year-" . substr($month, 0, 3) . "-$day\n";
```
```php
Item 2350001 was manufactured on: 2000-Jan-1
```


## str_getcsv 解析 CSV 字符串为一个数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.str_getcsv.php)。

```php
array str_getcsv ( string $input [, string $delimiter = "," [, string $enclosure = '"' [, string $escape = "\\" ]]] )
```

### 示例

```php
print_r(str_getcsv("1,mumingv\n2,henry", "\n"));
```
```php
Array
(
    [0] => 1,mumingv
    [1] => 2,henry
)
```


### 示例

```php
$csv = array_map('str_getcsv', file('../../data/data.csv'));
print_r($csv);
```
```php
array (
  0 => 
  array (
    0 => '1',
    1 => 'mumingv',
  ),
  1 => 
  array (
    0 => '2',
    1 => 'henry',
  ),
)
```


## str_ireplace 子字符串替换(忽略大小写)

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.str_ireplace.php)。

```php
mixed str_ireplace ( mixed $search , mixed $replace , mixed $subject [, int &$count ] )
```

### 示例

```php
$bodytag = str_ireplace("%Body%", "black", "<body text='%body%'>");
echo $bodytag . PHP_EOL; //<body text='black'>
```


### 示例

```php
$vowels = array("A", "E", "I", "O", "U");
$onlyconsonants = str_ireplace($vowels, "", "Hello World of PHP");
echo $onlyconsonants . PHP_EOL;  //Hll Wrld f PHP
```


### 示例

```php
$phrase  = "You should eat fruits, vegetables, and fiber every day.";
$healthy = array("fruits", "vegetables", "fiber");
$yummy   = array("pizza", "beer", "ice cream");
$newphrase = str_ireplace($healthy, $yummy, $phrase);
echo $newphrase . PHP_EOL;  //You should eat pizza, beer, and ice cream every day.
```


### 示例

```php
$str = str_ireplace("LL", "", "good golly miss molly!", $count);
echo $count . PHP_EOL; //2
```


## str_pad 使用另一个字符串填充字符串为指定长度

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.str_pad.php)。

```php
string str_pad ( string $input , int $pad_length [, string $pad_string = " " [, int $pad_type = STR_PAD_RIGHT ]] )
```

### 示例

```php
$str = "Hello world!";
$result_str = str_pad($str, 20);
echo $result_str, "//END", PHP_EOL; //Hello world!        //END

$result_str = str_pad($str, 20, "-");
echo $result_str, "//END", PHP_EOL; //Hello world!--------//END

$result_str = str_pad($str, 20, "-", STR_PAD_LEFT);
echo $result_str, "//END", PHP_EOL; //--------Hello world!//END

$result_str = str_pad($str, 20, "-*^", STR_PAD_BOTH);
echo $result_str, "//END", PHP_EOL; //-*^-Hello world!-*^-//END
```


## str_repeat 重复一个字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function..php)。

```php
string str_repeat ( string $input , int $multiplier )
```

### 示例

```php
$str = "Hello!";
$result_str = str_repeat($str, 3);
echo $result_str, "//END", PHP_EOL; //Hello!Hello!Hello!//END
```

```php
// 重复次数为0时，返回空字符串
$result_str = str_repeat($str, 0);
echo $result_str, "//END", PHP_EOL;
```


## str_replace 子字符串替换

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.str_replace.php)。

```php
mixed str_replace ( mixed $search , mixed $replace , mixed $subject [, int &$count ] )
```

### 示例：所有参数均为字符串，不是数组

```php
$bodytag = str_replace("%body%", "black", "<body text='%body%'>");
var_dump($bodytag);
```
```php
string(19) "<body text='black'>"
```

### 示例：去除字符串中的元音字母，第一个参数是数组，其他参数为字符串

```php
$vowels = array("a", "e", "i", "o", "u", "A", "E", "I", "O", "U");
$onlyconsonants = str_replace($vowels, "", "Hello World of PHP");
var_dump($vowels);
```
```php
array(10) {
  [0]=>
  string(1) "a"
  [1]=>
  string(1) "e"
  [2]=>
  string(1) "i"
  [3]=>
  string(1) "o"
  [4]=>
  string(1) "u"
  [5]=>
  string(1) "A"
  [6]=>
  string(1) "E"
  [7]=>
  string(1) "I"
  [8]=>
  string(1) "O"
  [9]=>
  string(1) "U"
}
```


## str_rot13 对字符串执行 ROT13 转换

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.str_rot13.php)。

```php
string str_rot13 ( string $str )
```

### 示例：

```php
echo str_rot13('PHP 4.3.0');  // CUC 4.3.0
echo str_rot13('CUC 4.3.0');  // PHP 4.3.0
```


## str_shuffle 随机打乱一个字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.str_shuffle.php)。

```php
string str_shuffle ( string $str )
```

### 示例：

```php
echo str_shuffle('abcdef');  // aecbdf
```


## str_split 将字符串转换为数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.str_split.php)。

```php
array str_split ( string $string [, int $split_length = 1 ] )
```

### 示例：

```php
$str = "Hello Friend";
$arr1 = str_split($str);
$arr2 = str_split($str, 3);
print_r($arr1);
print_r($arr2);
```
```php
Array
(
    [0] => H
    [1] => e
    [2] => l
    [3] => l
    [4] => o
    [5] =>  
    [6] => F
    [7] => r
    [8] => i
    [9] => e
    [10] => n
    [11] => d
)
Array
(
    [0] => Hel
    [1] => lo 
    [2] => Fri
    [3] => end
)
```


## str_word_count 返回字符串中单词的使用情况

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.str_word_count.php)。

```php
mixed str_word_count ( string $string [, int $format = 0 [, string $charlist ]] )
```

### 示例：

```php
$str = "Hello friend, you're looking good today!";
print_r(str_word_count($str));
print_r(str_word_count($str, 1));
print_r(str_word_count($str, 2));
```
```php
6
Array
(
    [0] => Hello
    [1] => friend
    [2] => you're
    [3] => looking
    [4] => good
    [5] => today
)
Array
(
    [0] => Hello
    [6] => friend
    [14] => you're
    [21] => looking
    [29] => good
    [34] => today
)
```


## strcasecmp 二进制安全比较字符串（不区分大小写）

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.strcasecmp.php)。

```php
int strcasecmp ( string $str1 , string $str2 )
```

### 示例：

```php
$var1 = "Hello";
$var2 = "hello";
if (strcasecmp($var1, $var2) == 0) {
        echo '$var1 is equal to $var2 in a case-insensitive string comparison';  // 运行会打印这句话
}
```
```php
$var1 is equal to $var2 in a case-insensitive string comparison
```


## strchr 查找字符串的首次出现 (strstr的别名)

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function..php)。

```php
string strchr ( string $haystack , mixed $needle [, bool $before_needle = false ] )
```

### 示例：

```php
$email  = 'name@example.com';
$domain = strchr($email, '@');
echo $domain;
```
```php
@example.com
```


## strcmp 二进制安全字符串比较 (区分大小写)

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.strcmp.php)。

```php
int strcmp ( string $str1 , string $str2 )
```

### 示例：

```php
$var1 = "Hello";
$var2 = "hello";
if (strcmp($var1, $var2) !== 0) {
        echo '$var1 is not equal to $var2 in a case sensitive string comparison';
}
```
```php
$var1 is not equal to $var2 in a case sensitive string comparison
```


## strcoll 基于区域设置的字符串比较(区分大小写)

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function..php)。

```php
int strcoll ( string $str1 , string $str2 )
```

### 示例：

```php
$var1 = "Hello";
$var2 = "hello";
if (strcoll($var1, $var2) !== 0) {
        echo '$var1 is not equal to $var2 in a case sensitive string comparison';
}
```
```php
$var1 is not equal to $var2 in a case sensitive string comparison
```


## strcspn 获取不匹配遮罩的起始子字符串的长度

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function..php)。

```php
int strcspn ( string $str1 , string $str2 [, int $start [, int $length ]] )
```

### 示例：

```php
$a = strcspn('abcd',  'apple');  // 从头开始数，a在apple中，所以返回0
$b = strcspn('abcd',  'banana');  // 从头开始数，a在banana中，所以返回0
$c = strcspn('hello', 'l');  // 从头开始数，h和e不在l中，所以返回2
$d = strcspn('hello', 'world');  // 从头开始数，h和e不在world中，所以返回2
var_dump($a);  // 0
var_dump($b);  // 0
var_dump($c);  // 2
var_dump($d);  // 2
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


## stripcslashes 反引用一个使用 addcslashes() 转义的字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.stripcslashes.php)。

```php
string stripcslashes ( string $str )
```

### 示例：

略。


## stripos 查找字符串首次出现的位置 (不区分大小写)

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.stripos.php)。

```php
int stripos ( string $haystack , string $needle [, int $offset = 0 ] )
```

### 示例：

```php
$findme    = 'a';
$mystring1 = 'xyz';
$mystring2 = 'ABC';

$pos1 = stripos($mystring1, $findme);
$pos2 = stripos($mystring2, $findme);

// 'a' 当然不在 'xyz' 中
if ($pos1 === false) {
        echo "The string '$findme' was not found in the string '$mystring1'\n";
}

// 注意这里使用的是 ===。简单的 == 不能像我们期望的那样工作，
// 因为 'a' 的位置是 0（第一个字符）。
if ($pos2 !== false) {
        echo "We found '$findme' in '$mystring2' at position $pos2\n";
}
```
```php
The string 'a' was not found in the string 'xyz'
We found 'a' in 'ABC' at position 0
```


## stripslashes 反引用一个引用字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.stripslashes.php)。

```php
string stripslashes ( string $str )
```

### 示例：

```php
$str = "Is your name O\'reilly?";
echo $str."\n";
echo stripslashes($str)."\n";
```
```php
Is your name O\'reilly?
Is your name O'reilly?
```


## stristr 查找字符串的首次出现 (不区分大小写)

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.stristr.php)。

```php
string stristr ( string $haystack , mixed $needle [, bool $before_needle = false ] )
```

### 示例：

```php
$email  = 'name@example.com';
$domain = stristr($email, 'E');
echo $domain;
```
```php
e@example.com
```


## strlen 获取字符串长度

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.strlen.php)。

```php
int strlen ( string $string )
```

### 示例：

```php
$str = 'abcdef';
echo strlen($str).PHP_EOL; // 6
$str = ' ab cd ';
echo strlen($str).PHP_EOL; // 7
```


## strnatcasecmp 使用自然排序算法比较字符串(不区分大小写)

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.strnatcasecmp.php)。

```php
int strnatcasecmp ( string $str1 , string $str2 )
```

### 示例：

```php
$arr2 = array("img12.png", "img10.png", "IMG2.png", "img1.png");
usort($arr2, "strnatcasecmp");
var_export($arr2);
```
```php
array (
  0 => 'img1.png',
  1 => 'IMG2.png',
  2 => 'img10.png',
  3 => 'img12.png',
)
```


## strnatcmp 使用自然排序算法比较字符串 (区分大小写)

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.strnatcmp.php)。

```php
int strnatcmp ( string $str1 , string $str2 )
```

### 示例：

```php
$arr2 = array("img12.png", "img10.png", "img2.png", "img1.png");
usort($arr2, "strnatcmp");
var_export($arr2);
echo PHP_EOL;
```
```php
array (
  0 => 'img1.png',
  1 => 'img2.png',
  2 => 'img10.png',
  3 => 'img12.png',
)
```


## strncasecmp 二进制安全比较字符串开头的若干个字符（不区分大小写）

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.strncasecmp.php)。

```php
int strncasecmp ( string $str1 , string $str2 , int $len )
```

### 示例：

```php
echo strncasecmp("Hello1", "hello2", 5);  // 0
```


## strncmp 二进制安全比较字符串开头的若干个字符 (区分大小写)

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.strncmp.php)。

```php
int strncmp ( string $str1 , string $str2 , int $len )
```

### 示例：

```php
echo strncmp("Hello1", "hello2", 5);  // -32
```


## strpbrk 在字符串中查找一组字符的任何一个字符 (区分大小写)

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.strpbrk.php)。

```php
string strpbrk ( string $haystack , string $char_list )
```

### 示例：

```php
$text = 'This is a Simple text.';
echo strpbrk($text, 'mi')."\n";
echo strpbrk($text, 'S')."\n";
```
```php
is is a Simple text.
Simple text.
```


## strpos 查找字符串首次出现的位置

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.strpos.php)。

```php
mixed strpos ( string $haystack , mixed $needle [, int $offset = 0 ] )
```

### 示例：

```php
$mystring = 'abc';
$findme   = 'a';
$pos = strpos($mystring, $findme);
if ($pos === false) {
    echo "The string '$findme' was not found in the string '$mystring'";
} else {
    echo "The string '$findme' was found in the string '$mystring'"; // 单引号中的变量也会被扩展变量值
    echo " and exists at position $pos" . PHP_EOL;
}
```
```php
The string 'a' was found in the string 'abc' and exists at position 0
```


## strrchr 查找指定字符在字符串中的最后一次出现

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.strrchr.php)。

```php
string strrchr ( string $haystack , mixed $needle )
```

### 示例：

```php
$PATH = "/usr/local/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/usr/java/jdk1.7.0_80/bin:/usr/java/jdk1.7.0_80/jre/bin:/usr/local/hadoop/bin:/usr/local/hadoop/sbin:/home/work/.local/bin:/home/work/bin:/usr/libexec/gcc/x86_64-redhat-linux/4.8.2";
echo substr(strrchr($PATH, ":"), 1);
```
```php
/usr/libexec/gcc/x86_64-redhat-linux/4.8.2
```


## strrev 反转字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.strrev.php)。

```php
string strrev ( string $string )
```

### 示例：

```php
$str = "Hello";
echo strrev($str), PHP_EOL; //olleH
```


## strripos 计算指定字符串在目标字符串中最后一次出现的位置 (不区分大小写)

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.strripos.php)。

```php
int strripos ( string $haystack , string $needle [, int $offset = 0 ] )
```

### 示例：

```php
$haystack = 'ababcd';
$needle   = 'aB';
$pos      = strripos($haystack, $needle);
if ($pos === false) {
    echo "Sorry, we did not find ($needle) in ($haystack)";
} else {
    echo "Congratulations!\n";
    echo "We found the last ($needle) in ($haystack) at position ($pos)";
}
```
```php
Congratulations!
We found the last (aB) in (ababcd) at position (2)
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




