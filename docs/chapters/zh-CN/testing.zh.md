# 测试

[回去](toc/default.html)

---

测试是生Rust的基础.

单元测试、集成测试、文档测试都装入的.

---

## 组织测试

测试通常在1的4可能的地点:

-   立即在功能测试.
-   (单元测试)`tests`子模块.
-   (私人集成测试)
-   在`tests/`目录中.

---

## (公共集成测试)

-   允许在同一个模块中测试功能和环境.
-   通常存在立即附近的功能.
-   好的测试,以确保一个单一的行动*作品*.

---

## 单元测试

<pre><code data-source="chapters/shared/code/testing/1.rs" data-trim="hljs rust"></code></pre>

---

## 单元测试

<pre><code data-source="chapters/shared/code/testing/2.bash" data-trim="hljs bash"></code></pre>

---

## `tests`子模块

-   允许测试的功能是用于其他项目.
-   私人api和功能测试.
-   对测试流程和用例.

---

## `tests`子模块

<pre><code data-source="chapters/shared/code/testing/3.rs" data-trim="hljs rust"></code></pre>

---

## `tests`子模块

<pre><code data-source="chapters/shared/code/testing/4.bash" data-trim="hljs bash"></code></pre>

---

## 文档测试

-   允许测试公共功能.
-   显示在`rustdoc`输出.
-   为演示用例和例子.

---

## 文档测试

<pre><code>
/// ```rust
/// use example::Direction;
/// let way_home = Direction::North;
/// ```
pub enum Direction { North, South, East, West }
</code></pre>

---

## 文档测试

<pre><code data-source="chapters/shared/code/testing/5.bash" data-trim="hljs bash"></code></pre>

---

## 集成测试

-   测试如果箱外部依赖.
-   用于长或全功能测试.

---

## 集成测试

`/tests/basic.rs`:

<pre><code data-source="chapters/shared/code/testing/6.rs" data-trim="hljs rust"></code></pre>

---

## 集成测试

<pre><code data-source="chapters/shared/code/testing/7.bash" data-trim="hljs bash"></code></pre>
