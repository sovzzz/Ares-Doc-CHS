# 避雷针

避雷针吸引闪电风暴并选择性地修改其伤害。

`[BuildingType]►LightningRod=` **(boolean)**

指定此建筑物是否吸引闪电。如果此建筑物是随机创建的云的最接近的对象，则将在建筑物正上方创建云。默认值为 *no*。

`[BuildingType]►LightningRod.Modifier=` **(float - modifier)**

设置了`LightningRod=yes`的建筑物被闪电击中，其伤害乘以此值。小于*1.0*的值会减少伤害，大于的值会增加伤害。默认值为 *1.0*。

> **注意**
>
> 此逻辑可能会在将来的版本中进行扩展。

*版本 0.2 中的新功能。*