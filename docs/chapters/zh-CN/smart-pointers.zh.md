# 锈蚀中的特殊指针

[回去](toc/default.html)

---

Rust提供了几个特殊的指针来处理不同的场景.

它们都有一些共同点:它们由所有权管理.

---

## `std::rc::Rc<T>`

线程内计数的运行时引用.

<pre><code data-source="chapters/shared/code/smart-pointers/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 语义

-   `Rc`是包含数据的句柄
-   句柄可以克隆
-   如果最后一个句柄丢失,则也删除数据
-   `Rc<T>`器具`Deref<Target=T>`

---

## `std::rc::Weak<T>`

指向数据的弱指针.

<pre><code data-source="chapters/shared/code/smart-pointers/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 语义

-   类似`Rc`然而,数据的存在并不能得到保证
-   单线程:保证数据在操作期间可用
-   是*不*自动解除引用
-   `Rc`圆圈是内存泄漏,弱指针可以防止

---

## 使用

-   经常用于需要复杂交叉引用的数据结构中
-   更高的运行时成本以实现更大的灵活性

---

## `std::sync::Arc<T>`

更贵的`Rc`它跨线程边界工作,因为原子计数器用于递增.

---

## 备注

不要使用`Arc`凭直觉`rustc`使用`Rc`越过线程边界.

---

## `std::borrow::Cow`

-   写上拷贝
-   关于借贷和所有权的摘要
-   仅在必要时克隆数据
-   <https://doc.rust-lang.org/std/borrow/enum.Cow.html#examples>
