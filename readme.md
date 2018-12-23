# ferrous-systems/rust-three-days-course [![explain]][source] [![translate-svg]][translate-list]

<!-- [![size-img]][size] -->

[explain]: http://llever.com/explain.svg
[source]: https://github.com/chinanf-boy/Source-Explain
[translate-svg]: http://llever.com/translate.svg
[translate-list]: https://github.com/chinanf-boy/chinese-translate-list
[size-img]: https://packagephobia.now.sh/badge?p=Name
[size]: https://packagephobia.now.sh/result?p=Name

「 三天就'生锈'(Rust) 」

[中文](./readme.md) | [english](https://github.com/ferrous-systems/rust-three-days-course)

---

## 校对 🀄️

<!-- doc-templite START generated -->
<!-- repo = 'ferrous-systems/rust-three-days-course' -->
<!-- commit = '3cb312e9eeb4cbee34eefdd796154ae81ce516d4' -->
<!-- time = '2018-12-04' -->

| 翻译的原文 | 与日期        | 最新更新 | 更多                       |
| ---------- | ------------- | -------- | -------------------------- |
| [commit]   | ⏰ 2018-12-04 | ![last]  | [中文翻译][translate-list] |

[last]: https://img.shields.io/github/last-commit/ferrous-systems/rust-three-days-course.svg
[commit]: https://github.com/ferrous-systems/rust-three-days-course/tree/3cb312e9eeb4cbee34eefdd796154ae81ce516d4

<!-- doc-templite END generated -->

静态网页版就在[docs 目录](./docs)

### 贡献

欢迎 👏 勘误/校对/更新贡献 😊 [具体贡献请看](https://github.com/chinanf-boy/chinese-translate-list#贡献)

## 生活

[help me live , live need money 💰](https://github.com/chinanf-boy/live-need-money)

---

# 教 Rust

**三天就'生锈'(Rust)**

"Teach Rust"是一个免费的研讨会材料,用于介绍 Rust 编程语言的课程.完整课程的时间大约是三到四天.

这些材料是由具有零 Rust 经验但具有编程背景的人创建的.

## 商业可用性

本课程由赞助和培训[asquera](http://asquera.de)用德语和英语.[Get in touch](mailto:info@asquera.de)用于定制报价.

西班牙语翻译由社区维护,我们很乐意提到培训师.

## 概观

该课程由两部分组成:

[The course presentations](presentation)用作 Rust 的所有基本方面的介绍.它有小部件,并且与 Rust 操场集成,例如带有翻译结构.

[The work examples](example).该课程从头开始构建一个小型 TCP 服务器.

与此同时,我们使用的所有通信材料都是提供的[here](communication-material).

## 演讲

演示材料分为许多中小型演示文稿,适用于 Rust 的各个方面.并非所有都是为了完全涵盖一个主题,而是作为重点的介绍.涵盖所有权和借款等基本内容的章节应该是详尽无遗的

演示文稿是 Reveal 演示文稿,其中包含用于国际化和集成的插件[Rust Playground](https://play.rust-lang.org).

通过演示的路径并不固定,以便在举办课程期间留有余地.我们使用的 pathes 的例子可以在[courses](courses)目录.我们建议您在准备参加研讨会时创建自己的.

## 例子

目前,该课程附带三个例子:

- 一个简单的 TCP 服务器,提供一个非常简单的 PUT 和 GET 接口来存储和删除消息
- 与 Tokio 和 Futures 一样建造
- 可以用作动态语言的 Rust 库

TCP 服务器应该从一开始构建,从一个新的箱子开始.

这里给出的例子是最终状态的一个例子.在开始本课程之前,您应该自己开发这个例子.

## 任务

可以找到各种任务`src/bin/`并且可以运行`cargo run --bin $TASK"`.

任务如下:

- `add-chapter $CHAPTER`- 按名称创建章节`$CHAPTER`对于每个区域设置.
- `add-code-example $CHAPTER $INDEX`- 适当地重命名所有现有代码示例(\<=`$INDEX`增加 1)for`$CHAPTER`为新的代码示例腾出空间.还会更新幻灯片以反映这一点.
- `build-indices`- 建立指数`presentation/toc/`从`.md`至`html`用于 Web 浏览器.
- `extract-code`- 从所有章节中的幻灯片中提取代码样本,并在中创建适当的副本`presentation/chapters/shared/code/*/*`,然后使用反映新位置的新元素更新幻灯片,不需要经常使用.
- `rename-chapter $OLD $NEW`- 重命名章节`$OLD`至`$NEW`适用于所有语言环境.
- `rename-chapters`- 用章节重命名章节`md`延伸到`chapter`.不应该经常使用.

## 开放式问题

目前,最大的问题是:

- 示例和演示文稿缺少自述文件

## 积分

该课程的开发资金来自[Asquera](https://asquera.de)为...提供的课程[Linuxhotel](https://linuxhotel.de).

它们是开源的,是对 Rust 语言增长的贡献.

如果您想资助课程的进一步发展,请预约培训!

## 商业用途

本课程旨在用于商业和免费使用.

## 培训师

- [Florian Gilcher](https://asquera.de)
- [Andrew Hobden](https://asquera.de)

想要在此列表中:打开一个[issue](https://github.com/skade/rust-three-days-course/issues)我们会加你

## 执照

<https://creativecommons.org/licenses/by-sa/4.0/>
