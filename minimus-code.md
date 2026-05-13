# minimus-code

代码与算法排版宏包，提供伪代码、代码清单和内联代码支持。

## 引入的宏包

### `algorithm2e`

伪代码排版。

| 宏包 | 说明 |
|------|------|
| `algorithm2e` | 提供`algorithm`环境和丰富的伪代码排版命令 |

预配置（`\PassOptionsToPackage`等）：

| 选项 | 说明 |
|------|------|
| `tworuled` | 双线标题 |
| `linesnumbered` | 显示行号 |
| `rightnl` | 注释右对齐 |
| `\DontPrintSemicolon` | 不显示行末分号 |
| `\SetKwProg{Function}{function}{}{end}` | 定义`\Function`块命令 |
| `\SetCommentSty{textrm}` | 定义注释格式 |

### `listings`

源代码清单排版。

| 宏包 | 说明 |
|------|------|
| `listings` | 提供`\lstinputlisting`、`\lstinline`命令和`lstlisting`环境 |

预配置的`\lstset`：

| 选项 | 说明 |
|------|------|
| `basicstyle=\ttfamily` | 等宽字体 |
| `numbers=left` | 左侧行号 |
| `captionpos=t` | 顶置标题 |
| `frame=lrtb` | 四周框线 |
| `breaklines=true` | 自动换行 |
| `tabsize=4` | 制表符宽度 |

预定义的listings样式：

| 样式 | 语言 |
|------|------|
| `bash` | Shell |
| `c` | C |
| `cpp` | C++ |
| `python` | Python |
| `scala` | Scala |
| `verilog` | Verilog |
| `riscv` | RISC-V汇编 |
| `latex` | LaTeX |
| `plain` | 纯文本 |

## 自定义命令

### `\code`

行内代码命令。对`\lstinline`的包装，自动在前后添加`$\hphantom{}$`以保持中文环境下的间距。

| 命令 | 说明 |
|------|------|
| `\code{text}` | 行内代码，内容中`%`和`\`需转义 |

## 自定义环境

### `Algoplain`

固定位置的伪代码环境。

```latex
\begin{Algoplain}
    ...
\end{Algoplain}
```

等价于`\begin{algorithm}[H]...\end{algorithm}`，伪代码始终固定在当前位置。

| 环境 | 说明 |
|------|------|
| `Algoplain` | 固定位置的`algorithm`环境（`[H]`模式） |

### `Code`

带标题的代码清单环境。

```latex
\begin{Code}*[caption;label]{style}
    ...
\end{Code}
```

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 清单不编号 |
| 2 | `[caption;label]` | 可选 | 标题和标签，格式为`code:label` |
| 3 | `{style}` | 可选 | listings样式名称，默认`plain` |

`[caption;label]`有几种用法
- `[caption]`，标题为`caption`，标签为`caption`。
- `[caption;]`，标题为`caption`，无标签。
- `[;label]`，无标题，标签为`label`。
- `[caption;label]`，标题为`caption`，标签为`label`。
- 在带`*`时，由于已经禁止编号，此时不会创建标签。

```latex
\begin{Code}[Python Example;py-example]{python}
    \lstinputlisting{script.py}
\end{Code}
```
