# 导入、模块和可见性

[回去](toc/default.html)

---

## 进口

所有使用过的项目必须声明.这类似于Java或Haskell.

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/1.rs" data-trim="hljs sh" class="lang-sh"></code></pre>

---

## 模块导入

相反,可以导入模块并限定每次使用.

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/2.rs" data-trim="hljs sh" class="lang-sh"></code></pre>

---

## 全球进口

您还可以从模块导入所有内容.

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/3.rs" data-trim="hljs sh" class="lang-sh"></code></pre>

这是*通常地*皱眉

---

## 序曲

该规则的一个例外是"Prelude":这是标准库中的一个特殊模块,自动完全导入.

---

## 其他前奏曲

其他图书馆提供`prelude`-模块,最常见的一种是`std::io`.

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/4.rs" data-trim="hljs rust" class="lang-"></code></pre>

这里,glob被接受.

---

## 结构性进口

您可以组合多个事物,它们也是嵌套的.

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/4-5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 重命名进口

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 本地导入

导入可以在函数内部进行.它们仅在函数内生效.

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/6.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 模块

Rust的模块系统类似于Python.

---

-   每个源文件都是一个模块
-   子模块可以位于同一个文件中,也可以位于另一个文件中
-   库被称为"板条箱",并包含模块

---

按照惯例,库的根模块在`src/lib.rs`.

单个应用程序的根模块`src/main.rs`.

用于多个应用程序的根模块`src/bin/*.rs`.

---

## 例子

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/7.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 将模块移动到单独的文件

我们的应用程序还可以具有以下布局:

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/8.rs" data-trim="hljs sh"></code></pre>

---

## 一个更大的模块作为目录

只需添加一个同名的新文件夹

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/9-2.rs" data-trim="hljs rust"></code></pre>

---

## 一个更大的模块作为目录

或者,通过`mod.rs`

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/9.rs" data-trim="hljs rust"></code></pre>

---

在这两种情况下,模块都必须向根模块注册.

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/10.rs" data-trim="hljs rust"></code></pre>

---

使用最后一个方法,您可以创建与`mod.rs`.

---

## 能见度

在Rust中,缺省情况下一切都是私有的.公开可用的类型标记为`pub`.

导出可以通过公共模块路径到达的公共类型和函数.

---

## 例子

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/11.rs" data-trim="hljs rust"></code></pre>

---

在使用之前必须公开并导入特性.

编译器将检测您是否使用未导入的特征.

---

## 结构体

结构稍微复杂一些.他们不出口田地,这使得他们的使用和建设不可能.这通常是有意的.

此外,默认情况下不导出结构函数.

---

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/12.rs" data-trim="hljs rust"></code></pre>

---

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/13.rs" data-trim="hljs rust"></code></pre>

---

一般来说,应避免导出字段:

-   结构的任何改变都会导致API破坏

-   由于优化,访问器函数通常与直接字段访问一样快.

---

## 酒吧资格赛

<pre><code data-source="chapters/shared/code/imports-modules-and-visibility/14.rs" data-trim="hljs rust"></code></pre>
