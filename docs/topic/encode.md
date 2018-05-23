# 编码处理

## 参考资料

[博客：中文字符集编码](http://www.cnblogs.com/finallyliuyu/archive/2013/05/10/3071023.html)

## 示例

### 示例：检测输入文件的格式，并将其转换为UTF-8编码

```
$contents = file_get_contents($file);
$encoding = mb_detect_encoding($contents, "UTF-8, GBK");
if (!$encoding) {
    return;
}
$contents = mb_convert_encoding($contents, 'UTF-8', $encoding);
```

