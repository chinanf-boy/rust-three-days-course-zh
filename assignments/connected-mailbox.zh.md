# The mailbox

实现一个小型TCP服务器,使用我们昨天写的协议处理请求.

## 1. Turn you project into a workspace

读<http://doc.crates.io/manifest.html>

工作区应包含您的服务器和昨天的redisish库.

```
my_project
|- Cargo.toml
|- redisish
|- connected-mailbox
```

```
$ cat connected-mailbox/Cargo.toml
...
[dependencies]
redisish = { path = "../redisish" }
```

## 2. Accept connections and implement the protocol

1.  每个连接只发送一个命令
2.  PUBLISH插入到消息框中
3.  RETRIEVE以FIFO方式检索消息

使用`.unwrap`对于开头的所有错误处理.

使用`std::net::TcpListener`用于连接.

使用`std::collections::VecDeque`用于存储.

阅读文档`std::io::Read`,`std::io::Write`特质,特别是`read_to_string`.

## 3. Do proper error handling

实施一个`ServerError`,允许两者兼顾`io::Error`s和`redisish::Error`秒.

## 4. Implement multithreading

每个连接:

1.  使用生成线程`std::thread::spawn`
2.  包裹着`VecDeque`在一个`std::sync::Mutex`和`std::sync::Arc`传递它
