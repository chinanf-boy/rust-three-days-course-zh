# 堆栈和堆

[回去](toc/default.html)

---

在堆栈上执行缺省分配

---

## 堆栈分配

<pre><code data-source="chapters/shared/code/stack-and-heap/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 盒子

堆分配由以下类型表示`Box`.

<pre><code data-source="chapters/shared/code/stack-and-heap/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 所有权与借款

`Box`拥有,但是可以借用包含的值.

<pre><code data-source="chapters/shared/code/stack-and-heap/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 其他堆分配

其他类型可能在堆上分配,最值得注意的是`Vec`和`String`.

---

## 放置在

目前*不*可以在自选位置分配值.缺少的特性称为"placein".

[Detailed discussion here](https://internals.rust-lang.org/t/lang-team-minutes-feature-status-report-placement-in-and-box/4646)

---

在大多数情况下,LLVM已经优化了堆栈分配,随后将堆转移到直接堆分配.
