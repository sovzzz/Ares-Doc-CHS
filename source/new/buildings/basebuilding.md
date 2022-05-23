# AI扩展基地的空间

AI通过任何不被视为车辆的建筑扩展基地空间，并且不受`BaseNormal`的限制，`BaseNormal`仅适用于人类玩家。Ares添加了一个选项来禁用扩展基地空间。

`[BuildingType]►AIBaseNormal=` **（boolean）**

​	这座建筑是否会扩大AI玩家的基地空间。如果同时设置了`UndeploysInto=` 并且 `ResourceGatherer=yes`，则默认为 *no*，否则默认由建筑物是否被视为车辆决定。

*3.0 版中的新功能。*



# AI偏好建造在基地内部

AI偏好将匿踪发生器放置在基地的中心而不是外围，这是《泰伯利亚之日》中`CloakGenerator=yes`的副作用。此功能已重新创建并变为可选功能。

`[BuildingType]►AIInnerBase=` **（boolean）**

​	AI是否更喜欢将这座建筑放在离其基地中心更近的地方。将其用于要保护的建筑物或提供范围效果的建筑物，如果它覆盖了基地的大部分，则效果最佳。如果 `CloakGenerator=yes`，则默认为 *yes*，否则为 *no*。

> **注意**
>
> 建筑占地越大，AI就越不可能在游戏后期在基地中心附近找到一个地方建造它，在这种情况下，游戏将回落到原来的逻辑，并在外围找到一个地方。

*3.0 版中的新功能。*