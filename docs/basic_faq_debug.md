# 调试FAQ

## 常用调试方法有哪些？

待补充。


## 如何打印调用堆栈？

使用`debug_backtrace`函数。

示例函数：

```
/**
 * 输出完整的调用堆栈信息
 * @access public
 * @return void
 */
public function debugBacktrace($infoExt = array()) {
    $info = array(
        'debug_backtrace' => debug_backtrace(),
        'info_ext' => $infoExt
    );
    $infoString = json_encode($info, JSON_UNESCAPED_UNICODE|JSON_UNESCAPED_SLASHES);
    var_dump($infoString);
}
```

