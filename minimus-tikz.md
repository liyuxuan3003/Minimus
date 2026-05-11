# minimus-tikz

绘图工具宏包，提供TikZ绘图、电路图、时序图和化学分子式排版支持。

## 引入的宏包

### `tikz`

TikZ绘图核心。

| 宏包 | 说明 |
|------|------|
| `tikz` | 提供`tikzpicture`环境和全套绘图命令 |

预加载的库：

| 库 | 用途 |
|----|------|
| `calc` | 坐标计算 |
| `intersections` | 交点计算 |
| `angles` | 角度绘制 |
| `perspective` | 简单3D投影 |
| `positioning` | 相对定位 |
| `shapes.geometric` | 几何形状节点 |
| `shapes.arrows` | 箭头形状节点 |
| `shapes.symbols` | 符号形状节点 |
| `quotes` | 引号语法标注 |
| `fit` | 包围盒节点 |

### `circuitikz`

电路图绘制。

| 宏包 | 说明 |
|------|------|
| `circuitikz` | 提供`circuitikz`环境和电路元件命令 |

预配置（`\PassOptionsToPackage`和`\ctikzset`）：

| 选项 | 值 | 说明 |
|------|-----|------|
| `europeanresistors` | | 欧式方块电阻 |
| `americaninductors` | | 美式波浪电感 |
| `americanvoltages` | | 美式电压符号 |
| `americancurrents` | | 美式电流符号 |
| `RPvoltages` | | rising potential voltages |
| `resistors/scale` | `0.65` | 电阻缩放 |
| `capacitors/scale` | `0.75` | 电容缩放 |
| `inductors/scale` | `0.70` | 电感缩放 |
| `diodes/scale` | `0.75` | 二极管缩放 |
| `sources/scale` | `0.9` | 独立源缩放 |
| `tripoles/mos style/arrows` | | MOS管：箭头+圆圈 |
| `logic ports` | `ieee` | IEEE风格逻辑门 |
| `logic ports/scale` | `0.65` | 逻辑门缩放 |
| `quadpoles/transformer/inner` | `1.0` | 变压器移除水平线 |
| `voltage/distance from node` | `0.85` | 电压标记距节点距离 |

### `tikz-timing`

时序图绘制。

| 宏包 | 说明 |
|------|------|
| `tikz-timing` | 提供`tikztimingtable`环境和时序标记命令 |

预加载的库：

| 库 | 说明 |
|----|------|
| `either` | 双态符号`E` |
| `overlays` | 覆盖层 |
| `counters` | 计数器 |
| `advnodes` | 高级节点 |

背景层和前景层已预定义（`background`、`foreground`）。

### `ifthen`

条件判断。

| 宏包 | 说明 |
|------|------|
| `ifthen` | 提供`\ifthenelse`命令，用于`\fliprotate`内部逻辑 |

### `chemfig`

化学分子式。

| 宏包 | 说明 |
|------|------|
| `chemfig` | 提供`\chemfig`命令，排版化学分子结构式 |

## 自定义命令

### `\fliprotate`

MOS管方向控制命令。circuitikz在通过`xscale=-1`、`yscale=-1`或`rotate=90`翻转晶体管时，节点文字也会跟着镜像或旋转，导致无法正常阅读。`\fliprotate`和对应的8种快捷样式（`f++r+`等）通过反向操作（`\ctikzflipx`、`\ctikzflipy`、`\ctikzflipxy`、`\rotatebox{-90}`）将文字翻回正常方向。

`f`部分（前两个`+`/`-`）控制x/y方向的翻转补偿，`r`部分（最后一个`+`/`-`）控制旋转补偿。

| 命令 | 说明 |
|------|------|
| `\fliprotate+-+-{text}+-` | 对`{text}`应用翻转/旋转补偿，7个`+`/`-`标记的排列决定补偿方式 |

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `+`/`-` | 标记 | 第一个标记 |
| 2 | `+`/`-` | 标记 | 第二个标记 |
| 3 | `+`/`-` | 标记 | 第三个标记 |
| 4 | `+`/`-` | 标记 | 第四个标记 |
| 5 | `{text}` | 必选 | 要显示的文字 |
| 6 | `+`/`-` | 标记 | 第五个标记（`r+`水平/`r-`垂直） |
| 7 | `+`/`-` | 标记 | 第六个标记 |

预定义的8种快捷样式（用作TikZ`node`选项）及其内部补偿行为：

| 样式 | 管子的变换 | `\fliprotate`对文字的补偿 |
|------|-----------|--------------------------|
| `f++r+` | 无变换 | 无补偿，直接输出文字 |
| `f-+r+` | xscale=-1 | `\ctikzflipx{text}`（x方向翻回） |
| `f+-r+` | yscale=-1 | `\ctikzflipy{text}`（y方向翻回） |
| `f--r+` | xscale=-1, yscale=-1 | `\ctikzflipxy{text}`（xy翻回） |
| `f++r-` | rotate=90 | `\rotatebox{-90}{text}`（旋转补偿） |
| `f-+r-` | xscale=-1, rotate=90 | `\rotatebox{-90}{\ctikzflipx{text}}` |
| `f+-r-` | yscale=-1, rotate=90 | `\rotatebox{-90}{\ctikzflipy{text}}` |
| `f--r-` | xscale=-1, yscale=-1, rotate=90 | `\rotatebox{-90}{\ctikzflipxy{text}}` |

```latex
\path (xAmp|-yAmp) node[op amp,f++r+,color=blue] (Amp) {} ;

\path (Mp.S|-yA) node[rground,f+-r+,anchor=south] (VIN) {};
```

### `semi thick`、`tlvdd`、`tlvss`、`mw`、`mh`

预定义的TikZ样式。

| 命令/样式 | 说明 |
|------|------|
| `semi thick` | `semithick`的别名 |
| `tlvdd` | 尾部向下的VDD |
| `tlvss` | 尾部向上的VSS |
| `mw=len` | `minimum width=len`的简写 |
| `mh=len` | `minimum height=len`的简写 |
