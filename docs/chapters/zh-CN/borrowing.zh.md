# 借用

[回去](toc/default.html)

---

## 你所拥有的,你可以借

---

所有权提供了坚实的语义基础,但从长远来看变得不切实际.

---

如果被调用的函数没有再次将所有权返回到值,那么在函数调用之后重用数据是不可能的.

---

我们改借吧!

---

<pre><code data-source="chapters/shared/code/borrowing/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

<pre class="diagram" data-source="chapters/shared/diagram/borrowing/1.diagram"></pre>

---

简单的借贷可以随时发生.

---

如果我们想要改变值呢?

---

<pre><code data-source="chapters/shared/code/borrowing/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

可变借贷是排他的!

---

## 借贷规则

价值观可以是:

- 想借多少就借多少
- 或者完全可变一次

所有权保留在调用上下文中,以及解除分配.

---

这能拯救我们吗?

---

## 你看到潜在的问题了吗?

<pre><code data-source="chapters/shared/code/borrowing/3.rs" data-trim="hljs rust"></code></pre>

---

如下:

- 每种类型`T`有一种类型`&T`
- 每种类型`T`有一种类型`&mut T`
- `&&T`是有效类型
- `& &mut T`不是有效类型.为什么?

---

## 借阅为参考

这意味着我们需要不时地去引用它们.

<pre><code data-source="chapters/shared/code/borrowing/4.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 借词是词汇性的.

<pre><code data-source="chapters/shared/code/borrowing/5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 这作品

<pre><code data-source="chapters/shared/code/borrowing/6.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 借贷与匹配

有时您希望引用枚举的内部值,但不希望使用它.

<pre><code data-source="chapters/shared/code/borrowing/7.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 非词汇生命周期

<https://github.com/rust-lang/rust/issues/43234>
