# 数据的存储和检索

## 保存数据以便后期使用

存储数据两种基本方法：
1. 保存到普通文件（flat file）
2. 保存到数据库（如：MySQL）

说明：PHP的文件读写操作与其他大多数编程语言的操作方式都是类似的。


## 存储和检索Bob的订单

略。


## 文件处理

文件处理操作主要就是指读写文件，处理步骤也是固定的，如下：
1. 打开文件；
2. 读/写数据；
3. 关闭文件；


## 打开文件 `fopen()`

### 选择文件模式

打开一个文件，要考虑三件事情：
1. 打开文件的目的是只读、只写、还是读写；
2. 对于写文件，是使用覆盖方式还是追加方式；
3. 对于写文件，是使用二进制方式还是纯文本方式；


### 使用fopen()打开文件

示例：
```clike
$fp = fopen("$DOCUMENT_ROOT/../orders/orders.txt", "w");
```

获取文档根目录的三种方式（推荐第一种方式）：
```clike
1. $_SERVER['DOCUMENT_ROOT']
2. $DOCUMENT_ROOT
3. $HTTP_SERVER_VARS['DOCUMENT_ROOT']
```

也可以使用文件的绝对路径来指定打开的文件。
```clike
$fp = fopen("/home/work/pmwd/orders/orders.txt", "w");
```

Linux和Windows的路径表示方法：
1. Linux只使用正斜线`/`；
2. Windows可以使用正斜线`/`或者反斜线`\`，但使用反斜线的话需要对进行转义`\\`；

关于`fopen()`函数使用的文件打开模式：

|模式   |模式名称       |含义               |
|-------|---------------|-------------------|
|r      |只读           |从文件头开始读     |
|r+     |读写           |从文件头开始读写   |
|w      |只写           |从文件头开始写，文件不存在则创建，存在则清空   |
|w+     |读写           |从文件头开始写，文件不存在则创建，存在则清空   |
|x      |谨慎写         |从文件头开始写，文件不存在则创建，存在则返回失败   |
|x+     |谨慎读写       |从文件头开始写，文件不存在则创建，存在则返回失败   |
|a      |追加写         |从文件头开始写，文件不存在则创建，存在则追加   |
|a+     |追加读写       |从文件头开始写，文件不存在则创建，存在则追加   |
|b      |二进制         |推荐使用           |
|t      |文本           |不推荐使用         |

如果指定了使用默认文件查找路径（通过php配置`include_path`指定），则可以不显示指定文件路径。
```clike
$fp = fopen('orders.txt', 'ab', true);
```

`fopen()`函数还支持文件名称以协议名称开头，如：`http://...`。


### 通过FTP或HTTP打开文件

`fopen()`函数除了能够打开一个本地文件之外，还能够通过FTP、HTTP或者其他协议来打开文件。该功能开关对应php.ini的配置项`allow_url_fopen`，默认开关是打开的。

说明：URL中的域名不区分大小写，但是路径和文件名是区分大小写的。


### 解决打开文件时可能遇到的问题

根据服务器设置的不同，PHP脚本可能是作为Web服务器用户或者脚本所在目录的拥有者来运行的。在大多数系统中，脚本将作为Web服务器用户来运行。

对程序执行可能产生的错误，可以使用`@`符号进行抑制。
```clike
@$fp = fopen('orders.txt', 'ab', true);
```
或者
```clike
$fp = @fopen('orders.txt', 'ab', true);
```
说明：推荐将`@`置于行首。


## 写文件 `fwrite()` `fputs()` `file_put_contents()`

`fputs()`是`fwrite()`的别名函数，两者是等价的。

```clike
fwite($fp, $outputstring);
```

`file_put_contents()`函数包含了文件打开和关闭的操作，可以看作是`fwrite()`的一个封装。


### fwrite()的参数

略。


### 文件格式

略。


## 关闭文件 `fclose()`

函数用法：
```clike
fclose()
```
说明：`fclose()`的返回值为`true`或者`false`，分别表示关闭成功或者关闭失败。


## 读文件 `fgetc()` `/` `fgets()` `fgetss()` `fgetcsv()` `/` `readfile()` `fpassthru()` `file()` `file_get_contents()`

### 以只读模式打开文件 `fopen()`

略。

### 知道何时读完文件 `feof()`

略。

### 每次读取一行数据 `fgets()` `fgetss()` `fgetcsv()`

对于函数`fgets()`：
```
$order = fgets($fp, 999);
```
说明：第二个参数为读取的长度，实际可以读取的长度为指定的长度减去1个字节。

对于函数`fgetss()`，其和`fgets()`的功能类似，区别在于它可以过滤字符串中包含的PHP和HTML标记。

说明：将HTML代码放在文件中会导致格式的破坏；将PHP代码放在文件中会引起安全问题，比如：用户可能恶意提交含有PHP代码的文本。


### 读取整个文件 `readfile()` `fpassthru()` `file()` `file_get_contents()`

1. `readfile()`函数包含了文件打开和关闭的操作，并且将文件内容输出到标准输出（浏览器）当中。
```clike
readfile("$DOCUMENT_ROOT/../orders/orders.txt");
```
2. `fpassthru()`函数与`readfile()`相比，需要事先打开文件，其他操作和`readfile()`完全一致。
```clike
$fp = fopen("$DOCUMENT_ROOT/../orders/orders.txt");
fpassthru($fp);
```
3. `file()`函数与`readfile()`相比，`file()`会将文件内容转换为数组的形式，文件中的每一行作为数组的一个元素，其他操作和`readfile()`完全一致。
```clike
$filearray = file("$DOCUMENT_ROOT/../orders/orders.txt");
```
4. `file_get_contents()`函数与`readfile()`相比，`file_get_contents()`会将文件内容转换为字符串的形式，其他操作和`readfile()`完全一致。
```clike
$string = file("$DOCUMENT_ROOT/../orders/orders.txt");
```


### 读取一个字符 `fgetc()`

示例：
```clike
while (!feof($fp)) {
    $char = fgetc($fp);
    if (!feof($fp)) {
        echo ($char == '\n' ? '<br />' : $char);
    }
}
```
说明：使用`fgetc()`函数需要注意的一点是，其会将文件末尾的`EOF`字符读取出来，而`fgets()`则不会。


## 使用其他有用的文件函数 `file_exists()` `filesize()` `unlink()` `rewind()` `fseek()` `ftell()`

### 查看文件是否存在 `file_exists()`

略。


### 确定文件大小 `filesize()`

补充：`nl2br()`函数将输出的`\n`字符转换成HTML的换行符`<br />`。


### 删除一个文件 `unlink()`

注意：PHP中没有`delete()`这个函数。


### 在文件中定位 `rewind()` `fseek()` `ftell()`

1. `rewind()`函数用于将文件指针复位到文件的开始；
2. `fseek()`函数用于设置文件指针在文件中的位置；
3. `ftell()`函数用于获取文件指针在文件中的位置；


## 文件锁定 `flock()`

文件锁定用于防止两个进程同时读或者写文件，从而导致数据不正确的问题。

读文件加锁示例：
```clike
$fp = fopen("/home/work/pmwd/orders/orders.txt", "rb");
flock($fp, LOCK_SH);
// 读操作...
fclose($fp, LOCK_UN);
```

写文件加锁示例：
```clike
$fp = fopen("/home/work/pmwd/orders/orders.txt", "wb");
flock($fp, LOCK_EX);
// 写操作...
fclose($fp, LOCK_UN);
```

文件锁定方式的缺点：两个进程同时申请锁的话，会导致竞争条件问题。

简单一句话就是：无锁会乱，有锁会竞争。


## 更好的方式：数据库管理系统

MySQL是一个关系数据库管理系统（RDBMS）。

### 使用普通文件的几个问题

略。

### RDBMS是如何解决这些问题的

延伸：PHP的SQLite扩展
1. SQLite可以创建一个简单的系统替代功能全面的数据库，但是又能够避免锁定以及其他使用普通文件相关的问题。
2. SQLite基于普通文件提供了一个SQL接口，方便用户操作。


## 进一步学习

略。

