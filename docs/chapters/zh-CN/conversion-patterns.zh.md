# 转换

[回去](toc/default.html)

---

Rust提供了多种方式来表达一种类型到另一种类型的转换.

这提高了安全性并传达了意图.

---

## `From<T>`,`Into<T>`

一种类型到另一种类型的转换.

如果`X`是`From<T>`然后`T`是`Into<X>`自动地.

使用取决于上下文.

---

## 例子

<pre><code data-source="chapters/shared/code/conversion-patterns/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 什么?`try!`或`?`具体做什么?

<pre><code data-source="chapters/shared/code/conversion-patterns/2.rs" data-trim="hljs rust"></code></pre>

---

## `AsRef<T>`

参考到参考转换.指示类型可以容易地生成对其他类型的引用.

---

## 例子

<pre><code data-source="chapters/shared/code/conversion-patterns/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## `Borrow<T>`和`BorrowMut<T>`

`Borrow<T>`关于所有权和借贷的摘要.`Borrow<T>`表示该类型可以借用`T`. 类似于`AsRef<T>`但是传达的是不同的意图.
