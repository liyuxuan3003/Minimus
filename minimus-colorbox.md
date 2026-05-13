# minimus-colorbox

彩色定理盒子宏包，提供定理、示例、日语对照、证明等带框环境。

## 引入的宏包

### `amsthm`

AMS定理环境。

| 宏包 | 说明 |
|------|------|
| `amsthm` | 提供`\newtheorem`命令，`Proof`和`Solution`环境的底层`proof`环境来源 |

### `aliascnt`

计数器别名。

| 宏包 | 说明 |
|------|------|
| `aliascnt` | 提供`\newaliascnt`命令，使相关定理类型共享同一计数器 |

### `tcolorbox`

带框文本框。

| 宏包 | 说明 |
|------|------|
| `tcolorbox` | 提供`\NewTcbTheorem`、`\NewTColorBox`等命令，预加载`breakable`（跨页分割）和`theorems`（定理支持）库 |

全局`\tcbset`预配置：

- 圆角`0.1mm`，浅灰背景，左边距`0.2cm`
- 标题加粗正体，标题上下间距`0.05cm`
- 允许跨页分割（`breakable`）
- 定理标题分隔符为空格

各类型盒子的配色：

| 类型 | 配色样式 | 边框颜色 |
|------|----------|----------|
| 定义类（`boxdefstyle`） | 绿灰色 |
| 定理类（`boxthmstyle`） | 蓝灰色 |
| 示例类（`boxexpstyle`） | 青色 |
| 文本类（`boxtxtstyle`） | 红色 |
| 日语例句（`boxjpsetstyle`） | 蓝色，圆角`1.0mm` |
| 日语对话（`boxjpcovstyle`） | 绿色，圆角`1.0mm` |



## 自定义环境

以下定理类环境均支持`*`（禁止编号）和`[title;label]`（标题与标签，分号分割，标签自动带前缀）。`BoxDesignPrinciple`不支持`*`。

### `BoxDefinition`、`BoxTheorem`、`BoxLemma`、`BoxCorollary`、`BoxProposition`、`BoxProperty`、`BoxFormula`、`BoxEquation`

定理类盒子。分别对应：定义、定理、引理、推论、命题、性质、公式、方程。

```latex
\begin{BoxDefinition}*[title;label]
    ...
\end{BoxDefinition}
```

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 不编号 |
| 2 | `[title;label]` | 可选 | 标题和标签（分号分割），标签自动补全为`def:label`、`thm:label`等 |

所有定理类盒子共享同一参数格式，标签前缀如下：

| 环境 | 标签前缀 | 计数器 |
|------|----------|--------|
| `BoxDefinition` | `def:label` | `boxdefinition` |
| `BoxTheorem` | `thm:label` | `boxtheorem` |
| `BoxLemma` | `lem:label` | `boxlemma` |
| `BoxCorollary` | `col:label` | `boxcorollary` |
| `BoxProposition` | `pps:label` | `boxproposition` |
| `BoxProperty` | `ppt:label` | `boxproperty` |
| `BoxFormula` | `fml:label` | `boxformula` |
| `BoxEquation` | `eqt:label` | `boxequation` |

### `BoxExample`

示例盒子。

| 标签前缀 | 计数器 |
|----------|--------|
| `exp:label` | `boxexample` |

### `BoxAlgorithm`、`BoxProcess`

算法和流程盒子。

| 环境 | 标签前缀 | 计数器 |
|------|----------|--------|
| `BoxAlgorithm` | `alg:label` | `boxalgorithm` |
| `BoxProcess` | `pro:label` | `boxprocess` |

### `BoxDesignPrinciple`

设计原则盒子。无`*`标记，始终编号。

| 标签前缀 | 计数器 |
|----------|--------|
| `despri:label` | `boxdesignprinciple` |

### `JPSentence`、`JPConversation`

日语对照环境。内容写入后，可选的中文翻译以`\tcblower`分割出现在盒子下方。

```latex
\begin{JPSentence}{translation}
    japanese text
\end{JPSentence}
```

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `{translation}` | 可选 | 中文翻译，出现在`\tcblower`之后 |

### `Proof`、`Solution`

证明与解答环境。

```latex
\begin{Proof}[reference]
    ...
\end{Proof}
```

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `[reference]` | 可选 | 引用目标（如`\cref{thm:test}`），默认无 |

```latex
\begin{Proof}[\cref{thm:main}]
    ...
\end{Proof}
```

标题分别为"证明"和"解"，末尾有水平分割线。
