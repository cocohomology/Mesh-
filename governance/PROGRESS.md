# Progress

> 本文件是课程当前状态的唯一权威入口。新会话优先读取本文件。

## Current phase

**Phase 0 complete — Course infrastructure and syllabus architecture established**

课程运行系统已经建立，尚未开始正式教学 Note。

## Current focus

下一阶段将从“课程如何运行”转向“课程具体如何组织”，先建立第一版正式模块图，再选择 Phase 1 教学入口。

## What is now settled

- 本课程不是传统“网格算法大全”。
- 课程追求数学结构与网格算法之间的强连接。
- 数学学习不与工程割裂。
- 数学上暂以拓扑、几何、分析三大层次作为高层观察框架，代数结构作为贯穿语言自然融入。
- 工程上把 mesh 看作有限离散表示，并持续追问其数据结构、离散对象、保持量和牺牲量。
- 核心算法需要分析：对象、假设、数学结构、核心定理、失效机制与推广。
- 理想理解链条为：`Algorithm <-> Theorem <-> Structure <-> Assumption <-> Failure <-> Generalization`。
- 课程大纲允许动态调整；大纲是地图，不是合同。
- 仓库文档必须足以让新聊天独立接手。
- Note 应是教学式讲义，而不是聊天摘要。
- 未成熟但重要的探索进入 Discussion，而不是强行写成正式结论。
- Reference 系统按当前问题驱动，不追求先建立庞大书目。
- 重要反馈按 local / note-level / module-level / course-level 分层处理，其中后两类必须写回仓库。

## Infrastructure now available

- `README.md`：总入口与仓库结构
- `governance/COURSE_PROTOCOL.md`：课程推进总协议
- `governance/HANDOFF.md`：跨聊天接手协议
- `governance/PROGRESS.md`：当前状态权威入口
- `governance/DECISIONS.md`：关键决策日志
- `governance/FEEDBACK_LOOP.md`：反馈闭环
- `governance/TASKS.md`：任务池
- `syllabus/PHILOSOPHY.md`：课程理念
- `syllabus/OUTLINE.md`：动态大纲系统
- `syllabus/MODULE_TEMPLATE.md`：模块模板
- `notes/README.md`：Note 规范
- `discussions/README.md`：Discussion 规范
- `refs/README.md`：Reference 规范

## What remains open

后续需要逐步形成：

- 第一版正式课程模块图与依赖关系；
- Phase 1 的教学入口；
- 第一篇 Note 的主题与切入方式；
- TeX / Markdown 的具体分工与构建方式；
- 实验代码是否进入本仓库或未来拆分；
- 第一批教材、论文与实现库；
- 首模块的阶段性验收方式。

## User feedback to preserve

- 希望掌握网格算法，但不是传统工程师式的“会写会调”。
- 希望算法背后建立整套数学理论。
- 数学上至少关注拓扑、几何、分析三大层面，代数结构融入其中而非孤立教学。
- 重要算法应能从宏观结构解释其成立范围与失效原因，例如 Delaunay triangulation。
- 传统 mesh processing 可作为工程参照，但不应成为课程唯一主线。
- 整个课程必须能够跨聊天持续推进。

## Next recommended action

建立第一版正式课程模块图。此时可以开始涉及具体内容组织，但仍先不要急着写第一篇正式 Note。模块图应明确：高层数学主线、工程算法坐标、依赖关系、可能的侧路，以及哪些主题适合作为首个教学入口。

## Last update

2026-09-16: Phase 0 infrastructure completed and reviewed for consistency.
