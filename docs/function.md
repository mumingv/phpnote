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
|htmlentities           |将HTML页面中的特殊字符转换成HTML实体   |
|nl2br                  |在字符串所有新行之前插入 HTML 换行标记 |
|strip_tags             |从字符串中去除 HTML 和 PHP 标记        |
|wordwrap               |打断字符串为指定数量的字串             |


## [变量与类型相关扩展](http://php.net/manual/zh/refs.basic.vartype.php)

### 数组 `79`

参考：[官方](http://php.net/manual/zh/ref.array.php) & [木名](#docs/function_array)

|函数                   |功能                                   |
|-----------------------|---------------------------------------|
|array_change_key_case | 返回字符串键名全为小写或大写的数组     |
|array_chunk | 将一个数组分割成多个|
|array_column | 返回数组中指定的一列|
|array_combine | 创建一个数组，用一个数组的值作为其键名，另一个数组的值作为其值|
|array_count_values | 统计数组中所有的值出现的次数|
|array_diff_assoc | 带索引检查计算数组的差集|
|array_diff_key | 使用键名比较计算数组的差集|
|array_diff_uassoc | 用用户提供的回调函数做索引检查来计算数组的差集|
|array_diff_ukey | 用回调函数对键名比较计算数组的差集|
|array_diff | 计算数组的差集|
|array_fill_keys | 使用指定的键和值填充数组|
|array_fill | 用给定的值填充数组|
|array_filter | 用回调函数过滤数组中的单元|
|array_flip | 交换数组中的键和值|
|array_intersect_assoc | 带索引检查计算数组的交集|
|array_intersect_key | 使用键名比较计算数组的交集|
|array_intersect_uassoc | 带索引检查计算数组的交集，用回调函数比较索引|
|array_intersect_ukey | 用回调函数比较键名来计算数组的交集|
|array_intersect | 计算数组的交集|
|array_key_exists | 检查给定的键名或索引是否存在于数组中|
|array_keys | 返回数组中部分的或所有的键名|
|array_map | 为数组的每个元素应用回调函数|
|array_merge_recursive | 递归地合并一个或多个数组|
|array_merge | 合并一个或多个数组|
|array_multisort | 对多个数组或多维数组进行排序|
|array_pad | 用值将数组填补到指定长度|
|array_pop | 将数组最后一个单元弹出（出栈）|
|array_product | 计算数组中所有值的乘积|
|array_push | 将一个或多个单元压入数组的末尾（入栈）|
|array_rand | 从数组中随机取出一个或多个单元|
|array_reduce | 用回调函数迭代地将数组简化为单一的值|
|array_replace_recursive | 使用传递的数组递归替换第一个数组的元素|
|array_replace | 使用传递的数组替换第一个数组的元素|
|array_reverse | 返回一个单元顺序相反的数组|
|array_search | 在数组中搜索给定的值，如果成功则返回相应的键名|
|array_shift | 将数组开头的单元移出数组|
|array_slice | 从数组中取出一段|
|array_splice | 把数组中的一部分去掉并用其它值取代|
|array_sum | 计算数组中所有值的和|
|array_udiff_assoc | 带索引检查计算数组的差集，用回调函数比较数据|
|array_udiff_uassoc | 带索引检查计算数组的差集，用回调函数比较数据和索引|
|array_udiff | 用回调函数比较数据来计算数组的差集|
|array_uintersect_assoc | 带索引检查计算数组的交集，用回调函数比较数据|
|array_uintersect_uassoc | 带索引检查计算数组的交集，用回调函数比较数据和索引|
|array_uintersect | 计算数组的交集，用回调函数比较数据|
|array_unique | 移除数组中重复的值|
|array_unshift | 在数组开头插入一个或多个单元|
|array_values | 返回数组中所有的值|
|array_walk_recursive | 对数组中的每个成员递归地应用用户函数|
|array_walk | 使用用户自定义函数对数组中的每个元素做回调处理|
|array | 新建一个数组|
|arsort | 对数组进行逆向排序并保持索引关系|
|asort | 对数组进行排序并保持索引关系|
|compact | 建立一个数组，包括变量名和它们的值|
|count | 计算数组中的单元数目或对象中的属性个数|
|current | 返回数组中的当前单元|
|each | 返回数组中当前的键／值对并将数组指针向前移动一步|
|end | 将数组的内部指针指向最后一个单元|
|extract | 从数组中将变量导入到当前的符号表|
|in_array | 检查数组中是否存在某个值|
|key_exists | 别名 array_key_exists|
|key | 从关联数组中取得键名|
|krsort | 对数组按照键名逆向排序|
|ksort | 对数组按照键名排序|
|list | 把数组中的值赋给一些变量|
|natcasesort | 用“自然排序”算法对数组进行不区分大小写字母的排序|
|natsort | 用“自然排序”算法对数组排序|
|next | 将数组中的内部指针向前移动一位|
|pos | current 的别名|
|prev | 将数组的内部指针倒回一位|
|range | 建立一个包含指定范围单元的数组|
|reset | 将数组的内部指针指向第一个单元|
|rsort | 对数组逆向排序|
|shuffle | 将数组打乱|
|sizeof | count 的别名|
|sort | 对数组排序|
|uasort | 使用用户自定义的比较函数对数组中的值进行排序并保持索引关联|
|uksort | 使用用户自定义的比较函数对数组中的键名进行排序|
|usort | 使用用户自定义的比较函数对数组中的值进行排序|


### Function Handling(函数处理) `13`

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
















