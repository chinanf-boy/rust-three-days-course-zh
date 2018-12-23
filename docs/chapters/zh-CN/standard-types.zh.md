# 标准类型

[回去](toc/default.html)

---

在锈菌中有几种普遍存在的类型.

他们利用强大的类型系统来完成基本任务.

---

## 概述

-   `Option<T>`-消除对`null`本原的
-   `Result<T,E>`-消除对例外的需要.
-   `Vec<T>`-可生长阵列.
-   `HashMap<K,V>`-密钥值存储.

---

## `Option<T>`

<pre><code data-source="chapters/shared/code/standard-types/1.rs" data-trim="hljs rust"></code></pre>

选项是包装器类型,需要展开才能使用.

---

## `Option<T>`

任何不总是返回值的函数返回`Option<T>`.

<pre><code data-source="chapters/shared/code/standard-types/2.rs" data-trim="hljs rust"></code></pre>

---

## `Option<T>`好处

程序员*总是*知道哪里有`None`可能出现,并能够决定如何处理这种情况.

这个特性有助于*消除神秘*从编码过程,和帮助的信心.

---

## `Option<T>`展开

`unwrap()`如果值为`None`.

这只推荐在测试和原型化中.

<pre><code data-source="chapters/shared/code/standard-types/3.rs" data-trim="hljs rust"></code></pre>

---

## `Option<T>`安全性

`match`是安全工作的几种方法之一`Option`s.

<pre><code data-source="chapters/shared/code/standard-types/4.rs" data-trim="hljs rust"></code></pre>

无论`maybe_a_value`这个程序永远不会崩溃.

---

## `Option<T>`问题

这种类型是否完全消除了对`null`原语?

有什么好处?

---

## `Result<T,E>`

<pre><code data-source="chapters/shared/code/standard-types/5.rs" data-trim="hljs rust"></code></pre>

结果是包含成功值或错误值的包装器类型.

---

## `Result<T,E>`使用

结果可以通过`unwrap()`就像`Option`类型,并且可以按照相同的方式进行处理.

<pre><code data-source="chapters/shared/code/standard-types/6.rs" data-trim="hljs rust"></code></pre>

在后面的章节中将讨论处理复杂的错误场景.

---

## `Result<T,E>`问题

这种类型是否完全消除了对异常的需求?

有什么好处?

---

## `Vec<T>`

拥有、可变、可生长的阵列.位于堆上.

<pre><code data-source="chapters/shared/code/standard-types/7.rs" data-trim="hljs rust"></code></pre>

---

## `Vec<T>`创造

创建与`Vec::new()`或`vec![]`宏.

<pre><code data-source="chapters/shared/code/standard-types/8.rs" data-trim="hljs rust"></code></pre>

---

## `Vec<T>`作为切片

`Vec<T>`器具`Deref<Target=[T]`因此,它很容易用作切片.

<pre><code data-source="chapters/shared/code/standard-types/9.rs" data-trim="hljs rust"></code></pre>

---

## `HashMap<K,V>`

HashMaps是关键值存储.键必须实现`Hash`.

<pre><code data-source="chapters/shared/code/standard-types/10.rs" data-trim="hljs rust"></code></pre>

---

## `HashMap<K,V>`:`entry()`

在适当的位置操纵键的冷却响应条目.

<pre><code data-source="chapters/shared/code/standard-types/11.rs" data-trim="hljs rust"></code></pre>
