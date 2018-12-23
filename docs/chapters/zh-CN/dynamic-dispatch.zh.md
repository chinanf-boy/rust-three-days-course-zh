# 动态调度

[回去](toc/default.html)

---

有时,我们希望决定在运行时使用哪个实现,而不是让编译器对代码进行单形化.

有两条路可以走.

---

## 通过Enums发送

如果可能的选择数量有限,可以使用Enum:

<pre><code data-source="chapters/shared/code/dynamic-dispatch/1.rs" data-trim="hljs rust"></code></pre>

---

## 替代形式

<pre><code data-source="chapters/shared/code/dynamic-dispatch/2.rs" data-trim="hljs rust"></code></pre>

---

## 推荐

如果不是严格必要的话,尽量减少Enum上的重复匹配.

---

## 特质对象

关于特征的引用或原始指针,也称为方框,描述所谓的"特征对象".

Trait对象是一对指向虚拟函数表和数据的指针.

---

## 局限性

-   每个对象只能使用一个特性
-   这种特性必须满足某些条件.

---

## 对象安全特性规则

-   对象安全的特征是*不*允许要求`Self: Sized`
-   所有方法都是对象安全的
    -   它们没有类型参数
    -   他们不使用`Self`

---

## 进一步性质

-   由于trait对象在运行时知道它们的确切类型,因此它们支持下推.

<pre><code data-source="chapters/shared/code/dynamic-dispatch/3.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 特征对象和闭包

关闭特性满足对象安全规则.

<pre><code data-source="chapters/shared/code/dynamic-dispatch/4.rs" data-trim="hljs rust"></code></pre>
