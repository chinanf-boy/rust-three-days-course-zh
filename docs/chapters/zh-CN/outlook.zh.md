# 展望

[回去](toc/default.html)

---

锈病在不久的将来会发生什么?

——

# 锈蚀2018

---

在2018年底,全年特性稳定的高潮被发布为`Rust 2018`

---

语言随着时间而改变.

但是稳定性和向后兼容性是基本的.

---

在不中断的情况下对语言进行核心更改*任何*现有代码.

可以选择更改.

<pre><code data-source="chapters/shared/code/outlook/1.toml" data-trim="hljs toml" class="lang-rust"></code></pre>

---

## 一些变化

---

### 模块系统返工

<pre><code data-source="chapters/shared/code/outlook/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

<pre><code data-source="chapters/shared/code/outlook/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

### 路径明晰

<pre><code data-source="chapters/shared/code/outlook/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

### 不再`extern crate`

---

### `?`在里面`main()`

<pre><code data-source="chapters/shared/code/outlook/4.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

### 循环罐`break`一个值

<pre><code data-source="chapters/shared/code/outlook/5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

### `impl Trait`vs`dyn Trait`

uname类型,实现一个特定对象特征和动态特征

<pre><code data-source="chapters/shared/code/outlook/6.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

`dyn Trait`是一种新的语法特征的对象.

原来语法`impl T`vs`T`是混乱和不对称.

<pre><code data-source="chapters/shared/code/outlook/7.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

### 很多很多东西

太多的列表.这里有一个简短的列表

-   128位的原语
-   匿名的一生
-   `_`&
-   `async`稳定的宏程序(编译器属性)`await`
-   在包容的范围
-   `..=`…
-   等等……
