# *AirRate*（空中动画播放速度）

当单位移动时，`WalkRate` 用于控制单位的动画，当它处于空闲状态时，使用 `IdleRate`。如果一个单位不移动，则算作空闲置，这也包括起飞，降落和悬停，因此直升机形式的单位即使明显在空中也不会播放其旋翼动画。Ares 为这种情况添加了一个新标签。

`[TechnoType]►AirRate=` **(integer - number of frames)**

如果大于 0，则定义在单位处于空中时，在多少帧之后，单元的动画将推进到下一帧。`AirRate` 优先于 `WalkRate` 和 `IdleRate`。0 禁用`AirRate`。默认值为 0。

*版本 0.6 中的新功能。*