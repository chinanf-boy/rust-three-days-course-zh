# 闭包

[回去](toc/default.html)

---

Rust有闭塞.多重的,偶数的

-   **优势:**只使用绝对必要的运行时资源进行高度优化,通常没有.
-   **缺点:**了解特定的闭包类型并不总是容易的.

---

## 记数法

<pre><code data-source="chapters/shared/code/closures/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

<pre><code data-source="chapters/shared/code/closures/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 闭合类型

弗内斯

-   闭包消耗其环境

FnMut 

-   闭包改变了它的环境

Fn

-   闭包以不变的方式引用其环境.

---

`rustc`自动推断类型,但是类型签名需要它!

---

闭包类型之间的关系是:Fn是超性状FnMut,FnMut是FnOnce的超性状.

---

## 闭包参数的符号

<pre><code data-source="chapters/shared/code/closures/3.rs" data-trim="hljs rust"></code></pre>

---

## 移动和结束

由于闭包环境是隐式的,所以将类型移动到闭包中是显式的.

<pre><code data-source="chapters/shared/code/closures/4.rs" data-trim="hljs rust"></code></pre>
