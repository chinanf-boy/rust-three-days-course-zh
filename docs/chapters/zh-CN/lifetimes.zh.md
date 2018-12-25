# 生命周期

[回去](toc/default.html)

---

<pre><code data-source="chapters/shared/code/lifetimes/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

<pre><code data-source="chapters/shared/code/lifetimes/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

铁 Rust 的一生以难以理解而臭名昭著.

---

这没有必要.

---

## 生命周期

- 生命周期描述值保留在内存中的时间
- 他们描述-他们不能强迫或改变任何事情
- 终身就是类型!

---

## 你已经用过了

<pre><code data-source="chapters/shared/code/lifetimes/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 动机

<pre><code data-source="chapters/shared/code/lifetimes/4.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

如果编译,这段代码将违反内存安全.

---

正确的结构定义是:

<pre><code data-source="chapters/shared/code/lifetimes/5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

包装现在是:

- 类型 T 上的泛型
- 以及终生'a(自己)
- 借来的价值必须存在*至少等长*

---

外卖:

生命周期描述最小条件

---

## 一个签名的多个生命周期

<pre><code data-source="chapters/shared/code/lifetimes/6.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 亚生命期

<pre><code data-source="chapters/shared/code/lifetimes/7.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

术语:`Input outlives Tokenizer`

---

终生不能*更多*然后描述一下"这个必须比另一个活得更长(或者至少等长)".

---

常见的陷阱:你不能"缩短生命周期",因为它仅仅描述了已经存在的东西.

---

## `'static`

`'static`生命比其他生命都长.那并不一定是永远的!

---

实例`'static`数据如下:

- 包含在二进制文件中的数据,例如静态字符串
- 堆分配的值(例如`Box`)
  - 只要它们不受生命周期较短的价值观的约束!
- 全局的

---

`'static`不是逃生舱口.在并发的,尤其是事件式的程序中,`'static`很平常.

这是因为大多数数据必须位于堆栈之外.

---

生命周期描述所有类型,不仅是引用,因此它们也是泛型代码中的界限.

<pre><code data-source="chapters/shared/code/lifetimes/8.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 终生爱丽丝

对于简单的情况,生命周期会自动插入到签名中.

<pre><code data-source="chapters/shared/code/lifetimes/9.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 生命与约束

<pre><code data-source="chapters/shared/code/lifetimes/10.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

<pre><code data-source="chapters/shared/code/lifetimes/11.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 生命与盒子

对于框,包含的值的默认生存期界限是`'static`. 有时,这太长并且可以被覆盖:

<pre><code data-source="chapters/shared/code/lifetimes/12.rs" data-trim="hljs rust" class="lang-rust" class="lang-rust"></code></pre>
