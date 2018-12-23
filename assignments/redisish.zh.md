1.  创建一个名为的库项目`redisish`
2.  实现以下功能

```rust
// appropriate data structures

pub fn parse(input: &str) -> Result<Command, Error> {
    ///...
}
```

3.  适当测试

## The protocol

该协议有两个命令:

"PUBLISH \\ \<消息>\\ n"

"检索\\ n"

应该将这些命令解析为`Command`值,`Error`应该适当地返回s(如空输入和未知动词等).

丢失的换行符是错误,可以忽略第一个换行符之后的所有内容.

允许空消息.

## Hints

阅读文档`str`(原始的),特别是`splitn`和`trim`.
