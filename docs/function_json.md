# [JSON函数](https://github.com/mumingv/php/tree/master/func/json)

## json_decode 对 JSON 格式的字符串进行解码

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.json-decode.php)。

```php
mixed json_decode ( string $json [, bool $assoc = false [, int $depth = 512 [, int $options = 0 ]]] )
```

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


