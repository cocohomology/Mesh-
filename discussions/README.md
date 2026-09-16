# Discussions System

## Purpose

`discussions/` 用于保存课程中重要但尚未成熟到可以写入正式 Note 的内容。

它是探索区，不是垃圾箱。

适合进入这里的内容包括：

- 用户与助手之间的重要争论；
- 某个经典算法失效机制的初步分析；
- 数学结构之间可能存在但尚未验证的联系；
- 一个工程现象可能对应的数学问题；
- 文献之间的冲突；
- 课程结构本身的开放问题；
- 值得未来研究的 conjecture / hypothesis / question。

## Suggested file structure

```markdown
# Discussion — Title

## Trigger
什么问题触发了这次讨论？

## Context
需要保留哪些背景？

## Current observations
目前有哪些相对可靠的观察？

## Competing viewpoints
若存在多种解释，分别是什么？

## Evidence
哪些来自定理、文献、实验、工程经验或直觉？

## Open questions
仍缺什么？

## Possible consequences
如果某个观点成立，对课程/算法/研究意味着什么？

## Next action
下一步如何验证或推进？

## Status
open / partially-resolved / promoted-to-note / archived
```

## Promotion rule

当一个 Discussion 中的内容已经：

- 定义稳定；
- 关键结论有依据；
- 教学结构清楚；
- 与课程主线的关系明确；

则应把成熟部分整理到 `notes/`，而不是直接把 Discussion 改名充当 Note。

Discussion 可以继续保留，作为思想演化记录。

## Cross-chat rule

任何对未来课程有明显影响的讨论，在聊天结束前应至少留下一个 Discussion 条目或写入 `DECISIONS.md`，避免新会话只看到结果却看不到问题来源。
