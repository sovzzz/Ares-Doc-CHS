# 初始装载物（装甲运输车）

在《将军》中，中国拥有装甲运输车，这是一种从工厂预先装满红色卫士的车辆。Ares将这个功能添加到《尤里的复仇》中。

建筑必须设置 `CanBeOccupied=yes` 或 `InfantryAbsorb=yes`。不支持其他建筑具有初始装载物。建筑只允许具有*InfantryType*装载物。

可驻军的建筑装入步兵的最高数量为`MaxNumberOccupants`，其他建筑或单位装入单位的最高数量为`Passengers`。检查`Size`和`SizeLimit`是模组作者的责任。

*InfantryType*不能具有初始乘客。

`[TechnoType]►InitialPayload.Types=` **(list of TechnoTypes)**

创建此对象时使用的初始装载物的种类。可以多写几次或者使用相应的 `InitialPayload.Nums` 装入多个。不支持*BuildingType*和*AircraftType*。建筑物只允许具有*InfantryType*有效载荷。不支持和自身一样的初始装载物，因为这会导致套娃。

`[TechnoType]►InitialPayload.Nums=` **(list of integers)**

将添加 `InitialPayload.Types` 中每种的可选次数。如果此列表包含的项目数少于 `InitialPayload.Types` 列表，则最后一个数字将用作后面所有类型的计数。如果未设置此标记，则假定所有计数均为 *1*。

*版本 0.A 中的新功能。*