# [JSON函数](https://github.com/mumingv/php/tree/master/func/json)

## json_decode 对 JSON 格式的字符串进行解码

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.json-decode.php)。

```php
mixed json_decode ( string $json [, bool $assoc = false [, int $depth = 512 [, int $options = 0 ]]] )
```

<font color="red">说明：本函数只能接受UTF-8编码的数据。</font>

### 示例：常用用法，将JSON字符串转换成一个PHP数组

```php
$json = '{"a":1,"b":2,"c":3,"d":4,"e":5}';
print_r(json_decode($json, true));
```
```php
Array
(
    [a] => 1
    [b] => 2
    [c] => 3
    [d] => 4
    [e] => 5
)
```


### 示例：非常用用法，将JSON字符串转换成一个PHP对象

<font color="red">说明：如果对象中的元素名称含有特殊字符，则可以使用 $obj->{'key-name'} 的方式进行访问。</font>

```php
$json = '{"a":1,"b":2,"c":3,"d":4,"e":5,"foo-bar":6}';
$obj = json_decode($json);
print_r($obj);
print_r($obj->c);  // 访问对象的元素
echo "\n";
print_r($obj->{'foo-bar'});  // 访问对象的元素
echo "\n";
```
```php
stdClass Object
(
    [a] => 1
    [b] => 2
    [c] => 3
    [d] => 4
    [e] => 5
)
3
6
```


### 示例：超大整数的处理

<font color="red">
说明：对于超大整数，可以有两种处理方式：<br/>
1. 默认会转换成浮点数；<br/>
2. 使用参数 JSON_BIGINT_AS_STRING 将其转换成字符串；<br/>
</font>

```php
$json = '{"number": 12345678901234567890}';
var_dump(json_decode($json));
var_dump(json_decode($json, false, 512, JSON_BIGINT_AS_STRING));
/*
object(stdClass)#2 (1) {
  ["number"]=>
  float(1.2345678901235E+19)
}
object(stdClass)#2 (1) {
  ["number"]=>
  string(20) "12345678901234567890"
}
```


### 示例：深度错误

```php
$json = json_encode(
    array(
        1 => array(
            'English' => array(
                'One',
                'January'
            ),
            'French' => array(
                'Une',
                'Janvier'
            )
        )
    )
);
// 获取JSON相关的错误常量数组(key为常量值，value为常量名称)
$constants = get_defined_constants(true);
$json_errors = array();
foreach ($constants["json"] as $name => $value) {
    if (!strncmp($name, "JSON_ERROR_", 11)) {
        $json_errors[$value] = $name;
    }
}
foreach (range(4, 3, -1) as $depth) {
    var_dump(json_decode($json, true, $depth));
    echo 'Last error: ', $json_errors[json_last_error()], PHP_EOL, PHP_EOL;
}
```
```php
array(1) {
  [1]=>
  array(2) {
    ["English"]=>
    array(2) {
      [0]=>
      string(3) "One"
      [1]=>
      string(7) "January"
    }
    ["French"]=>
    array(2) {
      [0]=>
      string(3) "Une"
      [1]=>
      string(7) "Janvier"
    }
  }
}
Last error: JSON_ERROR_NONE

NULL
Last error: JSON_ERROR_DEPTH
```


## json_encode 对变量进行 JSON 编码

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.json_encode.php)。

```php
string json_encode ( mixed $value [, int $options = 0 [, int $depth = 512 ]] )
```

### 示例：将数组转换成JSON字符串(无中文字符)

```php
$arr = array ('a'=>1,'b'=>2,'c'=>3,'d'=>4,'e'=>5);
echo json_encode($arr);
```
```php
{"a":1,"b":2,"c":3,"d":4,"e":5} 
```


### 示例: 将数组转换成JSON字符串(含中文字符)

```php
$arr = array(
    "id" => 1173,
    "collegeName" => "北京大学",
    "majorName" => "法学",
);
$json_str = json_encode($arr, JSON_UNESCAPED_UNICODE);
print_r($json_str);
```
```php
{"id":1173,"collegeName":"北京大学","majorName":"法学"}
```


## json_last_error_msg 返回 JSON 编码或解码时最后发生的错误信息

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.json-last-error-msg.php)。

```php
string json_last_error_msg ( void )
```

### 示例

略。


## json_last_error 返回 JSON 编码或解码时最后发生的错误

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.json-last-error.php)。

```php
int json_last_error ( void )
```

### 示例：对JSON字符串进行解码，并确认解码过程中是否发生问题

```php
// 一个有效的 json 字符串
$json[] = '{"Organization": "PHP Documentation Team"}';
// 一个无效的 json 字符串会导致一个语法错误，在这个例子里我们使用 ' 代替了 " 作为引号
$json[] = "{'Organization': 'PHP Documentation Team'}";
// 遍历数组中的JSON字符串，并进行解码
foreach ($json as $string) {
    echo 'Decoding: ' . $string;
    json_decode($string, true);
    switch (json_last_error()) {
        // 没有错误发生
        case JSON_ERROR_NONE:
            echo ' - No errors';
            break;
        // 到达了最大堆栈深度
        case JSON_ERROR_DEPTH:
            echo ' - Maximum stack depth exceeded';
            break;
        // 无效或异常的 JSON
        case JSON_ERROR_STATE_MISMATCH:
            echo ' - Underflow or the modes mismatch';
            break;
        // 控制字符错误，可能是编码不对
        case JSON_ERROR_CTRL_CHAR:
            echo ' - Unexpected control character found';
            break;
        // 语法错误
        case JSON_ERROR_SYNTAX:
            echo ' - Syntax error, malformed JSON';
            break;
        // 异常的 UTF-8 字符，也许是因为不正确的编码
        case JSON_ERROR_UTF8:
            echo ' - Malformed UTF-8 characters, possibly incorrectly encoded';
            break;
        // One or more recursive references in the value to be encoded
        case JSON_ERROR_RECURSION:
            echo ' - One or more recursive references in the value to be encoded';
            break;
        // One or more NAN or INF values in the value to be encoded
        case JSON_ERROR_INF_OR_NAN:
            echo ' - One or more NAN or INF values in the value to be encoded';
            break;
        // A value of a type that cannot be encoded was given
        case JSON_ERROR_UNSUPPORTED_TYPE:
            echo ' - A value of a type that cannot be encoded was given';
            break;
        // 未定义错误
        default:
            echo ' - Unknown error';
            break;
    }
    echo PHP_EOL;
}
```
```php
Decoding: {"Organization": "PHP Documentation Team"} - No errors
Decoding: {'Organization': 'PHP Documentation Team'} - Syntax error, malformed JSON
```


