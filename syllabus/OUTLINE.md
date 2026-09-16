# Dynamic Course Outline

> 本文件是课程内容地图，不是固定合同。当前版本只定义大纲系统的组织方式与高层骨架，不展开具体教学内容。

## 1. Purpose

大纲承担三件事：

- 给课程提供方向；
- 显式表示主题之间的依赖；
- 允许根据反馈动态重排。

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
- Failure modes：典型失效；
- Engineering meaning：工程含义；
- Exercises / experiments：必要练习与实验；
- Exit criteria：结束时应具备什么能力。

模板见 `MODULE_TEMPLATE.md`。

## 4. Dependency over chronology

模块排序优先遵循知识依赖，不追求教材章节式线性。

允许出现：

- 主线模块；
- 插入型前置模块；
- 数学侧路；
- 工程实验支线；
- 研究型开放问题。

## 5. Outline evolution

重大改动必须回答：

1. 原大纲哪里暴露了问题？
2. 新结构解决什么？
3. 是否影响已完成 Note？
4. 是否需要回补前置内容？
5. 新会话如何理解本次变化？

重大变化同时写入 `governance/DECISIONS.md`。

## 6. Current status

当前尚未冻结正式模块列表。

Phase 0 完成后，将依据课程理念、用户反馈与参考资料，建立第一版正式模块图。第一版大纲仍视为可证伪假设，而非最终课程目录。
