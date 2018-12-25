# 有效Rust蚀

[回去](toc/default.html)

---

## 遍历器

习惯Iterator-API并使用它们!

迭代器经过大量优化,尤其是它们的组合.

---

## 所有权方面值得注意的问题

如果不立即在集合中放置另一个值,则将数据从集合中移出并不容易.

印第安纳·琼斯`std::mem::swap`或`std::mem::replace`.

---

在某些情况下,`Drain`可以使用迭代器,该迭代器逐个从集合中抽取值并同时缩小值.

---

## 编译时代

`rustc`它不是最快的编译器,在LLVM中花费大量时间用于代码生成和优化.

`cargo check`只运行类型检查,不编译代码.

将代码分隔在多个板条箱中可能有帮助,因为板条箱只能在代码更改时重新编译.

减少泛型的使用可以提高编译时间.

---

## 优化二进制大小

-   使用系统分配器(夜间特性)
-   如果少用libstd,则可以替换它
-   减少单态化函数调用的数量

---

## 正确转换

避免传递可以评估为特定类型的通用参数.

<pre><code data-source="chapters/shared/code/effective-rust/1.rs" data-trim="hljs rust"></code></pre>

---

<pre><code data-source="chapters/shared/code/effective-rust/2.rs" data-trim="hljs rust"></code></pre>

在图书馆内嵌.

---

## 帮手

-   GDB支持Rust,也支持签出`rust-gdb`
-   `valgrind`生Rust效果好
-   [`afl.rs`](https://github.com/rust-fuzz/afl.rs)允许使用美国Fuzzy Lop进行模糊处理
-   [`cargo-fuzz`](https://github.com/rust-fuzz/cargo-fuzz)使用`libfuzz`用于模糊
-   [`cargo-kcov`](https://github.com/kennytm/cargo-kcov)能够处理代码覆盖
