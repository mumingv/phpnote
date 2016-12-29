# [Filesystem 文件系统](https://github.com/mumingv/php/tree/master/func/filesystem)

## file_get_contents 将整个文件读入一个字符串

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.file-get-contents.php)。

```php
string file_get_contents ( string $filename [, bool $use_include_path = false [, resource $context [, int $offset = -1 [, int $maxlen ]]]] )
```

### 示例：读取文件内容，存放到字符串中

```php
// 读取文件内容，存放到字符串中
$data_str = file_get_contents("data/school_special.txt");
// 字符串按换行符分割，形成数组，文件的每一行对应数组的一个元素
$data_arr = explode("\n", $data_str);
```


## file_put_contents 将一个字符串写入文件

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.file-put-contents.php)。

```php
int file_put_contents ( string $filename , mixed $data [, int $flags = 0 [, resource $context ]] )
```

### 示例：覆盖方式写文件

```php
$file = "test.txt";            
$data = "filesystem_file_put_contents overwrite\n";                                                                                  
file_put_contents($file, $data);
```


### 示例：追加方式写文件

```php
$data = "filesystem_file_put_contents append\n";                                                                                     
file_put_contents($file, $data, FILE_APPEND | LOCK_EX);
```








