# [常用函数](http://php.net/manual/zh/funcref.php)

## [数据库扩展](http://php.net/manual/zh/refs.database.php)

### MySQL `48 (部分)`

参考：[官方](http://php.net/manual/zh/ref.mysql.php) & [木名](#docs/function_mysql)

说明：mysql扩展在PHP 5.5版本废弃（还能使用但是会产生告警），在PHP 7.0版本移除，需要使用mysqli或者PDO_MySQL替换。

|函数                       |功能                                   |
|---------------------------|---------------------------------------|
|**mysql_connect**          |打开一个到 MySQL 服务器的连接          |
|mysql_select_db            |选择 MySQL 数据库                      |
|mysql_query                |发送一条 MySQL 查询                    |
|mysql_fetch_array          |从结果集中取得一行作为关联数组，或数字数组，或二者兼有|
|mysql_close                |关闭 MySQL 连接                        |
|mysql_escape_string        |转义一个字符串用于 mysql_query         |
|**mysql_real_escape_string**   |转义 SQL 语句中使用的字符串中的特殊字符，并考虑到连接的当前字符集|

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


### 字符串 `98 (部分)`

参考：[官方](http://php.net/manual/zh/ref.strings.php) & [木名](#docs/function_strings)

|函数                   |功能                                   |
|-----------------------|---------------------------------------|
|htmlentities           |将HTML页面中的特殊字符转换成HTML实体   |                         |


## [变量与类型相关扩展](http://php.net/manual/zh/refs.basic.vartype.php)

### 函数处理 `13`

参考：[官方](http://php.net/manual/zh/ref.funchand.php) & [木名](#docs/function_funchand)

|函数                   |功能                                   |
|-----------------------|---------------------------------------|
|call_user_func_array   |调用回调函数，并把一个数组参数作为回调函数的参数   |
|call_user_func         |把第一个参数作为回调函数调用           |
|create_function        |创建一个lambda风格的匿名函数           |
|forward_static_call_array  |创建一个静态方法，并用一个数组作为参数 |
|forward_static_call    |创建一个静态方法                       |
|func_get_arg           |返回参数列表的某一项                   |
|func_get_args          |返回一个包含函数参数列表的数组         |
|func_num_args          |返回传递给函数的参数个数               |
|function_exists        |如果给定的函数已经被定义就返回 TRUE    |
|get_defined_functions  |返回所有已定义函数的数组               |
|register_shutdown_function |注册一个函数，在每次PHP脚本执行完之后执行  |
|register_tick_function |注册一个定时执行函数                   |
|unregister_tick_function   |取消已注册的定时执行函数           |


## [其它基本扩展](http://php.net/manual/zh/refs.basic.other.php)

### URLs `10`

参考：[官方](http://php.net/manual/zh/ref.url.php) & [木名](#docs/function_url)

|函数                   |功能                                   |
|-----------------------|---------------------------------------|
|base64_decode          |对使用 MIME base64 编码的数据进行解码  |
|base64_encode          |使用 MIME base64 对数据进行编码        |
|get_headers            |取得服务器响应一个 HTTP 请求所发送的所有标头   |
|get_meta_tags          |从一个文件中提取所有的 meta 标签 content 属性，返回一个数组    |
|http_build_query       |生成 URL-encode 之后的请求字符串       |
|parse_url              |解析 URL，返回其组成部分               |
|rawurldecode           |对已编码的 URL 字符串进行解码          |
|rawurlencode           |按照 RFC 3986 对 URL 进行编码          |
|urldecode              |解码已编码的 URL 字符串                |
|urlencode              |编码 URL 字符串                        |
















