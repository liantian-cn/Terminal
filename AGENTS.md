# Terminal 工作指引

这是 `Terminal/` 的独立开发入口，只处理 Python 解析端这一侧。

## 必读文档

1. `./.context/README.md`
2. `./.context/01_shared_protocol.md`
3. `./.context/03_color_conventions.md`
4. `./.context/20_terminal_scope.md`

## 开发边界

- 如果只是协议、颜色、矩阵语义要改，先改 `Terminal/.context/` 里的协议文档，再决定是否继续动代码

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
