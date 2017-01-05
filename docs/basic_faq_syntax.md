# 语法FAQ

## php安装后的相关文件和配置在哪里？

### Yum安装

各配置文件/目录如下：

|名称                   |路径                   |
|-----------------------|-----------------------|
|扩展目录               |/usr/lib64/php/modules |

### 手动安装


## php需要安装哪些扩展？

扩展名称和安装方法如下。

```php
# yum install php-mbstring  // mbstring，多字节字符串
# yum install php-redis  // redis，redis扩展
```


## php命令各参数的功能和使用方法？

参考：[PHP手册](http://php.net/manual/zh/features.commandline.php)。

### 

`-h`：查看帮助

```
$ php -h
Usage: php [options] [-f] <file> [--] [args...]
   php [options] -r <code> [--] [args...]
   php [options] [-B <begin_code>] -R <code> [-E <end_code>] [--] [args...]
   php [options] [-B <begin_code>] -F <file> [-E <end_code>] [--] [args...]
   php [options] -- [args...]
   php [options] -a
...
```


### 

`-a`：使用交互式Shell

```bash
$ php -a
Interactive shell

php > echo "Hello World!\n";
Hello World!
php > exit;  # 当作php语句执行
php > exit   # 退出交互式Shell模式
```


### 

`-c`：运行脚本时指定php.ini配置所在的目录或者指定自定义的INI文件

```bash
$ php -c /etc/php.ini.orig hello.php 
Hello World!
```


### 

`-n`：运行脚本时不使用php.ini配置

```bash
$ php -n hello.php 
Hello World!
```


### 

`-d`：运行脚本时设置php.ini配置中的某个配置项的值

<font color="red">如果不指定配置项的值，默认取值为1。</font>

```bash
$ php -d max_execution_time -r '$foo = ini_get("max_execution_time"); var_dump($foo);'
string(1) "1"
```

设置配置项为空值。

```bash
$ php -d max_execution_time= -r '$foo = ini_get("max_execution_time"); var_dump($foo);'
string(0) ""
```

设置配置项为特定值。

```bash
$ php -d max_execution_time=3 -r '$foo = ini_get("max_execution_time"); var_dump($foo);'
string(1) "3"
$ php -d max_execution_time=hello -r '$foo = ini_get("max_execution_time"); var_dump($foo);' 
string(5) "hello"
```


### 

`-e`：为调试器生成扩展信息


### 

`-f`：指定要执行的php脚本

<font color="red">貌似没什么用，因为不管用不用-f参数都能够正确执行脚本。</font>

```bash
$ php -f hello
Hello World!
$ php -f hello.php 
Hello World!
```


### 

`-i`：查询`phpinfo()`信息

```
$ php -i
...
```


### 

`-l`：语法检查

检查通过。

```
$ php -l hello.php 
No syntax errors detected in hello.php
```

检查失败。

```php
$ cat error.php 
<?php
echo "Hello World!"

$ php -l error.php 
PHP Parse error:  syntax error, unexpected end of file, expecting ',' or ';' in error.php on line 4
Parse error: syntax error, unexpected end of file, expecting ',' or ';' in error.php on line 4
Errors parsing error.php
```


### 

`-m`：查询已安装的模块/扩展

```php
$ php -m
[PHP Modules]
bz2
calendar
Core
ctype
curl
date
...

[Zend Modules]
```


### 

`-r <code>`：在命令行运行php代码

```php
$ php -r 'echo "Hello World!\n";'
Hello World!
```

<font color="red">代码一定要使用单引号包含，使用双引号包含的话可能会碰到类似下面的问题。</font>

```php
$ php -r "$foo = 'bar'; echo $foo.PHP_EOL;"   
PHP Parse error:  syntax error, unexpected '=' in Command line code on line 1
```
```php
$ php -r '$foo = "bar"; echo $foo.PHP_EOL;'
bar
```


### 

`-B <begin_code>`：在处理 stdin 之前先执行 PHP 代码

`-R <code>`：对每个输入行都执行 PHP 代码

`-F <file>`：对每个输入行都执行 PHP 文件

`-E <end_code>`：在处理完输入后执行的 PHP 代码

<font color="red">该模式下可以使用内置变量 $argn 和 $argi，分别表示当前处理行的内容以及行号。</font>

示例：计算目录dir及其子目录下所有文件的总行数。

```
$ ls dir
float.c  number.c
```
```php
$ find dir | php -B '$line = 0;' -R '$line += count(file($argn));' -E 'echo "Total Lines: ".$line."\n";'
Total Lines: 22
```

示例：计算目录dir及其子目录下所有文件的行数(每个文件显示一行)。

```php
$ cat run.php 
<?php
echo "$argn's Lines: ".count(file($argn))."\n";
```
```
$ find dir | php -F run.php 
dir's Lines: 0
dir/number.c's Lines: 8
dir/float.c's Lines: 14
```


###  






## 对象作为函数参数传递时，是值传递还是引用传递？

默认情况下是传递引用。参考：[PHP手册](http://www.php.net/manual/zh/language.oop5.references.php)。


## PEAR和PECL有什么区别？

PEAR 是“PHP Extension and Application Repository”的缩写，即PHP扩展和应用仓库。

PECL 是“PHP Extension Community Library”的缩写，即PHP扩展库。

两者的区别：PEAR是PHP的上层扩展，使用PHP语言编写；PECL是PHP的底层扩展，使用C语言编写。


## PHP有哪些打印函数，它们之间的区别是什么？

















