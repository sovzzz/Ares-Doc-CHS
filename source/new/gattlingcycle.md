# 加特林增强功能

《尤里的复仇》中的加特林机炮系统会随着武器的射击时间越长而切换武器。一旦达到最高阶段，它将保持最后一种武器，直到目标被摧毁或单位被给予另一个命令。

通过在最后一个武器阶段使用`FireOnce=yes`，可以使加特林切换回第一阶段并再次开始旋转。此解决方法带有副作用；最明显的是，该单位会失去目标，因此可能不会向单个单位连续开火。

`[TechnoType]►Gattling.Cycle=` **(boolean)**

当最后一个 `Stage` （阶段）或`EliteStage` （精英阶段）结束后，计数器将回滚并重新启动第一阶段，而不会使射击单位失去目标。需要 `IsGattling=yes`。默认值为 *no*。

> **注意**
>
> 加速度射击效果取决于阶段和 `RateUp` 和 `RateDown` 值以及射击单位的各个状态。不能保证某个阶段的开火次数固定。

*0.3 版中的新功能。*