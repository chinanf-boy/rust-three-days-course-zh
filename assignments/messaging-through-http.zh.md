# An HTTP messaging broker

本练习的目的是在标准超HTTP库之上实现一个小型消息传递服务器.

服务器应该(最终)是异步的,经过测试并处理许多客户端.

还应该创建一个客户端.

本练习的目的是习惯Rust中的共享所有权技术,期货和异步编程.

该示例有意识地没有实现简单的现实协议,但可以扩展为一个.

## Specification

服务器在超级框架之上实现了一个简单的消息传递代理.为此,它应该实现三个端点:

## Preface

API是一个JSON API,应该使用适当的mime类型.

### Heartbeat

```
GET /
HEAD /
```

对"/"的请求应回复`200 OK`和一条短信:

```
{ "ok": true }
```

### Subscribe

```
GET /channels/<name>[,<name>,...]
```

将客户端订阅到一个或多个频道.只要客户端保持连接打开,服务器就会将该通道上发生的任何事件发送给客户端.格式为:

```
{ "channel": "<name>", "payload": <structured json|text>}\n
{ "channel": "<name>", "payload": <structured json|text>}\n
```

有效载荷结构的协商超出了服务器系统的范围.

断开连接的客户端不会收到事件.

### Publish

```
POST /channel/<name>
```

向频道发送任意事件.所有当前连接的频道订阅者都将收到该事件*有效载荷*.

该事件可以是JSON或任意文本.使用适当的MIME类型来指示其中任何一种.

## Extensions

### 1. Persistence

通道是持久的:在订阅时,客户端可以传递GET参数`last_message`,并将从频道中的该点接收所有消息.

### 2. Persistence on Disk

像扩展1.,但实际上保存到磁盘.
