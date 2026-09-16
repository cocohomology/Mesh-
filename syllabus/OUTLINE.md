# Dynamic Course Outline

> 本文件定义“大纲如何运作”；具体第一版模块图见 `MODULE_MAP.md`。大纲是地图，不是固定合同。

## 1. Purpose

大纲承担五件事：

- 给课程提供方向；
- 显式表示主题之间的依赖；
- 协调数学主线与工程能力；
- 管理主线 Note、支线 Note、习题课、编码任务、前沿专题与长期算法库积累；
- 允许根据用户反馈、工程实验和新技术发展动态重排。

任何模块都不应只因为“经典教材这么排”而存在。

## 2. Current architecture

课程采用三层结构：

### Core mathematical / algorithmic spine

围绕以下结构协同推进：

- **Topological structure**：组合关系、复形、流形性、边界、拓扑不变量；
- **Geometric structure**：嵌入、度量、长度、角度、面积、曲率、离散几何；
- **Analytic structure**：函数、算子、能量、PDE、谱与离散分析；
- **Discrete representation**：连续对象如何被采样、连接、近似为有限结构；
- **Computational geometry**：Delaunay/Voronoi、convexity、predicates、arrangements；
- **Robustness and failure**：退化、数值误差、模型不匹配、假设破坏与推广。

这些不是六门独立课程，而是互相穿插的坐标轴。

### Engineering track

每个核心模块都必须连接数据结构、成熟库、实现、测试、性能或鲁棒性中的至少一项。详细规则见 `ENGINEERING_TRACK.md`。

### Frontier tracks

快速发展的技术不因为“新”自动进入主线，也不因为“不传统”被排除。它们先作为 frontier track，持续问：

- 是否改变几何表示的基本范式？
- 是否提供了理解经典 mesh theory 的新视角？
- 是否对用户未来工程/职业方向具有长期价值？
- 是否已经成熟到值得系统教学，而非追逐短期热点？

当前 frontier tracks 包括 geometric deep learning、differentiable geometry、implicit/neural representations、3D/4D Gaussian Splatting、Physical AI / simulation bridge。具体见 `MODULE_MAP.md`。

## 3. Formal module map

第一版正式模块图已经建立：

- `MODULE_MAP.md`：模块依赖、核心问题、数学骨架、经典算法、工程重点、支线与前沿入口；
- `ENGINEERING_TRACK.md`：成熟库阅读、自研实现、测试与长期 Mesh Algorithm Library 的推进方式。

当前 v0.1 推荐入口为 `M00 — What is a mesh? Representation, incidence and data structures`，随后进入 topology、PL metric geometry，并以 Delaunay/Voronoi 作为第一次完整的“结构—定理—算法—失效—实现”案例。

该推荐入口仍允许被首批 Note 的实际反馈推翻。

## 4. Module design rule

每个正式 Module 应至少说明：

- Why now：为什么此时学习；
- Prerequisites：前置知识；
- Mathematical objects：研究对象；
- Structures：核心数学结构；
- Algorithms：相关算法；
- Visual / worked examples：哪些内容必须画图、哪些适合手算；
- Failure modes：典型失效；
- Engineering meaning：工程含义与应用场景；
- Library study：哪些成熟库值得阅读/作为 oracle；
- Perspective / side roads：值得拓展但不应冲垮主线的内容；
- Exercises / experiments：必要练习、实验与编码任务；
- Library contribution：是否有适合沉淀进 Mesh Algorithm Library 的实现；
- Exit criteria：结束时应具备什么能力。

模板见 `MODULE_TEMPLATE.md`。

## 5. Dependency over chronology

模块排序优先遵循知识依赖，不追求教材章节式线性。

允许出现：

- 主线模块；
- 插入型前置模块；
- 数学侧路；
- 工程实验支线；
- 支线 Note；
- 习题课；
- 编码 / library-building session；
- library source-reading session；
- frontier seminar；
- 研究型开放问题。

## 6. Main line and side roads

主线用于维持课程结构稳定，支线用于拓展视野。

支线可以来自：

- 某个数学结构的更深理论；
- 一个有价值的历史或行业故事；
- 网格在 CAD、图形学、有限元、机器人、视觉、医学等领域的应用；
- 主线中出现但暂时无法充分展开的猜想、开放问题或推广；
- 用户阅读 Note 时产生的联想；
- 快速发展的表示或学习方法。

当支线内容足够丰富时，应建立 side-note，而不是无限扩张主 Note。

## 7. Exercises and exercise sessions

习题不是模块装饰。

重要 Module 可在正式 Note 后插入习题课，尤其当以下情况出现时：

- 需要大量手算才能真正掌握定义；
- 需要构造反例理解假设；
- 某算法必须亲手走一遍；
- 某理论需要代码实验才能建立直觉；
- 编码实现值得沉淀进长期算法库。

习题量不设硬指标，质量优先。

## 8. References policy

长期参考地图维护在：

- `../refs/BOOKLIST.md`
- `../refs/LIBRARIES.md`

但每篇正式 Note 仍必须单独列出：

- 实际使用的 references；
- 推荐精读章节；
- optional reading；
- Requested references（若需要用户协助寻找/上传）。

这样用户不需要猜测当前 Note 需要哪些资料。

## 9. Note iteration may change the outline

Note 不是大纲的被动执行物。

一篇 Note 经用户阅读与多轮批注后，可能暴露：

- 前置知识缺失；
- 某个 Module 切分错误；
- 一条支线其实应该升级为主线；
- 当前教学顺序与真实理解顺序不一致；
- 某个算法实现值得提前进入工程路线；
- 某项“新技术”其实只是短期热点，或反过来已经值得升格。

发生这些情况时，应主动修改大纲，而不是为了保持原计划强行继续。

## 10. Outline evolution

重大改动必须回答：

1. 原大纲哪里暴露了问题？
2. 新结构解决什么？
3. 是否影响已完成 Note？
4. 是否需要回补前置内容？
5. 是否新增支线 Note / 习题课 / 编码任务 / library study？
6. 是否影响 Mesh Algorithm Library 的积累顺序？
7. 是否改变 frontier topic 的主线/支线地位？
8. 新会话如何理解本次变化？

重大变化同时写入 `governance/DECISIONS.md`。

## 11. Current status

第一版正式模块图 v0.1 已建立。

下一步不再是继续扩充目录，而是：

1. 对 M00 做首个正式 Module 设计；
2. 为 M00 选择精确 references 与 library-reading targets；
3. 建立正式 TeX Note template；
4. 开始 `M00-N01`，并用真实用户反馈检验模块图是否合理。