# Dynamic Course Outline

> 本文件是课程内容地图，不是固定合同。当前版本只定义大纲系统的组织方式与高层骨架，不展开具体教学内容。

## 1. Purpose

大纲承担四件事：

- 给课程提供方向；
- 显式表示主题之间的依赖；
- 允许根据反馈动态重排；
- 协调主线 Note、支线 Note、习题课、编码任务与长期算法库积累。

任何模块都不应只因为“经典教材这么排”而存在。

## 2. High-level structure

当前课程高层框架暂定围绕以下几条主轴协同推进：

- **Topological structure**：组合关系、复形、流形性、边界、拓扑不变量；
- **Geometric structure**：嵌入、度量、长度、角度、面积、曲率、离散几何；
- **Analytic structure**：函数、算子、能量、PDE、谱与离散分析；
- **Discrete representation**：连续对象如何被采样、连接、近似为有限结构；
- **Algorithms and data structures**：经典网格算法如何作为上述结构的计算化身；
- **Robustness and failure**：退化、数值误差、模型不匹配、假设破坏与推广。

这些不是六门独立课程，而是互相穿插的坐标轴。

## 3. Module design rule

每个正式 Module 应至少说明：

- Why now：为什么此时学习；
- Prerequisites：前置知识；
- Mathematical objects：研究对象；
- Structures：核心数学结构；
- Algorithms：相关算法；
- Visual / worked examples：哪些内容必须画图、哪些适合手算；
- Failure modes：典型失效；
- Engineering meaning：工程含义与应用场景；
- Perspective / side roads：值得拓展但不应冲垮主线的内容；
- Exercises / experiments：必要练习、实验与编码任务；
- Library contribution：是否有适合沉淀进 Mesh Algorithm Library 的实现；
- Exit criteria：结束时应具备什么能力。

模板见 `MODULE_TEMPLATE.md`。后续应根据本规范同步升级模板。

## 4. Dependency over chronology

模块排序优先遵循知识依赖，不追求教材章节式线性。

允许出现：

- 主线模块；
- 插入型前置模块；
- 数学侧路；
- 工程实验支线；
- 支线 Note；
- 习题课；
- 编码 / library-building session；
- 研究型开放问题。

## 5. Main line and side roads

主线用于维持课程结构稳定，支线用于拓展视野。

支线可以来自：

- 某个数学结构的更深理论；
- 一个有价值的历史或行业故事；
- 某种网格方法在 CAD、图形学、有限元、机器人、视觉、医学等领域的应用；
- 主线中出现但暂时无法充分展开的数学猜想、开放问题或推广；
- 用户阅读 Note 时产生的联想。

当支线内容足够丰富时，应建立 side-note，而不是无限扩张主 Note。

## 6. Exercises and exercise sessions

习题不是模块装饰。

大纲允许某个重要 Module 在正式 Note 后插入习题课，尤其当以下情况出现时：

- 需要大量手算才能真正掌握定义；
- 需要构造反例理解假设；
- 某算法必须亲手走一遍；
- 某理论需要代码实验才能建立直觉；
- 编码实现值得沉淀进长期算法库。

习题量不设硬指标，质量优先。

## 7. Note iteration may change the outline

Note 不是大纲的被动执行物。

一篇 Note 经用户阅读与多轮批注后，可能暴露：

- 前置知识缺失；
- 某个 Module 切分错误；
- 一条支线其实应该升级为主线；
- 当前教学顺序与真实理解顺序不一致；
- 某个算法实现值得提前进入工程路线。

发生这些情况时，应主动修改大纲，而不是为了保持原计划强行继续。

## 8. Outline evolution

重大改动必须回答：

1. 原大纲哪里暴露了问题？
2. 新结构解决什么？
3. 是否影响已完成 Note？
4. 是否需要回补前置内容？
5. 是否新增支线 Note / 习题课 / 编码任务？
6. 是否影响 Mesh Algorithm Library 的积累顺序？
7. 新会话如何理解本次变化？

重大变化同时写入 `governance/DECISIONS.md`。

## 9. Current status

当前尚未冻结正式模块列表。

下一步将依据课程理念、Note 教学规范、用户反馈与参考资料，建立第一版正式模块图。第一版大纲仍视为可证伪假设，而非最终课程目录。
