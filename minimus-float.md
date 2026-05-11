# minimus-float

图表排版宏包，提供表格和图片环境，支持长表格、子图、标签。

## 引入的宏包

### `float`

浮动体位置控制。

| 宏包 | 说明 |
|------|------|
| `float` | 提供`[H]`位置参数，禁止浮动体浮动 |

### `caption`、`subcaption`

标题与子标题。

| 宏包 | 说明 |
|------|------|
| `caption` | 提供`\caption`、`\captionof`命令，预配置表格和图片的标题间距 |
| `subcaption` | 提供`\subcaptionbox`命令，预配置子图编号格式为`(a)` |

### `tabularray`

现代表格排版。

| 宏包 | 说明 |
|------|------|
| `tabularray` | 提供`tblr`环境，是`Table`环境的基础表格引擎 |

### `multirow`

跨行合并单元格。

| 宏包 | 说明 |
|------|------|
| `multirow` | 提供`\multirow`命令，用于简单场景下的表格跨行 |

### `graphicx`、`pdfpages`

图形插入。

| 宏包 | 说明 |
|------|------|
| `graphicx` | 提供`\includegraphics`命令，支持插入PDF、PNG、JPG等图片 |
| `pdfpages` | 提供`\includepdf`命令，支持插入完整PDF页面 |

依赖`etoolbox`、`xparse`和`semi-split`作为基础工具。依赖`tikz`（已在`minimus-text`中加载）。

## 自定义命令

### `\linenone`、`\linesplit`、`\linemiddle`、`\lineborder`

表格线宽度预设。

| 命令 | 说明 |
|------|------|
| `\linenone` | $0.0\mathrm{pt}$，无宽度线 |
| `\linesplit` | $0.2\mathrm{pt}$，分隔线 |
| `\linemiddle` | $0.4\mathrm{pt}$，中间线 |
| `\lineborder` | $1.0\mathrm{pt}$，边框线 |

### `\figuresub`

子图命令，须在`Figure`环境内使用。

| 命令 | 说明 |
|------|------|
| `\figuresub*[caption;label]{graphics}{width}` | 排版子图，带`*`时不编号 |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 子图不编号 |
| 2 | `[caption;label]` | 可选 | 标题和标签（分号分割），标签自动补全为`fig:label` |
| 3 | `{graphics}` | 必选 | `\includegraphics{...}`命令 |
| 4 | `{width}` | 可选 | 子图宽度（`width\linewidth`），默认自适应 |

```latex
\figuresub[Left;a]{\includegraphics{left.pdf}}{0.45}
\figuresub[Right;b]{\includegraphics{right.pdf}}{0.45}
```

## 自定义环境

### `Table`

表格环境。基于`tblr`，支持短表格和长表格（`!!`）。

```latex
\begin{Table}*[caption;label]&&!!
  ...
\end{Table}
```

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 表格不编号 |
| 2 | `[caption;label]` | 可选 | 标题和标签（分号分割），标签自动补全为`tab:label` |
| 3 | `&` | 标记 | 移除中间线 |
| 4 | `&` | 标记 | 移除边框线 |
| 5 | `!` | 标记 | 启用浮动，使用`[htbp]`而非`[H]` |
| 6 | `!` | 标记 | 启用长表格（两个`!`写成`!!`） |

```latex
\begin{Table}[Table Caption;mytable]!
  \begin{tblr}{colspec={XX},hline{1,Z}={\lineborder},hline{2}={\linemiddle}}
    A & B \\
    C & D \\
  \end{tblr}
\end{Table}
```

Long table example:

```latex
\begin{Table}[Long Table Caption;longtable]!!
  \begin{tblr}{colspec={XXX}}
    A & B & C \\
    D & E & F \\
  \end{tblr}
\end{Table}
```

### `Figure`

图片环境。支持浮动控制和子图。

```latex
\begin{Figure}*[caption;label]!
  ...
\end{Figure}
```

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 图片不编号 |
| 2 | `[caption;label]` | 可选 | 标题和标签（分号分割），标签自动补全为`fig:label` |
| 3 | `!` | 标记 | 启用浮动，使用`[htbp]`而非`[H]` |

```latex
\begin{Figure}[Example Figure;example]!
  \includegraphics{image.pdf}
\end{Figure}
```
