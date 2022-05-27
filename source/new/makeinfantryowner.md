# *MakeInfantryOwner*（生成步兵归属）

最初的`MakeInfantry`逻辑总是将新创建的步兵的所有权授予中立方，除非动画是由步兵类型被`InfDeath=9`弹头杀死引起的（在这种情况下，击杀玩家将获得新步兵类型的所有权）。Ares允许你从几个选项中选择一个玩家来获得所有权。

`[Animation]►MakeInfantryOwner=` **(enumeration invoker|killer|victim|civilian|special|neutral|random)**

指定哪一方拥有在此动画播放后创建的生成的InfantryType。动画能够重映射归属方颜色，如果没有另行说明。默认为*invoker*。

注意

如果您使用 `Next=` 标记创建动画链，则 `MakeInfantry=` 最后一个播放动，而 `MakeInfantryOwner=` 放在第一个动画——即最初调用的动画。

请注意，这不是弹头属性；它在`artmd.ini`中相应的动画条目中运行。但是，`MakeInfantryOwner`仅适用于特定的动画;即由`InfDeathAnim`，`DeathAnims`，`InfantryExplode`，`FlamingInfantry`，`InfantryElectrocuted`，`InfantryHeadPop`，`InfantryNuked`，`InfantryVirus`，`InfantryMutate`、`InfantryBrute`和地图触发调用的那些。默认的 `MakeInfantryOwner` 是 *invoker*，它对应于不同的玩家，具体取决于动画。

- 对于 `InfDeathAnim`、`InfantryVirus` 和 `InfantryMutate`，*invoker*代表*killer*（击杀单位的所有者）。对于`NotHuman=no`受害者的`InfantryVirus`，**不使用**归属色映射。如果要重映射归属色，请明确使用*killer*。
- 对于 `InfantryExplode`、`FlamingInfantry`、`InfantryElectrocuted`、`InfantryHeadPop`、`InfantryNuked` 和 `InfantryBrute`，*invoker* 表示**不使用**归属色映射。如果要重映射归属色，则必须明确使用*neutral*。
- 对于 `DeathAnims`，*invoker*代表受害者（垂死单元的所有者）。
- 对于地图触发，*invoker*、*killer*和*victim*都表示被视为触发所有者的归属方。

*random*将从游戏中的所有玩家中随机选择一个玩家，包括*neutral*, *special*和*civilian*的所有可用的归属方。

注意

如果没有另行说明，与 `InfDeath=9` 一样，突变动画将使用单位调色板并重映射归属色，而不是`anim.pal` 。

*0.1 版中的新功能。*

*在 0.7 版更改。*