## 不安全锈

[回去](toc/default.html)

---

锈蚀类型系统提供了许多保证,但有时,它们使特定的解决方案难以或不可能.

因此,Rust具有"不安全代码"的概念.

---

允许使用不安全代码:

-   自由存取存储器
-   取消引用原始指针
-   调用外部函数
-   声明值`Send`和`Sync`
-   写入非同步全局变量

---

不不安全的是:

-   转换为原始指针
-   内存泄漏

---

不安全的代码永远不应该:

-   用于管理由不同分配器管理的内存
    -   从不建造`std:::vec::Vec`从C++向量中删除
-   在.ck上作弊,例如,通过改变类型的生存期或可变性.最常见的"但我确信有效"bug的来源.

---

## 生锈的小秘密

在实现数据结构时,不安全的情况并不少见.

安全锈是实现链接列表最糟糕的语言.有一个完整的[text on this](TODO:%20Link)

---

不安全代码必须*总是*被标记`unsafe`.

<pre><code data-source="chapters/shared/code/unsafe/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 陷阱`unsafe`

-   并非所有的例子都那么简单.`unsafe` *必须*保证Rust期望的不变量.
-   这个*尤其地*适用于所有权和可变借贷
-   `unsafe`可以导致具有2个所有者的值->双自由
-   `unsafe`可以使不可变数据暂时可变,这会导致承诺和眼泪的破灭.

---

锈让你可以射中自己的脚,它只需要你把枪从枪套和删除安全第一.

---

## 实际例子

由于Rust禁止混淆,所以在安全Rust中,不可能将一个切片分割成两个不重叠的部分.

<pre><code data-source="chapters/shared/code/unsafe/2.rs" data-trim="hljs rust"></code></pre>
