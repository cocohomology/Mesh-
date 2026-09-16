# Initial Book / Notes List v0.1

> 本书单不是“从头读完”的任务列表，而是课程的参考地图。每篇 Note 仍应在自己的 References / Requested refs 中列出真正使用或希望用户补充的资料。

## A. Core references

### R-B01 — Polygon Mesh Processing
- Authors: Mario Botsch, Leif Kobbelt, Mark Pauly, Pierre Alliez, Bruno Lévy
- Type: book
- Role: Primary / Engineering
- Relevant modules: M00, M07-M11, M14
- Why needed: 经典 geometry processing 工程坐标系；用于检查传统课程通常如何组织问题，并与我们的数学主线对照。
- Reading strategy: 按模块选读，不采用顺序通读。
- Status: identified

### R-B02 — Discrete Differential Geometry: An Applied Introduction
- Authors: Keenan Crane et al.
- Type: lecture notes / course notes
- Role: Primary
- Relevant modules: M02, M04-M08, M14
- Why needed: 将连续微分几何、离散算子和 geometry processing 算法建立紧密联系；教学风格与本课程理念较接近。
- Reading strategy: 与具体 Note 同步精读相关章节。
- Status: identified / public notes expected

### R-B03 — Computational Geometry: Algorithms and Applications
- Authors: Mark de Berg, Otfried Cheong, Marc van Kreveld, Mark Overmars
- Type: book
- Role: Primary
- Relevant modules: M03, M11, M13
- Why needed: Voronoi / Delaunay、arrangements、point location 等经典计算几何算法与证明框架。
- Reading strategy: 主要作为计算几何工具箱，不必覆盖全书。
- Status: identified

### R-B04 — Delaunay Mesh Generation
- Authors: Siu-Wing Cheng, Tamal K. Dey, Jonathan R. Shewchuk
- Type: book
- Role: Primary
- Relevant modules: M03, M13
- Why needed: 从 Delaunay 理论走向有质量保证的 mesh generation，是“结构—算法—鲁棒性—工程”的核心参考。
- Status: identified

### R-B05 — Geometry and Topology for Mesh Generation
- Author: Herbert Edelsbrunner
- Type: book
- Role: Primary / Mathematical perspective
- Relevant modules: M01, M03, M12, M13
- Why needed: 拓扑、计算几何与 mesh generation 的深层连接，符合本课程希望从数学结构理解算法的路线。
- Status: identified

## B. Analysis / DDG / numerical references

### R-B06 — Discrete Differential Geometry course material / SIGGRAPH notes
- Authors: various, including Crane / Desbrun / Schröder / Grinspun traditions
- Type: course notes / surveys
- Role: Secondary / Primary by topic
- Relevant modules: M02, M04-M08, M14
- Why needed: 不同 DDG 离散化传统常能解释同一公式的不同来源。
- Status: to curate per Note

### R-B07 — Discrete Exterior Calculus references
- Type: papers / notes
- Role: Secondary
- Relevant modules: M04
- Why needed: chain/cochain、exterior derivative、Hodge star 与离散 PDE 的统一语言。
- Status: to curate when M04 begins

### R-B08 — Finite Element Method references
- Type: textbook / notes
- Role: Secondary
- Relevant modules: M04, M05, M13, F03
- Why needed: weak formulation、basis functions、mass/stiffness matrix、convergence 与 conditioning。
- Note: 用户已有较强数学背景，不需要按工程教材从零铺陈；应针对 surface FEM / geometry processing 的连接选读。
- Status: to select

## C. Topology references

### R-B09 — Algebraic / combinatorial topology reference
- Type: textbook / notes
- Role: Secondary
- Relevant modules: M01, M11, M12
- Why needed: chain complex、homology、orientability 等内容需要严谨来源，但课程不准备重复一门完整代数拓扑课。
- Candidate direction: Hatcher / Munkres / computational topology texts, 按需要择一。
- Status: open

### R-B10 — Computational Topology: An Introduction
- Authors: Herbert Edelsbrunner, John Harer
- Type: book
- Role: Secondary / side road
- Relevant modules: M01, M12, possible persistent-homology side note
- Status: identified

## D. Surface processing / specialized references

### R-B11 — Parameterization / discrete conformal geometry references
- Type: papers / surveys / books
- Role: Secondary
- Relevant module: M07
- Candidate themes: harmonic maps, Tutte, LSCM, ABF++, discrete conformal equivalence
- Status: curate with module

### R-B12 — Spectral Geometry Processing references
- Type: SIGGRAPH course / surveys / papers
- Role: Secondary
- Relevant modules: M06, M14, F01
- Status: curate with module

### R-B13 — Surface reconstruction references
- Type: papers / surveys
- Role: Primary by algorithm
- Relevant module: M12
- Candidate canonical works: marching cubes, alpha shapes, ball pivoting, Poisson surface reconstruction, MLS
- Status: curate with module

## E. Frontier references

### R-F01 — 3D Gaussian Splatting for Real-Time Radiance Field Rendering
- Authors: Bernhard Kerbl, Georgios Kopanas, Thomas Leimkühler, George Drettakis
- Year: 2023
- Type: paper + reference implementation
- Role: Frontier
- Relevant module: F02
- Why needed: 代表 mesh / point / radiance-field 之外非常重要的显式可优化 3D 表示。
- Status: publicly available

### R-F02 — 4D Gaussian Splatting for Real-Time Dynamic Scene Rendering
- Authors: Guanjun Wu et al.
- Year: 2024
- Type: paper
- Role: Frontier
- Relevant module: F02
- Why needed: 用于观察时间、动态形变如何进入 Gaussian scene representation，而非因为“4D”名称本身进入主线。
- Status: publicly available

### R-F03 — DiffusionNet: Discretization Agnostic Learning on Surfaces
- Authors: Nicholas Sharp, Souhaib Attaiki, Keenan Crane, Maks Ovsjanikov
- Type: paper
- Role: Frontier / bridge
- Relevant module: F01
- Why needed: 很适合作为“经典离散几何算子如何成为 geometric learning primitive”的案例。
- Status: publicly available

## F. User-assisted Requested refs

目前没有任何资料是“缺失就无法开课”的硬阻塞项。

但如果用户手头方便获得以下完整电子资料，可以在相应模块开始前上传，便于逐页引用与精读：

- Polygon Mesh Processing；
- Delaunay Mesh Generation；
- Geometry and Topology for Mesh Generation；
- 用户认为值得对照的经典 mesh-processing / geometry-processing 教材。

每篇正式 Note 必须再次列出该 Note 真正需要的资料与具体章节。若出现关键论文无法完整读取，助手应在 Note 的 `Requested references` 或本目录中明确登记，而不是依赖二手摘要。

## G. Booklist maintenance rule

- `BOOKLIST.md` 保存长期地图；
- 某一 Module 的具体阅读任务应另建 module refs 或写入对应 Note；
- 一本书被列入这里，不代表课程承诺通读；
- frontier references 每隔一段时间重新评估，避免把短期热点固化成永久主线。