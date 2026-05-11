# minimus-math

数学宏包，提供数学符号、算符、快捷命令和数学排版环境。

## 引入的宏包

### `amsmath`、`amsthm`、`amssymb`

AMS 数学系列宏包。

| 宏包 | 说明 |
|------|------|
| `amsmath` | 提供`align`、`gather`、`split`等数学环境 |
| `amsthm` | 提供定理环境支持 |
| `amssymb` | 提供`\mathbb`、`\mathcal`等数学字体符号 |

方程编号设为按节递增（`\numberwithin{equation}{section}`）。

### `siunitx`

物理量与单位的排版。

| 宏包 | 说明 |
|------|------|
| `siunitx` | 提供`\qty`、`\unit`、`\num`等命令，用于排版带单位的物理量。`\qty`系列被重命名为`\qnum`/`\qnumlist`/`\qnumrange`/`\qnumproduct`，以避免与`physics`冲突 |

预配置设置：

| 设置项 | 值 | 说明 |
|--------|-----|------|
| `list-separator` | `{, }` | 列表分隔符 |
| `range-phrase` | `{\,\text{\textasciitilde{}}\,}` | 范围连接符 |
| `group-digits` | `none` | 不分组数字 |
| `inter-unit-product` | `{\cdot}` | 单位间用`·`连接 |

同时预配置了二进制单位（`\KB`、`\MB`、`\GB`、`\Kb`、`\Mb`、`\Kbps`、`\Mbps`等）。

### `physics`

物理排版命令。

| 宏包 | 说明 |
|------|------|
| `physics` | 提供`\vb`（向量）、`\dd`（微分）、`\pdv`（偏导）、`\qty`（括号）等物理排版命令 |

### `mathtools`

`amsmath`的增强包。

| 宏包 | 说明 |
|------|------|
| `mathtools` | 提供`\mathmakebox`（数学盒子宽度控制）、`\mathclap`、`\mathllap`、`\mathrlap`等增强命令 |

### `mhchem`

化学式排版。

| 宏包 | 说明 |
|------|------|
| `mhchem` | 提供`\ce`命令，用于排版化学式，如`\ce{H2O}`、`\ce{^{227}_{90}Th+}` |

## 自定义命令

### `\e`、`\i`、`\j`、`\k`

常用数学常数的快捷写法，统一为正体。

| 命令 | 说明 |
|------|------|
| `\e` | 自然常数$\mathrm{e}$ |
| `\i` | 虚数单位$\mathrm{i}$，覆盖了无点i |
| `\j` | 虚数单位$\mathrm{j}$（物理/工程） |
| `\k` | 四元数虚部$\mathrm{k}$ |

### `\N`、`\Z`、`\Q`、`\R`、`\C`、`\emptyset`

常用数集的快捷写法。

| 命令 | 说明 |
|------|------|
| `\N` | 自然数集$\mathbb{N}$ |
| `\Z` | 整数集$\mathbb{Z}$ |
| `\Q` | 有理数集$\mathbb{Q}$ |
| `\R` | 实数集$\mathbb{R}$ |
| `\C` | 复数集$\mathbb{C}$ |
| `\emptyset` | 空集，重定义为$\varnothing$ |

### `\dx`、`\dy`、`\dz`

微分的快捷写法，依赖`physics`的`\dd`命令。

| 命令 | 说明 |
|------|------|
| `\dx` | 对$x$的微分$\dd{x}$ |
| `\dy` | 对$y$的微分$\dd{y}$ |
| `\dz` | 对$z$的微分$\dd{z}$ |

### `\Sum`、`\Prod`、`\BigCap`、`\BigCup`、`\BigOplus`、`\BigOdot`、`\BigOtimes`

累加、连乘等大型算符的快捷写法，统一支持`[sub][sup]`参数格式。

| 命令 | 说明 |
|------|------|
| `\Sum[sub][sup]` | 累加$\sum$的快捷写法 |
| `\Prod[sub][sup]` | 连乘$\prod$的快捷写法 |
| `\BigCap[sub][sup]` | 交$\bigcap$的快捷写法 |
| `\BigCup[sub][sup]` | 并$\bigcup$的快捷写法 |
| `\BigOplus[sub][sup]` | 直和$\bigoplus$的快捷写法 |
| `\BigOdot[sub][sup]` | $\bigodot$的快捷写法 |
| `\BigOtimes[sub][sup]` | $\bigotimes$的快捷写法 |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `[sub]` | 可选 | 下限，默认无 |
| 2 | `[sup]` | 可选 | 上限，默认无 |

### `\Int`、`\Idnt`、`\Itnt`、`\Ilnt`、`\Ilot`、`\Isnt`、`\Isot`

积分符号的快捷写法，统一支持`[low][high]`参数格式。

| 命令 | 说明 |
|------|------|
| `\Int[low][high]` | 积分$\int$的快捷写法 |
| `\Idnt[low][high]` | 二重积分$\iint$的快捷写法 |
| `\Itnt[low][high]` | 三重积分$\iiint$的快捷写法 |
| `\Ilnt[low][high]` | 线积分$\int$的快捷写法 |
| `\Ilot[low][high]` | 闭合线积分$\oint$的快捷写法 |
| `\Isnt[low][high]` | 面积分$\iint$的快捷写法 |
| `\Isot[low][high]` | 闭合面积分$\oiint$的快捷写法 |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `[low]` | 可选 | 积分下限，默认无 |
| 2 | `[high]` | 可选 | 积分上限，默认无 |

### `\Lim`

极限的快捷写法，自动在趋近参数前添加`\to`。

| 命令 | 说明 |
|------|------|
| `\Lim[cond][to]` | 极限$\lim$的快捷写法 |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `[cond]` | 可选 | 极限条件，默认无 |
| 2 | `[to]` | 可选 | 趋近目标，默认无 |

### `\Grad`、`\Div`、`\Curl`

向量分析算符的快捷写法。

| 命令 | 说明 |
|------|------|
| `\Grad` | 梯度$\operatorname{grad}$ |
| `\Div` | 散度$\operatorname{div}$ |
| `\Curl` | 旋度$\operatorname{curl}$ |

### `\FT`、`\LT`

傅里叶变换与拉普拉斯变换的快捷写法，带`*`表示逆变换。

| 命令 | 说明 |
|------|------|
| `\FT[content]` | 傅里叶变换$\mathcal{F}\{x\}$ |
| `\FT*[content]` | 逆傅里叶变换$\mathcal{F}^{-1}\{x\}$ |
| `\LT[content]` | 拉普拉斯变换$\mathcal{L}\{x\}$ |
| `\LT*[content]` | 逆拉普拉斯变换$\mathcal{L}^{-1}\{x\}$ |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 取逆变换 |
| 2 | `[content]` | 可选 | 变换对象 |

### `\anglebkt`、`\floor`、`\ceil`

自适应括号的快捷写法，带`*`时自动缩放大小。

| 命令 | 说明 |
|------|------|
| `\anglebkt*{content}` | 尖括号$\langle\rangle$，带`*`时自适应大小 |
| `\floor*{content}` | 下取整$\lfloor\rfloor$，带`*`时自适应大小 |
| `\ceil*{content}` | 上取整$\lceil\rceil$，带`*`时自适应大小 |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `*` | 标记 | 自适应大小 |
| 2 | `{content}` | 必选 | 括号内的内容 |

## 自定义环境

### `Equation`

单行公式环境。

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

多行对齐公式环境，用`&`指定对齐点。

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

公式组对齐环境，每行可独立编号。

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

公式组居中环境，每行可独立编号。

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

阶梯排列的长公式环境。

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
