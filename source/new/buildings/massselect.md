# 批量选择

在《泰伯利亚之日》，像钻洞坦克和火炮这样的单位可以部署成1x1的建筑。当拖动选择框时，这些建筑物被视为车辆，因此其中许多建筑物可以快速取消部署。

此功能在《尤里的复仇》中仍然可用，对于可以取消部署但不应被视为车辆的建筑物，此功能无法关闭。

在Ares中，可以关闭此功能，用于 1x1 建筑，也可以为具有较大占地的建筑启用此功能，这些建筑物应被视为车辆：

`[BuildingType]►MassSelectable=` **(boolean)**

在批量选择时，这种类型的建筑是否被视为单位。如果为*no*，建筑将不被选中，即使它们反部署成为载具并且实际上被视为车辆。对于设置了`UndeploysInto=` 的 1x1 建筑，默认值为 *yes*。

*版本 0.B 中的新功能。*