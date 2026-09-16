# Feedback Loop

## Purpose

课程质量依赖持续反馈，而不是一次性设计。反馈既可以来自用户主观感受，也可以来自推导困难、代码实验、概念冲突、工程案例、习题、文献阅读和 Note 批注。

## Feedback categories

### 1. Depth feedback

例：
- 太浅，只停留在公式；
- 证明过度展开，主线丢失；
- 某个数学结构值得更深挖。

处理方式：调整 Note 深度、拆分侧路或补充前置内容。

### 2. Structure feedback

例：
- 某个主题出现太早；
- 两个模块其实应合并；
- 一个工程问题暴露了缺失的数学层。

处理方式：更新 `OUTLINE.md`，重大变化写入 `DECISIONS.md`。

### 3. Style feedback

例：
- 语言太碎；
- 像速记或论文摘要而不像讲义；
- 图示不足；
- 缺少手算例子；
- 公式符号不稳定；
- motivation / taste 太弱。

处理方式：直接修改 Note 写作规范或已有 Note，并优先补充教学层次而不是只扩写形式内容。

### 4. Understanding feedback

例：
- 用户能复述但不能解释；
- 能推公式但看不到结构；
- 理论懂了但不会判断算法失效；
- 能看懂算法但不能在小例子上手算；
- 代码能跑但解释不了结果。

处理方式：增加反例、图、等价刻画、worked example、习题、实验、编码任务或重新组织教学路径。

### 5. Perspective feedback

例：
- 主线清楚，但视野过窄；
- 某个概念与其他数学理论有明显联系；
- 某种算法在不同工业领域有重要用途；
- 某段历史 / 行业背景有助于理解为什么问题会如此发展。

处理方式：增加 side note、历史背景、应用地图；若内容足够大，则建立支线 Note。

### 6. Research feedback

例：
- 一个问题超出教材范围；
- 某个失效现象可能值得独立研究；
- 文献给出相互冲突的框架。

处理方式：写入 `discussions/`，必要时建立独立研究任务，不强行塞入主 Note。

### 7. Exercise feedback

习题本身也必须接受反馈：

- 是否真的迫使思考，而非机械代公式；
- 是否帮助暴露误解；
- 是否连接正文中的核心结构；
- 编码题是否可以沉淀为算法库组件；
- 是否值得组织习题课。

低价值习题可以直接删除，不追求题量。

## Note review loop

正式教学 Note 使用如下闭环：

1. 助手提交一个完整教学版本；
2. 用户阅读时保留原文，并使用 `notes/TEX_CONVENTIONS.md` 中规定的 `studentthought` 环境加入自己的思考、质疑、推导或联想；
3. 用户提交 Git；
4. 助手读取整篇更新后的 Note；
5. 助手使用 `assistantresponse` 回应对话性问题，并使用 `versionaddition` 增补正式讲义；
6. 必要时补图、worked example、习题、支线入口或代码任务；
7. 升级 Note 版本号并填写 revision history；
8. 判断反馈是否影响 module / syllabus / reference / task / algorithm library；
9. 若仍有关键未解决问题，则继续下一轮；否则 Note 可阶段收束并进入下一篇。

这一过程默认是**非破坏式**的：用户不删除原文，助手不抹去用户思考。学习过程本身是正式资料。

## Feedback processing rule

收到重要反馈后，不应只在聊天中回应。助手需要判断它属于：

- `local`：只影响当前解释；
- `note-level`：需要改 Note；
- `module-level`：需要改模块；
- `course-level`：需要改课程理念或大纲；
- `library-level`：形成可复用算法 / 数据结构 / 测试任务。

其中 module-level、course-level 和 library-level 反馈必须写回仓库。

## Preserve disagreement

用户与助手意见不一致时，不以“统一答案”为目标。若争议本身有价值，应记录：

- 双方观点；
- 各自依据；
- 尚缺什么证据；
- 是否可通过手算、实验、编码或文献判断；
- 后续何时重新判断。

课程允许长期存在开放分歧。
