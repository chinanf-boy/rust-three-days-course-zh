# 蹲下,恐慌,中止

[回去](toc/default.html)

---

在细节值下降时,会发生什么?

---

## Drop-Order

目前正在下降的顺序发生*不*标准化.

[Discussion](https://github.com/rust-lang/rfcs/issues/1857)

---

## 有很好的理由标准化在当前的形式.

-   在的范围值下降
-   订单*相反的顺序介绍*
-   立即释放值下降
-   结构字段了*最后第一*

---

## 析构函数

有时,回收之前必须采取某些行动.

为此,`Drop`特征可以实现.

---

<pre><code data-source="chapters/shared/code/drop-panic-abort/1.rs" data-trim="hljs rust"></code></pre>

---

## 警告!

析构函数不能返回错误.

---

## 也有可能

值通过消费函数的显式破坏.

这个目前不能静态地执行.`Drop`炸弹(失败的析构函数)可以确保这个错误被称为早期.

---

## 恐慌

生锈也有另一个错误机制:`panic!`

<pre><code data-source="chapters/shared/code/drop-panic-abort/2.rs" data-trim="hljs rust"></code></pre>

---

在恐慌的情况下,下列情况:

-   当前线程立即停止
-   堆栈已展开
-   删除所有受影响的值并运行它们的析构函数

---

恐慌是与C++异常类似的实现方式,但应该只用于致命错误.他们不能被(通常)抓住.

受影响的线死了.

---

## 捕捉恐慌

跨越FFI边界的恐慌是未定义的行为.在这些情况下,恐慌*必须*被抓住.对于这样的情况,有[std::panic::catch-unwind](https://doc.rust-lang.org/std/panic/fn.catch_unwind.html)和[std::panic::resume-unwind](https://doc.rust-lang.org/std/panic/fn.resume_unwind.html).

---

## 钩子

[std::panic::set_hook](https://doc.rust-lang.org/std/panic/fn.set_hook.html)允许设置正在运行的全局处理程序*之前*松开发生.

---

一般来说,`Result`如果要处理错误,总是传播错误的正确方法.

---

## 中止

在某些环境中,展开`panic!`不是很有意义.对于这些情况,`rustc`和`cargo`有一个开关,在恐慌时立即中止程序.

执行panic hook.

---

## 双重恐慌

在处理恐慌时进行恐慌(例如,在析构函数中)会调用未定义的行为.由于这个原因,程序将立即中止.
