# Course Philosophy

## 1. What this course is for

本课程的目标不是培养“会调用网格库、会实现若干经典算法”的工程熟练度，而是建立一套能够解释、重建、分析和推广网格算法的数学框架。

最终希望形成的能力包括：

- 面对一个网格算法，能够识别其真正作用的数学对象；
- 能从拓扑、几何、分析等层面理解其结构；
- 能把算法步骤还原到背后的定理与不变量；
- 能判断算法在哪些假设下成立、何时失效；
- 能理解不同推广版本为什么必须改变数学结构；
- 能把这种理解带回工程，实现更稳定的建模、调试与算法设计。

## 2. Mathematical worldview

课程暂定从三个主要层次理解 mesh：

### Topology

关注组合关系、邻接、定向、复形、边界、同调、流形条件等。

### Geometry

在拓扑结构上加入度量、嵌入、长度、角度、面积、曲率等几何信息。

### Analysis

在离散几何对象上承载函数、场与算子，讨论微分、Laplacian、能量、扩散、谱、PDE 等分析结构。

代数结构不单独作为孤立章节，而作为贯穿这些层次的语言自然出现。

## 3. Engineering worldview

从工程上，mesh 不仅是“三维模型格式”，而是一种把连续或复杂对象压缩为有限可计算结构的方式。

课程会持续追问：

- 网格究竟在离散什么？
- 数据结构保存了哪些信息？
- 某种算法改变了哪些自由度？
- 哪些结构被保持，哪些被牺牲？
- 算法的稳定性问题来自数值、组合、几何还是建模层？

## 4. Algorithm understanding standard

对于经典算法，不满足于“描述流程 + 复杂度 + 实现”。

理想理解链条是：

`Algorithm <-> Theorem <-> Structure <-> Assumption <-> Failure <-> Generalization`

例如遇到 Delaunay triangulation，不应只停留在空圆、flip、incremental insertion，而应进一步理解其与 Voronoi、凸性、lifting、度量结构、退化与推广之间的关系。

## 5. Teaching philosophy

教学 Note 不采用“论文压缩版”风格。

课程默认按照以下认知层次推进：

`Why -> Idea -> Motivation -> Picture -> Example -> Formal Theory -> Algorithm -> Failure -> Generalization -> Application`

其中：

- **idea、motivation、taste 是教学入口**。先建立宏观图景，知道为什么学、核心结构在哪里，再进入细节；
- **数学严谨性不可降低**，但严密证明属于深入层，而不是开场方式；
- **图与手算例子是正式教学内容**。复杂几何构型、算法步骤和失效案例原则上应可视化；抽象结构尽量安排可手算的小例子；
- **教学顺序可以重排学术材料**。论文为了新颖性和压缩而组织，课程为了理解而组织；
- **视野拓展是课程目标之一**。相关数学理论、历史、行业故事、跨领域应用可以作为 side road，必要时形成支线 Note；
- **习题是主动理解的工具**，不追求数量。好的习题应迫使读者计算、证明、构造反例、诊断失效、实验或编码；必要时开独立习题课。

详细规范见 `notes/README.md` 与 `notes/TEX_CONVENTIONS.md`。

## 6. Knowledge should accumulate into software

课程不是只生产文档。

长期目标之一是逐渐形成一个可复用、可测试、带数学解释的 **Mesh Algorithm Library**。课程中的编码练习、实验与算法实现应尽可能成为这一算法库的种子，而不是一次性 demo。

更长远的目标，是让：

- 已有的 spline / parametric geometry library；
- 正在发展的 topology algorithm library；
- 本课程形成的 mesh algorithm library；

逐步汇合为一套统一的几何算法体系。

这意味着课程中的数据结构、接口、测试、鲁棒性与数学抽象需要保持长期视角，但不为了未来统一而过早做复杂架构。

## 7. Relationship to traditional mesh-processing teaching

传统 mesh-processing 教材仍然有重要价值：它们提供经典问题、成熟算法与工程坐标系。

但本课程不会简单沿着“平滑、参数化、简化、重建……”的目录前进。传统目录更像应用索引；课程主线由数学结构与离散化思想决定。

## 8. Course tone

- 深，但不追求形式主义堆砌；
- 数学严谨，但始终追问工程意义；
- 工程具体，但不满足于经验参数；
- 允许支线和研究性问题；
- 允许推翻初版大纲；
- 允许长时间停留在一个真正重要的问题上；
- 允许一篇 Note 经历多轮“用户思考 -> 助手回应 -> 结构升级”的版本演化。

## 9. What success looks like

课程成功的标志不是“学完多少章节”，而是逐渐形成一种稳定的观察方式：

面对一个网格问题时，能自然地区分对象、结构、度量、算子、离散化、数值误差、组合退化和工程目标，并能从这些层次之间的联系中解释算法，而不是只依赖记忆与经验。

另一方面，知识应逐步沉淀为：

- 可反复阅读和迭代的高质量教学 Note；
- 有价值的习题与习题课记录；
- 可复用的算法实现与测试；
- 能暴露开放问题的 Discussion；
- 一张不断演化的数学—算法—工程知识地图。
