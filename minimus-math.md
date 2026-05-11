# minimus-math

数学宏包，提供数学符号、算符、快捷命令和数学排版环境。

## 引入的宏包

### amsmath, amsthm, amssymb

AMS 数学系列宏包。`amsmath` 提供 `align`、`gather`、`split` 等数学环境；`amsthm` 提供定理环境支持；`amssymb` 提供 `\mathbb`、`\mathcal` 等数学字体符号。

方程编号设为按节递增（`\numberwithin{equation}{section}`）。

### siunitx

物理量与单位排版。预配置了二进制前缀（`\kibi`、`\mebi` 等）和对应二进制单位（`\KB`、`\MB`、`\GB`，`\Kb`、`\Mb`，`\Kbps`、`\Mbps` 等）。

`\qty` 系列命令被重命名为 `\qnum` / `\qnumlist` / `\qnumrange` / `\qnumproduct`，以避免与 `physics` 宏包冲突。

| 设置项 | 值 | 说明 |
|--------|-----|------|
| `list-separator` | `{, }` | 列表分隔符 |
| `range-phrase` | `{\,\text{\textasciitilde{}}\,}` | 范围连接符 |
| `group-digits` | `none` | 不分组数字 |
| `inter-unit-product` | `{\cdot}` | 单位间用 `·` 连接 |

### physics

提供 `\vb`（向量）、`\dd`（微分）、`\pdv`（偏导）、`\qty`（括号）等物理排版命令。

### mathtools

`amsmath` 的增强包。提供 `\mathmakebox`（数学盒子宽度控制）、`\mathclap`、`\mathllap`、`\mathrlap` 等。

### mhchem

化学式排版。`\ce{H2O}`、`\ce{^{227}_{90}Th+}` 等。

## 自定义命令

### `\e`、`\i`、`\j`、`\k`

| 命令 | 输出 | 说明 |
|------|------|------|
| `\e` | $\mathrm{e}$ | 自然常数 |
| `\i` | $\mathrm{i}$ | 虚数单位（覆盖了无点 i） |
| `\j` | $\mathrm{j}$ | 虚数单位（物理/工程） |
| `\k` | $\mathrm{k}$ | 四元数虚部 |

### `\N`、`\Z`、`\Q`、`\R`、`\C`

| 命令 | 输出 | 说明 |
|------|------|------|
| `\N` | $\mathbb{N}$ | 自然数集 |
| `\Z` | $\mathbb{Z}$ | 整数集 |
| `\Q` | $\mathbb{Q}$ | 有理数集 |
| `\R` | $\mathbb{R}$ | 实数集 |
| `\C` | $\mathbb{C}$ | 复数集 |

同时重定义了 `\emptyset` 为 `\varnothing`：`∅`。

### `\dx`、`\dy`、`\dz`

| 命令 | 输出 | 说明 |
|------|------|------|
| `\dx` | $\dd{x}$ | 对 x 的微分 |
| `\dy` | $\dd{y}$ | 对 y 的微分 |
| `\dz` | $\dd{z}$ | 对 z 的微分 |

依赖 `physics` 的 `\dd` 命令。

### `\Sum[<下标>][<上标>]`

累加符号 `\sum` 的快捷写法。

| 序号 | 参数 | 类型 | 默认 | 说明 |
|------|------|------|------|------|
| 1 | 下标 | 可选 | 无 | 累加下限 |
| 2 | 上标 | 可选 | 无 | 累加上限 |

```latex
\Sum[i=1][n] a_i      →  \sum_{i=1}^{n} a_i
\Sum a_i               →  \sum a_i
```

同类命令：`\Prod`（连乘）、`\BigCap`（交）、`\BigCup`（并）、`\BigOplus`（直和）、`\BigOdot`、`\BigOtimes`。

### `\Int[<下限>][<上限>]`

积分符号 `\int` 的快捷写法。

| 序号 | 参数 | 类型 | 默认 | 说明 |
|------|------|------|------|------|
| 1 | 下限 | 可选 | 无 | 积分下限 |
| 2 | 上限 | 可选 | 无 | 积分上限 |

同类命令：

| 命令 | 等价 | 说明 |
|------|------|------|
| `\Idnt` | `\iint` | 二重积分 |
| `\Itnt` | `\iiint` | 三重积分 |
| `\Ilnt` | `\int` | 线积分 |
| `\Ilot` | `\oint` | 闭合线积分 |
| `\Isnt` | `\iint` | 面积分 |
| `\Isot` | `\oiint` | 闭合面积分 |

### `\Lim[<条件>][<趋近>]`

极限符号 `\lim` 的快捷写法。

| 序号 | 参数 | 类型 | 默认 | 说明 |
|------|------|------|------|------|
| 1 | 条件 | 可选 | 无 | 极限条件 |
| 2 | 趋近 | 可选 | 无 | 趋近目标（自动添加 `\to`） |

```latex
\Lim[n][\infty] a_n   →  \lim_{n\to\infty} a_n
\Lim[x\to 0] f(x)     →  \lim_{x\to 0} f(x)
```

### `\Grad`、`\Div`、`\Curl`

| 命令 | 输出 | 说明 |
|------|------|------|
| `\Grad f` | grad $f$ | 梯度 |
| `\Div F` | div $F$ | 散度 |
| `\Curl F` | curl $F$ | 旋度 |

### `\FT`、`\LT`

| 命令 | 输出 | 说明 |
|------|------|------|
| `\FT{x}` | $\mathcal{F}\{x\}$ | 傅里叶变换 |
| `\FT*{x}` | $\mathcal{F}^{-1}\{x\}$ | 逆傅里叶变换 |
| `\LT{x}` | $\mathcal{L}\{x\}$ | 拉普拉斯变换 |
| `\LT*{x}` | $\mathcal{L}^{-1}\{x\}$ | 逆拉普拉斯变换 |

### `\anglebkt*{<内容>}` / `\floor*{<内容>}` / `\ceil*{<内容>}`

自适应大小括号。带 `*` 时自动缩放，不带 `*` 时固定尺寸。

| 命令 | 不带 `*` | 带 `*` |
|------|----------|--------|
| `\anglebkt{x}` | $\langle x\rangle$ | $\left\langle x\right\rangle$ |
| `\floor{x}` | $\lfloor x\rfloor$ | $\left\lfloor x\right\rfloor$ |
| `\ceil{x}` | $\lceil x\rceil$ | $\left\lceil x\right\rceil$ |

## 自定义环境

### Equation — 单行公式

```latex
\begin{Equation}*[label]!!
  ...
\end{Equation}
```

| 序号 | 参数 | 类型 | 默认 | 说明 |
|------|------|------|------|------|
| 1 | `*` | 可选标记 | 无 | 公式不编号 |
| 2 | `label` | 可选 | 无 | 标签（自动补全为 `eq:label`） |
| 3 | `!` | 可选标记 | 无 | 强制公式零宽居中 |
| 4 | `!` | 可选标记 | 无 | 强制公式行宽居中（两个 `!` 写成 `!!`） |

```latex
% 基本用法：编号 + 标签
\begin{Equation}[einstein]
  E = mc^2
\end{Equation}

% 不编号
\begin{Equation}*
  ax^2 + bx + c = 0
\end{Equation}
```

### Split — 多行对齐公式

对 `equation` + `aligned` 的包装，支持用 `&` 对齐。

```latex
\begin{Split}*[label]{factor}!!
  f(x) &= x^2 + y^2 \\
       &+ \alpha + \beta + \gamma
\end{Split}
```

| 序号 | 参数 | 类型 | 默认 | 说明 |
|------|------|------|------|------|
| 1 | `*` | 可选标记 | 无 | 公式不编号 |
| 2 | `label` | 可选 | 无 | 标签（自动补全为 `eq:label`） |
| 3 | `factor` | 可选 | `1.0` | 行间距缩放因子（`\jot` 倍数） |
| 4 | `!` | 可选标记 | 无 | 强制零宽居中 |
| 5 | `!` | 可选标记 | 无 | 强制行宽居中（`!!`） |

### Align — 公式组对齐

对 `align` 的包装，每行可独立编号（通过快捷键 `\id`）。

```latex
\begin{Align}*[prefix]{factor}
  f(x) &= x^2 + y^2 \id{a} \\
  g(x) &= \alpha + \beta \id{b}
\end{Align}
```

| 序号 | 参数 | 类型 | 默认 | 说明 |
|------|------|------|------|------|
| 1 | `*` | 可选标记 | 无 | 公式不编号 |
| 2 | `prefix` | 可选 | 无 | 标签前缀（`\id{a}` → `eq:prefixa`） |
| 3 | `factor` | 可选 | `1.0` | 行间距缩放因子 |

同类环境：`Gather`（居中对齐公式组）、`Multline`（阶梯排列长公式）。
