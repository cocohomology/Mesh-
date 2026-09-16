# Feedback Loop

## Purpose

课程质量依赖持续反馈，而不是一次性设计。反馈既可以来自用户主观感受，也可以来自推导困难、代码实验、概念冲突、工程案例和文献阅读。

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
- 像速记而不像讲义；
- 图示不足；
- 公式符号不稳定。

处理方式：直接修改 Note 写作规范或已有 Note。

### 4. Understanding feedback

例：
- 用户能复述但不能解释；
- 能推公式但看不到结构；
- 理论懂了但不会判断算法失效。

处理方式：增加反例、等价刻画、实验、对比问题或重新组织教学路径。

### 5. Research feedback

例：
- 一个问题超出教材范围；
- 某个失效现象可能值得独立研究；
- 文献给出相互冲突的框架。

处理方式：写入 `discussions/`，必要时建立独立研究任务，不强行塞入主 Note。

## Feedback processing rule

收到重要反馈后，不应只在聊天中回应。助手需要判断它属于：

- `local`：只影响当前解释；
- `note-level`：需要改 Note；
- `module-level`：需要改模块；
- `course-level`：需要改课程理念或大纲。

其中 module-level 与 course-level 反馈必须写回仓库。

## Preserve disagreement

用户与助手意见不一致时，不以“统一答案”为目标。若争议本身有价值，应记录：

- 双方观点；
- 各自依据；
- 尚缺什么证据；
- 后续何时重新判断。

课程允许长期存在开放分歧。
