# Terminal `.context` 入口

这里是 `Terminal/` 这一侧的 AI 专用上下文，不是面向终端用户的说明书。

原则：

- 这里优先写项目边界、模块职责、运行链路、协议定义、开发约束。
- 以当前仓库代码为准；如果代码已经变了，应该在同一任务里补这里。
- 只要改到协议、颜色、矩阵、解码数据结构、线程链路、模块边界，就要同步更新 `.context/`。

建议阅读顺序：

1. `00_project_overview.md`
2. `01_shared_protocol.md`
3. `02_runtime_pipeline.md`
4. `03_color_conventions.md`
5. `20_terminal_scope.md`
6. `21_terminal_architecture.md`
7. `22_terminal_dev_rules.md`

按任务路由补读：

- 看整体定位、模块分层、项目现状：`00_project_overview.md`
- 改矩阵协议、Cell 语义、提取结果结构：`01_shared_protocol.md`
- 改实际执行顺序、线程协作、丢帧/排队策略：`02_runtime_pipeline.md`
- 改颜色分类、锚点颜色、脚标颜色语义：`03_color_conventions.md`
- 判断某个需求是否属于 Terminal 边界：`20_terminal_scope.md`
- 判断某个改动应该落在哪个包：`21_terminal_architecture.md`
- 做具体开发时的仓库内规则：`22_terminal_dev_rules.md`
