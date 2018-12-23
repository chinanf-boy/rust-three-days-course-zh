# 控制流`match`

[回去](toc/default.html)

---

检查枚举的变体,`match`使用.

---

<pre><code data-source="chapters/shared/code/match/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 备选方案:如果-let

<pre><code data-source="chapters/shared/code/match/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

<pre><code data-source="chapters/shared/code/match/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

比赛必须包括所有变体!

---

## 忽略变体

<pre><code data-source="chapters/shared/code/match/4.rs" data-trim="hljs rust"
class="lang-rust"></code></pre>

---

结果带有一个特殊的标记:它们不能被忽略!

<pre><code data-source="chapters/shared/code/match/5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

解决方案:匹配或传递.

---

`match`不仅在枚举上工作:

<pre><code data-source="chapters/shared/code/match/6.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

`match`和`if`表达:

<pre><code data-source="chapters/shared/code/match/7.rs" data-trim="hljs rust" class="lang-rust"></code></pre>
