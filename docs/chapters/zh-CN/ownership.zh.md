# 所有权

[回去](toc/default.html)

---

所有权是Rust菌内存管理的基础.

---

## 规则

-   每个值只有一个所有者
-   所有权可以转让
-   所有者负责从内存中删除数据
-   所有者拥有对数据的所有权限,并且可以对其进行更改

---

这些规则:

-   是Rust型系统的基础
-   在编译时执行
-   在许多其他方面是可行的

---

## 例子

<pre><code data-source="chapters/shared/code/ownership/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

<pre class="diagram" data-source="chapters/shared/diagram/ownership/1.diagram"></pre>

---

如果我们尝试使用`dot`第二次?

---

<pre><code data-source="chapters/shared/code/ownership/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 哎呀!

---

在Rust-Lingo中,称为`consuming`. `pacman`消耗`dot`.

这个值不能再使用了.

---

## 背景

打电话时`pacman`具有`dot`该值被"移动"到`pacman`. 此时,所有权移交给`pacman`. `main`不再是数据的所有者,因此不允许访问或操作数据.

---

## 使用移动:显式克隆

如果这种行为是不受欢迎的,怎么办?我们可以创建数据的第二个副本!

---

<pre><code data-source="chapters/shared/code/ownership/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

<pre class="diagram" data-source="chapters/shared/diagram/ownership/2.diagram"></pre>

---

克隆是一种通用操作,取决于手头数据的复杂性,可能代价高昂.

---

## 使用移动:复制而不是移动

<pre><code data-source="chapters/shared/code/ownership/4.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

Copy是指可以在内存中快速复制(使用memcopy)并允许复制的数据(例如:不是文件指针).

---

复制的值遵循标准的所有权规则,但是当所有权被传递时,它们被复制.

---

# 警告

围绕移动的术语是相似的,但与C++中使用的术语不相同,这就是为什么您应该总是使用Rust蚀术语:所有权、传递所有权和消耗.

---

## 实际例子

<pre><code data-source="chapters/shared/code/ownership/5.rs" data-trim="hljs rust"></code></pre>

如果我们在调用之后使用File会发生什么`use_file`?

---

## 小测验

`drop`是立即释放值的函数.实现是什么样子的?

<pre><code data-source="chapters/shared/code/ownership/6.rs" data-trim="hljs rust"></code></pre>

---

<pre><code data-source="chapters/shared/code/ownership/7.rs" data-trim="hljs rust"></code></pre>
