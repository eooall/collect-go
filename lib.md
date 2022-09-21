## errors

https://github.com/pkg/errors Go 语言自身提供的错误处理比较简单,这个库提供了更强大的功能，比如：

包装异常
包装堆栈等。
常用的有以下 API：
```code
// WithMessagef annotates err with the format specifier.
func WithMessagef(err error, format string, args ...interface{}) error

// WithStack annotates err with a stack trace at the point WithStack was called.
func WithStack(err error) error
```

## excelize

https://github.com/qax-os/excelize 是一个读写 Excel 的库，基本上你能遇到的 Excel 操作它都能实现。

## go-cache

https://github.com/patrickmn/go-cache 是一个类似于 Java 中的 Guava cache，线程安全，使用简单；不需要分布式缓存的简单场景可以考虑。

```code
c := cache.New(5*time.Minute, 10*time.Minute)
// Set the value of the key "foo" to "bar", with the default expiration time
c.Set("foo", "bar", cache.DefaultExpiration)
```

## copier

https://github.com/jinzhu/copier 看名字就知道这是一个数据复制的库， 可以将两个字段相同但对象不同的 struct 进行数据复制，也支持深拷贝。

```code
func Copy(toValue interface{}, fromValue interface{}) (err error) 
```

## env

https://github.com/caarlos0/env 这个库可以将我们的环境变量转换为一个 struct

```code
type config struct {
 Home string `env:"HOME"`
}
func main() {
 cfg := config{}
 if err := env.Parse(&cfg); err != nil {
  fmt.Printf("%+v\n", err)
 }

 fmt.Printf("%+v\n", cfg)
}
```

## user_agent

https://github.com/mssola/user_agent 是一个格式化 user-agent 的小工具。

```code
 func main() {
    ua := user_agent.New("Mozilla/5.0 (Linux; U; Android 2.3.7; en-us; Nexus One Build/FRF91) AppleWebKit/533.1 (KHTML, like Gecko) Version/4.0 Mobile Safari/533.1")

    fmt.Printf("%v\n", ua.Mobile())   // => true
    fmt.Printf("%v\n", ua.Bot())      // => false
    fmt.Printf("%v\n", ua.Mozilla())  // => "5.0"
    fmt.Printf("%v\n", ua.Model())    // => "Nexus One"
    fmt.Printf("%v\n", ua.Platform()) // => "Linux"
    fmt.Printf("%v\n", ua.OS()) 
 }
```

## phonenumbers

https://github.com/nyaruka/phonenumbers 手机号码验证库，可以不用自己写正则表达式了。

```code
// parse our phone number
num, err := phonenumbers.Parse("6502530000", "US")
```

## BloomRPC

https://github.com/uw-labs/bloomrpc 一个 gRPC 可视化工具

## elastic

https://github.com/olivere/elastic 这也是一个非常成熟的 elasticsearch 库

## go-pilosa

https://github.com/pilosa/go-pilosa 是一个位图数据库的客户端，位图数据库的场景应用比较有限，通常是有标签需求时才会用到；

比如求 N 个标签的交并补集；数据有一定规模后运营一定会提相关需求；

可以备着以备不时之需