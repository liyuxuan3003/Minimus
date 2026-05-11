# minimus-section

章节命令增强宏包，重定义标准章节命令以支持分号语法自动标签。

## 引入的宏包

### `apptools`

附录检测工具。

| 宏包 | 说明 |
|------|------|
| `apptools` | 提供`\IfAppendix`命令，用于判断当前是否处于附录环境 |

依赖`etoolbox`、`xparse`和`semi-split`作为基础工具。

`semi-split`是Minimus内部工具包，提供分号分割功能（`\SplitArgument{1}{;}`），将`{标题;标签}`分割为标题和标签两部分。

## 自定义命令

minimus-section不定义新的用户命令，而是重定义标准LaTeX章节命令，为它们增加自动标签功能。重定义的命令包括`\part`、`\chapter`、`\section`、`\subsection`、`\subsubsection`。

这些重定义在beamer文档类中不生效。

### `\part`、`\chapter`、`\section`、`\subsection`、`\subsubsection`

标准章节命令的增强版本，支持分号语法自动生成标签。

| 命令 | 说明 |
|------|------|
| `\part*[short]{title;label}!` | 重定义的`\part`，分号后为自动标签 |
| `\chapter*[short]{title;label}!` | 重定义的`\chapter`，分号后为自动标签 |
| `\section*[short]{title;label}!` | 重定义的`\section`，分号后为自动标签 |
| `\subsection*[short]{title;label}!` | 重定义的`\subsection`，分号后为自动标签 |
| `\subsubsection*[short]{title;label}!` | 重定义的`\subsubsection`，分号后为自动标签 |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 禁止编号 |
| 2 | `[short]` | 可选 | 短标题，用于页眉和目录 |
| 3 | `{title;label}` | 必选 | `title`为标题正文，`;label`可选，自动创建`\label` |
| 4 | `!` | 标记 | 控制短标题范围（见下） |

`!`标记控制短标题的使用范围：

- 不带`!`：短标题仅用于PDF书签，页眉和目录仍用完整标题
- 带`!`：短标题同时用于PDF书签、页眉和目录

标签前缀按层次自动分配：

| 命令 | 标签格式 | 示例 |
|------|----------|------|
| `\part{名称;intro}` | `part:intro` | |
| `\chapter{名称;intro}` | `chap:intro`（正文）或`ap:intro`（附录） | |
| `\section{名称;intro}` | `sec:intro` | |
| `\subsection{名称;intro}` | `subsec:intro` | |
| `\subsubsection{名称;intro}` | `subsubsec:intro` | |

```latex
\section{Introduction;intro}

See \cref{sec:intro}.
```

带`*`时不会创建标签。含编号时才创建标签。
