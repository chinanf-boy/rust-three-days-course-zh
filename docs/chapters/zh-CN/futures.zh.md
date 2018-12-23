# 期货

[回去](toc/default.html)

---

板条箱[`futures-rs`](https://github.com/alexcrichton/futures-rs)通常用于构建异步功能.它提供了类似于`Promise`在Javascript中.

---

## 关于性能和可用性的说明

-   Rust没有像Node.js那样的隐式运行时事件循环.
    -   Tokio提供了一个显式的.
-   期货是一种零成本的抽象.
-   用于`futures-rs`被认为是"不好的".
-   异步生态系统还很年轻.耐心点!

---

## 你拍了一张

`futures::sync::oneshot`提供基本的、单次使用的未来.

他们感觉自己像是一个频道,甚至带有`tx`和`rx`一对.

---

## 你拍了一张

<pre><code data-source="chapters/shared/code/futures/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 你拍了一张

如果我们交换`rx.wait()`以及`tx.send()`?

有**不**隐式线程,调用`rx.wait()`阻塞线程直到接收到数据!

---

## 你有单镜头(线程)

<pre><code data-source="chapters/shared/code/futures/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 多次拍摄

<pre><code data-source="chapters/shared/code/futures/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 57个频道(没有播放)

安`futures::sync::mpsc`表示将产生一系列期货的渠道.

`mpsc::channel`缓冲区大小是有限的,并且与背压有关.

`mpsc::unbounded`没有限制的大小,可以增长以适应所有内存.

---

## 57个频道(没有播放)

<pre><code data-source="chapters/shared/code/futures/4.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## CPU池中的趾

`futures-rs`随伴而来[`futures_cpupool`](https://docs.rs/futures-cpupool/0.1.7/futures_cpupool/)它提供了一种简单、易于使用的CPU池类型.

这允许我们调度任意(异构!)作业到一个池中,而不用担心它在哪里(以及何时)执行.

---

## CPU池中的趾

<pre><code data-source="chapters/shared/code/futures/5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 与期货的交互

大多数时候,你不会创造原始期货,并把它们四处发送.

相反,您可能最终会作为板条箱的一部分与它们进行交互.

与其担心如何创建和执行它们,不如更担心如何处理它们,以及如何处理它们.
