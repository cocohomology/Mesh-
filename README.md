# Mesh 深度学习课程

本仓库用于承载一门长期推进、数学结构驱动、与网格算法工程实践紧密耦合的 Mesh 深度学习课程。

本仓库的首要目标不是保存零散笔记，而是建立一套**可持续推进、可跨聊天接手、可动态修正、可追踪决策**的课程系统。任何新的 ChatGPT 会话在没有历史聊天上下文的情况下，只要阅读本仓库，就应该能够快速恢复：

- 课程为什么存在；
- 当前如何推进；
- 已经学到哪里；
- 哪些内容仍有争议；
- 用户与助手各自承担什么角色；
- Note 如何写、如何改、如何验收；
- 文献如何请求、收集、登记；
- 工程练习如何沉淀为长期算法库；
- 一个新会话该从哪里接手。

当前课程基础设施与第一版正式模块图已经建立，尚未开始第一篇正式教学 Note。

---

## 1. 仓库结构

```text
Mesh-/
├─ README.md
├─ governance/
│  ├─ COURSE_PROTOCOL.md        # 课程推进总协议
│  ├─ HANDOFF.md                # 跨聊天接手协议
│  ├─ PROGRESS.md               # 当前进度、下一步、阻塞项
│  ├─ DECISIONS.md              # 关键课程设计决策日志
│  ├─ FEEDBACK_LOOP.md          # 用户反馈与课程调整机制
│  └─ TASKS.md                  # 当前任务池与状态
├─ syllabus/
│  ├─ PHILOSOPHY.md             # 课程理念、目标、边界
│  ├─ OUTLINE.md                # 动态大纲规则
│  ├─ MODULE_MAP.md             # v0.1 正式课程模块图
│  ├─ ENGINEERING_TRACK.md      # 工程学习与 Mesh Algorithm Library 路线
│  └─ MODULE_TEMPLATE.md        # 模块设计模板
├─ notes/
│  ├─ README.md                 # 教学 Note 系统规范
│  └─ TEX_CONVENTIONS.md        # 用户批注、助手回应、版本标记规范
├─ refs/
│  ├─ README.md                 # 文献与资料系统规范
│  ├─ BOOKLIST.md               # 初版书籍/讲义/论文地图
│  └─ LIBRARIES.md              # 成熟 mesh / geometry library 学习索引
└─ discussions/
   └─ README.md                 # 重要讨论、未决问题与思想碎片归档规范
```

---

## 2. 新聊天如何接手

任何新会话在开始课程工作前，按以下顺序阅读：

1. `README.md`
2. `governance/HANDOFF.md`
3. `governance/PROGRESS.md`
4. `governance/DECISIONS.md`
5. 与当前任务相关的 `syllabus/`、`notes/`、`refs/` 文件

如果只允许极短时间恢复上下文，至少读取 `HANDOFF.md + PROGRESS.md`。

完成一次有实质进展的课程工作后，必须更新：

- `governance/PROGRESS.md`
- 必要时更新 `governance/DECISIONS.md`
- 如有新增或改变任务，更新 `governance/TASKS.md`
- 如改变课程理念或大纲，更新 `syllabus/`

**禁止只在聊天里形成关键结论而不写回仓库。**

---

## 3. 当前课程架构

课程采用三层结构：

### Core mathematical / algorithmic spine

以拓扑、几何、分析、离散表示、计算几何、鲁棒性等结构为骨架，经典网格算法作为这些结构的计算化身。

### Engineering track

成熟库阅读、数据结构、实现、测试、性能、数值与组合鲁棒性贯穿整个课程，并逐步形成 Mesh Algorithm Library。

### Frontier tracks

快速发展的 geometric learning、differentiable geometry、implicit/neural representations、3D/4D Gaussian Splatting、Physical AI 等先作为动态支线；只有当其长期价值和结构联系足够明确时才升级为主线。

正式模块依赖见 `syllabus/MODULE_MAP.md`。

---

## 4. 课程推进的基本单位

课程不是按“聊天次数”推进，而按以下产出推进：

- **Module**：一个相对完整的主题单元；
- **Note**：可独立阅读、可版本迭代的教学讲义；
- **Side-note**：服务拓展视野但不阻塞主线；
- **Discussion**：对关键问题的深入讨论与未决结论；
- **Exercise / Exercise Session**：推导、证明、手算、反例与习题课；
- **Experiment / Coding**：数值实验、算法复现、library candidate；
- **Library Study**：成熟库的设计和源码阅读。

Note 是知识沉淀主体，Discussion 是思想探索区，Progress 是课程状态的唯一权威入口。

---

## 5. 用户与助手的角色

### 助手

负责：

- 维护课程整体结构；
- 设计教学顺序；
- 解释、推导、组织数学与算法；
- 主动指出概念断裂、隐藏假设与理论边界；
- 将算法连接到背后的数学结构；
- 选择并阅读合适的成熟库与参考资料；
- 根据反馈修改课程；
- 维护本仓库文档，使课程可跨会话接续。

### 用户

负责：

- 阅读与质疑；
- 在 Note 中补充自己的数学直觉、工程经验、推导和疑问；
- 完成必要的推导、练习、代码实验；
- 对 Note 的风格、深度、节奏和大纲方向进行反馈；
- 在助手提出文献需求时协助提供论文、书籍或资料。

课程不是单向讲授，而是持续共同建模。

---

## 6. 核心运行原则

1. **数学结构优先于算法目录。**
2. **算法必须追问其结构来源、假设与失效机制。**
3. **理论与工程必须持续耦合，不能把工程放到课程结尾。**
4. **不以“会实现”作为掌握标准，也不把纯推理当作课程终点。**
5. **成熟库本身就是课程材料。**
6. **新技术允许进入，但必须区分长期结构价值与短期热点。**
7. **任何重要反馈都可能改变课程顺序与模块边界。**
8. **Note 追求教学性，并通过用户批注—助手回应反复迭代。**
9. **编码练习应尽可能积累为长期资产，而非一次性 demo。**
10. **仓库记录高于聊天上下文。**

---

## 7. 当前阶段

第一版正式模块图 v0.1 已建立。

当前推荐入口是：

`M00 — What is a mesh? Representation, incidence and data structures`

之后将进入 topology、piecewise-linear metric geometry，并把 Delaunay/Voronoi 作为早期第一个完整的“结构—定理—算法—失效—实现”案例。

下一步入口见：`governance/PROGRESS.md`。
