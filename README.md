# Minimus

Minimus是个人在长期LaTeX写作中整理出的一套宏包，包含许多自定义命令和环境，并集成了众多常用宏包。

Minimus的名称来源于坎巴拉太空计划（Kerbal Space Program）中对应现实中地球的Kerbin的第二卫星Minmus的错拼。

## 核心思想

- **固化宏包**——一套`\usepackage`替代散装配置，开箱即用
- **引用集成**——`;label`语法统一挂在命令/环境上，配合`cleveref`中文格式与`gbt7714`国标，引用无痛点
- **环境包装**——封装原生环境，解决长表格对齐、浮动控制、公式居中、子图编号等底层痛点
- **常用缩写**——高频符号两三个字符搞定（`\R`、`\dx`、`\Sum`），实用优先
- **中文本地化**——定理中文标题、"续表"、代码列表名等，检测中文环境自动切换

## 宏包列表

使用时请遵照以下顺序加载，调换顺序可能导致错误。

| 宏包 | 文档 |
|------|------|
| `minimus-section` | [minimus-section.md](minimus-section.md) |
| `minimus-text` | [minimus-text.md](minimus-text.md) |
| `minimus-math` | [minimus-math.md](minimus-math.md) |
| `minimus-float` | [minimus-float.md](minimus-float.md) |
| `minimus-code` | [minimus-code.md](minimus-code.md) |
| `minimus-colorbox` | [minimus-colorbox.md](minimus-colorbox.md) |
| `minimus-reference` | [minimus-reference.md](minimus-reference.md) |
| `minimus-bibtex` | [minimus-bibtex.md](minimus-bibtex.md) |

以下为可选模块，用于独立图件：

| 宏包 | 文档 |
|------|------|
| `minimus-tikz` | [minimus-tikz.md](minimus-tikz.md) |

编写规范见 [Plan.md](Plan.md)。
