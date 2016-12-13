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




