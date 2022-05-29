# 下落速度

当一个单位从飞机上投到战场上时，无论有没有降落伞，这些设置都定义了它加速的速度以及它下落的最大速度。

`[TechnoType]►FallRate.Parachute=` **(integer)**

带降落伞的单位向地面下落的每帧加速。默认为*1*。

`[TechnoType]►FallRate.NoParachute=` **(integer)**

不带降落伞的单位向地面下落的每帧加速。默认为*1*。

`[TechnoType]►FallRate.ParachuteMax=` **(integer)**

带降落伞的单位下落的最大速度。值必须是负数。默认为`[General]►ParachuteMaxFallRate`。

`[TechnoType]►FallRate.NoParachuteMax=` **(integer)**

不带降落伞的单位下落的最大速度。值必须是负数。默认为`[General]►ParachuteMaxFallRate`。

*版本 0.D 中的新功能。*