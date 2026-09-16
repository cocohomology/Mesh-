# TeX Conventions for Teaching Notes

## Purpose

本文件规定正式教学 Note 中的用户批注、助手回应和版本新增标记。目标是让多轮学习过程在同一份 TeX 文档中可追踪，同时避免不同版本内容混在一起无法辨认。

## 1. Metadata block

每篇正式 Note 开头应至少声明：

```tex
\newcommand{\notetitle}{...}
\newcommand{\noteversion}{v0.1}
\newcommand{\notestatus}{teaching}
\newcommand{\notelastupdate}{2026-09-16}
```

正文首页应显示版本、状态和更新时间。

## 2. Required annotation environments

正式模板应提供至少三种语义明确的环境。

### `studentthought`

用户追加自己的思考、质疑、推导、联想或局部计算。

```tex
\begin{studentthought}[关于某个定义]
这里写我的思考……
\end{studentthought}
```

原则：

- 用户默认不删除原文；
- 可以在任意相关位置插入；
- 可以带标题；
- 批注本身是课程材料的一部分，不视为“待清理评论”。

### `assistantresponse`

助手针对用户思考的直接回应。

```tex
\begin{assistantresponse}[v0.2]
这里回应问题，补充解释或指出需要继续验证的地方……
\end{assistantresponse}
```

应标记首次出现的版本。

### `versionaddition`

用于标记某个版本新增的正式教学正文。

```tex
\begin{versionaddition}[v0.2]
这是因上一轮阅读反馈而增加的正式内容……
\end{versionaddition}
```

它和 `assistantresponse` 的区别是：前者属于正式讲义内容，后者保留对话性回应。

## 3. Suggested implementation

正式 TeX 模板可基于 `tcolorbox` 实现。例如：

```tex
\usepackage[most]{tcolorbox}
\usepackage{xparse}

\NewTColorBox{studentthought}{O{}}{
  breakable,
  title={Student thought\if\relax\detokenize{#1}\relax\else: #1\fi},
  fonttitle=\bfseries
}

\NewTColorBox{assistantresponse}{O{}}{
  breakable,
  title={Assistant response\if\relax\detokenize{#1}\relax\else\ (#1)\fi},
  fonttitle=\bfseries
}

\NewTColorBox{versionaddition}{O{}}{
  breakable,
  title={Added in #1},
  fonttitle=\bfseries
}
```

当前这里只冻结**语义接口**，具体视觉样式可以在第一篇 Note 开始前调整。不要让配色或样式成为强依赖；即使未来更换宏包，三个环境名和语义应尽量保持稳定。

## 4. Version visibility

多轮迭代中，新增内容需要能够被读者识别，但不应永久让整篇文档像 diff。

建议分两个阶段：

- **教学迭代期**：保留 `versionaddition` 标记，方便识别某轮新增；
- **稳定整理期**：在双方明确同意后，可以把成熟的 `versionaddition` 融入普通正文，但 revision history 仍保存其来源。

`studentthought` 与有价值的 `assistantresponse` 原则上长期保留，因为它们记录真实思考过程。

## 5. Revision history

每篇 Note 末尾应有 revision history，例如：

```tex
\section*{Revision history}
\begin{itemize}
  \item v0.1 --- Initial teaching draft.
  \item v0.2 --- Added geometric example and response to comments on ...
\end{itemize}
```

版本更新不是简单记录“修了 typo”，而应优先记录教学结构、数学内容、图、例子、习题和用户反馈导致的变化。

## 6. Non-destructive learning record

课程默认采用“非破坏式学习记录”：

- 用户阅读时不直接删除助手原文；
- 助手回应时也不删除用户思考；
- 发现原文错误时，可以明确标记错误、给出修正版，并在必要时保留原错误的上下文；
- 只有在进入稳定整理阶段并且双方认为历史痕迹已失去教学价值时，才做清理。

这种机制的目的不是版本控制本身，而是把“理解如何发生”保存下来。

## 7. Figures, examples and exercises in TeX

正式 Note 应预留统一环境：

- `example` / `workedexample`：手算或算法追踪例；
- `exercise`：高价值习题；
- `codingexercise`：编码任务；
- `sidenote`：视野拓展；
- `failurecase`：反例与失效案例。

是否最终自定义这些环境，可在第一篇 Note 模板冻结时决定。关键要求是语义分层清晰，而不是全部用普通 `\paragraph{}` 混写。
