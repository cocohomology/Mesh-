# Progress

> 本文件是课程当前状态的唯一权威入口。新会话优先读取本文件。

## Current phase

**Phase 0 complete — infrastructure established**

**Phase 1 active — M00 teaching has started**

第一篇正式教学 Note 已完成 v0.1：

- `notes/M00/M00-N01-one-mesh-many-meanings.tex`
- Title: `One Mesh, Many Meanings：一个网格究竟是什么？`
- Status: teaching / awaiting first user reading and annotation

## Current focus

当前不要机械继续写 M00-N02。

下一步应由用户完整阅读 `M00-N01 v0.1`，使用 `studentthought` 环境在原 TeX 中加入思考、疑问、反例、工程联想与批注，然后提交更新。助手读取批注后：

1. 在 Note 中用 `assistantresponse` 回应；
2. 必要时用 `versionaddition` 增加正式教学内容；
3. 升级 Note 版本号并维护 revision history；
4. 根据反馈决定 M00-N02 的方向；
5. 重新检查 MODULE_MAP 是否需要调整。

## What M00-N01 establishes

第一篇 Note 不从 halfedge API 或算法清单出发，而先建立以下核心对象层次：

`graph -> complex -> PL geometry -> analysis -> software representation`

并强调反向的“forget structure”视角：算法真正依赖哪一层结构，是理解其边界与失效的重要工具。

Note 当前包含：

- 两三角形方形贯穿例子；
- graph 与 filled complex 的区别；
- abstract simplicial complex 与 geometric realization；
- intrinsic metric 的入口；
- orientation 与 boundary operator 的手算抵消；
- star / link 与局部 manifoldness 预览；
- indexed face set (`V,F`) 与 halfedge 的设计取舍；
- libigl / OpenMesh / geometry-central / CGAL `Surface_mesh` 的对象模型对照；
- 按 representation / topology / geometry / numerical layers 区分坏网格；
- 第一个 library candidate：`MeshAudit` validator；
- 高价值习题与编码任务；
- Note 内重复列出的 requested references。

## Course worldview — settled

- 本课程不是传统“网格算法大全”。
- 课程追求数学结构与网格算法之间的强连接。
- 数学学习不与工程割裂。
- 数学上以拓扑、几何、分析三大层次作为高层观察框架，代数结构作为贯穿语言自然融入。
- 工程上把 mesh 看作有限离散表示，并持续追问其数据结构、离散对象、保持量和牺牲量。
- 核心算法需要分析：对象、假设、数学结构、核心定理、失效机制与推广。
- 理想理解链条为：`Algorithm <-> Theorem <-> Structure <-> Assumption <-> Failure <-> Generalization`。

## Curriculum architecture

课程采用：

1. **Core mathematical/algorithmic spine**：稳定的数学结构与经典网格算法；
2. **Engineering track**：数据结构、成熟库、实现、测试、性能与鲁棒性，贯穿所有核心模块；
3. **Frontier tracks**：快速发展的 geometric learning、differentiable geometry、implicit/neural representation、3D/4D Gaussian Splatting、Physical AI 等方向。

正式地图见 `syllabus/MODULE_MAP.md`；工程路线见 `syllabus/ENGINEERING_TRACK.md`。

## References

长期资料地图：`refs/BOOKLIST.md`

成熟库索引：`refs/LIBRARIES.md`

M00 精确资料计划：`refs/M00.md`

M00-N01 末尾也显式重复了 Requested References。当前优先希望用户补充：

- Botsch et al., **Polygon Mesh Processing** 完整版本；
- Lutz Kettner (1999), **Using Generic Programming for Designing a Data Structure for Polyhedral Surfaces** 完整 PDF；
- 可选：固定版本的 Keenan Crane DDG 讲义；
- 若手头已有：解释 OpenMesh / CGAL / geometry-central 设计思想的论文或课程材料。

## Infrastructure now available

- `README.md`：总入口与仓库结构
- `governance/COURSE_PROTOCOL.md`：课程推进总协议
- `governance/HANDOFF.md`：跨聊天接手协议
- `governance/PROGRESS.md`：当前状态权威入口
- `governance/DECISIONS.md`：关键决策日志
- `governance/FEEDBACK_LOOP.md`：反馈闭环与 Note review loop
- `governance/TASKS.md`：任务池
- `syllabus/PHILOSOPHY.md`：课程理念
- `syllabus/OUTLINE.md`：动态大纲规则
- `syllabus/MODULE_MAP.md`：v0.1 正式模块图
- `syllabus/ENGINEERING_TRACK.md`：工程学习与算法库路线
- `syllabus/MODULE_TEMPLATE.md`：模块模板
- `notes/README.md`：教学 Note 规范
- `notes/TEX_CONVENTIONS.md`：Note 的 TeX 批注、回应与版本标记规范
- `notes/M00/M00-N01-one-mesh-many-meanings.tex`：第一篇正式 Note v0.1
- `discussions/README.md`：Discussion 规范
- `refs/README.md`：Reference 规范
- `refs/BOOKLIST.md`：长期资料地图
- `refs/LIBRARIES.md`：成熟库学习索引
- `refs/M00.md`：M00 精确资料计划

## What remains open

近期保持开放：

- M00-N01 第一轮用户批注将暴露哪些教学偏航；
- M00-N02 应走 deeper halfedge/incidence 路线，还是先做 comparative library lab；
- 是否需要把第一篇 Note 的 self-contained preamble 抽成正式公共 TeX template；
- MeshAudit 是否立即进入独立 Mesh Algorithm Library，还是先以课程练习形式存在；
- M00 的最终 exit criteria 是否需要独立习题课。

长期保持开放：

- 模块图会如何被实际 Note 反馈修改；
- 哪些 frontier tracks 将升级为主线；
- spline / topology / mesh 三套算法库何时、以何种抽象层统一。

## User feedback to preserve

- 希望掌握网格算法，但不是传统工程师式的“会写会调”。
- 希望算法背后建立整套数学理论。
- 同时强调工程能力，不能陷入纯推理游戏。
- 数学上至少关注拓扑、几何、分析三大层面，代数结构融入其中而非孤立教学。
- 重要算法应能从宏观结构解释其成立范围与失效原因，例如 Delaunay triangulation。
- 新技术可以进入课程，但应判断主线/支线地位，而非机械追热点。
- 成熟 mesh libraries 是重要学习资料，需要理解设计原理、优势、劣势和适用边界。
- 每篇 Note 必须明确 refs，并在 Note 内重复需要用户补充的资料。
- Note 必须让读者先知道“为什么”和“在做什么”，再进入严密细节。
- 图、worked example、习题、编码与支线内容都是教学体系的一部分，而不是装饰。
- 用户批注与助手回应要保存在 Note 的版本演化中。
- 长期不仅要有知识体系，还要形成可复用的 Mesh Algorithm Library，并最终与 spline / topology library 接轨。
- 整个课程必须能够跨聊天持续推进。

## Next recommended action

**用户阅读并批注 `M00-N01 v0.1`。**

在收到这一轮真实学习反馈之前，不预先锁定第二篇 Note。

## Last update

2026-09-16: M00 activated; first formal teaching Note `M00-N01 v0.1` written, M00 reference plan recorded, awaiting first user annotation round.