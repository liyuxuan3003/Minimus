# minimus-math

数学宏包，提供数学符号、算符、快捷命令和数学排版环境。

## 引入的宏包

### `amsmath`、`amsthm`、`amssymb`

| 宏包 | 说明 |
|------|------|
| `amsmath` | 提供`align`、`gather`、`split`等数学环境 |
| `amsthm` | 提供定理环境支持 |
| `amssymb` | 提供`\mathbb`、`\mathcal`等数学字体符号 |

方程编号设为按节递增（`\numberwithin{equation}{section}`）。

### `siunitx`

`\qty`系列命令被重命名为`\qnum`/`\qnumlist`/`\qnumrange`/`\qnumproduct`，以避免与`physics`宏包冲突。预配置了二进制单位（`\KB`、`\MB`、`\GB`等）。

| 设置项 | 值 | 说明 |
|--------|-----|------|
| `list-separator` | `{, }` | 列表分隔符 |
| `range-phrase` | `{\,\text{\textasciitilde{}}\,}` | 范围连接符 |
| `group-digits` | `none` | 不分组数字 |
| `inter-unit-product` | `{\cdot}` | 单位间用`·`连接 |

### `physics`

提供`\vb`（向量）、`\dd`（微分）、`\pdv`（偏导）、`\qty`（括号）等物理排版命令。

### `mathtools`

`amsmath`的增强包。提供`\mathmakebox`（数学盒子宽度控制）、`\mathclap`、`\mathllap`、`\mathrlap`等。

### `mhchem`

化学式排版，如`\ce{H2O}`、`\ce{^{227}_{90}Th+}`。

## 自定义命令

### `\e`、`\i`、`\j`、`\k`

| 命令 | 说明 |
|------|------|
| `\e` | 自然常数$\mathrm{e}$ |
| `\i` | 虚数单位$\mathrm{i}$，覆盖了无点i |
| `\j` | 虚数单位$\mathrm{j}$（物理/工程） |
| `\k` | 四元数虚部$\mathrm{k}$ |

### `\N`、`\Z`、`\Q`、`\R`、`\C`、`\emptyset`

| 命令 | 说明 |
|------|------|
| `\N` | 自然数集$\mathbb{N}$ |
| `\Z` | 整数集$\mathbb{Z}$ |
| `\Q` | 有理数集$\mathbb{Q}$ |
| `\R` | 实数集$\mathbb{R}$ |
| `\C` | 复数集$\mathbb{C}$ |
| `\emptyset` | 空集，重定义为$\varnothing$ |

### `\dx`、`\dy`、`\dz`

| 命令 | 说明 |
|------|------|
| `\dx` | 对$x$的微分$\dd{x}$ |
| `\dy` | 对$y$的微分$\dd{y}$ |
| `\dz` | 对$z$的微分$\dd{z}$ |

依赖`physics`的`\dd`命令。

### `\Sum`、`\Prod`、`\BigCap`、`\BigCup`、`\BigOplus`、`\BigOdot`、`\BigOtimes`

| 命令 | 说明 |
|------|------|
| `\Sum[下标][上标]` | 累加$\sum$的快捷写法 |
| `\Prod[下标][上标]` | 连乘$\prod$的快捷写法 |
| `\BigCap[下标][上标]` | 交$\bigcap$的快捷写法 |
| `\BigCup[下标][上标]` | 并$\bigcup$的快捷写法 |
| `\BigOplus[下标][上标]` | 直和$\bigoplus$的快捷写法 |
| `\BigOdot[下标][上标]` | $\bigodot$的快捷写法 |
| `\BigOtimes[下标][上标]` | $\bigotimes$的快捷写法 |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `[下标]` | 可选 | 下限，默认无 |
| 2 | `[上标]` | 可选 | 上限，默认无 |

### `\Int`、`\Idnt`、`\Itnt`、`\Ilnt`、`\Ilot`、`\Isnt`、`\Isot`

| 命令 | 说明 |
|------|------|
| `\Int[下限][上限]` | 积分$\int$的快捷写法 |
| `\Idnt[下限][上限]` | 二重积分$\iint$的快捷写法 |
| `\Itnt[下限][上限]` | 三重积分$\iiint$的快捷写法 |
| `\Ilnt[下限][上限]` | 线积分$\int$的快捷写法 |
| `\Ilot[下限][上限]` | 闭合线积分$\oint$的快捷写法 |
| `\Isnt[下限][上限]` | 面积分$\iint$的快捷写法 |
| `\Isot[下限][上限]` | 闭合面积分$\oiint$的快捷写法 |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `[下限]` | 可选 | 积分下限，默认无 |
| 2 | `[上限]` | 可选 | 积分上限，默认无 |

### `\Lim`

| 命令 | 说明 |
|------|------|
| `\Lim[条件][趋近]` | 极限$\lim$的快捷写法，自动在趋近参数前添加`\to` |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `[条件]` | 可选 | 极限条件，默认无 |
| 2 | `[趋近]` | 可选 | 趋近目标，默认无 |

### `\Grad`、`\Div`、`\Curl`

| 命令 | 说明 |
|------|------|
| `\Grad` | 梯度$\operatorname{grad}$ |
| `\Div` | 散度$\operatorname{div}$ |
| `\Curl` | 旋度$\operatorname{curl}$ |

### `\FT`、`\LT`

| 命令 | 说明 |
|------|------|
| `\FT[内容]` | 傅里叶变换$\mathcal{F}\{x\}$ |
| `\FT*[内容]` | 逆傅里叶变换$\mathcal{F}^{-1}\{x\}$ |
| `\LT[内容]` | 拉普拉斯变换$\mathcal{L}\{x\}$ |
| `\LT*[内容]` | 逆拉普拉斯变换$\mathcal{L}^{-1}\{x\}$ |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 取逆变换 |
| 2 | `[内容]` | 可选 | 变换对象 |

### `\anglebkt`、`\floor`、`\ceil`

| 命令 | 说明 |
|------|------|
| `\anglebkt*{内容}` | 尖括号$\langle\rangle$，带`*`时自适应大小 |
| `\floor*{内容}` | 下取整$\lfloor\rfloor$，带`*`时自适应大小 |
| `\ceil*{内容}` | 上取整$\lceil\rceil$，带`*`时自适应大小 |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 自适应大小 |
| 2 | `{内容}` | 必选 | 括号内的内容 |

## 自定义环境

### `Equation`

```latex
\begin{Equation}*[label]!!
  ...
\end{Equation}
```

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 公式不编号 |
| 2 | `[label]` | 可选 | 标签（自动补全为`eq:label`），默认无 |
| 3 | `!` | 标记 | 强制公式零宽居中 |
| 4 | `!` | 标记 | 强制公式行宽居中（两个`!`写成`!!`） |

```latex
\begin{Equation}[einstein]
  E = mc^2
\end{Equation}

\begin{Equation}*
  ax^2 + bx + c = 0
\end{Equation}
```

### `Split`

```latex
\begin{Split}*[label]{factor}!!
  f(x) &= x^2 + y^2 \\
       &+ \alpha + \beta + \gamma
\end{Split}
```

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 公式不编号 |
| 2 | `[label]` | 可选 | 标签（自动补全为`eq:label`），默认无 |
| 3 | `{factor}` | 可选 | 行间距缩放因子（`\jot`倍数），默认`1.0` |
| 4 | `!` | 标记 | 强制零宽居中 |
| 5 | `!` | 标记 | 强制行宽居中（`!!`） |

### `Align`

```latex
\begin{Align}*[prefix]{factor}
  f(x) &= x^2 + y^2 \id{a} \\
  g(x) &= \alpha + \beta \id{b}
\end{Align}
```

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 公式不编号 |
| 2 | `[prefix]` | 可选 | 标签前缀（`\id{a}`→`eq:prefixa`），默认无 |
| 3 | `{factor}` | 可选 | 行间距缩放因子，默认`1.0` |

### `Gather`

```latex
\begin{Gather}*[prefix]{factor}
  f(x) = x^2 + y^2 \id{a} \\
  g(x) = \alpha + \beta \id{b}
\end{Gather}
```

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 公式不编号 |
| 2 | `[prefix]` | 可选 | 标签前缀（`\id{a}`→`eq:prefixa`），默认无 |
| 3 | `{factor}` | 可选 | 行间距缩放因子，默认`1.0` |

### `Multline`

```latex
\begin{Multline}*[label]{factor}&{width}!!
  f(x) = x^2 + y^2 \\
       + \alpha + \beta + \gamma
\end{Multline}
```

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 公式不编号 |
| 2 | `[label]` | 可选 | 标签（自动补全为`eq:label`），默认无 |
| 3 | `{factor}` | 可选 | 行间距缩放因子，默认`1.0` |
| 4 | `&` | 分隔 | 无实际作用，用于分隔`{factor}`和`{width}` |
| 5 | `{width}` | 可选 | 总宽度（`width\linewidth`），默认自适应 |
| 6 | `!` | 标记 | 强制零宽居中 |
| 7 | `!` | 标记 | 强制行宽居中（`!!`） |
