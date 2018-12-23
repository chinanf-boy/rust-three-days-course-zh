# 基本类型

[回去](toc/default.html)

---

## 英茨

Rust带有所有标准的int类型,有符号和无符号

-   I8,U8
-   I16,U16
-   I32,U32
-   I64,U64
-   I128,U128

---

## 与体系结构相关的数字

Rust具有两种依赖于体系结构的数字类型:

-   伊希兹

---

## 铸件

可以在数字之间进行转换,*也缩短铸件*:

<pre><code data-source="chapters/shared/code/basic-types/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

如果大小没有给出,或者无法推断,int默认为`i32`.

---

## 溢流

溢出在调试模式下触发陷阱,但在发布模式下不触发.可以配置此行为.

---

## 漂浮物

Rust还带有所有标准大小的浮动:f8、f16、f32、f64

<pre><code data-source="chapters/shared/code/basic-types/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 数组

固定大小的数组具有以下符号:

<pre><code data-source="chapters/shared/code/basic-types/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 动态大小数组

Rust中动态大小的数组表示为切片.

片携带指向数组和长度的指针.无法调整切片的大小.

<pre><code data-source="chapters/shared/code/basic-types/4.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 单位类型

没有特定返回值的表达式返回单元类型`()`.

<pre><code data-source="chapters/shared/code/basic-types/5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>
