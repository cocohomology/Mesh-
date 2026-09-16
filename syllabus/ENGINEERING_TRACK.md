# Engineering Track v0.1

> 数学主线决定我们如何理解算法；工程线保证这种理解能进入真实软件、真实退化输入和真实性能约束。

## 1. Engineering objectives

课程结束时，希望具备的不只是“能实现几个算法”，而是：

- 能读懂成熟 mesh library 的核心数据结构与算法组织；
- 能识别 API 背后的数学假设；
- 能区分拓扑错误、几何退化、数值问题、建模目标错误和性能问题；
- 能针对经典算法构造 pathological cases；
- 能通过 differential test / invariant test / convergence test 判断实现可靠性；
- 能形成一套初具规模、可测试、可复用的 Mesh Algorithm Library；
- 为未来与 spline library、topology algorithm library 的统一保留清晰接口，但不过早抽象。

## 2. Library-study principle

成熟库不是只拿来调用，也不是要逐行抄写。

每次阅读一个库，至少回答：

1. 它如何表示 mesh？
2. topology 与 geometry 是否分离？
3. 它默认允许什么输入：manifold / non-manifold / polygon soup？
4. mutation 如何处理，句柄是否稳定？
5. 算法依赖哪些 kernel / predicate / solver？
6. robustness 来自哪里：exact arithmetic、filtered predicates、repair assumptions 还是 simply documented preconditions？
7. API 更偏 generic programming、matrix processing、object-oriented mesh，还是 pipeline？
8. 设计更适合教学、研究原型、工业鲁棒性还是大规模数据？

## 3. Reference / oracle / implementation 三种角色

同一个外部库在课程中可以扮演不同角色：

- **Reference**：阅读其设计与源码；
- **Oracle**：作为 differential testing 的对照结果；
- **Dependency**：对于非课程核心内容，允许直接依赖，而非重复造轮子。

我们不会为了“自研”而重新实现所有基础设施。只重写那些能真正形成理解或属于长期算法库核心的部分。

## 4. Proposed Mesh Algorithm Library growth

### Stage E0 — Test & visualization harness

优先建立：

- mesh I/O adapter；
- viewer / debug visualization；
- test mesh generator；
- numerical comparison helpers；
- timing / profiling；
- pathological-case corpus。

### Stage E1 — MeshCore

候选能力：

- handles / indices；
- incidence / adjacency traversal；
- boundary queries；
- manifold / orientation checks；
- property storage；
- basic topology edits。

在充分比较 OpenMesh / PMP / geometry-central / CGAL 后再决定是否自写完整 halfedge 核心。

### Stage E2 — Predicates & triangulation

- orientation predicates；
- incircle / insphere；
- exact/adaptive strategy experiments；
- planar Delaunay prototype；
- triangulation validity tests。

### Stage E3 — Discrete geometry & operators

- normals / areas / curvature estimates；
- gradient / Laplacian / mass matrix；
- sparse assembly；
- Poisson / harmonic solves；
- boundary-condition utilities。

### Stage E4 — Surface processing

按课程推进逐步加入：

- geodesics；
- parameterization；
- smoothing / remeshing；
- simplification；
- subdivision。

### Stage E5 — Robust geometry

从小而清晰的组件开始：

- intersection predicates；
- self-intersection detection；
- orientation / repair；
- slicing；
- simple Boolean experiments。

完整 industrial Boolean 不设为早期硬目标。

### Stage E6 — Reconstruction & meshing

- implicit extraction experiments；
- point-to-mesh reconstruction wrappers / reference implementations；
- Delaunay refinement；
- surface / volume meshing experiments。

### Stage E7 — Integration

当 Mesh / Topology / Spline 三个库都积累到一定程度，再研究统一几何层：

- shared primitive / tolerance policies；
- topology-geometry relation；
- adapters rather than premature inheritance；
- common testing and visualization infrastructure。

## 5. Testing doctrine

### Invariant tests

例：

- halfedge twin consistency；
- boundary of boundary = 0；
- Euler characteristic checks；
- orientation consistency；
- Delaunay predicate validity。

### Pathological tests

主动生成：

- near-collinear / near-cocircular points；
- zero-area / skinny triangles；
- duplicated vertices；
- flipped orientation；
- non-manifold edge / vertex；
- self-intersections；
- extreme scales / coordinates。

### Differential tests

与 CGAL、libigl、geometry-central、PMP、Gmsh、TetGen 等适当对比。

对比不是只看“输出是否一样”，而是看：

- 目标函数是否相同；
- 输入假设是否相同；
- tolerance / exactness policy 是否相同；
- 不同结果是否都合法。

### Convergence / refinement tests

对于离散分析量，应该随着 mesh refinement 研究误差，而不是只在一个 bunny 上看结果是否漂亮。

### Performance tests

至少记录：

- asymptotic expectation；
- 实际时间；
- memory layout；
- allocation / cache behavior；
- solver cost；
- robustness 机制的性能代价。

## 6. Coding exercise levels

- **Level A — hand implementation**：几十行即可暴露核心思想；
- **Level B — reference implementation**：可测试但不追求完整产品化；
- **Level C — library candidate**：接口、tests、error handling 达到长期保留标准；
- **Level D — external integration**：课程核心不在实现本身，学习如何正确使用成熟库。

每个 coding exercise 在 Note 中标明等级，避免所有练习都被错误地做成“生产代码”。

## 7. Language and tooling

默认工程主线以 C++ 为主，与现有几何开发环境保持一致。Python 可以用于：

- 数值实验；
- plotting / convergence study；
- 快速原型；
- geometric learning / differentiable processing；
- 生成测试数据。

线性代数与 sparse solver 的具体依赖随模块决定，不提前把课程绑定到单一库。

## 8. Feedback loop

工程实践发现的问题必须允许反向修改理论教学。例如：

- 代码发现某个 theorem 依赖未被 Note 强调的 generic-position assumption；
- 库 API 说明实际对象不是我们想象中的 manifold mesh；
- 性能瓶颈暴露数据结构设计比算法复杂度更重要；
- exact predicate 的工程代价迫使重新讨论 robustness model。

此类问题应回写 Note / Discussion / Syllabus，而不是只当 bug 修掉。