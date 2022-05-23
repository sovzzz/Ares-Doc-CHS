# 军校（出厂等级）

军校是授予其所有者训练具有一定老兵等级的特定单位和建筑的权利的建筑。如果玩家拥有多座军校建筑，则会获得最高的那种加成。效果不会叠加。

只有`Trainable=yes`单位或建筑才能获得老兵加成。如果一个对象已经通过其他方式提升到更高的级别（比如从`VeteranInfantry`中，或者通过渗透敌人的军工厂），那么老兵等级不会降低。

值为 *1.0* 表示老兵，值为 *2.0* 表示精英。您可以使用十进制值仅授予不满一级的升级，因这样升到下一级会更快。

`[BuildingType]►Academy.InfantryVeterancy=` **(double - veterancy levels)**

​	如果玩家拥有这些建筑之一，授予任何步兵种类（*InfantryType*）或任何`Organic=yes`载具种类（*VehicleType*）的老兵加成。默认为 *0.0*。

`[BuildingType]►Academy.AircraftVeterancy=` **(double - veterancy levels)**

​	如果玩家拥有这些建筑物之一，则授予任何飞行器种类（*AirplanetType*）或任何`ConcepterAircraft=yes` 的载具种类的老兵加成。默认为 *0.0*。

`[BuildingType]►Academy.VehicleVeterancy=` **(double - veterancy levels)**

​	如果玩家拥有这些建筑物之一，则授予任何具有`Organic=no`和`ConsideredAircraft=no`的载具种类的老兵加成。默认为 *0.0*。

`[BuildingType]►Academy.BuildingVeterancy=` **(double - veterancy levels)**

​	如果玩家拥有这些建筑之一，则授予任何建筑种类（*BuildingType*）的老兵加成。默认为 *0.0*。

可以使每个军校仅提升特定类型，或者不提升除指定类型之外的所有流派。默认情况下，军校会提升所有类型。

`[BuildingType]►Academy.Types=` **(list of TechnoTypes)**

受该军校影响的仅有类型可以获得定义的奖金。如果该列表为空，则所有类型都会受到影响。默认为*none*。

`[BuildingType]►Academy.Ignore=` **(list of TechnoTypes)**

永远不会受到该军校影响的类型。默认为*none*。

*版本 0.8 中的新功能。*