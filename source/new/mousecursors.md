# 鼠标光标

## 定义光标

可以使用新的 `[MouseCursors]` 节添加新的光标并更改默认光标，该部分将光标定义集中在一个位置。每个光标都有一个名称，然后可以将其用作请求鼠标光标的标签的有效值。每行定义一个光标，使用逗号分隔各值，如下所示：

`[MouseCursors]►Name=` **(cursor definition)**

`Name`（名称）键最长可包含 31 个字符。值按给定顺序输入，以逗号分隔：

*Frame,Count,Interval,MiniFrame,MiniCount,HotSpotX,HotSpotY*。没有定义的值为默认值。

译者注：示例参见[默认光标列表](../_downloads/MouseCursors.txt)。

*Frame*是`mouse.sha`中的光标开始的起始帧。第一帧为*0*。默认为 *0*。

*Count*是动画光标的帧数。默认为 *1*。

*Interval*是使光标设置动画的速率。默认值为 *0*。

*MiniFrame*类似于*Frame*，但指定的是鼠标放在小地图上时的光标。将其设置为 *-1* 可禁用小地图光标，并仅允许玩家在战场上点击。默认值为 -1。

*MiniCount*类似于*Count*，但指定的是鼠标放在小地图上时的光标。默认值为 *-1*。

*HotSpot* 指定处理点击事件的点。*HotSpotX*应该是*Left, Center*和*Right*之一。*HotSpotY*应该是*Top, Middle*和*Bottom*之一。例如，*Left,Top*会将光标的左上角视为端点。默认为*Left,Top*。

> **注意**
>
> 你不能直接使用与《尤里的复仇》其他补丁相同的定义方式，因为Ares使用描述性名称而不是数字来表示*HotSpotX，HotSpotY*部分。要转换值，请将 0 替换为*Left*或*Top*，将 *12345* 替换为*Center*或*Middle*，将 *54321* 替换为*Right*或*Bottom*。

*版本 0.D 中的新功能。*



## 默认光标

原始游戏的光标是隐式定义的，也就是说，即使没有显式定义它们，它们也存在并且可用。请参阅[默认光标列表](../_downloads/MouseCursors.txt)。

默认情况下，Ares 会添加几个新的命名光标，这些光标用于特殊目的，如新添加的功能，或用于区分不同的单位操作。可以重写这些光标，以便为这些函数提供单独的光标，而无需同时更改原始光标。

- *TogglePower*：用于在建筑物上开关电源时。默认为*Power*。
- *NoTogglePower*：用于在不允许开关电源。默认为*Disallowed*。
- *EngineerDamage*：工程师由于启用了多工程师而无法占领建筑物时的光标。默认为*Detonate*。
- *InfantryHeal*：盟友步兵的修复光标。默认为*355,1,0,-1,-1,Center,Middle*。
- *UnitRepair*：盟友单位上的修复光标。默认为*Repair*。
- *Tote*：用于调运载具。默认为蓝色移动光标。
- *TakeVehicle*：用于偷车贼和可占领载具的可驾驶逻辑。默认为 *Enter*。
- *Sabotage*：用于破坏者步兵的有效目标建筑。默认为 *Enter*。
- *RepairTrench*：用于工程师维修战壕。默认为*Repair*。

> **注意**
>
> 默认光标可能会更改。Ares 可能会添加更多特殊光标以区分更高版本中的操作、更改新光标的默认值或在默认光标上启用动画。
>

> **警告**
>
> 不支持更改名为*Default*的光标。
>

*版本 0.D 中的新功能。*

## 从早期版本迁移

0.D 之前的 Ares版本支持七个标记来定义鼠标光标：一个基本标记和六个附加标记，用于分别定义光标定义的每个部分。

要迁移到新的`[MouseCursors]`部分，请首先合并单独的标签，如`Cursor.Frame=355`，`Cursor.Count=1`，...转换为一行定义`，如 Cursor=355，1,...`。

如果您有这样的单行光标定义，请将其复制到新的 `[MouseCursors]` 部分，并为其指定一个新的唯一名称，如 `Medic`。使用此唯一名称而不是原来的 `Cursor=355，1,...` 行，也就是这样 `Cursor=Medic`。

如果在多个位置使用相同的光标定义，则无需为每个光标定义指定一个新名称。您可以复用现有光标。