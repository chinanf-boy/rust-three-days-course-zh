# Deref-Conversion

[回去](toc/default.html)

---

## 动机

为什么要进行以下工作?

<pre><code data-source="chapters/shared/code/deref-coersions/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

Box没有名为"x"的字段!

---

## 自动解引用

在某些情况下,Rust自动取消引用.像其他事情一样,必须明确要求:

-   通过使用`.`操作人员
-   通过显式地取消引用`*`
-   借钱时`&`
-   这有时会导致丑陋`&*`-模式

---

这使得包装类型非常符合人体工程学和易于使用!

---

解引用由`Deref`和`DerefMut`-性状.

<pre><code data-source="chapters/shared/code/deref-coersions/2.rs" data-trim="hljs rust"></code></pre>

当请求取消引用时,该调用被引入.

---

## 重要的行为举止

-   弦>和STR
-   Vec<T> -> &\[T]

不修改字符串或向量长度的函数应该接受切片.选择内存布局以便*无成本*.

---

<pre><code data-source="chapters/shared/code/deref-coersions/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>
