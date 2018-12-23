# 锈蚀嵌入式系统

[回去](toc/default.html)

---

## 留言地点

<http://www.rust-embedded.org/>

---

## 栈

Xargo:与libcore和libstd的交叉编译:<https://github.com/japaric/xargo>

交叉:使用QEMU对结果进行交叉测试<https://github.com/japaric/cross>

---

## 阅读

发现:通过锈发现微控制器.

<https://github.com/japaric/discovery>

铜:编程微控制器与锈和皮质-M.

<https://japaric.github.io/copper/>

---

## 项目

Tock,用于Cortex-M处理器的操作系统:[tockos.org](tockos.org)

---

## 问题

-   LLVM目标支持
    -   LLVM在苹果使用的目标上通常表现良好
    -   这并不意味着LLVM在任何方面都是敌对的!
-   锈蚀中未解决的要求,尤其是位场
-   内联程序集不稳定
-   核心开发人员是桌面和服务器开发人员,并不总是有足够的经验
    -   "没有比糟糕的解决方案更好的解决方案了!"
-   我们需要供应商买进

---

## 解决方案

-   Rust是LLVM中更好的目标支持背后的驱动力
    -   多个目标,特别是AVR,将在下一个版本中发布
-   热情的嵌入式社区
-   Rust对于核心无法实现的特性有一个非常好的社区流程
