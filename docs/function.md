# [常用函数](http://php.net/manual/zh/funcref.php)

## [影响 PHP 行为的扩展](http://php.net/manual/zh/refs.basic.php.php)

### PHP 选项/信息 `57`

参考：[官方](http://php.net/manual/zh/ref.info.php) & [木名](#docs/function_info)

|函数                       |功能                                   |
|---------------------------|---------------------------------------|
|assert_options | 设置/获取断言的各种标志|
|assert | 检查一个断言是否为 FALSE|
|cli_get_process_title | Returns the current process title|
|cli_set_process_title | Sets the process title|
|dl | 运行时载入一个 PHP 扩展|
|extension_loaded | 检查一个扩展是否已经加载|
|gc_collect_cycles | 强制收集所有现存的垃圾循环周期|
|gc_disable | 停用循环引用收集器|
|gc_enable | 激活循环引用收集器|
|gc_enabled | 返回循环引用计数器的状态|
|gc_mem_caches | Reclaims memory used by the Zend Engine memory manager|
|get_cfg_var | 获取 PHP 配置选项的值|
|get_current_user | 获取当前 PHP 脚本所有者名称|
|get_defined_constants | 返回所有常量的关联数组，键是常量名，值是常量值|
|get_extension_funcs | 返回模块函数名称的数组|
|get_include_path | 获取当前的 include_path 配置选项|
|get_included_files | 返回被 include 和 require 文件名的 array|
|get_loaded_extensions | 返回所有编译并加载模块名的 array|
|get_magic_quotes_gpc | 获取当前 magic_quotes_gpc 的配置选项设置|
|get_magic_quotes_runtime | 获取当前 magic_quotes_runtime 配置选项的激活状态|
|get_required_files | 别名 get_included_files|
|get_resources | Returns active resources|
|getenv | 获取一个环境变量的值|
|getlastmod | 获取页面最后修改的时间|
|getmygid | 获取当前 PHP 脚本拥有者的 GID|
|getmyinode | 获取当前脚本的索引节点（inode）|
|getmypid | 获取 PHP 进程的 ID|
|getmyuid | 获取 PHP 脚本所有者的 UID|
|getopt | 从命令行参数列表中获取选项|
|getrusage | 获取当前资源使用状况|
|ini_alter | 别名 ini_set|
|ini_get_all | 获取所有配置选项|
|ini_get | 获取一个配置选项的值|
|ini_restore | 恢复配置选项的值|
|ini_set | 为一个配置选项设置值|
|magic_quotes_runtime | 别名 set_magic_quotes_runtime|
|main | 虚拟的main|
|memory_get_peak_usage | 返回分配给 PHP 内存的峰值|
|memory_get_usage | 返回分配给 PHP 的内存量|
|php_ini_loaded_file | 取得已加载的 php.ini 文件的路径|
|php_ini_scanned_files | 返回从额外 ini 目录里解析的 .ini 文件列表|
|php_logo_guid | 获取 logo 的 guid|
|php_sapi_name | 返回 web 服务器和 PHP 之间的接口类型|
|php_uname | 返回运行 PHP 的系统的有关信息|
|phpcredits | 打印 PHP 贡献者名单|
|phpinfo | 输出关于 PHP 配置的信息|
|phpversion | 获取当前的PHP版本|
|putenv | 设置环境变量的值|
|restore_include_path | 还原 include_path 配置选项的值|
|set_include_path | 设置 include_path 配置选项|
|set_magic_quotes_runtime | 设置当前 magic_quotes_runtime 配置选项的激活状态|
|set_time_limit | 设置脚本最大执行时间|
|sys_get_temp_dir | 返回用于临时文件的目录|
|version_compare | 对比两个「PHP 规范化」的版本数字字符串|
|zend_logo_guid | 获取 Zend guid|
|zend_thread_id | 返回当前线程的唯一识别符|
|zend_version | 获取当前 Zend 引擎的版本|


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

### Filesystem 文件系统 `81`

参考：[官方](http://php.net/manual/zh/ref.filesystem.php) & [木名](#docs/function_filesystem)

|函数                   |功能                                   |
|---------------------------|---------------------------------------|
|basename | 返回路径中的文件名部分|
|chgrp | 改变文件所属的组|
|chmod | 改变文件模式|
|chown | 改变文件的所有者|
|clearstatcache | 清除文件状态缓存|
|copy | 拷贝文件|
|delete | 参见 unlink 或 unset|
|dirname | 返回路径中的目录部分|
|disk_free_space | 返回目录中的可用空间|
|disk_total_space | 返回一个目录的磁盘总大小|
|diskfreespace | disk_free_space 的别名|
|fclose | 关闭一个已打开的文件指针|
|feof | 测试文件指针是否到了文件结束的位置|
|fflush | 将缓冲内容输出到文件|
|fgetc | 从文件指针中读取字符|
|fgetcsv | 从文件指针中读入一行并解析 CSV 字段|
|fgets | 从文件指针中读取一行|
|fgetss | 从文件指针中读取一行并过滤掉 HTML 标记|
|file_exists | 检查文件或目录是否存在|
|**file_get_contents** | 将整个文件读入一个字符串|
|**file_put_contents** | 将一个字符串写入文件|
|file | 把整个文件读入一个数组中|
|fileatime | 取得文件的上次访问时间|
|filectime | 取得文件的 inode 修改时间|
|filegroup | 取得文件的组|
|fileinode | 取得文件的 inode|
|filemtime | 取得文件修改时间|
|fileowner | 取得文件的所有者|
|fileperms | 取得文件的权限|
|filesize | 取得文件大小|
|filetype | 取得文件类型|
|flock | 轻便的咨询文件锁定|
|fnmatch | 用模式匹配文件名|
|fopen | 打开文件或者 URL|
|fpassthru | 输出文件指针处的所有剩余数据|
|fputcsv | 将行格式化为 CSV 并写入文件指针|
|fputs | fwrite 的别名|
|fread | 读取文件（可安全用于二进制文件）|
|fscanf | 从文件中格式化输入|
|fseek | 在文件指针中定位|
|fstat | 通过已打开的文件指针取得文件信息|
|ftell | 返回文件指针读/写的位置|
|ftruncate | 将文件截断到给定的长度|
|fwrite | 写入文件（可安全用于二进制文件）|
|glob | 寻找与模式匹配的文件路径|
|is_dir | 判断给定文件名是否是一个目录|
|is_executable | 判断给定文件名是否可执行|
|is_file | 判断给定文件名是否为一个正常的文件|
|is_link | 判断给定文件名是否为一个符号连接|
|is_readable | 判断给定文件名是否可读|
|is_uploaded_file | 判断文件是否是通过 HTTP POST 上传的|
|is_writable | 判断给定的文件名是否可写|
|is_writeable | is_writable 的别名|
|lchgrp | 修改符号链接的所有组|
|lchown | 修改符号链接的所有者|
|link | 建立一个硬连接|
|linkinfo | 获取一个连接的信息|
|lstat | 给出一个文件或符号连接的信息|
|mkdir | 新建目录|
|move_uploaded_file | 将上传的文件移动到新位置|
|parse_ini_file | 解析一个配置文件|
|parse_ini_string | 解析配置字符串|
|pathinfo | 返回文件路径的信息|
|pclose | 关闭进程文件指针|
|popen | 打开进程文件指针|
|readfile | 输出文件|
|readlink | 返回符号连接指向的目标|
|realpath_cache_get | 获取真实目录缓存的详情|
|realpath_cache_size | 获取真实路径缓冲区的大小|
|realpath | 返回规范化的绝对路径名|
|rename | 重命名一个文件或目录|
|rewind | 倒回文件指针的位置|
|rmdir | 删除目录|
|set_file_buffer | stream_set_write_buffer 的别名|
|stat | 给出文件的信息|
|symlink | 建立符号连接|
|tempnam | 建立一个具有唯一文件名的文件|
|tmpfile | 建立一个临时文件|
|touch | 设定文件的访问和修改时间|
|umask | 改变当前的 umask|
|unlink | 删除文件|


## [文本处理（字符串）](http://php.net/manual/zh/refs.basic.text.php)

### 字符串 `98 (部分)`

参考：[官方](http://php.net/manual/zh/ref.strings.php) & [木名](#docs/function_strings)

|函数                   |功能                                   |
|-----------------------|---------------------------------------|
|addcslashes | 以 C 语言风格使用反斜线转义字符串中的字符|
|addslashes | 使用反斜线引用字符串|
|bin2hex | 函数把包含数据的二进制字符串转换为十六进制值|
|chop | rtrim 的别名|
|chr | 返回指定的字符|
|chunk_split | 将字符串分割成小块|
|convert_cyr_string | 将字符由一种 Cyrillic 字符转换成另一种|
|convert_uudecode | 解码一个 uuencode 编码的字符串|
|convert_uuencode | 使用 uuencode 编码一个字符串|
|count_chars | 返回字符串所用字符的信息|
|crc32 | 计算一个字符串的 crc32 多项式|
|crypt | 单向字符串散列|
|echo | 输出一个或多个字符串|
|explode | 使用一个字符串分割另一个字符串|
|fprintf | 将格式化后的字符串写入到流|
|get_html_translation_table | 返回使用 htmlspecialchars 和 htmlentities 后的转换表|
|hebrev | 将逻辑顺序希伯来文（logical-Hebrew）转换为视觉顺序希伯来文（visual-Hebrew）|
|hebrevc | 将逻辑顺序希伯来文（logical-Hebrew）转换为视觉顺序希伯来文（visual-Hebrew），并且转换换行符|
|hex2bin | 转换十六进制字符串为二进制字符串|
|html_entity_decode | Convert all HTML entities to their applicable characters|
|**htmlentities**           |将HTML页面中的特殊字符转换成HTML实体   |
|htmlspecialchars_decode | 将特殊的 HTML 实体转换回普通字符|
|htmlspecialchars | Convert special characters to HTML entities|
|implode | 将一个一维数组的值转化为字符串|
|join | 别名 implode|
|lcfirst | 使一个字符串的第一个字符小写|
|levenshtein | 计算两个字符串之间的编辑距离|
|localeconv | Get numeric formatting information|
|ltrim | 删除字符串开头的空白字符（或其他字符）|
|md5_file | 计算指定文件的 MD5 散列值|
|md5 | 计算字符串的 MD5 散列值|
|metaphone | Calculate the metaphone key of a string|
|money_format | 将数字格式化成货币字符串|
|nl_langinfo | Query language and locale information|
|**nl2br** | 在字符串所有新行之前插入 HTML 换行标记|
|number_format | 以千位分隔符方式格式化一个数字|
|ord | 返回字符的 ASCII 码值|
|parse_str | 将字符串解析成多个变量|
|print | 输出字符串|
|printf | 输出格式化字符串|
|quoted_printable_decode | 将 quoted-printable 字符串转换为 8-bit 字符串|
|quoted_printable_encode | 将 8-bit 字符串转换成 quoted-printable 字符串|
|quotemeta | 转义元字符集|
|rtrim | 删除字符串末端的空白字符（或者其他字符）|
|setlocale | 设置地区信息|
|sha1_file | 计算文件的 sha1 散列值|
|sha1 | 计算字符串的 sha1 散列值|
|similar_text | 计算两个字符串的相似度|
|soundex | Calculate the soundex key of a string|
|**sprintf** | 返回格式化字符串|
|sscanf | 根据指定格式解析输入的字符|
|str_getcsv | 解析 CSV 字符串为一个数组|
|str_ireplace | str_replace 的忽略大小写版本|
|str_pad | 使用另一个字符串填充字符串为指定长度|
|str_repeat | 重复一个字符串|
|str_replace | 子字符串替换|
|str_rot13 | 对字符串执行 ROT13 转换|
|str_shuffle | 随机打乱一个字符串|
|str_split | 将字符串转换为数组|
|str_word_count | 返回字符串中单词的使用情况|
|strcasecmp | 二进制安全比较字符串（不区分大小写）|
|strchr | 别名 strstr|
|strcmp | 二进制安全字符串比较|
|strcoll | 基于区域设置的字符串比较|
|strcspn | 获取不匹配遮罩的起始子字符串的长度|
|**strip_tags** | 从字符串中去除 HTML 和 PHP 标记|
|stripcslashes | 反引用一个使用 addcslashes 转义的字符串|
|stripos | 查找字符串首次出现的位置（不区分大小写）|
|stripslashes | 反引用一个引用字符串|
|stristr | strstr 函数的忽略大小写版本|
|strlen | 获取字符串长度|
|strnatcasecmp | 使用“自然顺序”算法比较字符串（不区分大小写）|
|strnatcmp | 使用自然排序算法比较字符串|
|strncasecmp | 二进制安全比较字符串开头的若干个字符（不区分大小写）|
|strncmp | 二进制安全比较字符串开头的若干个字符|
|strpbrk | 在字符串中查找一组字符的任何一个字符|
|strpos | 查找字符串首次出现的位置|
|strrchr | 查找指定字符在字符串中的最后一次出现|
|strrev | 反转字符串|
|strripos | 计算指定字符串在目标字符串中最后一次出现的位置（不区分大小写）|
|strrpos | 计算指定字符串在目标字符串中最后一次出现的位置|
|strspn | 计算字符串中全部字符都存在于指定字符集合中的第一段子串的长度。|
|strstr | 查找字符串的首次出现|
|strtok | 标记分割字符串|
|strtolower | 将字符串转化为小写|
|strtoupper | 将字符串转化为大写|
|strtr | 转换指定字符|
|substr_compare | 二进制安全比较字符串（从偏移位置比较指定长度）|
|substr_count | 计算字串出现的次数|
|substr_replace | 替换字符串的子串|
|substr | 返回字符串的子串|
|trim | 去除字符串首尾处的空白字符（或者其他字符）|
|ucfirst | 将字符串的首字母转换为大写|
|ucwords | 将字符串中每个单词的首字母转换为大写|
|vfprintf | 将格式化字符串写入流|
|vprintf | 输出格式化字符串|
|**vsprintf** | 返回格式化字符串|
|**wordwrap** | 打断字符串为指定数量的字串|


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


## [变量与类型相关扩展（数组）](http://php.net/manual/zh/refs.basic.vartype.php)

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


### 类/对象 `20`

参考：[官方](http://php.net/manual/zh/ref.classobj.php) & [木名](#docs/function_classobj)

|函数                   |功能                                   |
|-----------------------|---------------------------------------|
|__autoload             |尝试加载未定义的类                     |
|call_user_method_array |以参数列表的数组，调用用户方法         |
|call_user_method       |对特定对象调用用户方法                 |
|class_alias            |为一个类创建别名                       |
|class_exists           |检查类是否已定义                       |
|get_called_class       |后期静态绑定类的名称                   |
|get_class_methods      |返回由类的方法名组成的数组             |
|get_class_vars         |返回由类的默认属性组成的数组           |
|get_class              |返回对象的类名                         |
|get_declared_classes   |返回由已定义类的名字所组成的数组       |
|get_declared_interfaces|返回一个数组包含所有已声明的接口       |
|get_declared_traits    |返回所有已定义的 traits 的数组         |
|get_object_vars        |返回由对象属性组成的关联数组           |
|get_parent_class       |返回对象或类的父类名                   |
|interface_exists       |检查接口是否已被定义                   |
|is_a                   |如果对象属于该类或该类是此对象的父类则返回 TRUE|
|is_subclass_of         |如果此对象是该类的子类，则返回 TRUE    |
|method_exists          |检查类的方法是否存在                   |
|property_exists        |检查对象或类是否具有该属性             |
|trait_exists           |检查指定的 trait 是否存在              |


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


## [进程控制扩展](http://php.net/manual/zh/refs.fileprocess.process.php)

### 程序执行 `11`

参考：[官方](http://php.net/manual/zh/ref.exec.php) & [木名](#docs/function_exec)

|函数                   |功能                                   |
|-----------------------|---------------------------------------|
|escapeshellarg | 把字符串转码为可以在 shell 命令里使用的参数|
|escapeshellcmd | shell 元字符转义|
|**exec** | 执行一个外部程序|
|passthru | 执行外部程序并且显示原始输出|
|proc_close | 关闭由 proc_open 打开的进程并且返回进程退出码|
|proc_get_status | 获取由 proc_open 函数打开的进程的信息|
|proc_nice | 修改当前进程的优先级|
|proc_open | 执行一个命令，并且打开用来输入/输出的文件指针。|
|proc_terminate | 杀除由 proc_open 打开的进程|
|shell_exec | 通过 shell 环境执行命令，并且将完整的输出以字符串的方式返回。|
|system | 执行外部程序，并且显示输出|

## [其它基本扩展](http://php.net/manual/zh/refs.basic.other.php)

### JSON `4`

参考：[官方](http://php.net/manual/zh/ref.json.php) & [木名](#docs/function_json)

|函数                   |功能                                   |
|-----------------------|---------------------------------------|
|json_decode | 对 JSON 格式的字符串进行解码|
|json_encode | 对变量进行 JSON 编码|
|json_last_error_msg | Returns the error string of the last json_encode() or json_decode() call|
|json_last_error | 返回最后发生的错误|


### Misc(杂项函数) `24`

参考：[官方](http://php.net/manual/zh/ref.misc.php) & [木名](#docs/function_misc)

|函数                   |功能                                   |
|-----------------------|---------------------------------------|
|connection_aborted     | 检查客户端是否已经断开                |
|connection_status      | 返回连接的状态位                      |
|constant               | 返回一个常量的值                      |
|define                 | 定义一个常量                          |
|defined                | 检查某个名称的常量是否存在            |
|die                    | 等同于 exit                           |
|eval                   | 把字符串作为PHP代码执行               |
|exit                   | 输出一个消息并且退出当前脚本          |
|get_browser            | 获取浏览器具有的功能                  |
|__halt_compiler        | 中断编译器的执行                      |
|highlight_file         | 语法高亮一个文件                      |
|highlight_string       | 字符串的语法高亮                      |
|ignore_user_abort      | 设置客户端断开连接时是否中断脚本的执行|
|pack                   | Pack data into binary string          |
|php_check_syntax       | 检查PHP的语法（并执行）指定的文件     |
|php_strip_whitespace   | 返回删除注释和空格后的PHP源码         |
|show_source            | 别名 highlight_file                   |
|sleep                  | 延缓执行                              |
|sys_getloadavg         | 获取系统的负载（load average）        |
|time_nanosleep         | 延缓执行若干秒和纳秒                  |
|time_sleep_until       | 使脚本睡眠到指定的时间为止。          |
|uniqid                 | 生成一个唯一ID                        |
|unpack                 | Unpack data from binary string        |
|usleep                 | 以指定的微秒数延迟执行                |


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
















