# 串

[回去](toc/default.html)

---

Rust中有几种不同的弦.

最常见的是`String`和`&str`.

---

## `String`

-   *拥有*它存储的数据,并且可以自由地进行变异.
-   作为指向一些字节、长度和容量的指针存在.
-   存在于*堆*.
-   不执行`Copy`但是实现`Clone`.

---

## `&str`

-   对字符串片的不可变引用.
-   只看作借来的价值.
-   可以在堆、堆栈或程序内存中的任何位置.

---

## 创造

<pre><code data-source="chapters/shared/code/strings/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 什么时候使用什么?

-   `String`是*最容易的*出发时使用.再细化.
-   `String`拥有它的数据,因此它和`struct`或枚举.

-   `&'static str`对于常数值工作良好.
-   `&str`通常在函数参数中使用.

---

## `Deref`强制

仅仅因为存在多种类型并不意味着它们不能和谐工作.

<pre><code data-source="chapters/shared/code/strings/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

这是因为`String`S实现`Deref<Target=str>`.

---

## 异国字符串类型

-   `OsStr`和`OsString`在使用文件系统或系统调用时可能出现.

-   `CStr`和`CString`在与FFI一起工作时可能会出现.

之间的区别`*Str`和`*String`一般与正常类型相同.

---

## `OsString` & `OsStr`

这些类型表示*平台本土*串.这是必要的,因为Unix和Windows字符串具有不同的特征.

---

## 背后`OsString`场景

-   Unix字符串通常是任意的非零序列,通常解释为UTF-8.
-   Windows字符串通常是任意的非零序列,通常解释为UTF-16.
-   Rust色字符串总是有效的UTF-8,并且可能包含零.

`OsString`和`OsStr`弥合这一差距,允许廉价的往返转换`String`和`str`.

---

## `CString` & `CStr`

这些类型表示有效的C兼容字符串.

当使用外部代码进行FFI时,它们主要被使用.

强烈建议您阅读*全部的*使用这些类型之前的文档.

---

## 公共字符串任务

分裂:

<pre><code data-source="chapters/shared/code/strings/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 公共字符串任务

级联:

<pre><code data-source="chapters/shared/code/strings/4.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 公共字符串任务

替换:

<pre><code data-source="chapters/shared/code/strings/5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 接受`String`或`str`

可以毫不痛苦地接受:

<pre><code data-source="chapters/shared/code/strings/6.rs" data-trim="hljs rust" class="lang-rust"></code></pre>
