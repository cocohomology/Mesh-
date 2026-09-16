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
