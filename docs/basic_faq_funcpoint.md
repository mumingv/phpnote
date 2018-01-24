# 功能FAQ

## POST有哪几种提交数据方式？

参考：[四种常见的 POST 提交数据方式](https://imququ.com/post/four-ways-to-post-data-in-http.html)


## 如何根据中文标点符号拆分文本？

使用`mb_split`函数，完整代码请参考：[GitHub](https://github.com/mumingv/php/blob/master/func/mbstring/mb_split.php)。

```php
mb_regex_encoding('UTF-8');
mb_internal_encoding("UTF-8"); 
$v = mb_split('，|。|？',"我，是一个好人。是吧？");
print_r($v);
```
```
Array
(
    [0] => 我
    [1] => 是一个好人
    [2] => 是吧
    [3] => 
)
```

封装成函数，完整代码请参考：[GitHub](https://github.com/mumingv/php/blob/master/demo/string/demo_string_split.php)。

```php
/**
 * 使用标点符号分割文本，返回分割后的字符串数组
 */
function mbStringSplit($string) {
    mb_regex_encoding('UTF-8');
    mb_internal_encoding("UTF-8"); 
    $result = mb_split('。|！|？', $string); 
    if ((count($result) > 0) && (strlen(end($result)) == 0)) {
        array_pop($result);
    }
    return $result;
}
```


## 如何将JSON字符串转换成数组格式字符串并输出到文件中？

使用`var_export`和`file_put_contents`函数，完成代码参考：[GitHub](https://github.com/mumingv/php/tree/master/demo/string/demo_json_to_array)。

关键点在于`var_export`函数第二个参数的使用，其会将输出字符串作为返回值。
```php
$json_str = file_get_contents('input');
$arr = json_decode($json_str, true);
$result = var_export($arr, true);
file_put_contents('output', $result);
```


## 如何进行变量的序列化和反序列化？

序列化是将变量转换为可保存或可传输的字符串的过程；反序列化则相反。

完整代码请参考：[GitHub](https://github.com/mumingv/php/tree/master/demo/string/demo_serialize_and_unserialize)。

### serialize和unserialize函数

```php
$arr = array('a' => 'Apple' ,'b' => 'Banana' , 'c' => 'Coconut');  
// 序列化
$s = serialize($arr);
echo $s.PHP_EOL;  // 输出结果：a:3:{s:1:"a";s:5:"Apple";s:1:"b";s:6:"banana";s:1:"c";s:7:"Coconut";}  
// 反序列化  
$o = unserialize($s);  
print_r($o);
```

```php
a:3:{s:1:"a";s:5:"Apple";s:1:"b";s:6:"Banana";s:1:"c";s:7:"Coconut";}
Array
(
    [a] => Apple
    [b] => Banana
    [c] => Coconut
)
```

使用`serialize`函数可能对特殊字符处理不好，可以使用`base64_encode`函数进行处理。

```php
$arr = array('a' => 'Apple:1' ,'b' => 'Banana"2' , 'c' => 'Coconut\'3');  
  
//序列化数组  
$s = base64_encode(serialize($arr));
echo $s.PHP_EOL;  // 输出结果：a:3:{s:1:"a";s:5:"Apple";s:1:"b";s:6:"banana";s:1:"c";s:7:"Coconut";}  
  
//反序列化  
$o = unserialize(base64_decode($s));  
print_r($o);  
```

```php
YTozOntzOjE6ImEiO3M6NzoiQXBwbGU6MSI7czoxOiJiIjtzOjg6IkJhbmFuYSIyIjtzOjE6ImMiO3M6OToiQ29jb251dCczIjt9
Array
(
    [a] => Apple:1
    [b] => Banana"2
    [c] => Coconut'3
)
```

使用`base64_decode`函数会增加序列化字符串的长度，可以在编码前使用`gzcompress`函数进行压缩。

```php
$arr = array('a' => 'Apple:1' ,'b' => 'Banana"2' , 'c' => 'Coconut\'3');  
  
//序列化数组  
$s = base64_encode(gzcompress(serialize($arr)));
echo $s.PHP_EOL;  // 输出结果：a:3:{s:1:"a";s:5:"Apple";s:1:"b";s:6:"banana";s:1:"c";s:7:"Coconut";}  

//反序列化  
$o = unserialize(gzuncompress(base64_decode($s)));  
print_r($o);
```

```php
eJxLtDK2qi62MrRSSlSyLrYyt1JyLCjISbUyBPGAokkg2sJKySkxDwiVjKDCySDa0krJOT85P6+0RN1YyboWAA91FO0=
Array
(
    [a] => Apple:1
    [b] => Banana"2
    [c] => Coconut'3
)
```


## 如何读取文件并逐行处理？

使用`file_get_contents`和`explode`函数，完整代码请参考：[GitHub](https://github.com/mumingv/php/blob/master/demo/http_get_post/keyword/get_qu_info.php)。

```php
$query_str = file_get_contents("./input_query.txt");
$query_arr = explode("\n", $query_str);
```


## 如何统计代码执行耗时？

```
$start = intval(microtime(true) * 1000);
...
$end = intval(microtime(true) * 1000);
$time = $end - $start;
```










