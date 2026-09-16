# Handoff Protocol

## 目的

让任何新的聊天窗口、任何没有历史上下文的助手，都能快速接手课程，而不依赖用户重复说明。

## 必读顺序

接手时依次阅读：

1. `README.md`
2. `governance/PROGRESS.md`
3. `governance/DECISIONS.md`
4. `governance/TASKS.md`
5. 当前模块对应的 `syllabus/`、`notes/`、`discussions/`、`refs/` 文件

如果时间极少，优先读 `PROGRESS.md`。

## 接手后必须回答的五个问题

在开始新工作前，助手必须能够明确：

1. 当前课程处于哪个阶段？
2. 当前正在推进哪个模块或问题？
3. 上一次已经形成哪些确定结论？
4. 还有哪些开放问题或用户反馈未处理？
5. 下一步最小但有效的动作是什么？

若任一问题无法回答，应先补读仓库，而不是向用户重复询问已记录的信息。

## 每次课程结束后的交接动作

至少更新：

- `PROGRESS.md`：当前状态、完成内容、下一步；
- `TASKS.md`：新增、关闭或重排任务；
- `DECISIONS.md`：仅记录会影响未来理解或路线的关键决策。

按需更新：

- `OUTLINE.md`：课程结构变化；
- `notes/`：成熟教学内容；
- `discussions/`：仍在探索的重要讨论；
- `refs/`：新增资料或资料需求。

## 交接摘要模板

每次重大推进后，可在 `PROGRESS.md` 中按以下格式维护：

```markdown
### Current focus
...

### What is now settled
- ...

### What remains open
- ...

### User feedback to preserve
- ...

### Next recommended action
...
```

## 禁止事项

- 不要把关键路线只保存在聊天上下文；
- 不要假设新会话知道用户此前说过什么；
- 不要因历史上下文缺失而重做已经完成的工作；
- 不要在未检查 `DECISIONS.md` 前随意推翻课程原则；
- 不要为了保持旧大纲而忽视新的高质量反馈。
