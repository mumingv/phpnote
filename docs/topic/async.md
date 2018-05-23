# 异步处理

## 使用fastcgi_finish_request先回应答再处理业务

### 代码示例

```
public function execute() {
    $start = microtime(true);
    echo "intervene test ok!\n";

    fastcgi_finish_request();     

    usleep(100000); // 100ms
    $end = microtime(true);
    $total = ($end - $start) * 1000;

    file_put_contents('muming.txt', "start: {$start}, end: {$end}, total: {$total}.\n", FILE_APPEND);
    return;
}
```

### 压力测试

#### 相关配置

PHP-FPM子进程：php-fpm.conf中配置pm相关参数。

```
pm = static     		 // 进程管理模式：静态模式
pm.max_children = 128    // 系统启动后直接创建128个子进程
pm.max_requests = 10000  // 进程处理10000请求后重启
```

通过如下命令查看cpu信息。

```
$ cat /proc/cpuinfo
```
```
$ cat /proc/cpuinfo 
processor       : 0
vendor_id       : GenuineIntel
cpu family      : 6
model           : 45
model name      : Intel(R) Xeon(R) CPU E5-2620 0 @ 2.00GHz
stepping        : 7
cpu MHz         : 1999.999
cache size      : 4096 KB
fpu             : yes
fpu_exception   : yes
cpuid level     : 13
wp              : yes
flags           : fpu vme de pse tsc msr pae mce cx8 apic mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ss syscall nx pdpe1gb rdtscp lm constant_tsc arch_perfmon rep_good unfair_spinlock pni pclmulqdq ssse3 cx16 sse4_1 sse4_2 x2apic popcnt aes xsave avx hypervisor lahf_lm arat xsaveopt
bogomips        : 3999.99
clflush size    : 64
cache_alignment : 64
address sizes   : 40 bits physical, 48 bits virtual
power management:

processor       : 1
...

processor       : 2
...

processor       : 3
...
```

#### 测试结果

```
$ ab -c 120 -n 12000  http://cp01-rdqa-dev406-yinjie05.epc.baidu.com:8183/intervene/test
This is ApacheBench, Version 2.3 <$Revision: 1796539 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking cp01-rdqa-dev406-yinjie05.epc.baidu.com (be patient)
Completed 1200 requests
Completed 2400 requests
Completed 3600 requests
Completed 4800 requests
Completed 6000 requests
Completed 7200 requests
Completed 8400 requests
Completed 9600 requests
Completed 10800 requests
Completed 12000 requests
Finished 12000 requests


Server Software:        Apache
Server Hostname:        cp01-rdqa-dev406-yinjie05.epc.baidu.com
Server Port:            8183

Document Path:          /intervene/test
Document Length:        19 bytes

Concurrency Level:      120
Time taken for tests:   56.620 seconds
Complete requests:      12000
Failed requests:        0
Total transferred:      7020000 bytes
HTML transferred:       228000 bytes
Requests per second:    211.94 [#/sec] (mean)
Time per request:       566.205 [ms] (mean)
Time per request:       4.718 [ms] (mean, across all concurrent requests)
Transfer rate:          121.08 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        2   23 118.2      7    1404
Processing:   256  540 111.7    518    1744
Waiting:      256  537 108.3    516    1635
Total:        281  563 162.8    528    2088

Percentage of the requests served within a certain time (ms)
  50%    528
  66%    565
  75%    594
  80%    615
  90%    683
  95%    774
  98%    988
  99%   1569
 100%   2088 (longest request)
```


### 参考资料

- [鸟哥：使用fastcgi_finish_request提高页面响应速度](http://www.laruence.com/2011/04/13/1991.html)
- [鸟哥：加速PHP的ECHO](http://www.laruence.com/2011/02/13/1870.html)
- [PHP-FPM子进程数量应该如何设置？](https://segmentfault.com/a/1190000000630270)

