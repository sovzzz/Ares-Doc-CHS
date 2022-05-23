# 建造时间

译者注：建造时间=建造速度×价值。本页的标签虽然都是以“*BuildTime*”（建造时间）开头，但都是通过建造速度影响建造时间，没有直接指定建造时间，请勿望文生义。建造速度以*分钟/1000积分*为单位。本页中`BuildTime.Speed`、`BuildTime.MinLowPower`、`BuildTime.MaxLowPower`都是建造速度。

在Ares中，可以自定义与每种对象的建造时间相关的所有设置。

`[TechnoType]►BuildTime.Speed=` **(double - minutes)**

该科技种类的建造速度，默认为 `[General]►BuildSpeed`。

> **注意**
>
> 如果设置， `Wall=yes` 建筑物不再使用`WallBuildSpeedCoefficient` ，因为 `BuildTime.Speed` 将被视为最终值。

`[TechnoType]►BuildTime.Cost=` **(integer - credits)**

​	如果设置，则建造时间时则按此处的价值计算，而不是使用实际的价值。默认为`Cost`。

如果玩家没有足够的电量，则应用以下设置。定义了一个应用于低电量时的建造时间倍数`BuildTime.LowPowerPenalty`，以及限制某科技种类低电量时的建造速度上下限。

`[TechnoType]►BuildTime.LowPowerPenalty=` **(double - multiplier)**

​	低电量时建造时间的惩罚。默认为 `[General]►LowPowerPenaltyModifier`。

`[TechnoType]►BuildTime.MinLowPower=` **(double)**

​		低电量时的最低生产速度。低电量建造速度不会低于此值。默认为`[General]►MinLowPowerProductionSpeed`。

`[TechnoType]►BuildTime.MaxLowPower=` **(double)**

​	低电量时的最高生产速度。低电量建造速度不会大于此值。默认为 `[General]►MaxLowPowerProductionSpeed`。

当玩家有多个相同类型的工厂时，可以使用以下修改。

`[TechnoType]►BuildTime.MultipleFactory=` **(double - multiplier)**

​	每个额外的同种工厂提供的建造时间倍数。默认为`[General]►MultipleFactory`。

*2.0 版中的新功能。*