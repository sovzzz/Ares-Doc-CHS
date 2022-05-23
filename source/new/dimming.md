# 失能单位亮度调整

可在此处配置已失能的体素载具种类暗化的等级。使用第一个适用的值，就无视其他值。也就是说，如果没有没电的单位处于EMP下，则使用`DeactivateDimEMP`。这纯粹是装饰性的，将来顺序可能会发生变化。值为 *1.0* 将禁用调光效果。支持的范围是*0.0*到*1.0*，更高的值将使单位变亮。

> **注意**
>
> Shp载具种类以及建筑种类，飞行器种类和步兵种类不受调光的影响。

`[AudioVisual]►DeactivateDimEMP=` **(float - multiplier)**

EMP 下体素单位的光照等级。请参阅 [*EMP 逻辑*](../restored/emp.html)。默认值为 *0.8*。

`[AudioVisual]►DeactivateDimOperator=` **(float - multiplier)**

缺少操作员的体素单位的光照等级。请参阅[*操作员逻辑*](operator.html)。默认值为 *0.65*。

`[AudioVisual]►DeactivateDimPowered=` **(float - multiplier)**

没电的体素单位的光照等级。请参阅 [*通电逻辑*](newpoweredunitlogic.html)。默认值为 *0.5*。

*版本 0.7 中的新功能。*