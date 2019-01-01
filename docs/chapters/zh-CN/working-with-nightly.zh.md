# 与夜间工作

[回去](toc/default.html)

---

## 为什么?

- 依赖关系可能需要每晚
- 编译时间和错误消息有时是更好的(有时)
- 有几个特性尚未稳定
- 编译器插件

---

## 使用夜间

使用`rustup`在一个特定的目录中覆盖使用的版本.

<pre><code data-source="chapters/shared/code/working-with-nightly/1.bash" data-trim="hljs bash"></code></pre>

---

## 特性

特点是封闭的"特色旗帜",启用项目背后宽.

一些例子:

- `asm`它提供了内联汇编支持吗
- `no_std`禁用的特征`extern crate std`
- `inclusive_range`,类似于稳定`exclusive_range`

---

## 支持功能

要启用功能,添加以下行成`src/main.rs`(可执行文件),或`src/lib.rs`(库):

<pre><code data-source="chapters/shared/code/working-with-nightly/2.rs" data-trim="hljs rust"></code></pre>

---

## 编译器插件

编译器插件添加额外功能生 Rust.

- 例如:
- 剥绒机
- 库就像[`regex_macros`](https://github.com/rust-lang/regex#usage-regex-compiler-plugin)

---

## 使编译器插件

使编译器插件添加以下行成`src/main.rs`(可执行文件),或`src/lib.rs`(库):

<pre><code data-source="chapters/shared/code/working-with-nightly/3.rs" data-trim="hljs rust"></code></pre>

---

## 警告

它是未知的,当如果 compiler-plugins 将企稳.

---

## 稳定发展在夜间

值得推荐的使用的编译器接近发布版本使用.
