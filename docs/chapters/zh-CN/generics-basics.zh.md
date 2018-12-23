# 简单泛型

[回去](toc/default.html)

---

泛型是Rust的基础.

---

## 类属结构

<pre><code data-source="chapters/shared/code/generics-basics/1.rs" data-trim="hljs rust"></code></pre>

---

## 类型推断

Rust用足够的信息查找所有变量和泛型的类型.

这仅适用*里面*关于函数极限.

必须始终完整地输入签名.

---

## 通用枚举

<pre><code data-source="chapters/shared/code/generics-basics/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 重要通用枚举

---

## 选择权

<pre><code data-source="chapters/shared/code/generics-basics/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

描述不必存在的值.

`None`是一个值,不应该混淆`null`.

---

## 结果

<pre><code data-source="chapters/shared/code/generics-basics/4.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

描述操作是否成功并返回值或错误.

---

## 典型结果

<pre><code data-source="chapters/shared/code/generics-basics/5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 泛函

泛型函数具有类型参数.

<pre><code data-source="chapters/shared/code/generics-basics/6.rs" data-trim="hljs rust" class="lang-rust"></code></pre>
