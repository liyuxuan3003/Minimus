# minimus-reference

交叉引用宏包，提供中文格式的智能引用（`cleveref`）。

## 引入的宏包

### `hyperref`

超链接支持。

| 宏包 | 说明 |
|------|------|
| `hyperref` | 提供`\ref`、`\cite`的超链接跳转，预配置`hidelinks`（隐藏链接边框） |

### `aliascnt`

计数器别名。

| 宏包 | 说明 |
|------|------|
| `aliascnt` | 与minimus-colorbox配合使用，确保定理类盒子的引用格式正确 |

### `cleveref`

智能引用。

| 宏包 | 说明 |
|------|------|
| `cleveref` | 提供`\cref`和`\Cref`命令，自动添加引用类型前缀（如图、表、节等） |

依赖`etoolbox`和`xparse`作为基础工具。

## 自定义命令

minimus-reference不定义新的用户命令，而是预配置`\cref`和`\Cref`的中文引用格式。加载本包后`\cref`和`\Cref`会自动使用中文标签。同时定义了中文环境下的引用连接词。

### `\cref`、`\Cref`

智能引用命令（由`cleveref`提供，minimus-reference预配置中文格式）。

| 命令 | 说明 |
|------|------|
| `\cref{label1,label2,...}` | 智能引用，自动添加类型前缀 |
| `\Cref{label1,label2,...}` | 同上，首字母大写（中文环境下与`\cref`效果相同） |

中文引用格式：

| 引用类型 | 格式 | 示例 |
|----------|------|------|
| `part` | 第X部分 | 第I部分至第III部分 |
| `chapter` | 第X章 | 第1章至第3章 |
| `section` | 第X节 | 第1.1节 |
| `subsection` | 第X小节 | 第1.1、1.2和1.3小节 |
| `appendix` | 附录X | 附录A |
| `figure` | 图X | 图1.1-1.3 |
| `table` | 表X | 表1.1 |
| `equation` | 式(X) | 式(1.1) |
| `listing` | 代码X | 代码1.1 |
| `boxdefinition` | 定义X | 定义1.1 |
| `boxtheorem` | 定理X | 定理1.1、1.2和1.3 |

多引用分隔符（仅中文环境）：

| 场景 | 分隔符 | 示例 |
|------|--------|------|
| 两个引用 | 和 | 图1.1和图1.2 |
| 三个及以上 | 、 | 图1.1、1.2和1.3 |
| 范围 | 至 | 图1.1至1.3 |

```latex
\cref{sec:intro}                    % Section 1.1
\cref{fig:a,fig:b}                  % Figure 1.1 and 1.2
\cref{fig:a,fig:b,fig:c}            % Figure 1.1, 1.2 and 1.3
\cref{tab:a,tab:d}                  % Table 1.1 to Table 1.4
```

beamer文档类中`\cref`的超链接仅指向第一个引用目标（技术限制的折中方案）。
