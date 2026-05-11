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

### `esint`

更多积分符号。

| 宏包 | 说明 |
|------|------|
| `esint` | 提供`\oiint`、`\oint`、`\varint`等额外积分符号 |

### `extarrows`

带文字的长箭头。

| 宏包 | 说明 |
|------|------|
| `extarrows` | 提供`\xlongequal{text}`等可伸缩的文字箭头 |

### `upgreek`

直立希腊字母。

| 宏包 | 说明 |
|------|------|
| `upgreek` | 提供`\upalpha`、`\upbeta`、`\uppsi`等直立希腊字母，用于数学模式 |

### `xfrac`

小型行内分数。

| 宏包 | 说明 |
|------|------|
| `xfrac` | 提供`\sfrac{num}{den}`命令，排版小型行内分数 |

### `mathrsfs`

额外数学花体字体。

| 宏包 | 说明 |
|------|------|
| `mathrsfs` | 提供`\mathscr`命令，用于排版花体字母（如$\mathscr{E}$） |

### `mathdots`

更多省略号符号。

| 宏包 | 说明 |
|------|------|
| `mathdots` | 提供`\iddots`（逆对角线省略号）等额外省略号命令 |

### `nicematrix`

高级矩阵排版。

| 宏包 | 说明 |
|------|------|
| `nicematrix` | 提供`\pNiceMatrix`等命令，支持带行列标签的矩阵、块矩阵等 |

### `relsize`

数学缩放。

| 宏包 | 说明 |
|------|------|
| `relsize` | 提供`\mathlarger`和`\mathsmaller`，用于缩放数学符号的大小 |

### `yhmath`

宽重音符号。

| 宏包 | 说明 |
|------|------|
| `yhmath` | 提供`\wideparen`等宽重音符号 |

### `accents`

下方重音符号。

| 宏包 | 说明 |
|------|------|
| `accents` | 提供`\underaccent`命令，用于在符号下方添加重音 |

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
| `\dx` | 对$x$的微分$\mathrm{d}x$ |
| `\dy` | 对$y$的微分$\mathrm{d}y$ |
| `\dz` | 对$z$的微分$\mathrm{d}z$ |

### `\vi`、`\vj`、`\vk`

单位向量的快捷写法，依赖`physics`的`\vb*`命令。

| 命令 | 说明 |
|------|------|
| `\vi` | $\mathbf{i}$ |
| `\vj` | $\mathbf{j}$ |
| `\vk` | $\mathbf{k}$ |

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

### `\Var`、`\Cov`

概率论中方差与协方差的快捷写法。

| 命令 | 说明 |
|------|------|
| `\Var` | 方差$\operatorname{Var}$ |
| `\Cov` | 协方差$\operatorname{Cov}$ |

### `\arsinh`、`\arcosh`、`\artanh`、`\arcoth`、`\arsech`、`\arcsch`、`\atantwo`

反双曲函数与`atan2`的快捷写法。

| 命令 | 说明 |
|------|------|
| `\arsinh` | $\operatorname{arsinh}$ |
| `\arcosh` | $\operatorname{arcosh}$ |
| `\artanh` | $\operatorname{artanh}$ |
| `\arcoth` | $\operatorname{arcoth}$ |
| `\arsech` | $\operatorname{arsech}$ |
| `\arcsch` | $\operatorname{arcsch}$ |
| `\atantwo` | $\operatorname{atan2}$ |

### `\Beta`、`\PolyGamma`、`\BesselJ`、`\BesselN`、`\BesselH`、`\BesselI`、`\BesselK`、`\LegendreP`、`\LegendreQ`、`\SphericalY`、`\HermiteH`、`\FermiF`、`\hodge`

特殊函数的快捷写法。

| 命令 | 说明 |
|------|------|
| `\Beta` | $\operatorname{B}$，Beta函数（Gamma的推广） |
| `\PolyGamma` | $\psi$（直立），PolyGamma函数 |
| `\BesselJ` | $\operatorname{J}$，第一类Bessel函数 |
| `\BesselN` | $\operatorname{N}$，第二类Bessel函数（Neumann） |
| `\BesselH` | $\operatorname{H}$，第三类Bessel函数（Hankel） |
| `\BesselI` | $\operatorname{I}$，第一类修正Bessel函数 |
| `\BesselK` | $\operatorname{K}$，第二类修正Bessel函数 |
| `\LegendreP` | $\operatorname{P}$，第一类Legendre函数 |
| `\LegendreQ` | $\operatorname{Q}$，第二类Legendre函数 |
| `\SphericalY` | $\operatorname{Y}$，球谐函数 |
| `\HermiteH` | $\operatorname{H}$，Hermite多项式 |
| `\FermiF` | $\operatorname{F}$，Fermi函数 |
| `\hodge` | $\star$，Hodge星算子 |

### `\diag`、`\subspace`、`\rangespace`、`\nullspace`、`\vspan`、`\piv`、`\rowpiv`、`\colpiv`、`\Obig`

矩阵计算相关符号的快捷写法。

| 命令 | 说明 |
|------|------|
| `\diag` | $\operatorname{diag}$，对角矩阵 |
| `\subspace` | $\mathcal{S}$，子空间 |
| `\rangespace` | $\mathcal{R}$，值域 |
| `\nullspace` | $\mathcal{N}$，零空间 |
| `\vspan` | $\operatorname{span}$，张成空间（`\span`已被占用） |
| `\piv` | $\operatorname{piv}$，主元 |
| `\rowpiv` | $\operatorname{rowpiv}$，行主元 |
| `\colpiv` | $\operatorname{colpiv}$，列主元 |
| `\Obig` | $\mathcal{O}$，大O记号 |

### `\aff`、`\conv`、`\cone`、`\polyhedra`、`\Symm`、`\Herm`、`\dom`、`\epi`、`\hypo`、`\minimize`、`\maximize`、`\find`、`\subto`、`\relint`

凸优化相关符号的快捷写法。带`*`的运算符（`\minimize`、`\maximize`、`\find`、`\subto`）在行间模式中会在下方显示条件。

| 命令 | 说明 |
|------|------|
| `\aff` | $\operatorname{aff}$，仿射包 |
| `\conv` | $\operatorname{conv}$，凸包 |
| `\cone` | $\operatorname{cone}$，锥包 |
| `\polyhedra` | $\mathcal{P}$，多面体 |
| `\Symm` | $\mathbb{S}$，对称矩阵集 |
| `\Herm` | $\mathbb{H}$，Hermitian矩阵集 |
| `\dom` | $\operatorname{dom}$，定义域 |
| `\epi` | $\operatorname{epi}$，上图 |
| `\hypo` | $\operatorname{hypo}$，下图 |
| `\minimize` | $\operatorname{minimize}$，极小化 |
| `\maximize` | $\operatorname{maximize}$，极大化 |
| `\find` | $\operatorname{find}$，求解 |
| `\subto` | $\operatorname{subject\ to}$，约束条件 |
| `\relint` | $\operatorname{relint}$，相对内部 |

### `\sgn`、`\rect`、`\sinc`、`\erfc`、`\dirac`

工程函数符号的快捷写法。

| 命令 | 说明 |
|------|------|
| `\sgn` | $\operatorname{sgn}$，符号函数 |
| `\rect` | $\operatorname{rect}$，矩形函数 |
| `\sinc` | $\operatorname{sinc}$，采样函数（$\sin x/x$） |
| `\erfc` | $\operatorname{erfc}$，互补误差函数 |
| `\dirac` | $\delta$（直立），Dirac冲激函数 |

### `\softmax`、`\sigmoid`、`\ReLU`

深度学习常用激活函数的快捷写法。

| 命令 | 说明 |
|------|------|
| `\softmax` | $\operatorname{softmax}$ |
| `\sigmoid` | $\operatorname{sigmoid}$ |
| `\ReLU` | $\operatorname{ReLU}$ |

### `\kB`、`\Emf`

物理常量与电磁量符号的快捷写法。

| 命令 | 说明 |
|------|------|
| `\kB` | $k_{\mathrm{B}}$，Boltzmann常数 |
| `\Emf` | $\mathscr{E}$，电动势 |

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

### `\delt`、`\detv`

差分与导数的快捷写法。

| 命令 | 说明 |
|------|------|
| `\delt{x}` | $\Delta x$ |
| `\detv{x}{y}` | $\frac{\Delta x}{\Delta y}$，差分形式的导数 |

### `\zp`、`\zm`

$0_+$与$0_-$的快捷写法。

| 命令 | 说明 |
|------|------|
| `\zp` | $0_{+}$ |
| `\zm` | $0_{-}$ |

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

### `\xpar`、`\xhat`、`\xwav`、`\xvec`、`\xbar`、`\bbar`

宽重音符号的快捷写法。

| 命令 | 说明 |
|------|------|
| `\xpar{content}` | `\wideparen`的别名，上方宽弧 |
| `\xhat{content}` | `\widehat`的别名，上方宽帽 |
| `\xwav{content}` | `\widetilde`的别名，上方宽波浪线 |
| `\xvec{content}` | `\overrightarrow`的别名，上方宽箭头 |
| `\xbar{content}` | `\overline`的别名，上方宽线 |
| `\bbar{content}` | 下方添加短线的重音符号 |

### `\mal`、`\mas`、`\te`、`\<`

数学排版工具命令。

| 命令 | 说明 |
|------|------|
| `\mal{content}` | `\mathlarger`的别名，放大数学符号 |
| `\mas{content}` | `\mathsmaller`的别名，缩小数学符号 |
| `\te{content}` | `\mathrm`的缩写，如`\te{sin}`→$\mathrm{sin}$ |
| `\<content>` | 自适应尖括号$\left\langle x\right\rangle$ |

### `\forcezero`、`\forceline`

方程强制居中命令。默认情况下中等长度的编号公式会偏向标签一侧，这两个命令可以纠正。

| 命令 | 说明 |
|------|------|
| `\forcezero[width]{content}` | 将公式置入零宽盒子强制居中，标签保持同行 |
| `\forceline[width]{content}` | 将公式置入行宽盒子强制居中，标签移至下一行 |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `[width]` | 可选 | 盒子宽度（`width\linewidth`），默认`0.4`（`\forcezero`）或`1.0`（`\forceline`） |

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
