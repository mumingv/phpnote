# [数组函数](https://github.com/mumingv/php/tree/master/func/array)

## 总结

### 构造数组(6)

###### 

|函数名称           |含义                                   |
|-------------------|---------------------------------------|
|array              |构造数组|
|array_fill         |构造数组，需要提供值|
|array_fill_keys    |构造数组，需要提供键数组和值|
|array_combine      |构造数组，需要提供键数组和值数组|
|range              |构造包含范围单元的数组|
|compact            |建立一个数组，包括变量名和它们的值|


### 栈/队列(重复，不统计)

###### 

<font color="red">
入栈操作的返回值为操作后数组的大小；出栈操作的返回值为弹出的元素值。
</font>

|函数名称           |含义                                   |
|-------------------|---------------------------------------|
|array_push         |数组尾部插入元素(入栈)                 |
|array_pop          |数组尾部删除元素(出栈)                 |
|array_unshift      |数组头部插入元素(入栈)                 |
|array_shift        |数组头部删除元素(出栈)                 |


### 增加操作(2)

###### 

|函数名称           |含义                                   |
|-------------------|---------------------------------------|
|array_push         |数组尾部插入元素(入栈)                 |
|array_unshift      |数组头部插入元素(入栈)                 |


### 删除操作(3)

###### 

|函数名称           |含义                                   |
|-------------------|---------------------------------------|
|array_pop          |数组尾部删除元素(出栈)                 |
|array_shift        |数组头部删除元素(出栈)                 |
|array_unique       |移除数组中重复的值|

###### 

<font color="red">
说明：删除数组当中某一个元素的方法有两种：一是使用unset，二是使用array_splice。两者的区别在于：unset不会重排索引，而array_splice会重排索引。
</font>


### 修改操作(2)

###### 

|函数名称               |含义                                   |
|-----------------------|---------------------------------------|
|array_splice           |把数组中的一部分去掉并用其它值取代|
|shuffle                |将数组打乱|


### 查询操作(11)

###### 

|函数名称               |含义                                   |
|-----------------------|---------------------------------------|
|array_column           |返回数组中指定的一列|
|array_count_values     |统计各值出现的次数|
|array_filter           |用回调函数过滤数组中的单元|
|array_key_exists       |检查给定的键名或索引是否存在于数组中|
|array_keys             |返回数组中部分的或所有的键名|
|array_values           |返回数组中所有的值|
|array_rand             |从数组中随机取出一个或多个单元|
|array_search           |在数组中搜索给定的值，如果成功则返回相应的键名|
|array_slice            |从数组中取出一段|
|key_exists             |检查给定的键名或索引是否存在于数组中|
|in_array               |检查数组中是否存在某个值|


### 统计操作(4)

###### 

|函数名称               |含义                                   |
|-----------------------|---------------------------------------|
|count                  |计算数组中的单元数目或对象中的属性个数|
|sizeof(别名)           |计算数组中的单元数目或对象中的属性个数|
|array_sum              |计算数组中所有值的和|
|array_product          |计算数组中所有值的乘积|


### 数组指针(8)

###### 

|函数名称               |含义                                   |
|-----------------------|---------------------------------------|
|key                    |从关联数组中取得键名|
|current                |返回数组中的当前单元|
|pos(别名)              |返回数组中的当前单元|
|prev                   |将数组的内部指针倒回一位|
|next                   |将数组中的内部指针向前移动一位|
|reset                  |将数组的内部指针指向第一个单元|
|end                    |将数组的内部指针指向最后一个单元|
|each                   |返回数组中当前的键／值对并将数组指针向前移动一步|


### 合并拆分数组(3)

###### 

|函数名称               |含义                                   |
|-----------------------|---------------------------------------|
|array_merge            |合并一个或多个数组|
|array_merge_recursive  |递归地合并一个或多个数组|
|array_chunk            |将数组分割成多个小数组                 |


### 其他操作(12)

###### 

|函数名称               |含义                                   |
|-----------------------|---------------------------------------|
|array_change_key_case  |将键名改为全部大写或者全部小写的形式   |
|array_map              |为数组的每个元素应用回调函数|
|array_reduce           |用回调函数迭代地将数组简化为单一的值|
|array_replace          |使用传递的数组替换第一个数组的元素|
|array_replace_recursive|使用传递的数组递归替换第一个数组的元素|
|array_flip             |交换数组中的键和值|
|array_pad              |用值将数组填补到指定长度|
|array_reverse          |返回一个单元顺序相反的数组|
|array_walk             |使用用户自定义函数对数组中的每个元素做回调处理|
|array_walk_recursive   |对数组中的每个成员递归地应用用户函数|
|extract                |从数组中将变量导入到当前的符号表|
|list                   |把数组中的值赋给一些变量|


### 数组排序(12)

###### 

|函数名称           |含义                                   |
|-------------------|---------------------------------------|
|**sort**           |根据value排序，从小到大排列。原key丢弃。|
|rsort              |根据value排序，从大到小排列。原key丢弃。|
|usort              |根据value排序，排列顺序由用户自定义函数指定。原key丢弃。|
|**ksort**          |根据key排序，从小到大排列。原key保留。|
|krsort             |根据key排序，从大到小排列。原key保留。|
|uksort             |根据key排序，排列顺序由用户自定义函数指定。原key保留。|
|**asort**          |根据value排序，从小到大排列。原key保留。|
|arsort             |根据value排序，从大到小排列。原key保留。|
|uasort             |根据value排序，排列顺序由用户自定义函数指定。原key保留。|
|**natsort**        |与sort相比，区别在于该函数使用“自然排序”算法，区分大小写。|
|natcasesort        |与sort相比，区别在于该函数使用“自然排序”算法，不区分大小写。|
|**array_multisort**|对多个数组或多维数组进行排序|


### 数组差集(8)

###### 

|函数名称               |含义                                   |
|-----------------------|---------------------------------------|
|**array_diff**         |只比较value，使用内置比较函数|
|array_udiff            |只比较value，使用用户自定义比较函数|
|**array_diff_key**     |只比较key，使用内置比较函数|
|array_diff_ukey        |只比较key，使用用户自定义比较函数|
|**array_diff_assoc**   |比较key和value，value和key都使用内置比较函数|
|array_diff_uassoc      |比较key和value，value使用内置比较函数，key使用用户自定义比较函数|
|array_udiff_assoc      |比较key和value，value使用用户自定义比较函数，key使用内置比较函数|
|array_udiff_uassoc     |比较key和value，value使用用户自定义比较函数，key使用用户自定义比较函数|


### 数组交集(8)

###### 

|函数名称                |含义                                   |
|------------------------|---------------------------------------|
|**array_intersect**     |只比较value，使用内置比较函数|
|array_uintersect        |只比较value，使用用户自定义比较函数|
|**array_intersect_key** |只比较key，使用内置比较函数|
|array_intersect_ukey    |只比较key，使用用户自定义比较函数|
|**array_intersect_assoc**   |比较key和value，value和key都使用内置比较函数|
|array_intersect_uassoc  |比较key和value，value使用内置比较函数，key使用用户自定义比较函数|
|array_uintersect_assoc  |比较key和value，value使用用户自定义比较函数，key使用内置比较函数|
|array_uintersect_uassoc |比较key和value，value使用用户自定义比较函数，key使用用户自定义比较函数|



## array_change_key_case 返回字符串键名全为小写或大写的数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-change-key-case.php)。

```php
array array_change_key_case ( array $input [, int $case = CASE_LOWER ] )
```

### 示例：将数组的键名改为小写

```php
$input_array = array("FirSt" => 1, "SecOnd" => 4); 
print_r(array_change_key_case($input_array));
```
```php
Array
(
    [first] => 1
    [second] => 4
)
```


### 示例：将数组的键名改为大写

```php
$input_array = array("FirSt" => 1, "SecOnd" => 4); 
print_r(array_change_key_case($input_array, CASE_UPPER));
```
```php
Array
(
    [FIRST] => 1
    [SECOND] => 4
)
```


## array_chunk 将一个数组分割成多个

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-chunk.php)。

```php
array array_chunk ( array $input , int $size [, bool $preserve_keys = false ] )
```

### 示例：将数组分隔成子数组，每个子数组的大小为2

```php
$input_array = array('a', 'b', 'c', 'd', 'e');
print_r(array_chunk($input_array, 2));
```
```php
Array
(
    [0] => Array
    (
        [0] => a
        [1] => b
    )

    [1] => Array
    (
        [0] => c
        [1] => d
    )

    [2] => Array
    (
        [0] => e
    )
)
```


### 示例：将数组分隔成子数组，每个子数组的大小为2，并且保留原数组的key

```php
$input_array = array('a', 'b', 'c', 'd', 'e');
print_r(array_chunk($input_array, 2, true));
```
```php
Array
(
    [0] => Array
    (
        [0] => a
        [1] => b
    )

    [1] => Array
    (
        [2] => c  # 这里的key没有变化
        [3] => d  # 这里的key没有变化
    )

    [2] => Array
    (
        [4] => e  # 这里的key没有变化
    )
)
```


## array_column (PHP5.5) 返回数组中指定的一列

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-column.php)。

```php
array array_column ( array $input , mixed $column_key [, mixed $index_key ] )
```

<font color="red">注：版本要求 >= PHP5.5</font>

### 示例：从二维数组中提取名为`first_name`的列，将其作为一维数组返回

```php
$records = array(
    array(
        'id' => 2135,
        'first_name' => 'John',
        'last_name' => 'Doe',
    ),
    array(
        'id' => 3245,          
        'first_name' => 'Sally',        
        'last_name' => 'Smith',
    ),
    array(
        'id' => 5342,
        'first_name' => 'Jane',
        'last_name' => 'Jones',
    ),
    array(
        'id' => 5623,          
        'first_name' => 'Peter',        
        'last_name' => 'Doe',  
    )
);
$first_names = array_column($records, 'first_name');
print_r($first_names);
```


## array_combine 创建一个数组，用一个数组的值作为其键名，另一个数组的值作为其值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-combine.php)。

```php
array array_combine ( array $keys , array $values )
```

### 示例：根据两个一维数组构造一个二维数组

```php
$a = array('green', 'red', 'yellow');
$b = array('avocado', 'apple', 'banana');
$c = array_combine($a, $b);
print_r($c);
```
```php
Array
(       
    [green] => avocado
    [red] => apple
    [yellow] => banana
)
```


## array_count_values 统计数组中所有的值出现的次数

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-count-values.php)。

```php
array array_count_values ( array $input )
```

### 示例：统计数组中各value出现的次数

```php
$array = array(1, "hello", 1, "world", "hello");
print_r(array_count_values($array));
```
```php
Array   
(
    [1] => 2
    [hello] => 2
    [world] => 1
)
```


## array_diff_assoc 带索引检查计算数组的差集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-diff-assoc.php)。

```php
array array_diff_assoc ( array $array1 , array $array2 [, array $... ] )
```

<font color="red">
说明：</br>
1. 和array_diff相比，不仅会比较值是否相同，也会比较键是否相同; </br>
2. 可以多个数组一起求差集，不仅仅限于两个; </br>
3. 键或值比较的时候，都是统一转换成字符串进行比较; </br>
</font>

### 示例：两个数组的差集，即：$array1 - $array2

```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red"); 
$array2 = array("a" => "green", "yellow", "red");
$result = array_diff_assoc($array1, $array2);
print_r($result);              
```
```php
Array
( 
    [b] => brown
    [c] => blue
    [0] => red
)
```


### 示例：两个数组的差集，数字默认会转换成字符串进行比较

```php
$array1 = array(0, 1, 2);      
$array2 = array("00", "01", "2");
$result = array_diff_assoc($array1, $array2);
print_r($result);              
```
```php
Array
( 
    [0] => 0
    [1] => 1
)
```


### 多个数组的差集，即：$array1 - $array2 - $array3

```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "green", "yellow", "red");
$array3 = array("a" => "green", "b" => "brown");
$result = array_diff_assoc($array1, $array2, $array3);
print_r($result);
```
```php
Array
(
    [c] => blue
    [0] => red
)
```


## array_diff_key 使用键名比较计算数组的差集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-diff-key.php)。

```php
array array_diff_key ( array $array1 , array $array2 [, array $... ] )
```

### 示例：两个数组的差集

```php
$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);
$result = array_diff_key($array1, $array2);
print_r($result);
```
```php
Array
(
    [red] => 2
    [purple] => 4
)
```


### 示例：多个数组的差集

```php
$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);
$array3 = array('purple' => 9);
$result = array_diff_key($array1, $array2, $array3);
print_r($result);
```
```php
Array
(
    [red] => 2
)
```


## array_diff_uassoc 用用户提供的回调函数做索引检查来计算数组的差集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-diff-uassoc.php)。

```php
array array_diff_uassoc ( array $array1 , array $array2 [, array $... ], callable $key_compare_func )
```

### 示例：求两个数组的差集 $array1 - $array2

```php
function key_compare_func($a, $b)
{
    if ($a === $b) {
        return 0;
    }
    return (($a > $b) ? 1 : -1);
}
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "green", "yellow", "red");
$result = array_diff_uassoc($array1, $array2, "key_compare_func");
print_r($result);
```
```php
Array
(
    [b] => brown
    [c] => blue
    [0] => red
)
```


## array_diff_ukey 用回调函数对键名比较计算数组的差集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-diff-ukey.php)。

```php
array array_diff_ukey ( array $array1 , array $array2 [, array $ ... ], callable $key_compare_func )
```

### 示例：两个数组的差集

```php
function key_compare_func($key1, $key2)
{
    if ($key1 == $key2)
        return 0;
    else if ($key1 > $key2)
        return 1;
    else
        return -1;
}
$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);
print_r(array_diff_ukey($array1, $array2, 'key_compare_func'));
```
```php
Array
(
    [red] => 2
    [purple] => 4
)
```


## array_diff 计算数组的差集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-diff.php)。

```php
array array_diff ( array $array1 , array $array2 [, array $... ] )
```

### 示例：两个数组的差集

```php
$array1 = array("a" => "green", "red", "blue", "red", "purple");
$array2 = array("b" => "green", "yellow", "red");
$result = array_diff($array1, $array2);
print_r($result);
```
```php
Array
(
    [1] => blue
    [3] => purple
)
```


### 示例：多个数组的差集

```php
$array1 = array("a" => "green", "red", "blue", "red", "purple");
$array2 = array("b" => "green", "yellow", "red");
$array3 = array(0 => "purple");
$result = array_diff($array1, $array2, $array3);
print_r($result);
```
```php
Array
(
    [1] => blue
)
```


## array_fill_keys 使用指定的键和值填充数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-fill-keys.php)。

```php
array array_fill_keys ( array $keys , mixed $value )
```

```php
$keys = array('foo', 5, 10, 'bar');
$a = array_fill_keys($keys, 'banana');
print_r($a);
```
```php
Array
(
    [foo] => banana
    [5] => banana
    [10] => banana
    [bar] => banana
)
```


## array_fill 用给定的值填充数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-fill.php)。

```php
array array_fill ( int $start_index , int $num , mixed $value )
```

### 示例：填充数组，第一个元素的key为正数

```php
$a = array_fill(5, 6, 'banana');
print_r($a);
```
```php
Array
(
    [5] => banana
    [6] => banana
    [7] => banana
    [8] => banana
    [9] => banana
    [10] => banana
)
```


### 示例：填充数组，第一个元素的key为负数

```php
$b = array_fill(-2, 4, 'pear');
print_r($b);
```
```php
Array
(
    [-2] => pear  # 第1个元素的key对应函数的第1个参数
    [0] => pear   # 第2个元素的key为0
    [1] => pear
    [2] => pear
)
```


## array_filter 用回调函数过滤数组中的单元

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-filter.php)。

```php
array array_filter ( array $array [, callable $callback [, int $flag = 0 ]] )
```

### 示例：过滤数组中基数值或偶数值

```php
function odd($var)
{
    return($var & 1);
}

function even($var)
{
    return(!($var & 1));
}

$array1 = array("a"=>1, "b"=>2, "c"=>3, "d"=>4, "e"=>5);
$array2 = array(6, 7, 8, 9, 10, 11, 12);

echo "Odd :\n";
print_r(array_filter($array1, "odd"));
echo "Even:\n";
print_r(array_filter($array2, "even"));
```
```php
Odd :
Array
(
    [a] => 1
    [c] => 3
    [e] => 5
)
Even:
Array
(
    [0] => 6
    [2] => 8
    [4] => 10
    [6] => 12
)
```


### 示例：不使用自定义的判定函数，去除值为FALSE的项

```php
$array1 = array("apple" => 5, "banana" => 0, "pear" => 6);
print_r(array_filter($array1));
```
```php
Array
(
    [apple] => 5
    [pear] => 6
)
```


## array_flip 交换数组中的键和值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-flip.php)。

```php
array array_flip ( array $trans )
```

### 交换键和值

```php
$trans = array("a" => 1, "b" => 2, "c" => 3);
$trans = array_flip($trans);
print_r($trans);
```
```php
Array
(
    [1] => a
    [2] => b
    [3] => c
)
```


### 交换键和值，含有多个值相同的项，则只保留最后一个

```php
$trans = array("a" => 1, "b" => 2, "c" => 2);
$trans = array_flip($trans);
print_r($trans);
```
```php
Array
(
    [1] => a
    [2] => c  # key为"b"的项被丢弃
)
```


## array_intersect_assoc 带索引检查计算数组的交集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-intersect-assoc.php)。

```php
array array_intersect_assoc ( array $array1 , array $array2 [, array $ ... ] )
```

### 示例：获取两个数组的交集（键和值都相同才会保存到结果中）

```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "green", "b" => "yellow", "blue", "red");
$result_array = array_intersect_assoc($array1, $array2);
print_r($result_array);
```
```php
Array
(
    [a] => green
```


## array_intersect_key 使用键名比较计算数组的交集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-intersect-assoc.php)。

```php
array array_intersect_key ( array $array1 , array $array2 [, array $ ... ] )
```

### 示例：获取两个数组的交集（键相同就会保存到结果中）

```php
$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);
print_r(array_intersect_key($array1, $array2));
```
```php
Array
(
    [blue] => 1
    [green] => 3
)
```


## array_intersect_uassoc 带索引检查计算数组的交集，用回调函数比较索引

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-intersect-assoc.php)。

```php
array array_intersect_uassoc ( array $array1 , array $array2 [, array $ ... ], callable $key_compare_func )
```

### 示例：获取两个数组的交集，用户提供自定义比较函数
```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "GREEN", "B" => "brown", "yellow", "red");
$result = array_intersect_uassoc($array1, $array2, "strcasecmp");
print_r($result);
```
```php
Array
(
    [b] => brown
)
```


## array_intersect_ukey 用回调函数比较键名来计算数组的交集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-intersect-ukey.php)。

```php
array array_intersect_ukey ( array $array1 , array $array2 [, array $... ], callable $key_compare_func )
```

### 示例：获取两个数组的交集

```php
function key_compare_func($key1, $key2)
{
    if ($key1 == $key2)
        return 0;
    else if ($key1 > $key2)
        return 1;
    else
        return -1;
}
$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);
print_r(array_intersect_ukey($array1, $array2, 'key_compare_func'));
```
```php
Array
(
    [blue] => 1
    [green] => 3
)
```


## array_intersect 计算数组的交集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-intersect.php)。

```php
array array_intersect ( array $array1 , array $array2 [, array $ ... ] )
```

### 示例：获取两个数组的交集

```php
$array1 = array("a" => "green", "red", "blue");
$array2 = array("b" => "green", "yellow", "red");
$result = array_intersect($array1, $array2);
print_r($result);
```
```php
Array
(
    [a] => green
    [0] => red
)
```


### 示例：获取多个数组的交集

```php
$array1 = array("a" => "green", "red", "blue");
$array2 = array("b" => "green", "yellow", "red");
$array3 = array("c" => "green", "blue");
$result = array_intersect($array1, $array2, $array3);
print_r($result);
```
```php
Array
(
    [a] => green
)
```


## array_key_exists 检查给定的键名或索引是否存在于数组中

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-key-exists.php)。

```php
bool array_key_exists ( mixed $key , array $search )
```

### 示例：检查key是否在数组当中

```php
$search_array = array('first' => 1, 'second' => 4);
if (array_key_exists('first', $search_array)) {
        echo "The 'first' element is in the array\n";
}
```
```php
The 'first' element is in the array
```


### 示例：isset() 对于数组中为 NULL 的值不会返回 TRUE，而 array_key_exists() 会返回TRUE

```php
$search_array = array('first' => null, 'second' => 4);
if (isset($search_array['first'])) {
    echo "isset: The 'first' element is in the array\n";
} else {
    echo "isset: The 'first' element is not in the array\n";  // 打印该行
}

if (array_key_exists('first', $search_array)) {
    echo "array_key_exists: The 'first' element is in the array\n";  // 打印该行
} else {
    echo "array_key_exists: The 'first' element is not in the array\n";
}
```
```php
isset: The 'first' element is not in the array
array_key_exists: The 'first' element is in the array
```


## array_keys 返回数组中部分的或所有的键名

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-keys.php)。

```php
array array_keys ( array $array [, mixed $search_value [, bool $strict = false ]] )
```

### 示例：返回所有键名

```php
$array = array(0 => 100, "color" => "red");
print_r(array_keys($array));
```
```php
Array
(
    [0] => 0
    [1] => color
)
```


### 示例：返回指定的值对应的键名

```php
$array = array("blue", "red", "green", "blue", "blue");
print_r(array_keys($array, "blue"));
```
```php
Array
(
    [0] => 0
    [1] => 3
    [2] => 4
)
```


### 示例：返回指定的值对应的键名，使用严格的比较

```php
$array = array("blue", "red", "green", "blue", "blue");
print_r(array_keys($array, "blue", true));
```
```php
Array
(
    [0] => 0
    [1] => 3
    [2] => 4
)
```


## array_map 为数组的每个元素应用回调函数

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-map.php)。

```php
array array_map ( callable $callback , array $array1 [, array $... ] )
```

### 示例：一个数组参数

```php
function cube($n)
{
    return($n * $n * $n);
}
$a = array(1, 2, 3, 4, 5); 
$b = array_map("cube", $a);
print_r($b);
```
```php
Array
(
    [0] => 1
    [1] => 8
    [2] => 27
    [3] => 64
    [4] => 125
)
```


### 示例：两个数组参数

```php
function add($m, $n)
{
    return($m + $n);
}
$a = array(1, 2, 3, 4, 5);
$b = array(1, 2, 3, 4, 5);
$c = array_map("add", $a, $b);
print_r($c);
```
```php
Array
(
    [0] => 2
    [1] => 4
    [2] => 6 
    [3] => 8
    [4] => 10
)
```


## array_merge_recursive 递归地合并一个或多个数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-merge-recursive.php)。

### 示例：递归合并数组

```php
$ar1 = array("color" => array("favorite" => "red"), 5);
$ar2 = array(10, "color" => array("favorite" => "green", "blue"));
$result = array_merge_recursive($ar1, $ar2);
print_r($result);
```
```php
Array
(
    [color] => Array
        (
            [favorite] => Array
                (
                    [0] => red
                    [1] => green
                )

            [0] => blue
        )

    [0] => 5
    [1] => 10
)
```


## array_merge 合并一个或多个数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-merge.php)。

```php
array array_merge ( array $array1 [, array $... ] )
```

<font color="red">说明：
1. 如果两个字符串key值相同，则该键名后面的值将覆盖前一个值；
2. 如果两个数字key值相同，则不会丢弃，所有的数字key值均会重新编号；
</font>

### 示例：合并数组

```php
$array1 = array("color" => "red", 2, 4);
$array2 = array("a", "b", "color" => "green", "shape" => "trapezoid", 4);
$result = array_merge($array1, $array2);
print_r($result);
```
```php
Array
(
    [color] => green
    [0] => 2
    [1] => 4
    [2] => a
    [3] => b
    [shape] => trapezoid
    [4] => 4
)
```


## array_multisort 对多个数组或多维数组进行排序

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-multisort.php)。

```php
bool array_multisort ( array &$arr [, mixed $arg = SORT_ASC [, mixed $arg = SORT_REGULAR [, mixed $... ]]] )
```

### 示例：对多个数组进行排序

```php
$ar1 = array(10, 100, 100, 0);
$ar2 = array(1, 3, 2, 4);
array_multisort($ar1, $ar2);
var_export($ar1);
```
```php
array (
    0 => 0,
    1 => 10,
    2 => 100,
    3 => 100,
)
```
```php
var_export($ar2);
```
```php
array (
    0 => 4,
    1 => 1,
    2 => 2,
    3 => 3,
)
```


### 示例：对多维数组按行进行排序

```php
$ar = array(
    array("10", 11, 100, 100, "a"),
    array(   1,  2, "2",   3,   1)
);
array_multisort($ar[0], SORT_ASC, SORT_STRING,
    $ar[1], SORT_DESC, SORT_NUMERIC);
var_export($ar);
```
```php
array (
    0 => 
    array (
        0 => '10',
        1 => 100,
        2 => 100,
        3 => 11,
        4 => 'a',
    ),
    1 => 
    array (
        0 => 1,
        1 => 3,
        2 => '2',
        3 => 2,
        4 => 1,
    ),
)
```


## array_pad 用值将数组填补到指定长度

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-pad.php)。

```php
array array_pad ( array $input , int $pad_size , mixed $pad_value )
```

### 示例：填充数组，在数组尾部进行填充

```php
$input = array(12, 10, 9); 
$result1 = array_pad($input, 5, 0); 
print_r($result1);
```
```php
Array
(
    [0] => 12
    [1] => 10
    [2] => 9
    [3] => 0
    [4] => 0
)
```


### 示例：填充数组，在数组头部进行填充

```php
$result2 = array_pad($input, -7, -1);
print_r($result2);
```
```php
Array
(
    [0] => -1
    [1] => -1
    [2] => -1
    [3] => -1
    [4] => 12
    [5] => 10
    [6] => 9
)
```


### 示例：如果目标长度小于当前长度，则不进行填充

```php
$result3 = array_pad($input, 2, "noop");
print_r($result3);
```
```php
Array
(
    [0] => 12
    [1] => 10
    [2] => 9
)
```


## array_pop 将数组最后一个单元弹出（出栈）

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-pop.php)。

```php
mixed array_pop ( array &$array )
```

### 示例：将元素弹出栈，返回值为弹出的元素

```php
$stack = array("orange", "banana", "apple", "raspberry");
$fruit = array_pop($stack);
print_r($fruit);
echo PHP_EOL;
print_r($stack);
```
```php
raspberry
Array
(
    [0] => orange
    [1] => banana
    [2] => apple
)
```


## array_product 计算数组中所有值的乘积

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-product.php)。

```php
number array_product ( array $array )
```

### 示例：计算数组所有元素的乘积

```php
$a = array(2, 4, 6, 8); 
echo "product(a) = " . array_product($a) . "\n";
```
```php
product(a) = 384
```


### 示例：对空数组计算乘积

```php
$a = array();
echo "product(a) = " . array_product($a) . "\n";
```
```php
product(a) = 1
```


## array_push 将一个或多个单元压入数组的末尾（入栈）

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-push.php)。

```php
int array_push ( array &$array , mixed $var [, mixed $... ] )
```

<font color="red">
说明：<br/>
1. 该函数和语句 "$array[] = $var" 功能相同；<br/>
2. 返回值为元素插入后，数组中元素的总个数；<br/>
</font>

### 示例：入栈操作
```php
$stack = array("orange", "banana");
$number = array_push($stack, "apple", "raspberry");
print_r($stack);
print_r($number);
```
```php
Array
(
    [0] => orange
    [1] => banana
    [2] => apple
    [3] => raspberry
)
4
```


## array_rand 从数组中随机取出一个或多个单元

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-rand.php)。

```php
mixed array_rand ( array $input [, int $num_req = 1 ] )
```

### 示例：随机获取一个元素的键名，返回键名单个值 

```php
$input = array("Neo", "Morpheus", "Trinity", "Cypher", "Tank");
$rand_key = array_rand($input);
print_r($rand_key);  // 4
echo "\n";
```


### 示例：随机获取两个元素的键名，返回包含多个键名的数组

```php
$rand_keys = array_rand($input, 2);
print_r($rand_keys);
```
```php
Array
(
    [0] => 0
    [1] => 2
)
```


## array_reduce 用回调函数迭代地将数组简化为单一的值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-reduce.php)。

```php
mixed array_reduce ( array $input , callable $function [, mixed $initial = NULL ] )
mixed callback ( mixed &$result , mixed $item )
```

### 示例：简化数组，计算数组中所有元素的和

```php
function rsum($v, $w)
{
    $v += $w;
    return $v;
}
$a = array(1, 2, 3, 4, 5);
$b = array_reduce($a, "rsum");
print_r($b);
echo "\n";
```
```php
15
```


### 示例：简化数组，计算数组中所有元素的积

<font color="red">说明：第三个参数为初始值。</font>

```php
function rmul($v, $w)
{
    $v *= $w;
    return $v;
}
$a = array(1, 2, 3, 4, 5);
$c = array_reduce($a, "rmul", 10);
print_r($c);
echo "\n";
```
```php
1200
```


### 示例：简化空数组

```php
function rsum2($v, $w)
{
    $v += $w;
    return $v;
}
$x = array();
$d = array_reduce($x, "rsum2", "No data to reduce");
print_r($d);
echo "\n";
```
```php
No data to reduce
```


## array_replace_recursive 使用传递的数组递归替换第一个数组的元素

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-replace-recursive.php)。

```php
array array_replace_recursive ( array $array1 , array $array2 [, array $... ] )
```

### 示例：使用一个数组作为替换数组

```php
$base = array('citrus' => array( "orange") , 'berries' => array("blackberry", "raspberry"), );
$replacements = array('citrus' => array('pineapple'), 'berries' => array('blueberry'));
$basket = array_replace_recursive($base, $replacements);
print_r($basket);
```
```php
Array
(
    [citrus] => Array
        (
            [0] => pineapple
        )

    [berries] => Array
        (
            [0] => blueberry
            [1] => raspberry
        )
)
```


### 示例：使用两个数组作为替换数组

```php
$base = array('citrus' => array("orange") , 'berries' => array("blackberry", "raspberry"), 'others' => 'banana' );
$replacements = array('citrus' => 'pineapple', 'berries' => array('blueberry'), 'others' => array('litchis'));
$replacements2 = array('citrus' => array('pineapple'), 'berries' => array('blueberry'), 'others' => 'litchis');
$basket = array_replace_recursive($base, $replacements, $replacements2);
print_r($basket);
```
```php
Array
(
    [citrus] => Array
        (
            [0] => pineapple
        )

    [berries] => Array
        (
            [0] => blueberry
            [1] => raspberry
        )

    [others] => litchis
)
```


## array_replace 使用传递的数组替换第一个数组的元素

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-replace.php)。

```php
array array_replace ( array $array1 , array $array2 [, array $... ] )
```

### 示例：使用一个数组作为替换数组

```php
$base = array("orange", "banana", "apple", "raspberry");
$replacements = array(0 => "pineapple", 4 => "cherry");
$replacements2 = array(0 => "grape");
$basket = array_replace($base, $replacements, $replacements2);
print_r($basket);
```
```php
Array
(
    [0] => grape
    [1] => banana
    [2] => apple
    [3] => raspberry
    [4] => cherry
)
```


## array_reverse 返回一个单元顺序相反的数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-reverse.php)。

```php
array array_reverse ( array $array [, bool $preserve_keys = false ] )
```

### 示例：颠倒数组，key值重新编号

```php
$input  = array("php", 4.0, array("green", "red"));
$result = array_reverse($input);
print_r($result);
```
```php
Array
(
    [0] => Array
    (
        [0] => green
        [1] => red
    )

    [1] => 4
    [2] => php
)
```


### 示例：颠倒数组，key值保留

```php
$input  = array("php", 4.0, array("green", "red"));
$result_keyed = array_reverse($input, true);
print_r($result);
```
```php
Array
(
    [2] => Array
    (
        [0] => green
        [1] => red
    )

    [1] => 4
    [0] => php
)
```


## array_search 在数组中搜索给定的值，如果成功则返回相应的键名

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-search.php)。 

### 示例：在数组中搜索值

```php
$array = array(0 => 'blue', 1 => 'red', 2 => 'green', 3 => 'red');
$key = array_search('green', $array); // $key = 2;
echo($key."\n");
$key = array_search('red', $array);   // $key = 1;
echo($key."\n");
```


## array_shift 将数组开头的单元移出数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-shift.php)。

```php
mixed array_shift ( array &$array )
```

### 示例：移除开头的单元，数组的key值会自动调整

```php
$stack = array("orange", "banana", "apple", "raspberry");
$fruit = array_shift($stack);
var_export($stack);
echo PHP_EOL;
```
```php
array (
  0 => 'banana',
  1 => 'apple',
  2 => 'raspberry',
)
```


## array_slice 从数组中取出一段

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-slice.php)。

```php
array array_slice ( array $array , int $offset [, int $length = NULL [, bool $preserve_keys = false ]] )
```

### 示例：截取数组第2个元素一直到最后一个元素

```php
$input = array("a", "b", "c", "d", "e");
$output = array_slice($input, 2);      // returns "c", "d", and "e"
var_export($output);
```
```php
array (
    0 => 'c',
    1 => 'd',
    2 => 'e',
)
```


### 示例：截取数组倒数第二个元素

```php
$input = array("a", "b", "c", "d", "e");
$output = array_slice($input, -2, 1);  // returns "d"
var_export($output);
```
```php
array (
    0 => 'd',
)
```


### 示例：获取数组的前三个元素

```php
$input = array("a", "b", "c", "d", "e");
$output = array_slice($input, 0, 3);   // returns "a", "b", and "c"
var_export($output);
```
```php
array (
    0 => 'a',
    1 => 'b',
    2 => 'c',
)
```


### 示例：获取数组元素的同时，保留原key值

```php
$input = array("a", "b", "c", "d", "e");
print_r(array_slice($input, 2, -1, true));
```
```php
Array
(
    [2] => c
    [3] => d
)
```


## array_splice 把数组中的一部分去掉并用其它值取代

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-splice.php)。

```php
array array_splice ( array &$input , int $offset [, int $length = 0 [, mixed $replacement ]] )
```

<font color="red">
关于参数length：<br/>
1. 如果省略 length，则移除数组中从 offset 到结尾的所有部分；<br/>
2. 如果指定了 length 并且为正值，则移除这么多单元；<br/>
3. 如果指定了 length 并且为负值，则移除从 offset 到数组末尾倒数 length 为止中间所有的单元；<br/>
4. 当给出了 replacement 时要移除从 offset 到数组末尾所有单元时，用 count($input) 作为 length；<br/> 
</font>

### 示例：删除第二个元素

```
$input = array("red", "green", "blue", "yellow");
array_splice($input, 2, 1);
var_export($input);
```
```
array (
  0 => 'red',
  1 => 'green',
  2 => 'yellow',
)
```


### 示例：删除数组中第二个及之后的元素

```php
$input = array("red", "green", "blue", "yellow");
array_splice($input, 2);
var_export($input);
```
```php
array (
    0 => 'red',
    1 => 'green',
)
```


### 示例：删除数组中除了首尾之外的所有元素

```php
$input = array("red", "green", "blue", "yellow");
array_splice($input, 1, -1);
var_export($input);
```php
```
array (
    0 => 'red',
    1 => 'yellow',
)
```


### 示例：替换元素（多个元素替换成一个）

```php
$input = array("red", "green", "blue", "yellow");
array_splice($input, 1, count($input), "orange");
var_export($input);
```
```php
array (
    0 => 'red',
    1 => 'orange',
)
```


### 示例：替换元素（一个元素替换成多个）

```php
$input = array("red", "green", "blue", "yellow");
array_splice($input, -1, 1, array("black", "maroon"));
var_export($input);
```
```php
array (
    0 => 'red',
    1 => 'green',
    2 => 'blue',
    3 => 'black',
    4 => 'maroon',
)
```


### 插入元素

```php
$input = array("red", "green", "blue", "yellow");
array_splice($input, 3, 0, "purple");
var_export($input);
```
```php
array (
    0 => 'red',
    1 => 'green',
    2 => 'blue',
    3 => 'purple',
    4 => 'yellow',
)
```


## array_sum 计算数组中所有值的和

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-sum.php)。

```php
number array_sum ( array $array )
```

### 示例：计算数组中所有值的和，整数求和

```php
$a = array(2, 4, 6, 8);
echo "sum(a) = " . array_sum($a) . "\n"; //sum(a) = 20
```
```php
sum(a) = 20
```


### 示例：计算数组中所有值的和，浮点数求和

```php
$b = array("a" => 1.2, "b" => 2.3, "c" => 3.4);
echo "sum(b) = " . array_sum($b) . "\n"; //sum(b) = 6.9
```
```php
sum(b) = 6.9
```


## array_udiff_assoc 带索引检查计算数组的差集，用回调函数比较数据

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-udiff-assoc.php)。

```php
array array_udiff_assoc ( array $array1 , array $array2 [, array $ ... ], callable $data_compare_func )
```

### 示例：两个数组的差集

```php
class cr {
    private $priv_member;
    function cr($val)
    {
        $this->priv_member = $val;
    }

    static function comp_func_cr($a, $b)
    {
        if ($a->priv_member === $b->priv_member) return 0;
        return ($a->priv_member > $b->priv_member)? 1:-1;
    }
}

$a = array("0.1" => new cr(9), "0.5" => new cr(12), 0 => new cr(23), 1=> new cr(4), 2 => new cr(-15),);
$b = array("0.2" => new cr(9), "0.5" => new cr(22), 0 => new cr(3), 1=> new cr(4), 2 => new cr(-15),);

$result = array_udiff_assoc($a, $b, array("cr", "comp_func_cr"));
print_r($result);
```
```php
Array
(
    [0.1] => cr Object
        (
            [priv_member:cr:private] => 9
        )

    [0.5] => cr Object
        (
            [priv_member:cr:private] => 12
        )

    [0] => cr Object
        (
            [priv_member:cr:private] => 23
        )
)
```


## array_udiff_uassoc 带索引检查计算数组的差集，用回调函数比较数据和索引

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-udiff-uassoc.php)。

```php
array array_udiff_uassoc ( array $array1 , array $array2 [, array $ ... ], callable $data_compare_func , callable $key_compare_func )
```

### 示例：两个数组的差集

```php
class cr {
    private $priv_member;
    function cr($val)
    {
        $this->priv_member = $val;
    }

    static function comp_func_cr($a, $b)
    {
        if ($a->priv_member === $b->priv_member) return 0;
        return ($a->priv_member > $b->priv_member)? 1:-1;
    }

    static function comp_func_key($a, $b)
    {
        if ($a === $b) return 0;
        return ($a > $b)? 1:-1;
    }
}
$a = array("0.1" => new cr(9), "0.5" => new cr(12), 0 => new cr(23), 1=> new cr(4), 2 => new cr(-15),);
$b = array("0.2" => new cr(9), "0.5" => new cr(22), 0 => new cr(3), 1=> new cr(4), 2 => new cr(-15),);

$result = array_udiff_uassoc($a, $b, array("cr", "comp_func_cr"), array("cr", "comp_func_key"));
print_r($result);
```
```php
Array
(
    [0.1] => cr Object
        (
            [priv_member:cr:private] => 9
        )

    [0.5] => cr Object
        (
            [priv_member:cr:private] => 12
        )

    [0] => cr Object
        (
            [priv_member:cr:private] => 23
        )

)
```


## array_udiff 用回调函数比较数据来计算数组的差集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-udiff.php)。

```php
array array_udiff ( array $array1 , array $array2 [, array $ ... ], callable $data_compare_func )
```

### 示例：两个数组的差集

```php
class cr {
    private $priv_member;
    function cr($val)
    {   
        $this->priv_member = $val;
    }   

    static function comp_func_cr($a, $b) 
    {   
        if ($a->priv_member === $b->priv_member) return 0;
        return ($a->priv_member > $b->priv_member)? 1:-1;
    }   
}
$a = array("0.1" => new cr(9), "0.5" => new cr(12), 0 => new cr(23), 1=> new cr(4), 2 => new cr(-15),);
$b = array("0.2" => new cr(9), "0.5" => new cr(22), 0 => new cr(3), 1=> new cr(4), 2 => new cr(-15),);
$result = array_udiff($a, $b, array("cr", "comp_func_cr"));
print_r($result);
```
```php
Array
(
    [0.5] => cr Object
        (
            [priv_member:cr:private] => 12
        )

    [0] => cr Object
        (
            [priv_member:cr:private] => 23
        )
)
```


## array_uintersect_assoc 带索引检查计算数组的交集，用回调函数比较数据

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-uintersect-assoc.php)。

```php
array array_uintersect_assoc ( array $array1 , array $array2 [, array $ ... ], callable $data_compare_func )
```

### 示例：计算数组的交集

<font color="red">说明：函数strcasecmp是不区分大小写比较字符串。</font>

```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "GREEN", "B" => "brown", "yellow", "red");
print_r(array_uintersect_assoc($array1, $array2, "strcasecmp"));
```
```php
Array
(
    [a] => green
)
```


## array_uintersect_uassoc 带索引检查计算数组的交集，用回调函数比较数据和索引

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-uintersect-uassoc.php)。

```php
array array_uintersect_uassoc ( array $array1 , array $array2 [, array $ ... ], callable $data_compare_func , callable $key_compare_func )
```

### 示例：计算数组的交集

```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "GREEN", "B" => "brown", "yellow", "red");
print_r(array_uintersect_uassoc($array1, $array2, "strcasecmp", "strcasecmp"));
```
```php
Array
(
    [a] => green
    [b] => brown
)
```


## array_uintersect 计算数组的交集，用回调函数比较数据

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-uintersect.php)。

```php
array array_uintersect ( array $array1 , array $array2 [, array $ ... ], callable $data_compare_func )
```

### 示例：计算数组的交集

```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "GREEN", "B" => "brown", "yellow", "red");
print_r(array_uintersect($array1, $array2, "strcasecmp"));
```
```php
Array
(
    [a] => green
    [b] => brown
    [0] => red
)
```


## array_unique 移除数组中重复的值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-unique.php)。

```php
array array_unique ( array $array [, int $sort_flags = SORT_STRING ] )
```

### 示例：移除数组中重复的值

```php
$input = array("a" => "green", "red", "b" => "green", "blue", "red");
$result = array_unique($input);
print_r($result);
```
```php
Array
(
    [a] => green
    [0] => red
    [1] => blue
)
```


## array_unshift 在数组开头插入一个或多个单元

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-unshift.php)。

```php
int array_unshift ( array &$array , mixed $var [, mixed $... ] )
```

### 示例：在数组开头插入两个元素

```php
$queue = array("orange", "banana");
array_unshift($queue, "apple", "raspberry");
print_r($queue);
```
```php
Array
(
    [0] => apple
    [1] => raspberry
    [2] => orange
    [3] => banana
) 
```


## array_values 返回数组中所有的值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-values.php)。

```php
array array_values ( array $input )
```

### 示例：获取数组中所有的值

```php
$array = array("size" => "XL", "color" => "gold");
print_r(array_values($array));
```
```php
Array
(
    [0] => XL
    [1] => gold
)
```


## array_walk_recursive 对数组中的每个成员递归地应用用户函数

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-walk-recursive.php)。

```php
bool array_walk_recursive ( array &$input , callable $funcname [, mixed $userdata = NULL ] )
```

### 例：针对数组中的每个成员作用用户自定义函数

```php
$sweet = array('a' => 'apple', 'b' => 'banana');
$fruits = array('sweet' => $sweet, 'sour' => 'lemon');
function test_print($item, $key)
{
    echo "$key holds $item\n";
}
array_walk_recursive($fruits, 'test_print');
```
```php
a holds apple
b holds banana
sour holds lemon
```


## array_walk 使用用户自定义函数对数组中的每个元素做回调处理

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-walk.php)。

```php
bool array_walk ( array &$array , callable $callback [, mixed $userdata = NULL ] )
```

### 示例：针对数组中的每个成员作用用户自定义函数

```php
$fruits = array("d" => "lemon", "a" => "orange", "b" => "banana", "c" => "apple");
function test_alter(&$item1, $key, $prefix)
{
    $item1 = "$prefix: $item1";
}
function test_print($item2, $key)
{
    echo "$key. $item2\n";
}
echo "Before ...:\n";
array_walk($fruits, 'test_print');
array_walk($fruits, 'test_alter', 'fruit');
echo "... and after:\n";
array_walk($fruits, 'test_print');
```
```php
Before ...:
d. lemon
a. orange
b. banana
c. apple
... and after:
d. fruit: lemon
a. fruit: orange
b. fruit: banana
c. fruit: apple
```


## array 新建一个数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array.php)。

```php
array array ([ mixed $... ] )
```

### 示例：创建一个数组

```php
$fruits = array (
    "fruits"  => array("a" => "orange", "b" => "banana", "c" => "apple"),
    "numbers" => array(1, 2, 3, 4, 5, 6),
    "holes"   => array("first", 5 => "second", "third")
);
print_r($fruits);
```
```php
Array
(
    [fruits] => Array
        (
            [a] => orange
            [b] => banana
            [c] => apple
        )

    [numbers] => Array
        (
            [0] => 1
            [1] => 2
            [2] => 3
            [3] => 4
            [4] => 5
            [5] => 6
        )

    [holes] => Array
        (
            [0] => first
            [5] => second
            [6] => third
        )
)
```


### 示例：访问双引号内的数组

<font color="red">说明：双引号内使用数组，需要使用大括号括起来。</font>

```php
$foo = array('bar' => 'baz');
echo "Hello {$foo['bar']}!"; // Hello baz!
```
```php
Hello baz!
```


## arsort 对数组进行逆向排序并保持索引关系

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.arsort.php)。

```php
bool arsort ( array &$array [, int $sort_flags = SORT_REGULAR ] )
```

### 示例：数组逆向排序

```php
$fruits = array("d" => "lemon", "a" => "orange", "b" => "banana", "c" => "apple");
arsort($fruits);
foreach ($fruits as $key => $val) {
    echo "$key = $val\n";
}
```
```php
a = orange
d = lemon
b = banana
c = apple
```


## asort 对数组进行排序并保持索引关系

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.asort.php)。

```php
bool asort ( array &$array [, int $sort_flags = SORT_REGULAR ] )
```

### 示例：数组排序

```php
$fruits = array("d" => "lemon", "a" => "orange", "b" => "banana", "c" => "apple");
asort($fruits);
foreach ($fruits as $key => $val) {
    echo "$key = $val\n";
}
```
```php
c = apple
b = banana
d = lemon
a = orange
```


## compact 建立一个数组，包括变量名和它们的值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.compact.php)。

```php
array compact ( mixed $varname [, mixed $... ] )
```

### 示例：根据变量创建数组

```php
$country = 'China';
$city  = "Beijing";
$company = 'Baidu';

$location = array('country', 'city');
$array = compact($location, 'company');
print_r($array);
```
```php
Array
(
    [country] => China
    [city] => Beijing
    [company] => Baidu
)
```


## count 计算数组中的单元数目或对象中的属性个数

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.count.php)。

```php
int count ( mixed $var [, int $mode = COUNT_NORMAL ] )
```

### 示例：获取数组中的单元数目

```php
$a[0] = 1;
$a[1] = 3;
$a[2] = 5;
$result = count($a);
print_r($result);  // 3

$result = count(null);
print_r($result);  // 0

$result = count(false);
print_r($result);  // 1
```


### 示例：获取数组中的单元数目(递归)

```php
$food = array('fruits' => array('orange', 'banana', 'apple'),
              'veggie' => array('carrot', 'collard', 'pea'));
echo count($food, COUNT_RECURSIVE);  // 8
echo count($food);  // 2
```


## current 返回数组中的当前单元

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.current.php)。

```php
mixed current ( array &$array )
```

<font color="red">
说明：<br/>
1. 该函数返回FALSE或者是等同于FALSE的数值，比较需要使用全等号"==="；<br/>
2. 该函数不改变数组内部指针的值；<br/>
</font>

### 示例：

```php
$transport = array('foot', 'bike', 'car', 'plane');
$mode = current($transport);
echo $mode . PHP_EOL; //foot

$mode = next($transport);
echo $mode . PHP_EOL; //bike

$mode = current($transport);
echo $mode . PHP_EOL; //bike

$mode = prev($transport);
echo $mode . PHP_EOL; //foot

$mode = end($transport);
echo $mode . PHP_EOL; //plane

$mode = current($transport);
echo $mode . PHP_EOL; //plane

$mode = reset($transport);
echo $mode . PHP_EOL; //foot

$arr = array();
var_dump(current($arr)); // bool(false)

$arr = array(array());
var_dump(current($arr)); // array(0) { } 
```


## each 返回数组中当前的键／值对并将数组指针向前移动一步

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.each.php)。

```php
mixed each ( array &$array )
```

### 示例：使用each

```php
$transport = array('foot', 'bike', 'car', 'plane');
$return = each($transport);
print_r($return);
$return = each($transport);
print_r($return);
```
```php
Array
(
    [1] => foot
    [value] => foot
    [0] => 0
    [key] => 0
)
Array
(
    [1] => bike
    [value] => bike
    [0] => 1
    [key] => 1
)
```


### 示例：遍历数组(使用list和each)

```php
$fruit = array('a' => 'apple', 'b' => 'banana', 'c' => 'cranberry');
reset($fruit);
while (list($key, $val) = each($fruit)) {
    echo "$key => $val\n";
}
```
```php
a => apple
b => banana
c => cranberry
```


## end 将数组的内部指针指向最后一个单元

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.end.php)。

```php
mixed end ( array &$array )
```

### 示例：

```php
$fruits = array('apple', 'banana', 'cranberry');
echo end($fruits);  // cranberry
```


## extract 从数组中将变量导入到当前的符号表

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.extract.php)。

```php
int extract ( array &$var_array [, int $extract_type = EXTR_OVERWRITE [, string $prefix = NULL ]] )
```

### 示例：从数组中导入变量

```php
$size = "large";
$var_array = array("color" => "blue",
                   "size"  => "medium",
                   "shape" => "sphere");
extract($var_array, EXTR_PREFIX_SAME, "wddx");
echo "$color, $size, $shape, $wddx_size\n";
```
```php
blue, large, sphere, medium
```


## in_array 检查数组中是否存在某个值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.in-array.php)。

```php
bool in_array ( mixed $needle , array $haystack [, bool $strict = FALSE ] )
```

### 示例：字符串是区分大小写的

```php
$os = array("Mac", "NT", "Irix", "Linux");
if (in_array("mac", $os)) {
    echo "Got mac";
} else {
    echo "Can't got mac" . PHP_EOL; //Can't got mac
}
```

### 示例：数值型数据

```php
if (in_array(1, array(0, 1))) {
    echo "1 is in array(0, 1)", PHP_EOL;
} else {
    echo "1 is not in array(0, 1)", PHP_EOL;
}
```
```php
1 is in array(0, 1)
```


## key_exists 检查给定的键名或索引是否存在于数组中

说明：该函数是array_key_exists的别名。


## key 从关联数组中取得键名

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.key.php)。

```php
mixed key ( array &$array )
```

<font color="red">
说明：<br/>
1. key和current都不会移动数组指针；<br/>
2. key返回当前数组指针的key，current返回当前数组指针的value；<br/>
</font>

### 示例：从关联数组中获取键名

```php
$array = array(
    'fruit1' => 'apple',
    'fruit2' => 'orange',
    'fruit3' => 'grape',
    'fruit4' => 'apple',
    'fruit5' => 'apple',
);
while ($fruit_name = current($array)) {
    if ($fruit_name == 'apple') {
        echo key($array)."\n";
    }
    next($array);
}
```
```php
fruit1
fruit4
fruit5
```


## krsort 对数组按照键名逆向排序

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.krsort.php)。

```php
bool krsort ( array &$array [, int $sort_flags = SORT_REGULAR ] )
```

### 示例：数组按照键名逆向排序

```php
$fruits = array("d"=>"lemon", "a"=>"orange", "b"=>"banana", "c"=>"apple");
krsort($fruits);
foreach ($fruits as $key => $val) {
    echo "$key = $val\n";
}
```
```php
d = lemon
c = apple
b = banana
a = orange
```


## ksort 对数组按照键名排序

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.ksort.php)。

```php
bool ksort ( array &$array [, int $sort_flags = SORT_REGULAR ] )
```

### 示例：数组按照键名排序

```php
$fruits = array("d" => "lemon", "c" => "orange", "b" => "banana", "a" => "apple");
ksort($fruits);
foreach ($fruits as $key => $val) {
    echo "fruits[" . $key . "] = " . $val . "\n";
}
```
```php
fruits[a] = apple
fruits[b] = banana
fruits[c] = orange
fruits[d] = lemon
```


## list 把数组中的值赋给一些变量

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.list.php)。

```php
array list ( mixed $varname [, mixed $... ] )
```

### 示例：一般用法

```php
$info = array('coffee', 'brown', 'caffeine');

// 列出所有变量
list($drink, $color, $power) = $info;
echo "$drink is $color and $power makes it special.\n"; //coffee is brown and caffeine makes it special.

// 列出部分变量
list($drink, , $power) = $info;
echo "$drink has $power.\n"; //coffee has caffeine.

// 列出部分变量
list( , , $power) = $info;
echo "I need $power!\n"; //I need caffeine!

// list()不能对字符串起作用
list($bar) = "abcde";
var_dump($bar); // NULL
```


### 示例：嵌套list

```php
list($a, list($b, $c)) = array(1, array(2, 3));
var_dump($a, $b, $c); //int(1) int(2) int(3)
```


### 示例：返回值

```php
$arr = list($a, list($b, $c)) = array(1, array(2, 3));
var_export($arr);
echo PHP_EOL;
```
```php
array (
  0 => 1,
  1 => 
  array (
      0 => 2,
      1 => 3,
  ),
)
```


## natcasesort “自然排序”算法对数组进行不区分大小写字母的排序

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.natcasesort.php)。

```php
bool natcasesort ( array &$array )
```

### 示例：“普通排序”和“自然排序”的对比

```php
$array1 = $array2 = array('IMG0.png', 'img12.png', 'img10.png', 'img2.png', 'img1.png', 'IMG3.png');

sort($array1);
echo "Standard sorting\n";
print_r($array1);

natcasesort($array2);
echo "\nNatural order sorting (case-insensitive)\n";
print_r($array2);
```

```php
Standard sorting
Array
(
    [0] => IMG0.png
    [1] => IMG3.png
    [2] => img1.png
    [3] => img10.png
    [4] => img12.png
    [5] => img2.png
)

Natural order sorting (case-insensitive)
Array
(
    [0] => IMG0.png
    [4] => img1.png
    [3] => img2.png
    [5] => IMG3.png
    [2] => img10.png
    [1] => img12.png
)
```


## natsort “自然排序”算法对数组排序

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.natsort.php)。

```php
bool natsort ( array &$array )
```

### 示例：“普通排序”和“自然排序”的对比

```php
$array1 = $array2 = array("img12.png", "img10.png", "img2.png", "img1.png");

asort($array1);
echo "Standard sorting\n";
print_r($array1);

natsort($array2);
echo "\nNatural order sorting\n";
print_r($array2);
```
```php
Standard sorting
Array
(
    [3] => img1.png
    [1] => img10.png
    [0] => img12.png
    [2] => img2.png
)

Natural order sorting
Array
(
    [3] => img1.png
    [2] => img2.png
    [1] => img10.png
    [0] => img12.png
) 
```


## next 将数组中的内部指针向前移动一位

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.next.php)。

```php
mixed next ( array &$array )
```

### 示例：参考 array_current.php

```php
$transport = array('foot', 'bike', 'car', 'plane');
echo current($transport)."\n";  // foot
echo next($transport)."\n";     // bike
echo next($transport)."\n";     // car
echo prev($transport)."\n";     // bike
echo end($transport)."\n";      // plane
```


## pos 返回数组中的当前单元

说明：该函数是current的别名。


## prev 将数组的内部指针倒回一位

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.prev.php)。

```php
mixed prev ( array &$array )
```

### 示例：参考 array_current.php

```php
$transport = array('foot', 'bike', 'car', 'plane');
echo current($transport)."\n";  // foot
echo next($transport)."\n";     // bike
echo next($transport)."\n";     // car
echo prev($transport)."\n";     // bike
echo end($transport)."\n";      // plane
```


## range 建立一个包含指定范围单元的数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.range.php)。

```php
array range ( mixed $start , mixed $limit [, number $step = 1 ] )
```

### 示例：生成数组

```php
foreach (range(0, 10, 1) as $number) {
        echo $number . " ";  // 0 1 2 3 4 5 6 7 8 9 10 
}
echo PHP_EOL;
```


## reset 将数组的内部指针指向第一个单元

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.reset.php)。

```php
mixed reset ( array &$array )
```

### 示例：使用reset

```php
$array = array('step one', 'step two', 'step three', 'step four');
next($array);
next($array);
reset($array);
echo current($array)."\n";
```
```php
step one
```


## rsort 对数组逆向排序

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.rsort.php)。

```php
bool rsort ( array &$array [, int $sort_flags = SORT_REGULAR ] )
```

<font color="red">说明：该函数将使得所有的key都重新设置。</font>

### 示例：

```php
$fruits = array("lemon", "orange", "banana", "apple");
rsort($fruits);
foreach ($fruits as $key => $val) {
    echo "fruits[" . $key . "] = " . $val . "\n";
}
```
```php
fruits[0] = orange
fruits[1] = lemon
fruits[2] = banana
fruits[3] = apple
```


### 示例：自然排序且不区分大小写

```php
$fruits = array(
    "Orange1", "orange2", "Orange3", "orange20"
);
rsort($fruits, SORT_NATURAL | SORT_FLAG_CASE);
foreach ($fruits as $key => $val) {
    echo "fruits[" . $key . "] = " . $val . "\n";
} 
```
```php
fruits[0] = orange20
fruits[1] = Orange3
fruits[2] = orange2
fruits[3] = Orange1
```


## shuffle 将数组打乱

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function..php)。

```php
bool shuffle ( array &$array )
```

### 示例：打乱数组

```php
$numbers = range(1, 20);
shuffle($numbers);
foreach ($numbers as $number) {
    echo "$number ";
}
```
```php
12 19 18 3 2 14 13 15 10 9 17 7 1 5 20 16 4 11 6 8 
```


## sizeof 计算数组中的单元数目或对象中的属性个数

说明：该函数是count的别名。


## sort 对数组排序

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.sort.php)。

```php
bool sort ( array &$array [, int $sort_flags = SORT_REGULAR ] )
```

### 示例：数组排序

```php
$fruits = array("lemon", "orange", "banana", "apple");
sort($fruits);
foreach ($fruits as $key => $val) {
    echo "fruits[" . $key . "] = " . $val . "\n";
}
```
```php
fruits[0] = apple
fruits[1] = banana
fruits[2] = lemon
fruits[3] = orange
```


### 示例：自然排序且不区分大小写

```php
$fruits = array(
    "Orange1", "orange2", "Orange3", "orange20"
);
sort($fruits, SORT_NATURAL | SORT_FLAG_CASE);
foreach ($fruits as $key => $val) {
    echo "fruits[" . $key . "] = " . $val . "\n";
}
```
```php
fruits[0] = Orange1
fruits[1] = orange2
fruits[2] = Orange3
fruits[3] = orange20
```


## uasort 使用用户自定义的比较函数对数组中的值进行排序并保持索引关联

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.uasort.php)。

```php
bool uasort ( array &$array , callable $cmp_function )
```

### 示例：数组排序(使用自定义函数进行比较)

```php
function cmp($a, $b) {
    if ($a == $b) {
        return 0;
    }
    return ($a < $b) ? -1 : 1;
}
$array = array('a' => 4, 'b' => 8, 'c' => -1, 'd' => -9, 'e' => 2, 'f' => 5, 'g' => 3, 'h' => -4);
uasort($array, 'cmp');
print_r($array);
```
```php
Array
(
    [d] => -9
    [h] => -4
    [c] => -1
    [e] => 2
    [g] => 3
    [a] => 4
    [f] => 5
    [b] => 8
)
```


## uksort 使用用户自定义的比较函数对数组中的键名进行排序

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.uksort.php)。

```php
bool uksort ( array &$array , callable $cmp_function )
```

### 示例：根据数组键名排序

```php
function cmp($a, $b)
{
    $a = preg_replace('@^(a|an|the) @', '', $a);
    $b = preg_replace('@^(a|an|the) @', '', $b);
    return strcasecmp($a, $b);
}
$a = array("John" => 1, "the Earth" => 2, "an apple" => 3, "a banana" => 4);
uksort($a, "cmp");
foreach ($a as $key => $value) {
    echo "$key: $value\n";
}
```
```php
an apple: 3
a banana: 4
the Earth: 2
John: 1
```


## usort 使用用户自定义的比较函数对数组中的值进行排序

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.usort.php)。

```php
bool usort ( array &$array , callable $cmp_function )
```

### 示例：数组排序

```php
function cmp($a, $b)
{
    if ($a == $b) {
        return 0;
    }
    return ($a < $b) ? -1 : 1;
}
$a = array(3, 2, 5, 6, 1);
usort($a, "cmp");
foreach ($a as $key => $value) {
    echo "$key: $value\n";
}
```
```php
0: 1
1: 2
2: 3
3: 5
4: 6
```

