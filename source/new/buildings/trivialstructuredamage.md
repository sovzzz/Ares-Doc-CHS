# 轻微建筑伤害

可以像早期的游戏（如泰伯利亚黎明和红色警戒）一样，当一方的电量较低时建筑会损耗。建筑在没有电力时会失去生命值，由数量和间隔定义，直到最低生命值。伤害总是由`[General]►C4Warhead`处理。

在早期的游戏中，只有消耗电力的建筑物在每个间隔内降低一点生命值，直到达到黄色生命值。

`[General]►Degrade.Enabled=` **(boolean)**

当玩家的电力较低时，建筑是否在`DamageDelay`定义的间隔内受到伤害。默认值为 *no*。

`[General]►Degrade.Percentage=` **(double - percentage)**

在低电力情况下，该建筑物的生命状况将继续下降。生命值等于或低于此值的建筑物不会进一步损耗。默认为 `[AudioVisual]►ConditionYellow`。

`[General]►Degrade.AmountNormal=` **(integer - hitpoints)**

在低电力情况下，对`Power`等于或大于 0 的建筑物造成的伤害。默认值为 *0*。

`[General]►Degrade.AmountConsumer=` **(integer - hitpoints)**

在低电力情况下对`Power`小于 0 的建筑物造成的损害。默认值为 *1*。

这些全局选项可以按*BuildingType*进行自定义。

`[BuildingType]►Degrade.Percentage=` **(double - percentage)**

在低电力情况下，该建筑的生命将损耗达到的百分比。值为 *1.0* 不会损耗此建筑，值为 0.0 的值将使它损耗，直到完全破坏。默认值为 `[General]►Degrade.Percentage`。

`[BuildingType]►Degrade.Amount=` **(integer - hitpoints)**

在低电力情况下，该建筑将每隔一段`DamageDelay`受到伤害的量。值为 *0* 不会损耗此建筑。如果`Power`大于或等于0，默认同`[General]►Degrade.AmountNormal`，否则默认同`[General]►Degrade.AmountConsumer`。

轻微建筑伤害可以为每一方单独开启或者关闭。默认情况下，`MultiplayPassive=yes`不会受影响

`[Country]►Degrades=` **(boolean)**

这个国家拥有的建筑物在低电力情况下是否会损耗。对于 `MultiplayPassive=yes`，默认值为 *no*，否则为 *yes*。

`[House]►Degrades=` **(boolean)**

这个国家拥有的建筑物在低电力情况下是否会损耗。仅在单人任务中受支持。默认值为 `[Country]►Degrades`。

*版本 0.A 中的新功能。*