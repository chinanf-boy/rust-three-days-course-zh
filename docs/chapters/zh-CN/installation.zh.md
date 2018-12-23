# 工具链

[回去](toc/default.html)

---

<https://www.rust-lang.org/en-US/install.html>

---

## 生锈

Rustup是管理Rusts编译器工具链的标准工具.

<http://rustup.rs/>

---

## 重要命令

<pre><code data-source="chapters/shared/code/installation/1.sh" data-trim="hljs sh"></code></pre>

---

# 第一步

执行以下命令:

<pre><code data-source="chapters/shared/code/installation/2.sh" data-trim="hljs sh"></code></pre>

这将加载默认库和文档的来源,以便完成和脱机使用.

---

## 工具链的内容

-   鲁斯特
-   货物
-   鲁斯多克
-   锈蚀(LLDB)
-   LBCys/LIbSTD

安装的调试器依赖于平台.

---

## 鲁斯特

<pre><code data-source="chapters/shared/code/installation/3.sh" data-trim="hljs sh"></code></pre>

Rust编译器构建并链接Rust代码.

`rustc`几乎完全是用《锈》写的.

---

## 功能测试

<pre><code data-source="chapters/shared/code/installation/4.rs" data-trim="hljs rust"></code></pre>

---

<pre><code data-source="chapters/shared/code/installation/5.sh" data-trim="hljs sh"></code></pre>

---

## 货物

<pre><code data-source="chapters/shared/code/installation/6.sh" data-trim="hljs sh"></code></pre>

---

货物是锈菌构建和包装管理工具.

货物随同安装`rustc`但不是紧密绑定`rustc`版本.

---

## 再一次带货

<pre><code data-source="chapters/shared/code/installation/7.sh" data-trim="hljs sh"></code></pre>

---

## 环顾四周

-   货柜里有什么?
-   货物锁里有什么?

有关详细信息,请查看[Cargo Manifest docs](http://doc.crates.io/manifest.html).

---

## 货物也管理工具

<pre><code data-source="chapters/shared/code/installation/8.sh" data-trim="hljs sh"></code></pre>
