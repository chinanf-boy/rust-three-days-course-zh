# 动态和静态库

[回去](toc/default.html)

---

让我们尝试使用C语言中的Rust.

---

## 图书馆

<pre><code data-source="chapters/shared/code/dynamic-and-static-libs/1.rs" data-trim="hljs rust"></code></pre>

---

## C-Header(摘录)

<pre><code data-source="chapters/shared/code/dynamic-and-static-libs/2.c" data-trim="hljs c"></code></pre>

---

## 货物

<pre><code data-source="chapters/shared/code/dynamic-and-static-libs/3.toml" data-trim="hljs toml"></code></pre>

`cargo build`现在将构建静态库而不是rlib.`cdylib`s是一种特殊的dylib,它也可以删除所有特定于Rust的元数据.

---

## 用法

<pre><code data-source="chapters/shared/code/dynamic-and-static-libs/4.c" data-trim="hljs c"></code></pre>

<pre><code data-source="chapters/shared/code/dynamic-and-static-libs/5.sh" data-trim="hljs sh"></code></pre>

---

## 执行

<pre><code data-source="chapters/shared/code/dynamic-and-static-libs/6.sh" data-trim="hljs sh"></code></pre>

---

## 哎呀!

照顾好所有权!

<pre><code data-source="chapters/shared/code/dynamic-and-static-libs/7.rs" data-trim="hljs rust"></code></pre>

---

## 帮手

-   Cheddar-从Rust-Libs生成C-Header.
