# 动画伤害

## 使用武器

代替直接使用弹头（`Warhead`）造成伤害，定义一个武器制造射弹并立即引爆。这允许应用一些武器效果。

`[Animation]►Weapon=` **(weapon)**

​	用于提供动画伤害的武器。如果设置，则创建一个射弹并立即引爆。传递的伤害由动画定义，而不是武器。

> **注意**
>
> 武器必须已经为游戏所知，否则无法正确解析。建议将其添加到“武器类型”（*WeaponTypes*）列表中。

> **注意**
>
> 目前，创建的射弹既不属于创建动画的玩家，也不归动画所附加的单位或建筑的所有者所有。虽然使用弹头（`Warhead`）提供的伤害至少为计分目的知道创建动画的玩家，但武器伤害不会传递这些信息。这种情况将来可能会改变。

*2.0 版中的新功能。*



## 伤害延迟

`[Animation]►Damage.Delay=` **(integer - animation frames)**

​	动画造成两次伤害之间的延迟。需要伤害（`Damage`）大于或等于 1.0 。值为 0 将禁用延迟。默认值为 0。

> 注意
>
> 请注意，此值以动画帧为单位进行度量：根据速率（`Rate`），动画可能不会在每个游戏帧中都前进到下一个动画帧。

*2.0 版中的新功能。*


