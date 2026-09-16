# References System

## Purpose

`refs/` 管理课程所需的书籍、论文、讲义、实现、网站与资料请求。

这里不追求一开始建立庞大的 bibliography，而是服务于当前课程问题。

## Reference categories

建议按用途登记：

- **Primary**：当前模块必须深入阅读的核心资料；
- **Secondary**：用于补充证明、不同视角或背景；
- **Engineering**：实现、库、源码、工程经验；
- **Historical**：历史来源与概念演化；
- **Optional**：有价值但暂不阻塞课程；
- **Requested**：助手需要但当前仓库中没有，希望用户协助寻找或上传。

## Reference entry template

```markdown
### [ID] Title
- Authors:
- Type: book / paper / notes / code / website
- Role: Primary / Secondary / Engineering / Historical / Optional / Requested
- Relevant module:
- Why needed:
- What to read:
- Status: missing / available / skimmed / read / integrated
- Local file or link:
- Notes:
```

## Reading principle

不是“把一本经典书从头读到尾”才算学习。

每次引入资料都应回答：

- 当前具体问题是什么？
- 为什么这份资料适合回答它？
- 需要精读哪一部分？
- 哪些章节可以暂时跳过？
- 阅读后要产出什么：Note、证明、实验、算法实现还是课程结构调整？

## User-assisted acquisition

若助手发现某篇论文、书籍章节或资料很关键，但无法直接获得完整内容，应明确向用户登记请求，而不是凭二手描述假装已读。

建议将此类需求写为 `Requested`，包含准确标题、作者、用途和优先级。用户可随后上传资料，再由助手整合。

## Evidence discipline

进入正式 Note 的重要历史判断、非常规定理、工程边界或争议性说法，尽可能追溯到可靠来源。

课程允许基于直觉产生假设，但必须与已确认事实分开标记。
