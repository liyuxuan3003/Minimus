# minimus-code

代码与算法排版宏包，提供伪代码、代码清单和内联代码支持。

## 引入的宏包

### `algorithm2e`

伪代码排版。

| 宏包 | 说明 |
|------|------|
| `algorithm2e` | 提供`algorithm`环境和丰富的伪代码排版命令，预配置`tworuled`（双线标题）、`linesnumbered`（行号）、`rightnl`（注释右对齐），默认不显示行末分号 |

预定义了`\Function`块命令（`\SetKwProg`）：

```latex
\Function{name}{params}{
  body
}
```

### `listings`

源代码清单排版。

| 宏包 | 说明 |
|------|------|
| `listings` | 提供`\lstinputlisting`、`\lstinline`命令和`lstlisting`环境 |

预配置的全局`\lstset`：

- 基础样式：`\ttfamily`字体，左侧行号，顶置标题，四周框线
- 自动换行：`breaklines=true`
- 制表符宽度：`tabsize=4`

预定义了的listings语言样式：`bash`、`c`、`cpp`、`python`、`scala`、`verilog`、`riscv`、`latex`、`plain`。



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
| 2 | `[caption;label]` | 可选 | 标题和标签（分号分割），标签自动补全为`code:label` |
| 3 | `{style}` | 可选 | listings样式名称，默认`plain` |

```latex
\begin{Code}[Python Example;py-example]{python}
  \lstinputlisting{script.py}
\end{Code}
```
