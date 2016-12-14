# 模块接口

## File


## GET/POST

### 示例1：GET接口请求数据

代码：[php/func/curl/demo_curl.php]()

```php
<?php
function get_data($url) {
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, $url);
    curl_setopt($ch, CURLOPT_TIMEOUT, 2);
    curl_setopt($ch,CURLOPT_FOLLOWLOCATION,1);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    $r = curl_exec($ch);
    curl_close($ch);
    return $r;  
} 

$url = 'http://123.56.21.232:8254/myprojects/demo/get_json_data.php';
$data = get_data($url);
$data = json_decode($data, true);
print_r($data);
```


### 示例2：GET接口请求数据

代码：[php/func/curl/demo_curl_get.php]()

```php
function curl_get($url, array $get = array(), array $options = array()) 
{    
    $defaults = array( 
        CURLOPT_URL => $url. (strpos($url, '?') === FALSE ? '?' : ''). http_build_query($get), 
        CURLOPT_HEADER => 0, 
        CURLOPT_RETURNTRANSFER => TRUE, 
        CURLOPT_TIMEOUT => 4 
    ); 
    
    $ch = curl_init(); 
    curl_setopt_array($ch, ($options + $defaults)); 
    if (! $result = curl_exec($ch)) 
    { 
        trigger_error(curl_error($ch)); 
    } 
    curl_close($ch); 
    return $result; 
} 

$url = 'http://123.56.21.232:8254/myprojects/demo/get_json_data.php';
$data = curl_get($url);
$data = json_decode($data, true);
print_r($data);
```


### 示例3：POST接口请求数据

代码：[php/func/curl/demo_curl_post.php]()

```php
function curl_post($url, array $post = array(), array $options = array()) 
{ 
    $defaults = array( 
        CURLOPT_POST => 1, 
        CURLOPT_HEADER => 0, 
        CURLOPT_URL => $url, 
        CURLOPT_FRESH_CONNECT => 1, 
        CURLOPT_RETURNTRANSFER => 1, 
        CURLOPT_FORBID_REUSE => 1, 
        CURLOPT_TIMEOUT => 4, 
        CURLOPT_POSTFIELDS => http_build_query($post) 
    ); 

    $ch = curl_init(); 
    curl_setopt_array($ch, ($options + $defaults)); 
    if( ! $result = curl_exec($ch)) 
    { 
        trigger_error(curl_error($ch)); 
    } 
    curl_close($ch); 
    return $result; 
} 

$url = 'http://123.56.21.232:8254/myprojects/demo/get_json_data.php';
$data = curl_post($url);
$data = json_decode($data, true);
print_r($data);
```


## MySQL


## Redis

Redis的默认端口号是`6379`。

### 安装

使用yum进行安装。

```
# yum install redis
```


### 启动

在后台启动。

```
# nohup redis-server &
```


### 使用PHP访问



## RPC



