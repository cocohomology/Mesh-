# Mesh / Geometry Library Study Index v0.1

> 本文件记录课程中值得阅读、对比或作为测试 oracle 的成熟库。目标不是收集链接，而是理解不同库对“mesh 是什么”以及“robust geometry 应该怎么做”的不同回答。

## 1. Core libraries

### L01 — CGAL
- Role: Engineering / Robustness / Oracle
- Main value:
  - broad computational geometry framework；
  - explicit kernel / traits / concept design；
  - robust predicates and constructions；
  - polygon mesh processing、Boolean、repair、remeshing、meshing 等完整生态。
- Best modules: M03, M11, M13
- What to study:
  - `Surface_mesh` / FaceGraph concepts；
  - kernel and exactness policy；
  - preconditions and named parameters；
  - Polygon Mesh Processing package architecture；
  - Boolean / repair / meshing 的 robustness strategy。
- Trade-off to discuss: 强泛型与鲁棒性带来的复杂 API、模板层级、编译与学习成本。

### L02 — libigl
- Role: Teaching / Prototype / Matrix-based geometry processing
- Main value:
  - 算法多以 `V,F` 与 Eigen matrix 形式呈现；
  - 接近论文公式与快速原型；
  - 适合观察“geometry processing 是否真的需要重量级 mesh object”。
- Best modules: M02, M04-M10, M14
- What to study:
  - matrix-oriented API；
  - algorithm-as-function design；
  - sparse operators and optimization；
  - 与 halfedge-style library 的设计差异。
- Trade-off to discuss: 对频繁 topology mutation 与复杂 connectivity 操作并非天然最合适。

### L03 — geometry-central
- Role: Teaching / DDG / Modern mesh architecture
- Main value:
  - modern surface mesh data structure；
  - intrinsic geometry 与 DDG 工具；
  - mesh connectivity 与 geometry quantities 的清晰区分；
  - 与 Keenan Crane 系列 DDG 教学材料衔接很好。
- Best modules: M00, M02, M04, M06-M08, M14
- What to study:
  - `SurfaceMesh` / `ManifoldSurfaceMesh`；
  - element handles；
  - dense buffers / data containers；
  - intrinsic triangulations / operators where relevant。

### L04 — PMP Library
- Role: Teaching / Compact C++ reference implementation
- Main value:
  - 现代、相对紧凑的 C++ polygon mesh library；
  - core mesh + canonical algorithms + viewer；
  - decimation、remeshing、subdivision、smoothing 等经典实现集中。
- Best modules: M00, M08-M10
- What to study:
  - `SurfaceMesh` design；
  - property system；
  - iterators/circulators；
  - canonical algorithm implementation style。
- Good use: 比 CGAL 更容易做源码教学阅读。

### L05 — OpenMesh
- Role: Data-structure reference
- Main value:
  - mature halfedge-based mesh representation；
  - dynamic properties；
  - topology editing model；
  - 很适合作为“经典 editable mesh data structure”的代表。
- Best modules: M00, M01, M08-M10
- What to study:
  - handles / halfedges；
  - status and property system；
  - topology mutation。

## 2. Meshing systems

### L06 — Gmsh
- Role: Engineering / End-to-end meshing system
- Main value:
  - CAD/geometry -> mesh -> solver/post-processing pipeline；
  - surface and volume mesh generation；
  - sizing fields / adaptive meshing；
  - C/C++/Python 等 API。
- Best module: M13, F03
- What to study:
  - geometry representation与meshing pipeline边界；
  - algorithm choice / mesh size control；
  - CAD-to-analysis workflow；
  - industrial input handling。

### L07 — TetGen
- Role: Algorithm reference / Oracle
- Main value:
  - constrained Delaunay tetrahedralization；
  - quality tetrahedral meshing；
  - boundary conformity；
  - 与 FEM/FVM 直接连接。
- Best modules: M03, M13
- What to study:
  - 3D Delaunay difficulties；
  - quality criteria；
  - slivers；
  - predicates and boundary handling。

### L08 — Triangle (Jonathan Shewchuk)
- Role: Canonical 2D triangulation / Robustness reference
- Main value:
  - planar Delaunay / constrained triangulation / quality meshing；
  - adaptive exact predicates tradition；
  - 连接理论和极具工程影响力的实现。
- Best modules: M03, M13
- Status: source/reference to curate when M03 begins.

## 3. Point cloud / reconstruction / broad 3D systems

### L09 — Open3D
- Role: Engineering / 3D data pipeline / Frontier bridge
- Main value:
  - point cloud, triangle mesh, reconstruction, registration, visualization；
  - C++ + Python；
  - GPU / ML support；
  - 适合 M12 后研究 mesh 与 point-cloud pipeline 的关系。
- Best modules: M12, F01, F02

### L10 — trimesh
- Role: Python prototyping / I/O / utility
- Main value:
  - 轻量快速实验；
  - mesh queries / conversion / I/O；
  - 适合作为实验脚本工具，而非核心数学结构参考。
- Best use: exercises and testing harness.

## 4. Differentiable / learning libraries

### L11 — PyTorch3D
- Role: Frontier / Differentiable 3D
- Main value:
  - batched mesh representation；
  - differentiable rendering / geometry operations；
  - 与 learning pipeline 集成。
- Best modules: F01, F02
- Question to ask: 当 mesh 进入 tensor/batch/autograd 体系时，传统 halfedge topology assumptions 会发生什么变化？

### L12 — Open3D-ML / PyTorch Geometric ecosystem
- Role: Frontier
- Main value:
  - point/graph learning pipelines；
  - 用于对比 graph-based 与 geometry-aware representation。
- Best module: F01

## 5. Modern representation reference implementations

### L13 — graphdeco-inria / gaussian-splatting
- Role: Frontier implementation reference
- Main value:
  - original 3D Gaussian Splatting implementation；
  - optimizer + density control + visibility-aware splatting；
  - 很适合研究“mesh 之外的 explicit representation”。
- Best module: F02

### L14 — 4DGS implementations
- Role: Frontier
- Main value:
  - dynamic scene representation；
  - 时间、deformation field 与 explicit Gaussian primitives 的组合。
- Best module: F02
- Rule: 进入课程前重新检查当时最新代表方法，不把 2024 的某一实现永久固定为唯一标准。

## 6. Comparison dimensions

每次正式 library study 至少按以下维度做表：

| Dimension | Questions |
|---|---|
| Mathematical object | graph / manifold mesh / polygon soup / point set / volumetric mesh? |
| Connectivity | explicit halfedge / index matrices / implicit? |
| Geometry storage | vertex positions only? intrinsic edge lengths? arbitrary properties? |
| Mutation | easy / expensive / unsupported? |
| Robustness | exact predicates? tolerances? documented preconditions? |
| Genericity | templates / concepts / dynamic runtime? |
| Linear algebra | Eigen / custom / tensor backend? |
| Performance model | dynamic editing / batch processing / GPU / sparse solve? |
| Pedagogical value | formula-transparent or abstraction-heavy? |
| Industrial value | breadth, stability, difficult-input handling |
| License / integration | can it be used as reference, dependency, or only oracle? |

## 7. Course policy

- 不设唯一“标准库”。不同设计反映不同数学与工程立场。
- 每个核心模块至少选 1–3 个最相关库阅读，而不是所有库都看。
- 自己实现算法前先明确：这次是为了教学、研究、library asset，还是成熟库已经足够。
- 新技术库更新很快，F01/F02 开始前必须重新检查生态与代表实现。