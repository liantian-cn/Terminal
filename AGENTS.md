# Terminal 工作指引

这是 `Terminal/` 的独立开发入口，只处理 Python 解析端这一侧。

## 先读

1. `./.context/README.md`
2. `./.context/20_terminal_scope.md`
3. `./.context/22_terminal_dev_rules.md`

## 按任务路由补读

- 看项目现状、模块总览、主流程顺序：
  - `./.context/00_project_overview.md`
- 改矩阵协议、Cell 语义、解码输出结构、`decoded_data`：
  - `./.context/01_shared_protocol.md`
- 改截图到发键的执行顺序、线程关系、worker 协作、丢帧策略、热重载：
  - `./.context/02_runtime_pipeline.md`
- 改颜色、脚标类型、锚点颜色、颜色分类：
  - `./.context/03_color_conventions.md`
- 判断改动应该落在哪个包，或要不要跨层：
  - `./.context/21_terminal_architecture.md`

## 模块路由

- `capture/`、显示器、截图、矩阵定位：
  - `01_shared_protocol.md`
  - `02_runtime_pipeline.md`
  - `21_terminal_architecture.md`
- `pixelcalc/`、矩阵切块、颜色、标题识别、提取结构：
  - `00_project_overview.md`
  - `01_shared_protocol.md`
  - `03_color_conventions.md`
  - `21_terminal_architecture.md`
- `context/`、`rotation/`、按键发送：
  - `00_project_overview.md`
  - `01_shared_protocol.md`
  - `02_runtime_pipeline.md`
  - `21_terminal_architecture.md`
- `ui/`、`workers/`、开始停止、日志、线程调度：
  - `02_runtime_pipeline.md`
  - `21_terminal_architecture.md`
- `notes/`：
  - `22_terminal_dev_rules.md`
  - 只把它当实验区，不当正式实现来源

## 开发边界

- 如果只是协议、颜色、矩阵语义、线程链路要改，先改 `Terminal/.context/` 里的文档，再决定是否继续动代码。

## 开发规则

- Git 永远工作在小写的 `draft` 分支；如果不在 `draft`，先切过去
- 任何修改文件前，先提交一次 `backup`
- 修改完成后，再提交一次这次改动的简要信息
- 不主动“优化”用户代码；只有用户明确要求，或用户先指出实际异常，才处理
- 处理异常时，只改异常相关部分，不顺手扩散修改
- 补注释时，不要强行套主流规范；函数中间注释和行尾注释都允许
- 不要顺手帮用户做额外操作，除非用户明确要求
- Python 命令统一用 `uv run`
- 修改前先看 `git status --short`；无论是否脏工作区，都先按项目规则提交一次 `backup`
