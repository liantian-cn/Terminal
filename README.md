# Terminal

该项目是[M.I.D.N.I.G.H.T/](https://github.com/liantian-cn/M.I.D.N.I.G.H.T/)项目的子项目。

接收并解析[DejaVu](https://github.com/liantian-cn/DejaVu)传来的信号，执行超维指令，直接操控游戏世界的生死轮回，执掌无限夜幕的迭代权柄。

## 新坑优势

本项目是[EZWowX2](https://github.com/liantian-cn/EZWowX2)项目的后续新坑，有诸多优势。

- 作者还在维护、更多的手写代码：为了去掉AI屎山，本项目代码手写量>95%，作者维护意愿更强。
- 使用兼容性更好的GDI截图：优化了算法，在Ryzen 9700X下能实现100fps。性能测试见`notes`目录。
- 游戏内设置：动态变量设置由游戏内插件完成。
- 循环热加载：在ide里编辑代码，保存后，rotation会自动重载。

## 使用方式

- 务必从[官网](https://www.python.org/downloads/release/python-31210/)下载python 3.12.10
- 使用`pip install -r requirements.txt`或`uv sync完成依赖安装`
- 执行`clear ; uv run .\main.py`运行程序。

## 循环书写

- 阅读[docs](https://github.com/liantian-cn/Terminal/tree/main/docs/)的文档，书写循环。
- 循环放置于`terminal\rotation`目录。

## 问题提交

-
