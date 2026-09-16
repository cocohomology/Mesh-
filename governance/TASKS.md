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
- [x] 建立第一版正式课程模块图 `syllabus/MODULE_MAP.md`
- [x] 建立贯穿课程的工程学习与 Mesh Algorithm Library 路线 `syllabus/ENGINEERING_TRACK.md`
- [x] 建立初版书籍/讲义/前沿资料地图 `refs/BOOKLIST.md`
- [x] 建立成熟 mesh / geometry library 学习索引 `refs/LIBRARIES.md`
- [x] 明确 core spine + engineering track + frontier tracks 的课程结构

### TODO — immediate

- [ ] 设计 M00 正式 Module 文件
  - Why: v0.1 推荐从“mesh 究竟是什么”开始，需要把高层地图变成可教学单元
  - Input: `syllabus/MODULE_MAP.md`、`syllabus/MODULE_TEMPLATE.md`、`refs/LIBRARIES.md`
  - Output: M00 的 big picture、Note 列表、图示/手算计划、库阅读、习题、coding 与 exit criteria
  - Done when: 可以直接开始第一篇 Note

- [ ] 建立正式 TeX Note template / preamble
  - Why: 第一篇 Note 开始前，需要把用户批注、助手回应、版本新增、图、worked example、习题与 coding exercise 的环境真正落到可编译模板
  - Input: `notes/TEX_CONVENTIONS.md`、M00 实际需求
  - Output: 可复用 TeX 模板与编译说明
  - Done when: 可以直接创建并编译 `M00-N01`

- [ ] 为 M00 建立精确 reference plan
  - Why: 长期书单已经建立，但第一篇 Note 必须告诉用户具体看什么/需要什么资料
  - Input: `refs/BOOKLIST.md`、`refs/LIBRARIES.md`
  - Output: M00 used/recommended/optional/requested refs
  - Done when: 用户不需要猜测要准备哪些资料

- [ ] 设计 M00 的首次 library study
  - Why: 数据结构问题必须结合真实成熟库，而不是只做抽象比较
  - Candidate: OpenMesh / PMP / geometry-central / CGAL Surface_mesh / libigl
  - Output: 一张设计维度对比表 + 首轮源码阅读目标
  - Done when: M00-N01/N02 能引用真实库设计

### TODO — near term

- [ ] 完成 `M00-N01 — One mesh, many meanings`
- [ ] 建立首个习题 / coding session：手工小网格、incidence、halfedge traversal、validity tests
- [ ] 根据用户对 M00 首批 Note 的反馈重新审查 `MODULE_MAP.md`
- [ ] 规划 Mesh Algorithm Library 的最小实际仓库/目录结构
- [ ] M03 开始前补齐 Triangle / robust predicates 的精确源码与论文参考
- [ ] Frontier track 开始前重新检索当时代表技术，不直接沿用当前技术快照

## Task handoff template

新增任务尽量写成：

```markdown
- [ ] 任务名称
  - Why: 为什么现在要做
  - Input: 依赖哪些文件/资料
  - Output: 需要产生什么文件或结论
  - Done when: 完成标准
```
