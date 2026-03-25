# Terminal 范围

`Terminal` 是游戏外的解析与执行端。

## 当前目标

- 找到 `DejaVu` 输出的矩阵区域
- 抓取矩阵图像
- 把图像还原成矩阵与像素块
- 识别图标、颜色、文字和标记区
- 输出结构化状态供后续策略层使用

## 当前已知技术

- GUI: PySide6
- 抓图: `mss`
- 矩阵处理: `numpy`
- 图标哈希: `xxhash`
- 相似图标识别: OpenCV

## 本轮非目标

- 不在这里细化完整 GUI 布局
- 不定义完整策略脚本语言
- 不定义完整按键发送系统实现
- 不顺手修改 `DejaVu` 代码

## 对 agent 的要求

- 进入 `Terminal` 任务后，只开发 `Terminal/`
- 共享协议问题回到当前目录的 `01_shared_protocol.md` 与 `03_color_conventions.md`
- 如果发现必须改 `DejaVu` 才能继续，先停下并要求拆任务
