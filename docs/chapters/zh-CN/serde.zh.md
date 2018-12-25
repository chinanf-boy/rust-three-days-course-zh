# `serde`

[回去](toc/default.html)

---

## **塞尔**I化与**扩散系数**串行化

<https://serde.rs/>

---

## `Serialize` & `Deserialize`

使Rust结构可串行化:

<pre><code data-source="chapters/shared/code/serde/1.rs" data-trim="hljs rust"></code></pre>

---

## 格式

Serde支持多种格式,例如:

-   杰森
-   CBOR
-   钇铝石榴石
-   托姆尔
-   BSON
-   梅塞格帕克
-   …更多!

你喜欢那个缩略词沙拉吗?

---

## `Serialize`

对JSON:

<pre><code data-source="chapters/shared/code/serde/2.rs" data-trim="hljs rust"></code></pre>

---

## `Deserialize`

来自JSON:

<pre><code data-source="chapters/shared/code/serde/3.rs" data-trim="hljs rust"></code></pre>

---

## 转码

<pre><code data-source="chapters/shared/code/serde/4.rs" data-trim="hljs rust"></code></pre>

---

## 属性

`serde`具有可利用的大量属性:

<pre><code data-source="chapters/shared/code/serde/5.rs" data-trim="hljs rust"></code></pre>

<https://serde.rs/attributes.html>
