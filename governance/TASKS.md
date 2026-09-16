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
- [x] 完成第一篇正式 Note `notes/M00/M00-N01-one-mesh-many-meanings.tex` v0.1
- [x] 建立 M00 精确 reference plan `refs/M00.md`

### DOING — immediate

- [ ] **M00-N01 第一轮用户阅读与批注**
  - Why: 大纲与 Note 必须接受真实学习反馈，而不是助手单方面继续铺课
  - Input: `notes/M00/M00-N01-one-mesh-many-meanings.tex` v0.1
  - User action: 不删除原文，使用 `studentthought` 环境加入思考、质疑、计算、工程联想并提交 Git
  - Assistant action after commit: 读取全部批注，用 `assistantresponse` 回应，必要时用 `versionaddition` 补正式内容，升级版本号与 revision history
  - Done when: 第一轮反馈被吸收并形成下一版本

### TODO — after first review

- [ ] 根据 M00-N01 的真实反馈回看 `syllabus/MODULE_MAP.md`
  - Why: 第一篇 Note 是课程大纲的第一次实际压力测试
  - Output: 保持、微调或重构模块顺序/粒度的明确判断

- [ ] 决定 M00-N02 的方向
  - Candidate A: deeper incidence / boundary / orientation / halfedge implementation
  - Candidate B: comparative library lab — libigl vs geometry-central vs OpenMesh/CGAL
  - Input: 用户对 v0.1 的批注
  - Done when: `PROGRESS.md` 明确下一篇 Note 或 lab

- [ ] 决定是否把 M00-N01 的 self-contained TeX preamble 抽成公共 template
  - Why: 第一篇 Note 已经实际验证所需环境；避免在没有实践前冻结模板
  - Input: v0.1 编译与阅读反馈
  - Output: reusable template if worthwhile

- [ ] 设计 M00 正式 Module 文件
  - Why: 第一篇 Note 已经反向提供更真实的模块粒度信息
  - Input: `M00-N01` 首轮反馈、`MODULE_MAP.md`、`MODULE_TEMPLATE.md`
  - Output: M00 big picture、Note 列表、库阅读、习题、coding 与 exit criteria

- [ ] 规划 MeshAudit 的实现落点
  - Why: v0.1 已把它作为第一个 library candidate；需决定是先做课程练习还是直接形成可复用代码
  - Input: 用户对编码任务的反馈、未来 Mesh Algorithm Library 组织方式

### TODO — near term

- [ ] 建立首个习题 / coding session（若 M00-N01 反馈表明需要）
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
