# `std`图书馆旅游

[回去](toc/default.html)

---

是时候参观一些有趣的地方了`std`.

我们将集中于那些我们没有在其他方面覆盖的部分.

---

## 收藏

[`std::collections`](https://doc.rust-lang.org/std/collections/index.html)

包含许多有价值的数据结构.特别地:

-   [`Vec`](https://doc.rust-lang.org/std/vec/struct.Vec.html)用于存储值序列.
-   [`HashMap`](https://doc.rust-lang.org/std/collections/struct.HashMap.html)用于存储为键值对.

在寻求优化代码时,其他选项可能是合适的.

---

## 条目

[`std::collections::hash_map::Entry`](https://doc.rust-lang.org/std/collections/hash_map/enum.Entry.html)

打电话`.entry()`在一`HashMap`访问此API并允许"插入或更新"访问.

<pre><code data-source="chapters/shared/code/std-lib-tour/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 幻象数据

[`std::marker::PhantomData`](https://doc.rust-lang.org/std/marker/struct.PhantomData.html)

零大小类型用于标记它们拥有`T`. 这对于需要标记、泛型或使用不安全代码的类型很有用.

<pre><code data-source="chapters/shared/code/std-lib-tour/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 命令

[`std::process::Command`](https://doc.rust-lang.org/std/process/struct.Command.html)

流程构建器,提供对新流程应如何生成的细粒度控制.用于与其他可执行文件交互.

<pre><code data-source="chapters/shared/code/std-lib-tour/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 同步原语

[`std::sync`](https://doc.rust-lang.org/std/sync/)

提供此类类型`Mutex`,`RwLock`,`CondVar`,`Arc`和`Barrier`s.

<pre><code data-source="chapters/shared/code/std-lib-tour/4.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 读写

[`std::io::Read`](https://doc.rust-lang.org/std/io/trait.Read.html) & [`std::io::Write`](https://doc.rust-lang.org/std/io/trait.Write.html)

对文件、套接字、缓冲区以及它们之间的任何东西的通用读写功能.也是部分[`std::io::prelude`]\([`std::io::prelude::*`](https://doc.rust-lang.org/std/io/prelude/).

<pre><code data-source="chapters/shared/code/std-lib-tour/5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 文件系统操作

[`std::fs`](https://doc.rust-lang.org/std/fs/) & [`std::path`](https://doc.rust-lang.org/std/path/)

路径处理和文件操作.

<pre><code data-source="chapters/shared/code/std-lib-tour/6.rs" data-trim="hljs rust" class="lang-rust"></code></pre>
