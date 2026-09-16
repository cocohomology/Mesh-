# Notes System

## Purpose

`notes/` 保存正式教学讲义。Note 是课程知识沉淀的主体，不是聊天记录、摘要、论文式压缩稿或速记。

课程中的 Note 有两个目标：

1. **教会知识**：让读者知道正在解决什么问题、为什么值得解决、核心结构是什么、细节如何推演、算法如何实现；
2. **扩展视野**：把主线知识放进更大的数学、算法、工程与行业背景中，帮助形成 taste，而不仅是记住结论。

因此 Note 的评价标准不是“定理是否齐全”，而是读完后是否真正建立了结构化理解。

## Teaching-first principle

正式 Note 必须优先采用教学叙事，而不是学术论文叙事。

推荐的理解层级是：

`Idea -> Motivation -> Geometric / mathematical picture -> Concrete example -> Formal statement -> Derivation / proof -> Algorithm -> Failure -> Generalization -> Engineering meaning`

其中：

- **Idea / motivation / taste 优先出现**：先解释为什么要做、问题从哪里来、最值得注意的结构是什么；
- **形式理论随后深入**：定义、定理与证明必须严谨，但不能替代宏观解释；
- **算法必须回到结构**：不能只给伪代码或步骤，要解释其数学来源、假设、保持量和失效方式；
- **教学顺序可以不同于论文顺序**：必要时重排证明、先给图像直觉、先做例子，再回头形式化。

## Visual standard

图不是可有可无的装饰，而是正式教学内容的一部分。

遇到以下内容时，原则上应主动画图：

- 网格局部组合结构；
- 几何构型；
- 算法步骤；
- 对偶结构；
- 退化 / 失效案例；
- 参数变化造成的结构变化；
- 需要空间直觉的证明；
- 多个数学对象之间的映射与关系。

正式 TeX Note 优先使用 TikZ / PGFPlots / 适当的矢量图；必要时可使用经过说明的外部图。图必须有教学目的，并在正文中被解释和引用。

## Hand-worked examples

对于抽象理论或复杂算法，应尽量安排小规模、可手算的例子。

例子不只是“验证公式”，而应承担以下一种或多种作用：

- 暴露定义真正包含的信息；
- 让读者亲手走完算法；
- 比较两个等价刻画；
- 展示某个假设被破坏后的结果；
- 解释一个矩阵、算子或能量从哪里来；
- 在进入代码前验证数学理解。

如果一个核心算法完全无法在小例子上手工追踪，应重新检查教学拆解是否足够细。

## Perspective and side notes

Note 除主线外，可以适量加入拓展内容，包括但不限于：

- 相关数学理论、猜想或历史背景；
- 与其他数学领域的联系；
- 同一结构在不同算法中的再次出现；
- 网格在 CAD、图形学、有限元、机器人、视觉、科学计算、医学等领域的实际用途；
- 经典算法、软件或行业发展中的小故事；
- 当前仍开放的问题。

原则是 **拓展视野但不冲垮主线**。

若某个侧路值得系统展开，则从主 Note 中留下入口，并新建 side-note，而不是无限扩张主 Note。

## Exercises are part of the teaching system

习题不是为了“每章末尾看起来完整”而存在。

只有当习题承担明确教学任务时才加入，例如：

- 手算一个非平凡例子；
- 证明正文中刻意留下的关键事实；
- 构造反例；
- 比较两个定义 / 算法；
- 诊断算法失效；
- 修改假设并判断结论如何变化；
- 做数值实验；
- 编码实现一个局部算法或数据结构；
- 对真实 mesh 做实验并解释结果。

高价值习题可以比正文更重要。课程允许专门开启 **Exercise Session / 习题课**，集中讨论解法、失败思路、推广和实现。

编码习题同时服务一个长期目标：逐步形成一个初具规模的 **Mesh Algorithm Library**。它未来希望与已有的样条库、正在建立的拓扑算法库形成统一的几何算法体系。课程中的实现任务应尽量避免一次性 demo，而优先考虑可测试、可复用、可逐步合并进算法库的设计。

## Suggested internal structure

并非每篇都必须机械遵循，但建议检查以下内容是否被覆盖：

```text
0. Version / status / prerequisites
1. Why this note? / motivation
2. Big picture and core idea
3. Visual intuition and worked example
4. Mathematical objects and definitions
5. Key structures / theorems / derivations
6. Algorithmic incarnation
7. Worked algorithm example
8. Failure modes / counterexamples
9. Generalization and deeper connections
10. Engineering interpretation / applications
11. Side roads and perspective
12. Exercises / experiments / coding tasks
13. References
14. Revision notes
```

## Note lifecycle and versioning

每篇 Note 必须有显式版本号，例如：

- `v0.1`：首个可读草稿；
- `v0.x`：仍在教学迭代；
- `v1.0`：完成至少一轮用户阅读与响应，可视为阶段稳定；
- `v1.x`：后续扩展或课程回访；
- `v2.0+`：结构性重写或理论框架发生明显升级。

状态可额外使用：`draft / teaching / revised / stable`。

版本号不是装饰。每次重要更新必须能回答：

- 为什么更新；
- 响应了什么反馈 / 思考；
- 哪些内容是本版本新增；
- 是否影响大纲、前后 Note 或习题。

具体 TeX 批注与版本标记见 `TEX_CONVENTIONS.md`。

## User–assistant iterative loop

正式 Note 的标准迭代过程是：

1. 助手生成一个完整教学版本并提交 Git；
2. 用户阅读；
3. 用户**不删除原文**，而是用规定的 TeX environment / command 在原 Note 中加入自己的思考、质疑、计算、联想和批注；
4. 用户提交 Git；
5. 助手重新阅读整篇 Note，尤其是用户批注；
6. 助手在同一 Note 中直接补充解释、修正结构、回应问题、增加图例 / 例子 / 习题，并用版本标记区分新增内容；
7. 升级 Note 版本号，并同步记录 revision note；
8. 若反馈暴露课程级问题，则同步更新 `syllabus/`、`governance/`、`refs/` 或其他相关文件；
9. 如有必要继续下一轮，直到双方认为当前 Note 可以阶段收束，再进入下一篇。

这个循环的目标不是把用户批注“清理掉”，而是让 Note 保存真实的学习轨迹与思想交锋。除非双方明确决定整理稳定版，否则历史性思考应保留。

## Note vs Discussion

成熟、可教学、结构闭合的内容进入 Note。

仍在探索、存在争议、只有局部观察或尚未验证的内容进入 `discussions/`。不要为了“文档完整”把猜测伪装成讲义结论。

当 Discussion 逐渐成熟时，可以：

- 回流主 Note；
- 形成 side-note；
- 变成习题 / 项目；
- 形成独立研究任务。

## Format

正式 Note 原则上以 **TeX 为主**，因为课程需要大量公式、证明、TikZ 图、版本批注与长期维护。

Markdown 主要承担：

- 索引；
- 进度；
- 课程治理；
- 大纲；
- 任务与参考资料记录。

在开始第一篇 Note 前，需要把 TeX 模板、编译方式、环境和版本标记规范冻结到“足够稳定可用”的程度，但以后仍允许演化。

## Feedback and revision

用户对 Note 的反馈需要判断层级：

- 局部措辞 / 解释：直接补充或修改；
- 数学缺口：补推导、反例、图示或重构；
- 教学顺序问题：可能重排章节或拆 Note；
- 缺乏直觉：增加 motivation、手算例子、图与类比；
- 缺乏视野：补 side road / application / historical context；
- 习题价值不足：删除机械习题，改成有明确训练目的的题目；
- 暴露课程结构问题：同步更新 syllabus；
- 引出研究问题：转入 discussions；
- 引出工程积累：进入 Mesh Algorithm Library 任务。

Note 不追求“一稿定稿”。课程允许一篇真正重要的 Note 经历多轮长期演化。
