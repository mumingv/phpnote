# 字符串操作与正则表达式

## 创建一个示例应用程序：智能表单邮件

`mail()`函数用来发送电子邮件，函数原型：
```clike
bool mail(string $to, string $subject, string $message [, string $additional_headers [, string $additional_parameters]]);
```

参考：RFC822协议。

如果需要附加多个邮件头，只要使用换行符`\r\n`将它们隔开就可以。


## 字符串的格式化

### 字符串的整理：`trim()` `ltrim()` `rtrim()` `chop()`

说明：`chop()`是`rtrim()`的别名。


### 格式化字符串以便显示：`nl2br()` `print()`

1. 使用HTML格式化：`nl2br()`；
2. 为打印输出而格式化字符串：`print()` `printf()` `sprintf()`
3. 改变字符串中的字母大小写：`strtoupper()` `strtolower()` `ucfirst()` `ucwords()`


### 格式化字符串以便存储：`addslashes()` `stripslashes()`

数据库会将一些字符理解为控制字符，如：`''` `""` `\` `NULL`。

这两个函数主要是将字符串进行数据库存取操作时使用。将字符串存入数据库时，使用`addslashes()`函数进行格式化；从数据库读取字符串后，使用`stripslashes()`函数进行恢复。

PHP配置`magic_quotes_gpc`（可以在php.ini文件中找到），其用于自动添加或去除反斜杠。

说明：`gpc`是`GET``POST``Cookie`这三者的缩写，取各单词第一个字母。

可以使用`get_magic_quotes_gpc()`函数检查配置`magic_quotes_gpc`是否启用，如果启用了，在显示用户数据之前，需要调用`stripslashes()`函数，否则这些反斜杠会被显示出来。


## 用字符串函数连接和分割字符串

### 使用函数`explode()` `implode()` `join()`

1. `explode()`函数将字符串分割为数组；
2. `implode()`函数将数组值合并为字符串；
3. `join()`函数是`implode()`的别名；


### 使用`strtok()`函数

`strtok()`函数一次只从字符串中获取一些片段（也称为“令牌”）。


### 使用`substr()`函数

`substr()`函数获取子字符串。


## 字符串的比较

### 字符串的排序：`strcmp()` `strcasecmp()` `strnatcmp()` `strnatcasecmp()`

`strcmp()`函数用于比较字符串，区分大小写；`strcasecmp()`是其不区分大小写比较的版本。

`strnatcmp()`函数用于按自然顺序比较字符串，区分大小写；`strnatcasecmp()`是其不区分大小写比较的版本。

注：自然顺序示例：12比2要大。[阅读材料](http://www.naturalordersort.org/)


### 获取字符串的长度：`strlen()`

略。


## 使用字符串函数匹配和替换子字符串

### 在字符串中查找子字符串：`strstr()` `strchr()` `strrchr()` `stristr()`

`strstr()`函数用于查找自字符串。

`strchr()`函数是`strstr()`的别名。

`strrstr()`函数用于反向查找子字符串。

`stristr()`函数是`strstr()`不区分大小写的版本。


### 查找子字符串的位置：`strpos()` `strrpos()`

`strpos()`函数用于查找子字符串在字符串中的位置。

`strrpos()`函数用于反向查找子字符串在字符串中的位置。

说明：`strpos()`函数与`strstr()`相比，速度要快一些。


### 替换子字符串：`str_replace()` `substr_replace()`

`str_replace()`函数用于子字符串替换。函数原型如下：
```clike
mixed str_replace ( mixed $search , mixed $replace , mixed $subject [, int &$count ] )
```

`substr_replace()`函数用于替换字符串的子串。
```clike
mixed substr_replace ( mixed $string , mixed $replacement , mixed $start [, mixed $length ] )
```


## 正则表达式介绍

PHP支持两种风格的正则表达式语法：POSIX和Perl。

对于Perl风格的正则表达式，可以参考：[PCRE](http://www.php.net/pcre)

本节主要讲解POSIX风格的正则表达式，具体语法请参考：[《Linux Shell编程》](http://123.56.21.232:8102/#docs/regex_extended)


## 用正则表达式查找子字符串：`ereg()` `eregi()`

略。


## 用正则表达式替换子字符串：`ereg_replace()` `eregi_replace()`

略。


## 使用正则表达式分割字符串：`split()`

略。

## 进一步学习

待整理：正则表达式函数。

参考资料：
1. [regexp的man页面](http://man.cx/regex)；
2. [devshed](http://www.devshed.com/)
3. [phpbuilder](http://www.phpbuilder.com/)

