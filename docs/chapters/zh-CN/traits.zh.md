# 实施和特点

[回去](toc/default.html)

---

Rust提供了将函数绑定到类型的可能性.

---

# 警告

这有时看起来像面向对象的编程,但实际上并非如此.

特别地,运行时多态性、消息、类、子类型和方法重载丢失.

---

## 简单实现:关联函数

<pre><code data-source="chapters/shared/code/traits/1.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 备注

`new`这里纯粹是约定俗成的.

---

## Python打招呼

<pre><code data-source="chapters/shared/code/traits/2.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 借贷和所有权`self`

这跟平常没什么不同,只是刚开始有点不熟悉.

-   借用一个函数*同时借用*.
-   这特别适用于可变借贷!
-   `self`没有`&`从调用上下文返回值的所有权.

---

## 常见OO的有趣区别

-   值可以替换自己
-   例如,迭代器和构建器可以具有使用`self`因此无效.
-   这解决了使迭代器无效的问题.

---

## 旁白

-   实现可以多次发生

---

## 自我

`Self`是锈菌中的一种特殊类型.它总是引用实现引用的类型.

<pre><code data-source="chapters/shared/code/traits/3.rs" data-trim="hljs rust"></code></pre>

---

## 特点

特征是抽象类型的Rusts变体.

---

我们已经遇到了一个特点:`Debug`.

---

特性定义函数类型必须实现.然后可以通用地使用它们.

---

<pre><code data-source="chapters/shared/code/traits/4.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 自我

`Self`是一种特殊类型:它是当前正在实现的类型.

---

## 共性性状

特征可以有类型参数.

---

<pre><code data-source="chapters/shared/code/traits/5.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

处理一般性状是非常常见的.

---

## 性状推断

性状的类型推断是非常先进的,但有时也可能出现不可判定的情况.在这种情况下,编译器需要帮助进行决策.

有多种技术.

---

## 超滤膜

统一函数调用语法

<pre><code data-source="chapters/shared/code/traits/6.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## 关联类型

关联类型是泛型参数,但在推断期间会忽略它们.

---

<pre><code data-source="chapters/shared/code/traits/7.rs" data-trim="hljs rust" class="lang-rust"></code></pre>

---

## `impl Trait`

`impl Trait`在不需要命名值的类型时使用.

```rust
fn main() {
    let v = vec![1,2,3];
    let i = make_iter(&v);
}

fn make_iter<'a>(v: &'a Vec<u8>) -> impl Iterator<Item=u8> + 'a {
    v.iter().map(|v| (*v)*2)
}
```

---

```rust
fn main() {
    let v = vec![1,2,3];
    let i = v.iter();
    let i2 = double(i);
}

fn double<'a>(i: impl Iterator<Item=&'a u8> + 'a) -> impl Iterator<Item=u8> + 'a {
    i.map(|v| (*v)*2)
}
```

---

局限性:

-   不`impl Trait`性状方法

---

```rust
trait Foo {}

trait Bar {
    fn fooify(&self) -> impl Foo;
}
```
