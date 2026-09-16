# Tasks

本文件维护当前任务池。任务应足够具体，可以被另一个聊天直接执行。

## Status conventions

- `TODO`：尚未开始
- `DOING`：当前进行中
- `BLOCKED`：被依赖或资料阻塞
- `DONE`：完成
- `DEFERRED`：明确延后

## Current tasks

### DONE

- [x] 初始化仓库 README 与整体目录约定
- [x] 建立课程运行协议
- [x] 建立跨聊天交接协议
- [x] 建立当前进度入口
- [x] 建立关键决策日志
- [x] 建立反馈闭环机制
- [x] 建立课程理念与动态大纲系统
- [x] 建立 Module 模板
- [x] 建立 Note 系统
- [x] 建立 Discussion 系统
- [x] 建立 Reference 系统
- [x] 对 Phase 0 文档做首次一致性审查
- [x] 强化教学 Note 规范：图示、worked example、idea/motivation/taste、支线、习题与习题课
- [x] 建立 Note 多轮版本与用户批注 / 助手回应的 TeX 语义规范
- [x] 将 Mesh Algorithm Library 长期目标写入课程理念与模块设计

### TODO

- [ ] 建立第一版正式课程模块图
  - Why: 从“运行机制”进入“内容设计”
  - Input: `syllabus/PHILOSOPHY.md`、`notes/README.md`、历史讨论、后续用户反馈
  - Output: 第一版正式模块依赖图与模块列表
  - Done when: 可以据此选择 Phase 1 教学入口

- [ ] 决定 Phase 1 的正式教学入口
  - Why: 避免未经设计直接写第一篇 Note
  - Input: 第一版正式模块图
  - Output: 首个 active module 与第一篇 Note 计划
  - Done when: `PROGRESS.md` 明确记录下一教学动作

- [ ] 确定第一批核心参考资料
  - Why: 为首批模块提供可靠教材、论文与工程实现来源
  - Input: 正式模块图
  - Output: `refs/` 中的首批条目与 Requested 清单
  - Done when: 首模块所需资料明确

- [ ] 建立正式 TeX Note template / preamble
  - Why: 第一篇 Note 开始前，需要把用户批注、助手回应、版本新增、图、worked example、习题与 coding exercise 的环境真正落到可编译模板
  - Input: `notes/TEX_CONVENTIONS.md`、首篇 Note 的实际需求
  - Output: 可复用 TeX 模板与编译说明
  - Done when: 可以直接创建并编译第一篇正式 Note

- [ ] 设计首个 Module 的验收方式
  - Why: 掌握标准不能只依赖“读完了”
  - Input: 首模块内容
  - Output: 解释、推导、手算、实验、失效诊断与实现层面的 exit criteria
  - Done when: 可以客观判断阶段完成

- [ ] 规划 Mesh Algorithm Library 的最小组织方式
  - Why: 编码习题应逐步沉淀为长期资产，但不应过早复杂架构
  - Input: 前若干 Module 的实际算法需求、已有样条库与拓扑库方向
  - Output: 初版代码组织、测试原则、与课程 Note 的链接方式
  - Done when: 首个可复用算法实现有明确落点

## Task handoff template

新增任务尽量写成：

```markdown
- [ ] 任务名称
  - Why: 为什么现在要做
  - Input: 依赖哪些文件/资料
  - Output: 需要产生什么文件或结论
  - Done when: 完成标准
```
