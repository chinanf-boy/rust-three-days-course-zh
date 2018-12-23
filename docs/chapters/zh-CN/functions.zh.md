# 功能

[回去](toc/default.html)

---

## 宣言

<pre><code data-source="chapters/shared/code/functions/1.rs" data-trim="hljs rust"></code></pre>

---

## 争论

<pre><code data-source="chapters/shared/code/functions/2.rs" data-trim="hljs rust"></code></pre>

---

## 返回

返回是可选的.签名必须完整.

<pre><code data-source="chapters/shared/code/functions/3.rs" data-trim="hljs rust"></code></pre>

---

## 泛函

泛型函数具有类型参数.

<pre><code data-source="chapters/shared/code/functions/4.rs" data-trim="hljs rust"></code></pre>

---

## 有界

泛型函数也可以具有边界.

这些是等价的:

<pre><code data-source="chapters/shared/code/functions/5.rs" data-trim="hljs rust"></code></pre>

---

# 评论

-   不具有`Copy`特性在通过值传递时被消耗.
-   返回引用可能涉及澄清生存期(稍后讨论).
