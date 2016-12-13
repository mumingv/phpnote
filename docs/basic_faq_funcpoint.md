# 功能FAQ

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


## 如何将Json字符串转换成数组格式字符串并输出到文件中？

使用`var_export`和`file_put_contents`函数，完成代码参考：[GitHub](https://github.com/mumingv/php/tree/master/demo/string/demo_json_to_array)。

关键点在于`var_export`函数第二个参数的使用，其会将输出字符串作为返回值。
```php
$json_str = file_get_contents('input');
$arr = json_decode($json_str, true);
$result = var_export($arr, true);
file_put_contents('output', $result);
```




