### crontab 表达式解析工具

[历史版本源码位置](https://github.com/kasiss-liu/go-tools/tree/master/cron)

- 支持分钟、秒级表达式验证
    
    > 表达式长度6位以下（含6位）为常用分钟级crontab表达式，位数不足6位时，以第一位为分钟表达式自动补全
    
    > 表达式长度为7位为秒级表达式，验证时会匹配当前秒数

- Usage
```go
# 单个对象构建
c := NewCron().SetMinute("*/2").SetHour("*").SetDayOfMonth("?").SetMonth("*").SetDayOfWeek("*").SetYear("*")
if c.ValidExpress() == nil {
    println(c.ToExpress())
}

# 使用字符串构建对象
cronExpress, err = NewCronWithExpress("10,20 */5 10-20 * * ? *")
if err == nil {
    println(cronExpress.ToExpress())
    println(cronExpress.)
}

# 验证
Valid(cronExpress, time.Now())

# 字符串表达式验证
ValidExpress("10,20 */5 10-20 * * ? *",time.Now())

```