# 发送与同步

[回去](toc/default.html)

---

对于并发语义,Rust有两个特殊特性.

-   `Send`标记一个安全的结构*发送*线程之间.
-   `Sync`标记一个安全的结构*分享*线程之间.
    -   (`&T`是`Send`)

---

Rust使用这些特性来防止数据竞争.

他们是*自动导出*如果合适,适用于所有类型.

---

## 自动派生

<pre><code data-source="chapters/shared/code/send-and-sync/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

有一些值得注意的类型不是`Send`或`Sync`.

如`Rc`原始指针`UnsafeCell`.

---

## 例子:`Rc`

<pre><code data-source="chapters/shared/code/send-and-sync/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 例子:`Rc`

<pre><code data-source="chapters/shared/code/send-and-sync/3.output" data-trim="hljs output"></code></pre>

---

## 实施

可以添加`Send`和`Sync`一种类型.

<pre><code data-source="chapters/shared/code/send-and-sync/4.rs" data-trim="hljs rust"></code></pre>

在这些情况下,线程安全的任务留给了实现者.

---

## 关系

如果一个类型实现了这两者`Sync`和`Copy`然后它也可以实现`Send`.

---

## 关系

一种`&T`可以实现`Send`如果类型`T`也实现`Sync`.

<pre><code data-source="chapters/shared/code/send-and-sync/5.rs" data-trim="hljs rust"></code></pre>

---

## 关系

一种`&mut T`可以实现`Send`如果类型`T`也实现`Send`.

<pre><code data-source="chapters/shared/code/send-and-sync/6.rs" data-trim="hljs rust"></code></pre>

---

## 后果

有`Send`和`Sync`?

---

## 后果

在类型系统级别上携带此信息允许将数据竞争bug降低到*编译时间*水平.

防止这个错误类到达生产系统.

`Send`和`Sync`独立于并发选择(异步、线程等).
