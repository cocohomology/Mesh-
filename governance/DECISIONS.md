# Decisions Log

本文件只记录会影响未来课程理解、路线或协作方式的关键决策。不要把一般聊天摘要塞进这里。

## D-001 — Repository is the durable source of truth

**Date:** 2026-09-16

课程不能依赖单一聊天上下文。重要状态、路线、反馈和成熟结论必须写回仓库。

## D-002 — Mathematical structure is primary

**Date:** 2026-09-16

课程不以传统 mesh-processing 算法目录作为最高层组织原则。数学结构、对象层次与离散化思想优先；算法作为这些结构的计算化身来学习。

## D-003 — Theory and engineering must stay coupled

**Date:** 2026-09-16

禁止形成“先学纯数学、以后再看算法”的割裂模式。每个核心理论都要寻找工程对象与算法落点，每个核心算法都要寻找其数学结构、定理、假设与失败模式。

## D-004 — Core algorithm analysis schema

**Date:** 2026-09-16

对重要算法，默认追问：

1. 对象是什么？
2. 假设了什么结构？
3. 保持或优化什么量？
4. 正确性的核心定理是什么？
5. 哪些假设破坏后，什么性质先失效？
6. 推广时替换了什么数学结构？

这一模式可随课程发展修订，但不得退化为仅讲流程与代码。

## D-005 — Notes are teaching documents, not transcripts

**Date:** 2026-09-16

Note 应可独立阅读、结构完整、符号一致、图示与推导服务于理解。聊天中的探索过程只在成熟后进入 Note；未成熟内容进入 Discussion。

## D-006 — Syllabus is dynamic

**Date:** 2026-09-16

大纲是地图，不是合同。允许根据数学联系、用户反馈、工程案例、研究问题和前置缺口改变顺序、拆分或合并模块。

## D-007 — Course architecture uses core spine + engineering track + frontier tracks

**Date:** 2026-09-16

第一版正式课程采用三层结构：

- core mathematical/algorithmic spine：稳定的数学结构与经典网格算法；
- engineering track：数据结构、成熟库、实现、测试、性能与鲁棒性，贯穿所有核心模块；
- frontier tracks：geometric deep learning、differentiable geometry、implicit/neural representations、3D/4D Gaussian Splatting、Physical AI 等快速发展方向。

Frontier topic 不因“新”自动升级为主线，也不因“不传统”被排除。其地位需要依据长期价值、成熟度、与核心结构的联系和用户反馈动态调整。

## D-008 — Mature libraries are course material, not merely dependencies

**Date:** 2026-09-16

CGAL、libigl、geometry-central、PMP、OpenMesh、Gmsh、TetGen、Open3D、PyTorch3D 等成熟库将按模块选择性阅读。

阅读目标包括：对象模型、数据结构、数学假设、robustness policy、solver/kernel dependency、API philosophy、性能模型与适用边界。

外部库可分别充当 Reference、Oracle 或 Dependency；不要求为了“自研”重写所有功能。

## D-009 — Engineering work should accumulate into a Mesh Algorithm Library

**Date:** 2026-09-16

编码练习按教学实现、reference implementation、library candidate、external integration 分级。长期目标是形成可测试、可复用的 Mesh Algorithm Library，并在成熟后与 spline library 和 topology algorithm library 逐步连接。

禁止为了未来统一而过早设计复杂抽象；优先让课程中的真实算法需求推动架构。

## D-010 — Initial recommended entry is M00, not a famous algorithm

**Date:** 2026-09-16

v0.1 推荐从 `M00 — What is a mesh? Representation, incidence and data structures` 开始。原因是后续拓扑、度量、离散分析与算法鲁棒性都依赖对 mesh 对象层次的清晰认识。

Delaunay/Voronoi 被安排为早期第一个 grand case study，用于完整训练 `Structure <-> Theorem <-> Algorithm <-> Failure <-> Implementation`。

此入口不是永久决定；首批 Note 的用户反馈可以推翻它。