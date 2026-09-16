# Module Template

每个正式模块建议使用以下模板。可按需要删改，但应保留“数学结构—算法—失效—工程意义”这一核心链条，并显式考虑教学方式、支线、习题和工程沉淀。

```markdown
# Module XX — Title

Status: planned | active | paused | completed-stage

## Why now

为什么此时学习本模块？它解决主线中的什么缺口？

## Prerequisites

需要哪些已有概念、Note、算法或工程经验？

## Big picture / taste

本模块最重要的 idea、motivation 和观察方式是什么？
学习前应先获得怎样的宏观图景？

## Mathematical objects

研究对象是什么？

## Core structures

真正控制问题的拓扑 / 几何 / 分析 / 代数结构是什么？

## Central questions

希望回答哪些本质问题？

## Key theorems / principles

哪些定理或原则支撑后续算法？

## Visual plan

哪些几何关系、算法过程、对偶结构、退化情况必须画图？

## Worked examples

哪些内容应通过小规模手算例子来理解？

## Algorithms

本模块对应哪些经典或重要网格算法？

## Failure modes and boundary cases

算法在哪些假设下成立？哪些场景会失效？失效属于模型、数学结构、组合退化还是数值问题？

## Generalizations

改变哪些结构后会得到怎样的推广？

## Engineering meaning

这些理论与算法在 CAD、图形学、有限元、机器人、视觉、科学计算等场景中意味着什么？

## Perspective / side roads

有哪些值得拓展视野但不应冲垮主线的数学理论、猜想、历史、行业故事或跨领域联系？
哪些值得发展为 side-note？

## Notes planned

计划包含哪些主 Note / side-note？

## Exercises / derivations

哪些习题真正承担教学任务？
包括手算、证明、反例构造、算法追踪等。

## Experiments / coding exercises

哪些内容需要数值实验或编码？
哪些实现适合进入长期 Mesh Algorithm Library？

## Library contribution

若本模块产生可复用代码，预期沉淀为什么模块 / 数据结构 / 测试？

## Exercise session

是否需要专门习题课？如果需要，为什么？

## References

需要哪些教材、论文、实现库或历史资料？

## Open questions

哪些问题当前保持开放？

## Exit criteria

完成模块时，用户应能够解释、推导、手算、诊断和实现到什么程度？
```

## Module status

- `planned`：已进入大纲但未开始；
- `active`：正在教学；
- `paused`：主动暂停，需注明原因；
- `completed-stage`：阶段完成，但允许未来回访和升级。

`completed-stage` 不表示主题永久封闭。Note 迭代、习题课、支线研究或算法库实现都可能使模块重新 active。
