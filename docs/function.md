# [常用函数](http://php.net/manual/zh/funcref.php)

## [文件系统相关扩展](http://php.net/manual/zh/refs.fileprocess.file.php)


## [文本处理](http://php.net/manual/zh/refs.basic.text.php)

### PCRE `10`

参考：[官方](http://php.net/manual/zh/ref.pcre.php) & [木名](#docs/function_pcre)

PCRE是Perl格式的正则表达式，是PHP语言官方推荐的正则匹配方式。

|函数                   |功能                                   |
|-----------------------|---------------------------------------|
|preg_match             |执行一个正则表达式匹配                 |
|preg_match_all         |执行一个全局正则表达式匹配             |
|preg_replace           |执行一个正则表达式的搜索和替换         |
|preg_replace_callback  |执行一个正则表达式搜索并且使用一个回调进行替换 |
|preg_replace_callback_array  |执行一个正则表达式搜索并且使用多个回调进行替换 |
|preg_filter            |正则表达式搜索和替换                   |
|preg_split             |通过一个正则表达式分隔字符串           |
|preg_grep              |返回匹配模式的数组条目                 |
|preg_quote             |转义正则表达式字符                     |
|preg_last_error        |返回最后一个PCRE正则执行产生的错误代码 |


### POSIX Regex `7`

参考：[官方](http://php.net/manual/zh/ref.regex.php) & [木名](#docs/function_regex)

重要说明：POSIX格式的正则表达式函数已不再推荐使用，相关函数由Perl格式的正则表达式函数取代。

为了保证知识体系的完整性，这里还是列出了相关的函数。

|函数                   |功能                                   |
|-----------------------|---------------------------------------|
|ereg                   |正则表达式匹配                         |
|eregi                  |正则表达式匹配，不区分大小写           |
|ereg_replace           |正则表达式替换                         |
|eregi_replace          |正则表达式替换，不区分大小写           |
|split                  |用正则表达式将字符串分割到数组中       |
|spliti                 |用正则表达式将字符串分割到数组中，不区分大小写 |
|sql_regcase            |产生用于匹配的正则表达式，不区分大小写 |

说明：
1. `ereg()`和`eregi()`都对应PCRE的`preg_match()`函数。
2. `ereg_replace()`和`eregi_replace()`都对应PCRE的`preg_replace()`函数。
3. `split()`和`spliti()`都对应PCRE的`preg_split()`函数。
4. `sql_regcase()`没有对应的PCRE函数。

