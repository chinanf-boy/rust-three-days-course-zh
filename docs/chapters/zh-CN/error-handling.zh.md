# 错误处理

[回去](toc/default.html)

---

错误处理在Rust中是显式的.

具有已知错误条件的任何函数返回`Result<T,E>`.

**没有例外.**

---

<pre><code data-source="chapters/shared/code/error-handling/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 必须使用结果

<pre><code data-source="chapters/shared/code/error-handling/2.output" data-trim="hljs output"></code></pre>

---

## 使用`match`

<pre><code data-source="chapters/shared/code/error-handling/3.rs" data-trim="hljs rust"></code></pre>

---

## 使用带条件的结果

用`is_ok()`与错误`is_err()`:

<pre><code data-source="chapters/shared/code/error-handling/4.rs" data-trim="hljs rust"></code></pre>

---

## 使用`?`

使用`?`在具有多个可能的故障的函数中.

<pre><code data-source="chapters/shared/code/error-handling/5.rs" data-trim="hljs rust"></code></pre>

---

## 使用`?`

输出:

<pre><code data-source="chapters/shared/code/error-handling/6.output" data-trim="hljs output"></code></pre>

注意提前退出.

---

## 使用`?`在里面`main`

-   `main`可以返回`Result`
-   自此生Rust稳定`1.26`.

<pre><code data-source="chapters/shared/code/error-handling/6.rs" data-trim="hljs rust"></code></pre>

---

## 结果是包装类型

可以更改`Result<T,E>`变成一个`Result<U,E>`没有打开它.

变换A`Result<T,E>`变成一个`Result<T,X>`这也是可能的.

<pre class="diagram" data-source="chapters/shared/diagram/error-handling/1.diagram"></pre>

---

## 映射结果值

<pre><code data-source="chapters/shared/code/error-handling/7.rs" data-trim="hljs rust"></code></pre>

`map_err()`也有.

---

## 只报告错误

如果只需要报告错误,但没有有意义的返回值,请使用`Result<(), Error>`.
