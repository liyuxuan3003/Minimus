# minimus-tikz

绘图工具宏包，提供TikZ绘图、电路图、时序图和化学分子式排版支持。

## 引入的宏包

### `tikz`

TikZ绘图核心。

| 宏包 | 说明 |
|------|------|
| `tikz` | 提供`tikzpicture`环境和全套绘图命令 |

预加载的TikZ库：

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

预配置：

- 电阻：欧式方块（`europeanresistors`），缩放`0.65`
- 电感：美式波浪（`americaninductors`），缩放`0.70`
- 电容：缩放`0.75`
- 二极管：缩放`0.75`
- 独立源：缩放`0.9`
- MOS管：箭头+圆圈（`tripoles/mos style/arrows`）
- 逻辑门：IEEE风格（`logic ports=ieee`），缩放`0.65`
- 变压器：移除水平线（`inner=1.0`）
- 电压标记：距节点`0.85`

### `tikz-timing`

时序图绘制。

| 宏包 | 说明 |
|------|------|
| `tikz-timing` | 提供`tikztimingtable`环境 |

预加载的时序库：`either`（双态符号`E`）、`overlays`（覆盖层）、`counters`（计数器）、`advnodes`（高级节点）。背景层和前景层已预定义（`background`、`foreground`）。

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

晶体管方向控制命令。通过参数控制管子的翻转和旋转方向。

| 命令 | 说明 |
|------|------|
| `\fliprotate++++-{node}{text}` | 按`f`/`r`（正向/反向）和`+`/`-`（源漏极性）组合控制晶体管方向和文字标注 |

参数为四个标记（`+-`）加一个标记（`+-`）：

| 序号 | 格式 | 类型 | 说明 |
|------|------|------|------|
| 1 | `+`/`-` | 标记 | 正向信号极性 |
| 2 | `+`/`-` | 标记 | 反向信号极性 |
| 3 | `+`/`-` | 标记 | 正向偏置极性 |
| 4 | `+`/`-` | 标记 | 反向偏置极性 |
| 5 | `{node}` | 必选 | 晶体管节点名 |
| 6 | `+`/`-` | 标记 | 方向（`+`水平，`-`垂直） |
| 7 | `{text}` | 必选 | 文字标注内容 |

同时定义了8种晶体管方向样式作为快捷方式：`f++r+`、`f-+r+`、`f+-r+`、`f--r+`、`f++r-`、`f-+r-`、`f+-r-`、`f--r-`。

### TikZ样式

预定义的TikZ样式：

| 命令/样式 | 说明 |
|------|------|
| `semi thick` | `semithick`的别名 |
| `tlvdd` | 尾部向下的VDD |
| `tlvss` | 尾部向上的VSS |
| `mw=len` | `minimum width=len`的简写 |
| `mh=len` | `minimum height=len`的简写 |
