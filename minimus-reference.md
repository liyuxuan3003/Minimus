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
| `aliascnt` | 提供`\newaliascnt`命令，实现计数器别名 |

### `cleveref`

智能引用。

| 宏包 | 说明 |
|------|------|
| `cleveref` | 提供`\cref`和`\Cref`命令，自动添加引用类型前缀 |

加载本包后`\cref`和`\Cref`会自动使用中文格式：

| 引用类型 | 格式 |
|----------|------|
| `part` | 第X部分 |
| `chapter` | 第X章 |
| `section` | 第X节 |
| `subsection` | 第X小节 |
| `subsubsection` | 第X小节 |
| `appendix` | 附录X |
| `figure` | 图X |
| `table` | 表X |
| `equation` | 式(X) |
| `listing` | 代码X |
| `boxdefinition` | 定义X |
| `boxtheorem` | 定理X |
| `boxlemma` | 引理X |
| `boxcorollary` | 推论X |
| `boxproposition` | 命题X |
| `boxproperty` | 性质X |
| `boxformula` | 公式X |
| `boxequation` | 方程X |
| `boxexample` | 例X |
| `boxalgorithm` | 算法X |
| `boxprocess` | 流程X |
| `boxdesignprinciple` | 设计原则X |

beamer文档类中`\cref`的超链接仅指向第一个引用目标（技术限制的折中方案）。
