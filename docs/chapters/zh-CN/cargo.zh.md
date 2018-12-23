# 货物

[回去](toc/default.html)

---

货物是锈病的标准建造工具链.

每次发布`rustc`装运的货物有特定的版本.

一般来说,货物独立于使用的`rustc`版本.

---

## 项目

货物项目包含(至少):

-   单据(货单)
-   在`src`文件夹(默认)

---

此外,货物项目可以包括:

-   测试(默认目录)`tests`)
-   基准(默认目录)`benches`)
-   构建脚本(默认)`build.rs`)
-   示例(默认目录)`examples`)

---

## 舱单

这个[Cargo-Manifest](http://doc.crates.io/manifest.html)使用[TOML](http://doc.crates.io/manifest.html). 它至少包含项目的名称.

<pre><code data-source="chapters/shared/code/cargo/1.toml" data-trim="hljs toml"></code></pre>

---

## `cargo build`

`cargo build`构建整个项目并将结果放到目录中`target`.

默认情况下,cargo使用Debug配置文件,这意味着生成的二进制文件没有经过优化,并且带有调试符号!

`cargo build --release`使用优化配置文件.

---

*总是使用* `--release`对于基准测试,尤其是迭代器从优化中获得了巨大的速度提升.

---

## `cargo run`

如果项目包含应用程序,则可以使用`cargo run -- [Arguments]`.

如果包含多个,则可以使用`--bin <name>`.

调试配置文件在这里是默认的.

---

## `cargo test`

`cargo test`运行所有测试.您可以提供测试名称或模块名称来筛选正在运行的测试.

测试默认情况下使用调试配置文件.

`cargo test`运行所有测试,包括文档测试和示例编译!

---

## `cargo bench`

`cargo bench`运行所有基准测试.

基准测试默认为发布配置文件.

---

## 版本控制

在锈蚀社区[Semantic Versioning](https://semver.org)是推荐的版本控制标准.

-   如果有中断的接口更改,则必须引发主要版本.
-   如果添加新特性,则必须引发次要版本
-   补丁版本标志着bug修复和性能改进.

---

## 预释放

如果库的版本如下`1`它被认为是"预发布",这意味着,在*每个小版本*.

---

## 版本表达式

Cargo允许以不同方式表达版本范围.

-   `=1.2.3`确切的说,货物只使用那个
-   `0.1`"0.1"系列的任何补丁版本
-   `< 0.8`任何小于"0.8"的次要版本

有关详细信息,请查看[docs](http://doc.crates.io/manifest.html)

---

## 版本解析

在第一次构建时(或`cargo update`(cargo)计算满足Cargo.toml中所述约束的版本树.如果成功,它将保存在Lockfile(Cargo.lock)中.

建议始终将Lockfile置于版本控制之下!(用于可重复构建)

---

## 详细依赖关系

货物有三种不同的依赖关系:

-   正常依赖
-   构建依赖项
-   测试依赖性

---

## 例子

<pre><code data-source="chapters/shared/code/cargo/2.toml" data-trim="hljs toml"></code></pre>

---

## 详细依赖关系

<pre><code data-source="chapters/shared/code/cargo/3.toml" data-trim="hljs toml"></code></pre>

<pre><code data-source="chapters/shared/code/cargo/4.toml" data-trim="hljs toml"></code></pre>

---

## 旁白

如果图书馆要在.es.io上出版,则禁止在.es.io之外的附属机构.

---

## 局部路径

通过本地图书馆可以临时替换图书馆.为此,需要注册它们的路径`$PROJECT_PATH/.cargo/config`.

<pre><code data-source="chapters/shared/code/cargo/5.toml" data-trim="hljs toml"></code></pre>

这里找到的图书馆优先.这允许对补丁进行简单的测试.

---

## 轮廓

可以定制货物配置文件(释放、工作台、测试…).在[Manifest-documentation](http://doc.crates.io/manifest.html)

---

## 目标

-   可以基于编译目标配置概要文件和依赖项
-   `cargo build --target ...`使用该目标
-   必须预先安装目标
-   考虑使用xargo

---

## 工作空间

货物可以将工作区中的多个项目分组.然后它们共享设置以及相同的设置`target`目录.

见[manifest documentation](http://doc.crates.io/manifest.html)详情.

---

## 特征

`rustc`提供在编译时忽略某些代码部分的能力.这是通过特性标志实现的.

<pre><code data-source="chapters/shared/code/cargo/6.rs" data-trim="hljs rust"></code></pre>

---

这些可以登记在`Cargo.toml`.

<pre><code data-source="chapters/shared/code/cargo/7.toml" data-trim="hljs toml"></code></pre>

---

然后表示依赖关系:

<pre><code data-source="chapters/shared/code/cargo/8.toml" data-trim="hljs toml"></code></pre>

---

## 直接调用`rustc`

`cargo rustc`调用`rustc`直接并允许传递附加参数.
