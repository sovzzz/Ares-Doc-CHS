# 工厂和克隆



## 不同单位的工厂（狗舍）

`[InfantryOrVehicle]►BuiltAt=` **(list of BuildingTypes)**

单位将会从列表中本方拥有的第一个空闲建筑产出。如果未设置*BuildingType*，则将检查可以生产此单位的所有工厂。默认值为*no*。

`[BuildingType]►Factory.ExplicitOnly=` **(boolean)**

将此值设置为 *yes*，以仅允许此工厂生产在 `BuiltAt` 列表中明确提及此 *BuildingType* 的单位。具有空的`BuiltAt` 列表的单位将不会在此处生成。与所有工厂没此标签时在每个单位上声明 `BuiltAt` 列表效果相同。（译者注：没有此标签时，所有对应类型的单位都能在本工厂生产，必须要在每种单位都设上建造处才能不在此处生产。拥有此标签，那么只有指定在此工厂生产，才会从此工厂生产。以下面的狗屋为例，狗`BuiltAt=`狗屋，那么狗只能从狗屋出来。此时人也会从狗屋出来。狗屋设置了`Factory.ExplicitOnly=yes`，就不需要给每个人都加上`BuiltAt=`兵营）默认值为 *no*。

> **快速入门**
>
> 要重新创建《红色警戒》中在狗屋中训练的狗，请设置 `[KENN]►Factory=InfantryType`， `[KENN]►Factory.ExplicitOnly=yes`， `[DOG]►BuiltAt=KENN` 并在 `[DOG]►Prerequisite`中包含 `[KENN]`。



## *VehicleTypes*的“克隆缸”

`[BuildingType]►CloningFacility=` **(boolean)**

定义此建筑是否将克隆所有具有与自身相同的`Naval`设置、有 `Cloneable=yes` 和 `ClonedAt=none`的 *VehicleType*。这是*VehicleTypes*版本的“克隆缸”。默认值为 *no*。

## 克隆选项

`[InfantryOrVehicle]►Cloneable=` **(boolean)**

这个步兵或单位是否可以被 `Cloning=yes`、 `CloningFacility=yes` 或者它们的 `ClonedAt` 建筑克隆。默认值为 *yes*。

`[InfantryOrVehicle]►ClonedAs=` **（TechnoType）**

生成此对象的克隆体时用作替代的类型。如果未设置，则克隆将采用与此对象相同的种类。单位只能克隆为*VehicleType*，步兵只能克隆为*InfantryType*。默认值为*none*。（译者注：实际表现看来应该默认为自身）

`[InfantryOrVehicle]►ClonedAt=` **(list of BuildingTypes)**

将会从本方拥有的每一个列表内建筑中产出一个该对象的克隆体。如果建筑物被封住，玩家将不会获得退款。默认值为*none*（译者注：实际表现看来，默认是 `Cloning=yes`、 `CloningFacility=yes`建筑）。

> **注意**
>
> 克隆将忽略设置了 `Factory=` 的建筑物。请注意，不是`Factory `让单位正确行走或驶出，`WeaponsFactory=yes`，`GDIBarracks=yes`，`NODBarracks=yes`和`YuriBarracks=yes`才是。

> **注意**
>
> 如果指定了 `ClonedAt`，则`Cloning=yes` 或 `CloningFacility=yes` 都不会克隆对象。

*版本 0.2 中的新功能。*

*在 3.0 版更改。*