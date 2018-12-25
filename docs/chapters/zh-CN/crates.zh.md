# 板条箱

[回去](toc/default.html)

---

Rust调用库`crates`. 板条箱的管理通常通过以下方式完成`cargo`但这并不是绝对必要的.

---

## 图书馆的使用

在Rust 2015,您需要通过`extern crate`-声明.

<pre><code data-source="chapters/shared/code/crates/0.rs" data-trim="hljs rust"></code></pre>

这导入"SERialisation/DEserialisation"-Framework.

---

在Rust2018年,这不再需要.通过货物申报的图书馆可以简单地用于`use`-声明.

<pre><code data-source="chapters/shared/code/crates/1.rs" data-trim="hljs rust"></code></pre>

---

## 宏用法

由于Rust 2018不再需要显式地导入宏,它们就像函数一样工作.

简单地调用宏如下

<pre><code data-source="chapters/shared/code/crates/2.rs" data-trim="hljs rust"></code></pre>

您可能仍然会遇到旧的Rust代码,它依赖于`#[macro_use]`

---

Crates可以重命名,就像普通使用语句一样:

<pre><code data-source="chapters/shared/code/crates/3.rs" data-trim="hljs rust"></code></pre>

注意`crate`在使用关键字之前.您使用的是本地别名.原作仍然存在.

---

备选方案:通过cargo重命名依赖项:

<pre><code data-source="chapters/shared/code/crates/4.toml" data-trim="hljs toml"></code></pre>

---

## 克拉西奥

可以在[crates.io](https://crates.io)它们的文档自动发布到[docs.rs](https://docs.rs).

---

## 板条箱及其应用

`cargo install my_crate`安装装有板条箱的应用程序.
