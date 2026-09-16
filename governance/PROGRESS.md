# Progress

> 本文件是课程当前状态的唯一权威入口。新会话优先读取本文件。

## Current phase

**Phase 0 complete — infrastructure established**

**Phase 1 design ready — v0.1 formal curriculum map established; first teaching module not yet written**

## Current focus

课程已经从“如何运行”进入“具体学什么、如何把理论与工程交织”的阶段。

第一版正式模块图、工程线、书单和成熟库索引已经建立。下一步不是继续无限扩充大纲，而是把 `M00 — What is a mesh?` 设计成第一个可执行 Module，并建立正式 TeX Note template，然后开始 `M00-N01`。

## What is now settled

### Course worldview

- 本课程不是传统“网格算法大全”。
- 课程追求数学结构与网格算法之间的强连接。
- 数学学习不与工程割裂。
- 数学上以拓扑、几何、分析三大层次作为高层观察框架，代数结构作为贯穿语言自然融入。
- 工程上把 mesh 看作有限离散表示，并持续追问其数据结构、离散对象、保持量和牺牲量。
- 核心算法需要分析：对象、假设、数学结构、核心定理、失效机制与推广。
- 理想理解链条为：`Algorithm <-> Theorem <-> Structure <-> Assumption <-> Failure <-> Generalization`。

### Curriculum architecture

课程采用：

1. **Core mathematical/algorithmic spine**：稳定的数学结构与经典网格算法；
2. **Engineering track**：数据结构、成熟库、实现、测试、性能与鲁棒性，贯穿所有核心模块；
3. **Frontier tracks**：快速发展的 geometric learning、differentiable geometry、implicit/neural representation、3D/4D Gaussian Splatting、Physical AI 等方向。

Frontier topic 不因为新而自动进入主线；开始正式教学前必须重新检查当时代表技术与成熟度。

### v0.1 module map

正式地图见 `syllabus/MODULE_MAP.md`。

当前模块包括：

- M00 mesh object / representation / data structures；
- M01 combinatorial topology；
- M02 piecewise-linear metric geometry；
- M03 Voronoi / Delaunay / convexity / robust predicates；
- M04 discrete differential operators / FEM / DEC；
- M05 variational geometry processing；
- M06 geodesics / diffusion / spectral geometry；
- M07 parameterization / discrete conformal geometry；
- M08 smoothing / fairing / remeshing；
- M09 simplification / approximation / LOD；
- M10 subdivision / multiresolution；
- M11 intersections / repair / Boolean operations；
- M12 reconstruction / point & implicit geometry；
- M13 surface / volume mesh generation；
- M14 deformation / shape analysis / correspondence；
- F01 geometric deep learning / differentiable geometry；
- F02 implicit/neural scene representation, NeRF, 3DGS, 4DGS；
- F03 simulation / physical geometry / Physical AI bridge。

v0.1 推荐从 M00 开始；M03 Delaunay/Voronoi 将作为早期第一个 grand case study。

### Engineering line

`syllabus/ENGINEERING_TRACK.md` 已定义：

- 外部库作为 Reference / Oracle / Dependency 三种角色；
- invariant / pathological / differential / convergence / performance tests；
- coding exercise 分为 hand implementation / reference implementation / library candidate / external integration；
- Mesh Algorithm Library 的分阶段积累路线；
- 不为“自研”重写一切，也不为未来三库统一而过早抽象。

### Mature libraries

`refs/LIBRARIES.md` 已建立首批索引，包括 CGAL、libigl、geometry-central、PMP、OpenMesh、Gmsh、TetGen、Triangle、Open3D、PyTorch3D 等。

这些库本身也是课程材料：需要研究对象模型、connectivity、mutation、property、robustness、genericity、solver/kernel、性能模型和适用边界。

### References

`refs/BOOKLIST.md` 已建立长期参考地图。每篇正式 Note 仍必须单独列出 used / recommended / optional / requested references 和具体阅读章节。

### Note system

- Note 必须是教学式讲义，而不是聊天摘要或论文压缩版。
- 认知顺序优先强调：`Why -> Idea -> Motivation -> Picture -> Example -> Formal Theory -> Algorithm -> Failure -> Generalization -> Application`。
- 图示与可手算的小例子属于正式教学内容。
- 支线理论、历史、行业故事和跨领域应用可以形成 side-note。
- 习题不追求数量，只保留真正承担思考、计算、反例、实验或编码任务的高价值题目；必要时开启习题课。
- 编码习题长期服务于 Mesh Algorithm Library。
- 每篇 Note 有显式版本号，并采用用户—助手多轮非破坏式迭代。
- 用户通过 `studentthought` 加入思考；助手通过 `assistantresponse` 回应，并用 `versionaddition` 标记新版本正式新增内容。

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
- `discussions/README.md`：Discussion 规范
- `refs/README.md`：Reference 规范
- `refs/BOOKLIST.md`：长期资料地图
- `refs/LIBRARIES.md`：成熟库学习索引

## What remains open

近期需要形成：

- M00 正式 Module 文件；
- 第一篇正式 Note 的完整 TeX template / preamble 与编译方式；
- M00 的精确 used/recommended/requested references；
- M00 首轮成熟库源码阅读计划；
- Mesh Algorithm Library 的实际仓库/目录组织方式；
- 首个 Module 的阶段性验收方式。

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
- 传统 mesh processing 可作为工程参照，但不应成为课程唯一主线。
- 新技术可以进入课程，但应判断主线/支线地位，而非机械追热点；3D/4DGS、geometric deep learning 只是示例。
- 成熟 mesh libraries 是重要学习资料，需要理解设计原理、优势、劣势和适用边界。
- 每篇 Note 必须明确 refs；长期书单/库索引也应维护在仓库。
- Note 必须让读者先知道“为什么”和“在做什么”，再进入严密细节。
- 图、worked example、习题、编码与支线内容都是教学体系的一部分，而不是装饰。
- 用户批注与助手回应要保存在 Note 的版本演化中。
- 长期不仅要有知识体系，还要形成可复用的 Mesh Algorithm Library，并最终与 spline / topology library 接轨。
- 整个课程必须能够跨聊天持续推进。

## Next recommended action

设计 `M00` 正式 Module 文件，同时建立 TeX template 和 M00 精确参考计划。完成这三项后开始 `M00-N01 — One mesh, many meanings: graph, complex, PL surface, data structure`。

第一篇 Note 完成并经过用户首轮批注后，立即做一次大纲回看，而不是机械进入 M00-N02。

## Last update

2026-09-16: v0.1 formal module map, engineering track, reference booklist and mature-library study index established.