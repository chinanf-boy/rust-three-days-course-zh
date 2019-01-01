# 内存方面的考虑

[回去](toc/default.html)

---

`size_of`和`size_of_val`帮助检查类型的大小(以字节为单位).

<pre><code data-source="chapters/shared/code/memory-considerations/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 成熟度

Rust 中的所有值都具有固定或灵活大小的内存大小.语言通过标记特征来表达这一点.`Sized`. `Sized`类型具有在编译时已知的大小.

小型型号*必须*通过间接(例如,通过借用)来解决.

---

## 结构尺寸

结构具有其包含的值的大小.

<pre><code data-source="chapters/shared/code/memory-considerations/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 工具书类

参考文献的大小为 1`usize`. 对于简单的盒子也是如此.

<pre><code data-source="chapters/shared/code/memory-considerations/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 特质对象

Trait 对象需要 2`usize`.

<pre><code data-source="chapters/shared/code/memory-considerations/4.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 片

切片需要 2 次.他们的盒子也是如此.

<pre><code data-source="chapters/shared/code/memory-considerations/5.output" data-trim="hljs output" class="lang-rust"></code></pre>

---

## 向量

向量需要 3 次使用,以另外存储它们的容量.

<pre><code data-source="chapters/shared/code/memory-considerations/6.output" data-trim="hljs output" class="lang-rust"></code></pre>

---

## `&str`,`Box<str>`,`String`

它们的行为与切片和向量相同.

---

## 枚举类型

枚举需要其最大值的大小、1 字节的判别式以及填充.

<pre><code data-source="chapters/shared/code/memory-considerations/7.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

如果 0 不是合法值,则 Option 将其用作`None`-病例.

目前还没有稳定的方法将此消息传递给编译器.
