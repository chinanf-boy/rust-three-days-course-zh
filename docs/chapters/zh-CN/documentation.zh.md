# 文档

[回去](toc/default.html)

---

## `rustdoc`

Rust 提供了一个标准文档工具,称为`rustdoc`. 它通常通过以下方式使用`cargo doc`.

因为这个 Rust 代码几乎总是以通用格式进行文档化.

---

## `std`文档

标准库文档托管在<https://doc.rust-lang.org/std/>.

本地脱机版本可以通过以下操作打开:

<pre><code data-source="chapters/shared/code/documentation/1.bash" data-trim="hljs bash"></code></pre>

---

## 纸板箱文件

托运箱的文件<http://crates.io/>可以在<https://docs.rs/>.

一些板条箱还可以通过其列表上的"文档"链接找到其他文档<http://crates.io/>.

---

## 示例:模块

<iframe src="https://doc.rust-lang.org/std/vec/" width="100%" height="400">
</iframe>

---

## 示例:模块

这个页面记录了`vec`模块.

它从一些示例开始,然后列出`struct`模块导出的 s、特征或函数.

---

## 它是如何产生的?

`rustdoc`可以读取 Rust 代码和 Markdown 文档.

`//!`和`///`注释读作 Markdown.

<pre><code data-source="chapters/shared/code/documentation/2.rs" data-trim="hljs rust"></code></pre>

---

## 示例:组件

<iframe src="https://doc.rust-lang.org/std/string/#structs" width="100%" height="400">
</iframe>

---

## 示例:函数

<iframe src="https://doc.rust-lang.org/std/string/struct.String.html#method.new" width="100%" height="400">
</iframe>

---

## 代码示例

默认情况下,测试文档中的代码块.

<pre><code data-trim="hljs rust">
/// ```rust
/// assert_eq!(always_true(), true)
/// ```
fn always_true() -> bool { true }
</code></pre>

---

## 无运行实例

此代码将不会运行,因为它不会终止.

<pre><code data-trim="hljs rust">
/// ```rust,no_run
/// serve();
/// ```
fn serve() -> ! { loop {} }
</code></pre>

---

## 导航

函数的参数和返回类型是到它们各自类型的链接.

左侧的侧边栏提供到模块其他部分的快速导航.

---

## Cargo 一体化

此命令构建并打开当前项目的文档:

```sh
$ cargo doc --open
```

---

```sh
$ cargo doc --document-private-items --open
```
