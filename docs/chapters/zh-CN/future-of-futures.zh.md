# 期货的未来

[回去](toc/default.html)

---

快点等

`async` & `await`

---

.=异步计算

-   网络IO
-   来自其他线程或计算机的消息
-   连锁经营

---

Rust没有隐式的运行时事件循环(比如node.js)

---

## 抽象层

---

`Future<T>`和`Poll<T>`

部分`libcore`和`libstd`

---

`futures-rs`上面的抽象箱子

---

`tokio`抽象板条箱提供事件循环

---

## 一切都不稳定

每晚需要`futures_api`特征标志

---

<pre><code data-source="chapters/shared/code/future-futures/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

<pre><code data-source="chapters/shared/code/future-futures/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

大多数期货不会马上准备好.

相反,返回`Poll::Pending`直到准备好.

`poll()`将来自事件循环.

---

![](img/futures-rs-logo.svg)

`futures-rs`营救

---

有`oneshot`

<pre><code data-source="chapters/shared/code/future-futures/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

期货组合商

<pre><code data-source="chapters/shared/code/future-futures/4.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 显式运行时

![](img/tokio.jpg)

`tokio-rs`营救

---

`tokio`提供异步执行器和运行时

<pre><code data-source="chapters/shared/code/future-futures/5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 未来`futures`

<br/>

-   两个新关键词
-   编写看起来同步的代码
    -   免费获得异步\*

<small>\*(ISH)</small>

---

<pre><code data-source="chapters/shared/code/future-futures/6.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 我要那个!

---

## 时间线

-   RFC 2394(跟踪问题6550547)
-   在编译器中实现
-   几个阻塞问题(51719,53249,53259,…)
-   *不是*包括在《铁锈2018》中
    -   但很快就~~2018年末~~2019!)
