# 单位的*Facings*（朝向）

Ares支持具有8个以上朝向的*VehicleTypes*。在`artmd.ini`设置

`[VehicleType]►Facings=` **(integer)**

用于基于 SHP 的单位的面数。要大于等于*8*的2的整数次幂。小于 *8* 的值将导致仅使用第一帧。默认为 *8*。

*版本 0.9 中的新功能。*

