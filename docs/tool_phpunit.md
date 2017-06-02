# phpunit - 单元测试工具

## 安装

## 示例

### 编写测试用例

```
class ValidatorTest extends PHPUnit_Framework_TestCase {

    private $validator = null;

    public function setUp() {
        $this->validator = new Validator();
    }

    /**
     * 数据类型不正确
     */
    public function testInvalid() {
        $schema = array(
            'DATA_TYPE' => 'Int',
            'DATA_RANGE' => 'value > 0 && value < 100',
            'DATA_OPTION' => array(3, 15, 19, 30, 99),
        );
        $value = '30';
        $errorMsg = '';
        $result = $this->validator->validate($schema, $value, $errorMsg);

        $this->assertFalse($result);
        $this->assertEquals('Data type Int is invalid!', $errorMsg);
    }
}
```


### 执行测试用例

```php
$ phpunit UnitTest ValidatorTest.php 
PHPUnit 3.4.15 by Sebastian Bergmann.
........
Time: 0 seconds, Memory: 3.75Mb
OK (8 tests, 16 assertions)
```

## 参考

官网网站：http://www.phpunit.cn/

PHPUnit手册：http://www.phpunit.cn/manual/current/zh_cn/phpunit-book.html

