# 破坏者

《沙丘 2000》有破坏者，这是一个步兵单位，可以进入敌人的建筑物并牺牲自己立即摧毁它们。这在Ares中被重建。

只有敌方玩家拥有的建筑物是可破坏的。如果建筑物可以被破坏，玩家将获得名为*Sabotage*的光标，这是一个新的可自定义的[*鼠标光标*](mousecursors.html)。

> **注意**
>
> 临时隐形功能尚未实现。

`[InfantryType]►Saboteur=` **(boolean)**

这支步兵能否炸毁一座可破坏的建筑物。建筑物将像被放置C4一样被摧毁，破坏者在这个过程中被消耗掉。需要`Infiltrate=yes`。不支持与车辆劫持、`CanDrive=yes`、C4（`C4=yes` 或通过老兵等级授予）和 `Occupier=yes` 逻辑一起支持。默认值为 *no*。

`[InfantryType]►Saboteur=` **(boolean)**

这座建筑是否不能被破坏。如果是，破坏者就不能进入这种结构。对于 `CanC4=no` 或 `TechLevel=-1` `CanBeOccupied=yes` 建筑物，默认值为 *yes*，否则为 *no*。

*版本 0.A 中的新功能。*