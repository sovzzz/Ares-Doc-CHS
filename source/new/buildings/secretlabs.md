# 秘密实验室

最初的秘密实验室系统有三个独立的全局标志来控制奖励，并且不允许授予*AircraftTypes*。已解决秘密实验室逻辑的一些缺陷（请参阅[*对原始 Bug 的修复*](../../bugfixes/type1/index.html)）。

在Ares中，只有建筑首次被`MultiplayPassive=no`国家占领后，或者预先放置在地图上首次分配所属权时才会有奖励（译者注：Boon n.恩惠，有用的东西。此处翻译为奖励）。最终获取的奖励是随机选择的，但只有秘密实验室所有者目前无法建造的东西才有可能被选中。

此逻辑已通过以下“每栋建筑物”标志进行了扩展。必须在建筑物上设置`SecretLab=yes`，才能将其视为秘密实验室，从而让这些标志生效。

`[Building]►SecretLab.PossibleBoons=` **(list of TechnoTypes)**

指定该特定建筑物可能作为秘密实验室奖励的所有建筑物，车辆，步兵和飞机。默认为 `[常规]►SecretInfantry`、`[General]►SecretUnits` 和 `[General]►SecretBuildings` 中的所有项目。

`[Building]►SecretLab.GenerateOnCapture=` **(boolean)**

秘密实验室是否应该重新选择每次建筑物被`MultiplayPassive=no`国家占领或分配到所属权时提供的奖励。否则，在第一次被占领后就不会变动。默认值为 *no*。（译者注：原文描述不清，按RA2DIY版翻译。存疑，待测试）

每个可能的奖励都可以指定以下标志。两者都只在选择奖励时进行检查，因此如果`SecretLab.GenerateOnCapture=no`，则被禁用国家可能仍然会获得奖励，或者要求的国家晚占领秘密实验室时被拒。

> **注意**
>
> 这意味着，当被占领时，这些秘密实验室可能会显得不服从`SecretLab.RequiredHouses`和`SecretLab.ForbiddenHouses`。这不是一个错误。

`[Boon]►SecretLab.RequiredHouses=` **(list of countries)**

指定允许哪些国家将此单位作为秘密实验室奖励。默认为所有国家。

`[Boon]►SecretLab.RequiredHouses=` **(list of countries)**

指定哪些国家不允许将此单位作为秘密实验室奖励。默认为无。

*0.1 版中的新功能。*

*在 0.9 版更改。*

 