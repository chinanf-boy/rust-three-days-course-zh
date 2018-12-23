# 包袱

[回去](toc/default.html)

---

## 什么?

WebAssembly支持在Web浏览器等Javascript环境中运行Rust(以及其他).

它在许多方面都是asm.js的继承者.

它目前是一个开发标准,并且通常默认情况下不启用.

---

## 果茶

WebAssembly仍然没有得到广泛的支持,并且有许多粗糙的边缘.

---

## 安装

目前,安装程序有些未细化,但是将来应该改进.

-   取`emsdk`从[emscripten](http://kripken.github.io/emscripten-site/docs/getting_started/downloads.html).
-   在明智的地方把它拆开.
-   导航到终端中的目录.

---

## 安装:`emcc`

<pre><code data-source="chapters/shared/code/wasm/1.bash" data-trim="hljs bash"></code></pre>

第三个命令的输出将提供添加什么的指令`$PATH`如果需要的话.

> 我们使用`incoming`利用最新的改进.

---

## 安装:`emcc`

工具链的版本非常重要.验证没有运行以下错误:

<pre><code data-source="chapters/shared/code/wasm/2.bash" data-trim="hljs bash"></code></pre>

---

## 安装:`rustup`靶标

`rustup`允许安装多个编译目标.

<pre><code data-source="chapters/shared/code/wasm/3.bash" data-trim="hljs bash"></code></pre>

---

# 独立可执行文件

---

## 独立可执行文件

<pre><code data-source="chapters/shared/code/wasm/4.bash" data-trim="hljs bash"></code></pre>

<pre><code data-source="chapters/shared/code/wasm/5.rs" data-trim="hljs rust"></code></pre>

---

## 独立可执行文件

<pre><code data-source="chapters/shared/code/wasm/6.bash" data-trim="hljs bash"></code></pre>

这将创建一个目录结构,如下所示:

<pre><code data-source="chapters/shared/code/wasm/7.output" data-trim="hljs bash"></code></pre>

---

## 独立可执行文件

一旦我们生成`wasm`和`js`我们想把它们与`site`文件夹.我们可以使用`Makefile`为此.

<pre><code data-source="chapters/shared/code/wasm/8.makefile" data-trim="hljs makefile"></code></pre>

---

## 独立可执行文件

创造`site/index.html`:

<pre><code data-source="chapters/shared/code/wasm/9.html" data-trim="hljs html"></code></pre>

---

## 独立可执行文件

运行`python -m SimpleHTTPServer`或者等同于,浏览`localhost:8000/site`并且打开控制台产生以下输出:

<pre><code data-source="chapters/shared/code/wasm/10.output" data-trim="hljs bash"></code></pre>

---

# JS锈病

---

## JS锈病

导出用于Javascript的函数要复杂一些.

此外,必须像与C的交互一样处理交互.

---

## JS锈病

当前需要夜间频道来使这个功能正常工作:

<pre><code data-source="chapters/shared/code/wasm/11.bash" data-trim="hljs bash"></code></pre>

---

## JS锈病

<pre><code data-source="chapters/shared/code/wasm/12.bash" data-trim="hljs bash"></code></pre>

<pre><code data-source="chapters/shared/code/wasm/13.rs" data-trim="hljs rust"></code></pre>

---

## JS锈病

我们可以像以前一样使用Makefile.

<pre><code data-source="chapters/shared/code/wasm/8.makefile" data-trim="hljs makefile"></code></pre>

---

## JS锈病

这个`onRuntimeInitialized`钩子`Module`定义加载WebAssembly之后调用的内容.

<pre><code data-source="chapters/shared/code/wasm/14.html" data-trim="hljs html"></code></pre>

---

## JS锈病

运行`python -m SimpleHTTPServer`或者等同于,浏览`localhost:8000/site`并且打开控制台产生以下输出:

<pre><code data-source="chapters/shared/code/wasm/15.output" data-trim="hljs bash"></code></pre>

---

# 生锈的JS

---

## 生锈的JS

从Rust调用JS代码也有类似的复杂性.

它主要通过传递`--js-library`在链接时间标志,这需要夜间通道生锈.

传递数字相对比较简单,但是传递更复杂的东西(比如字符串)需要额外的努力.

---

## 生锈的JS

返回Rust代码的字符串:

<pre><code data-source="chapters/shared/code/wasm/17.js" data-trim="hljs javascript"></code></pre>

---

## 生锈的JS

调用Javascript函数:

<pre><code data-source="chapters/shared/code/wasm/18.rs" data-trim="hljs rust"></code></pre>

---

## DOM交互

有一个[WebPlatform crate](https://github.com/tcr/rust-webplatform)探索并做出贡献.

<pre><code data-source="chapters/shared/code/wasm/19.rs" data-trim="hljs rust"></code></pre>

---

## 未来

WebAssembly正在迅速变得更加精炼和成熟.Rust的整合工作也在进行中.

让你的眼睛去皮,获得更多,更好的支持!
