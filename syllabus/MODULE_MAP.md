# Course Module Map v0.1

> 本文件给出课程第一版正式模块图。它是当前最重要的内容地图，但不是不可修改的合同。用户在阅读 Note 后的反馈可以改变模块顺序、粒度、主线/支线身份甚至整体结构。

## 0. Design goal

课程同时追求两种能力：

1. **Theory-level mastery**：能从数学对象、结构、定理、假设、失效与推广理解网格算法；
2. **Engineering-level mastery**：能读成熟库、实现关键算法、构造测试、诊断退化、理解数据结构与性能，并逐步形成自己的 Mesh Algorithm Library。

因此课程不采用“先纯数学、再算法、最后工程”的分层教学，而采用交织式结构：

`Mathematical structure <-> Canonical algorithms <-> Robust implementation <-> Library anatomy <-> Experiments`

经典内容构成稳定主线；快速发展的技术以 frontier track 进入，只有当它们改变我们对几何表示或核心算法的理解时，才升级为主线。

---

## 1. Global map

```text
M00  Mesh as a finite geometric object & software object
 | \
 |  +--> M02  Piecewise-linear metric geometry
 v           | \
M01  Topology & combinatorics  |  +--> M03  Delaunay / Voronoi / predicates
 | \         |                  |       |
 |  \        v                  |       +--> M13 Meshing
 |   +----> M04 Discrete analysis / FEM / DEC
 |              |
 |              v
 |            M05 Variational geometry processing
 |            / |  \ \
 |           /  |   \ +--> M06 Geodesics / diffusion / spectrum
 |          /   |    +----> M07 Parameterization / conformal geometry
 |         /    +---------> M08 Smoothing / fairing / remeshing
 |        +---------------> M09 Simplification / approximation / LOD
 |                           |
 |                           +--> M10 Subdivision / multiresolution
 |
 +--> M11 Robust intersections / repair / Boolean operations

M02 + M03 + M04 ---> M12 Reconstruction / implicit & point-set geometry
M05 + M06 --------> M14 Deformation / shape analysis / correspondence

Frontier tracks:
F01 Geometric deep learning & differentiable geometry  <- M04/M06/M12
F02 Neural / explicit scene representations (NeRF, 3DGS, 4DGS, hybrids) <- M12
F03 Simulation / physical geometry / Physical AI bridge <- M04/M13/M14

Cross-cutting engineering track E runs through every module.
```

这张图表达的是依赖关系，而不是严格时间表。某些模块可能在实践中交错推进。

---

# Part I — Object, topology, metric, computational geometry

## M00 — What is a mesh? Representation, incidence and data structures

**Status:** core / recommended entry module

### Central question

一个 mesh 到底是什么？同一个对象为什么可以同时被看成 face-index list、graph、cell/simplicial complex、piecewise-linear surface 和软件数据结构？

### Mathematical backbone

- vertices / edges / faces 与 incidence；
- graph、simplicial complex、cell complex 的关系；
- abstract complex vs embedded realization；
- local neighborhood、star、link 的直觉；
- surface mesh / polygon soup / non-manifold data 的区别。

### Engineering backbone

- indexed face set；
- halfedge、winged-edge、corner table 等表示；
- handle / iterator / circulator / property system；
- topology 与 geometry storage 的分离；
- immutable vs editable mesh；
- cache locality、动态修改与稳定句柄。

### Library anatomy

重点对比 OpenMesh / PMP / geometry-central / CGAL Surface_mesh / libigl 的对象模型。

### Library contribution

建立 MeshCore 的最小数据模型、validity checker 与基础 traversal；是否自己完整实现 halfedge，在完成库比较后决定。

### Exit criterion

看到一种 mesh API 时，能够解释它保存了什么、不保存什么、允许哪些拓扑操作，以及这些设计换来了什么性能或鲁棒性。

---

## M01 — Combinatorial topology of surface meshes

**Status:** core

### Central question

不看坐标，只看连接关系时，一个 surface mesh 已经知道多少关于“表面”的信息？

### Mathematical backbone

- orientability、boundary、connected component；
- combinatorial manifold 与 link condition；
- Euler characteristic 与 genus；
- chains / boundary operator / homology 的计算化视角；
- local topology 与 global topology；
- topology-changing operations。

### Algorithms

- connected components；
- boundary extraction；
- orientation propagation；
- manifoldness detection；
- genus / Euler checks；
- edge collapse / split / flip 的拓扑合法性。

### Engineering focus

建立 topology invariant tests；把“算法崩了”与“输入根本不是假定的流形”区分开。

### Side-note candidates

CW complex、discrete Morse theory、persistent homology、拓扑清洗。

---

## M02 — Piecewise-linear metric geometry

**Status:** core

### Central question

在组合网格上加入长度或嵌入后，怎样重新建立连续曲面的几何概念？

### Mathematical backbone

- intrinsic vs extrinsic geometry；
- piecewise-linear metric；
- edge length、angle、area、normal；
- angle defect 与离散 Gaussian curvature；
- mean curvature 的多种离散化；
- sampling、approximation 与 discretization error。

### Algorithms

- face/vertex normals；
- curvature estimation；
- local frames；
- quality measures；
- basic distance queries。

### Engineering focus

研究不同离散几何量为什么会对 irregular / noisy mesh 敏感，以及“几何量的定义”和“估计器”之间的区别。

### Side-note candidates

Regge calculus、Alexandrov geometry、discrete curvature theorems。

---

## M03 — Voronoi, Delaunay, convexity and robust predicates

**Status:** core / first grand algorithm case study

### Central question

为什么一个看似初等的 triangulation algorithm 会同时连接空圆、Voronoi、凸包、lifting、局部 flip 与全局最优性质？它又为什么会在退化、曲面或错误 metric 下失效？

### Mathematical backbone

- Voronoi / Delaunay duality；
- empty-circle criterion；
- paraboloid lifting 与 convex hull；
- local-to-global flip criterion；
- degeneracy、general position 与 non-uniqueness；
- constrained / weighted / regular triangulation；
- surface / intrinsic / anisotropic variants 的思想。

### Algorithms

- incremental triangulation；
- edge flipping；
- Bowyer-Watson；
- orientation / incircle predicates；
- point location。

### Engineering focus

- floating-point predicates vs exact / adaptive predicates；
- combinatorial consistency；
- pathological tests；
- 与 CGAL / Triangle 类实现做 differential test。

### Library contribution

predicates layer + planar triangulation prototype。

### Exit criterion

能够从“结构假设被破坏”解释 Delaunay 类算法的失败，而不是只会列 edge cases。

---

# Part II — Analysis on discrete surfaces

## M04 — Discrete differential operators: FEM, DEC and Laplace-Beltrami

**Status:** core

### Central question

怎样在 mesh 上重新建立 gradient、divergence、Laplacian、differential form 与 PDE？不同离散化为什么会导向相同或不同的公式？

### Mathematical backbone

- scalar/vector fields on meshes；
- weak formulation；
- piecewise-linear finite elements；
- cotangent Laplacian；
- mass matrices；
- discrete exterior calculus：chain / cochain / exterior derivative / Hodge star；
- consistency、convergence、maximum principle 等性质。

### Algorithms

- Poisson solve；
- harmonic functions；
- Laplacian smoothing 的分析解释；
- heat diffusion；
- Hodge decomposition 的入口。

### Engineering focus

- sparse matrix assembly；
- boundary conditions；
- null space / gauge fixing；
- direct vs iterative solver；
- conditioning 与 mesh quality。

### Library contribution

离散 operator 与 sparse solve 基础层。

---

## M05 — Variational geometry processing

**Status:** core bridge module

### Central question

为什么大量 mesh algorithms 本质上都是“选一个能量 + 选一个离散空间 + 解一个优化问题”？

### Mathematical backbone

- energy functional；
- Euler-Lagrange / weak form；
- quadratic energy；
- constrained optimization；
- local/global optimization；
- convexity、non-convexity 与 regularization。

### Engineering focus

把数学目标、离散变量、约束、求解器与结果质量分开；学习诊断“模型不对”与“solver 不对”。

### Role

M05 不以独立算法数量取胜，而为 M06–M10、M14 提供统一语言。

---

## M06 — Geodesics, diffusion and spectral geometry

**Status:** core

### Mathematical backbone

- shortest paths vs intrinsic geodesics；
- Eikonal equation；
- heat equation 与 distance；
- Laplace spectrum、eigenfunctions；
- local vs global geometry。

### Algorithms

- graph Dijkstra；
- fast marching on meshes；
- heat method；
- spectral filtering / signatures 的入口。

### Engineering focus

比较不同 distance notion、精度、复杂度、mesh dependency，并建立可视化误差实验。

---

# Part III — Classical surface processing as mathematics in action

## M07 — Parameterization and discrete conformal geometry

**Status:** core

### Mathematical backbone

- disk topology / cuts；
- harmonic maps；
- Tutte embedding；
- conformal / authalic distortion；
- discrete conformal ideas；
- Jacobian 与 singular values 的 distortion view。

### Algorithms

- harmonic parameterization；
- LSCM；
- ABF/ABF++ 思想；
- seam / cut graph basics。

### Engineering applications

UV、texture mapping、remeshing、surface PDE transfer、manufacturing flattening。

---

## M08 — Smoothing, fairing, mesh quality and remeshing

**Status:** core

### Mathematical backbone

- Laplacian flow / mean-curvature-flow intuition；
- fairness energies；
- sampling density；
- isotropy / anisotropy；
- centroidal Voronoi / Delaunay ideas；
- element quality vs approximation quality。

### Algorithms

- Laplacian / Taubin / bilateral smoothing；
- isotropic remeshing；
- edge split / collapse / flip / relocation；
- feature-aware variants。

### Engineering focus

把“看起来更平滑”“triangle quality 更好”“geometry approximation 更好”三件事严格区分。

---

## M09 — Simplification, approximation and level of detail

**Status:** core

### Mathematical backbone

- approximation error；
- Hausdorff / point-to-surface / normal error；
- local surrogate vs global objective；
- quadric error metrics；
- topology constraints；
- progressive representations。

### Algorithms

- vertex clustering；
- edge collapse；
- QEM；
- progressive mesh / LOD；
- geometry-aware simplification。

### Engineering focus

与已有 spline simplification 经验形成横向比较：参数复杂度、几何误差、局部贪心与全局结构之间的关系。

### Library contribution

可测试的 simplification pipeline + error measurement suite。

---

## M10 — Subdivision surfaces and multiresolution

**Status:** core-secondary

### Mathematical backbone

- refinement operators；
- stationary subdivision；
- eigenanalysis near extraordinary vertices；
- smoothness；
- multiresolution / wavelet intuition。

### Algorithms

- Loop；
- Catmull-Clark；
- sqrt(3) 等代表方法；
- detail coefficients / multires editing。

### Role

连接“离散 mesh”与“极限光滑曲面”，也是样条、CAD 与 mesh 三条知识线的重要交汇点。

---

# Part IV — Robust modeling, reconstruction and meshing

## M11 — Intersection, repair and Boolean operations

**Status:** core engineering-heavy

### Central question

为什么最简单的几何操作在工业实现中会成为最困难的部分之一？

### Mathematical backbone

- arrangements / intersection complexes；
- winding / inside-outside；
- topology consistency；
- exact predicates vs constructions；
- degeneracies 与 symbolic perturbation 的思想。

### Algorithms

- triangle-triangle intersection；
- self-intersection detection；
- mesh slicing；
- Boolean union/intersection/difference；
- orientation / stitching / hole filling / manifold repair。

### Library anatomy

重点研究 CGAL robustness strategy，并与轻量库实现进行对比。

### Library contribution

从 validation / detection / repair 小组件开始，不一开始挑战完整 industrial Boolean kernel。

---

## M12 — Surface reconstruction and representation conversion

**Status:** core

### Mathematical backbone

- samples -> surface 的逆问题；
- implicit functions / signed distance；
- sampling density / noise / topology ambiguity；
- regularization；
- reconstruction 与 approximation 的区别。

### Algorithms

- marching cubes / dual-contouring ideas；
- alpha shapes / crust-style ideas；
- ball pivoting；
- Poisson surface reconstruction；
- MLS / implicit fitting 的入口。

### Engineering applications

3D scanning、reverse engineering、vision、medical imaging、robotics mapping。

### Bridge

本模块是 mesh 与 point cloud、implicit field、neural representation 的主要接口。

---

## M13 — Mesh generation: from domains to computation-quality meshes

**Status:** core engineering-heavy

### Mathematical backbone

- triangulation vs meshing；
- element quality；
- Delaunay refinement；
- sizing fields；
- boundary conformity；
- slivers 与高维困难；
- surface / tetrahedral mesh generation。

### Algorithms / systems

- constrained Delaunay；
- Delaunay refinement；
- advancing-front ideas；
- tetrahedralization；
- adaptive meshing。

### Library anatomy

Gmsh、TetGen、CGAL meshing packages。

### Engineering applications

FEM/CFD、CAD-to-analysis、simulation、manufacturing。

---

## M14 — Deformation, shape analysis and correspondence

**Status:** advanced core-secondary

### Mathematical backbone

- deformation energies；
- rigidity / ARAP；
- shape spaces；
- intrinsic descriptors；
- functional maps / spectral correspondence 的入口。

### Algorithms

- Laplacian editing；
- ARAP deformation；
- spectral descriptors；
- correspondence basics。

### Role

作为分析、优化、谱理论和实际编辑工具的综合模块。

---

# Part V — Frontier tracks

Frontier track 默认不阻塞主线。每进入一个 frontier topic，先回答：它是在解决传统 mesh 的什么限制？它是否改变了表示、优化或计算的基本范式？

## F01 — Geometric deep learning and differentiable geometry

**Status:** optional/frontier, likely important

候选主题：

- graph neural networks vs surface-aware networks；
- spectral / spatial geometric learning；
- DiffusionNet 一类利用几何算子的模型；
- equivariance；
- differentiable rendering / differentiable geometry processing；
- PyTorch3D / Open3D-ML；
- 为什么 discretization invariance 是核心问题。

若用户未来职业路线进一步靠近 Physical AI / 3D perception，本支线可升级为主线。

## F02 — Beyond meshes: implicit fields, NeRF, 3DGS and 4DGS

**Status:** optional/frontier

目的不是追热点，而是比较 representation bias：

- mesh：显式拓扑 + piecewise geometry；
- point / surfel / Gaussian：局部显式 primitive；
- voxel / field：空间离散；
- implicit neural field / SDF / NeRF：函数表示；
- 3D Gaussian Splatting：可优化的 anisotropic Gaussian primitives + splatting；
- 4DGS / dynamic representations：时间与形变如何进入表示。

核心问题是“什么时候 mesh 是正确表示，什么时候不是”，以及不同表示之间如何转换。

## F03 — Simulation, physical geometry and Physical AI bridge

**Status:** optional/frontier

候选主题：

- volumetric mesh 与 FEM；
- contact / collision；
- deformable bodies；
- differentiable simulation；
- scene geometry for robotics；
- learned geometry 与 classical numerical geometry 的结合。

---

# 2. Cross-cutting engineering track

每个 Module 都至少选择以下一项工程输出：

- `Read`: 阅读成熟库的相关实现与接口；
- `Reproduce`: 独立实现核心算法的教学/参考版本；
- `Test`: 构造 invariants、pathological cases、differential tests；
- `Profile`: 测性能、内存与数值稳定性；
- `Visualize`: 建立可视化用于理解算法过程和失败；
- `Integrate`: 将稳定实现沉淀进 Mesh Algorithm Library。

禁止把 coding exercise 退化成一次性 demo。

---

# 3. Recommended learning phases

这不是硬性顺序，而是 v0.1 推荐路线。

### Phase 1 — Learn the object

M00 -> M01 -> M02，并在 M03 用 Delaunay 进行第一次“结构—定理—算法—失效—实现”完整训练。

### Phase 2 — Put analysis on the mesh

M04 -> M05 -> M06。

### Phase 3 — Classical processing, now seen structurally

M07 / M08 / M09 / M10，可依据兴趣与工程需要部分交错。

### Phase 4 — Industrial difficulty

M11 / M12 / M13 / M14。这里开始大量读取成熟库和论文，并强化 robustness、benchmark 与系统设计。

### Phase 5 — Frontier and synthesis

F01 / F02 / F03 按职业方向、兴趣与课程反馈选择；同时做跨模块 capstone 与 library integration。

---

# 4. Recommended Phase 1 entry

当前推荐从 **M00 — What is a mesh?** 开始，而不是直接从 Delaunay 或离散 Laplacian 开始。

原因：课程未来所有数学与工程争论都依赖“我们到底把 mesh 当成什么对象”。M00 既能快速进入实际代码，也能自然引出 M01/M02，并能从第一篇 Note 起就比较成熟库的数据模型。

首批 Note 可以暂拟：

1. `M00-N01` — One mesh, many meanings: graph, complex, PL surface, data structure；
2. `M00-N02` — Halfedge and its relatives: why connectivity representation matters；
3. `M00-N03` — Mesh validity: manifoldness, orientation, boundary and invariants；
4. 习题/编码课 — 手工构造若干小网格，画 incidence/halfedge，写 traversal 与 validity tests。

是否保持此入口，由首轮用户反馈决定。

---

# 5. How the map evolves

每完成一篇重要 Note 或一个工程实验，都允许重新判断：

- 当前模块是否过大/过小；
- 某个 side road 是否应升级；
- 某个 core topic 是否其实可以降级；
- 是否遗漏关键工程问题；
- frontier topic 是否已经成熟到值得进入主线；
- library implementation 是否暴露了理论教学没有覆盖的假设。

任何显著改变同步更新 `OUTLINE.md`、`PROGRESS.md` 和必要的 `DECISIONS.md`。