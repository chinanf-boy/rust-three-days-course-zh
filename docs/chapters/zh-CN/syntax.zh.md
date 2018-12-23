# 句法

[回去](toc/default.html)

---

Rust具有受函数语言影响的C风格的语法.

具体的功能将在后面介绍.

---

## 基础

<pre><code data-source="chapters/shared/code/syntax/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## `if`

<pre><code data-source="chapters/shared/code/syntax/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## `match`

<pre><code data-source="chapters/shared/code/syntax/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## `if let`

<pre><code data-source="chapters/shared/code/syntax/4.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## `loop`和`while`

<pre><code data-source="chapters/shared/code/syntax/5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## `for`和`while let`

<pre><code data-source="chapters/shared/code/syntax/6.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## `struct`,`type`和`enum`

<pre><code data-source="chapters/shared/code/syntax/7.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## `impl`和`trait`

<pre><code data-source="chapters/shared/code/syntax/8.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 借用

<pre><code data-source="chapters/shared/code/syntax/9.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 寿命

`'foo`可以用来描述借款的寿命.

<pre><code data-source="chapters/shared/code/syntax/10.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 作用域

锈是块状的.范围可以返回值.

<pre><code data-source="chapters/shared/code/syntax/11.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 闭包

<pre><code data-source="chapters/shared/code/syntax/12.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 泛型

<pre><code data-source="chapters/shared/code/syntax/13.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

一般来说`where`语法优先.

---

## `use`和`mod`

<pre><code data-source="chapters/shared/code/syntax/14.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 属性

Rust属性用于许多不同的事物.在[reference](https://doc.rust-lang.org/reference/attributes.html).

<pre><code data-source="chapters/shared/code/syntax/15.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 分号上的

没有分号的行隐式返回.别担心,如果你忘了,编译器会告诉你的.

<pre><code data-source="chapters/shared/code/syntax/16.rs" data-trim="hljs rust" class="lang-rust"></code></pre>
