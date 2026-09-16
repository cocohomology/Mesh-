# Notes System

## Purpose

`notes/` 保存正式教学讲义。Note 是课程知识沉淀的主体，不是聊天记录、摘要或速记。

## Writing standard

每篇 Note 应尽量满足：

- 可独立阅读；
- 有明确问题意识，而非堆砌定义；
- 符号稳定；
- 推导完整到足以重建核心结论；
- 说明概念之间为什么相关；
- 数学抽象要落回网格对象与算法；
- 算法要追踪其结构来源、假设、失效与推广；
- 图示、反例、实验在真正帮助理解时加入；
- 避免聊天式碎片语言。

## Suggested internal structure

并非每篇都必须机械遵循，但可参考：

```text
Motivation
Objects and definitions
Geometric / topological / analytic structure
Key theorem or derivation
Algorithmic incarnation
Failure modes / counterexamples
Generalization
Engineering interpretation
Exercises / questions
References
```

## Draft lifecycle

建议使用：

- `draft`：结构尚可能大改；
- `teaching`：可用于当前教学；
- `revised`：已吸收一轮主要反馈；
- `stable`：阶段上稳定，但仍允许未来修订。

## Note vs Discussion

成熟、可教学、结构闭合的内容进入 Note。

仍在探索、存在争议、只有局部观察或尚未验证的内容进入 `discussions/`。不要为了“文档完整”把猜测伪装成讲义结论。

## Format

当前尚未最终决定 Markdown 与 TeX 的分工。原则上：

- 需要大量公式、证明、图示、长期保存的正式讲义倾向 TeX；
- 状态、索引、轻量说明适合 Markdown。

在正式开始 Note 前再确定构建与目录规范。

## Feedback and revision

用户对 Note 的反馈需要判断层级：

- 局部措辞/解释：直接修改；
- 数学缺口：补充或重构；
- 教学顺序问题：可能拆 Note；
- 暴露课程结构问题：同步更新 syllabus；
- 引出研究问题：转入 discussions。

Note 不追求“一稿定稿”。
