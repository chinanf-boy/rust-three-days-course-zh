# FFI

[回去](toc/default.html)

---

## 效率!

<small>(这是德国)</small>

*»高效«C绑定*

---

RustABI是*不*稳定.

---

Rust支持platform-ABI.

---

与共享/静态库.

或*是*一个.

---

*»高效«C绑定*

<br/>

没有转换成本

---

## 使用C从生Rust

---

## 基本的例子

Hello world从C

---

让我们假设你*真的*想要使用printf

<pre><code data-source="chapters/shared/code/ffi/hello.c" data-trim="hljs rust"></code></pre>

<pre><code data-source="chapters/shared/code/ffi/hello.h" data-trim="hljs rust"></code></pre>

---

## 事情待办事项

-   结合对函数在头
-   链接外部代码库
-   叫那些`unsafe { ... }`
-   为C函数转化数据

---

## 在我们开始之前

<pre><code data-source="chapters/shared/code/ffi/1.rs" data-trim="hljs rust"></code></pre>

禁用一些生Rust的命名的绑带

<small>(在C代码)</small>

---

## 绑定功能

<pre><code data-source="chapters/shared/code/ffi/hello.h" data-trim="hljs rust"></code></pre>

<pre><code data-source="chapters/shared/code/ffi/2.rs" data-trim="hljs rust"></code></pre>

---

## 原始类型

一些编译器类型转换可以推导出的.

-   `c_uint`·以`u32`
-   `c_int`·以`i32`
-   `c_void`·以`()`
-   等……

---

## 调用这个

<pre><code data-source="chapters/shared/code/ffi/3.rs" data-trim="hljs rust"></code></pre>

---

## 货物(构建系统)支持

-   通过构建依赖箱建立本地代码
    -   `gcc`, `clang`, `cmake`,……
-   `build.rs`文件负责链接代码

---

## 结构体

枚举和结构的布局是由编译器.

`#[repr(C)]`指导编译器使用平台布局.

<pre><code data-source="chapters/shared/code/ffi/4-1.rs" data-trim="hljs rust"></code></pre>

---

## 枚举

<pre><code data-source="chapters/shared/code/ffi/4-3.rs" data-trim="hljs rust"></code></pre>

---

## 不透明的类型

当不知道(或)关心内部的布局,可以使用不透明的结构.

<pre><code data-source="chapters/shared/code/ffi/4-2.rs" data-trim="hljs rust"></code></pre>

---

## 回调

`extern "C"`也适用于函数指针给外面的功能.

<pre><code data-source="chapters/shared/code/ffi/6.rs" data-trim="hljs rust"></code></pre>

---

## 真实的例子

绑定imagemagick生Rust!

<small>(有人已经做了,但让我们再做一次)</small>

---

## bindgen

`imagemagick`有一个*很多*的功能.`extern "C"`不要写这些

<pre><code data-source="chapters/shared/code/ffi/7.rs" data-trim="hljs rust"></code></pre>

---

在这一点上,包括绑定很简单\*

<pre><code data-source="chapters/shared/code/ffi/8.rs" data-trim="hljs rust"></code></pre>

---

## 建筑层

<pre><code data-source="chapters/shared/code/ffi/9.rs" data-trim="hljs rust"></code></pre>

---

## 建筑层

<pre><code data-source="chapters/shared/code/ffi/10.rs" data-trim="hljs rust"></code></pre>

---

## 包装不安全代码安全生Rust

---

## 内存管理

<pre><code data-source="chapters/shared/code/ffi/11.rs" data-trim="hljs rust"></code></pre>

---

**结构体与一个字段在运行时消失.**

隔离的生命周期管理从其余的代码的指针.

---

## 利用C的生Rust

---

作品simmilarly你已经看到.

使用逆向platform-ABI——发出本地库

---

## 例如:插件`weechat`

---

## 货物的设置

<pre><code data-source="chapters/shared/code/ffi/12.toml" data-trim="hljs toml"></code></pre>

---

其他类似的概念.

-   `extern "C"`功能.
-   `#[repr(C)]`结构/枚举.
-   使数据C兼容.

---

<pre><code data-source="chapters/shared/code/ffi/13.rs" data-trim="hljs toml"></code></pre>

<small>你看到其他的功能</small>

---

现在怎么办呢?

---

## 创建绑定

<small>(不,这不是一个似曾相识的)</small>

C代码需要`.h`文件包括定义防Rust功能.

`cbindgen`是一个很好的工具来自动生成它们.

---

但是:不是必需的,因为插件API通过指定weechat !

---

<pre><code data-source="chapters/shared/code/ffi/14.rs" data-trim="hljs toml"></code></pre>

---

完整代码:[spacekookie/weechat-rs](https://github.com/spacekookie/weechat-rs/tree/master/examples/hello_weechat)

随时运行,玩、测试……

---

## 有些事情不在

---

---
