# *Scorch*（灼痕）和*Flamer*（火焰）

《泰伯利亚之日》对凝固汽油弹动画有特殊的支持：这两个标签催生了由`SmallFire`和`LargeFire`定义的新的火焰动画。这已经像以前一样重新实现。

与《泰伯利亚之日》相比，有一个显着的行为变化：即便`SmallFire`和`LargeFire`设置不正确，游戏也不会在即将创建这些类型的新动画时崩溃。

`[Animation]►Scorch=` **(boolean)**

是否在此动画结束时把新的 `[AudioVisual]►SmallFire` 动画也附加到此动画附着的对象上。不会在水、海滩、冰或岩石地形上生成。有关行为和要求的完整描述，请参阅[在ModEnc上的灼痕](https://www.modenc.renegadeprojects.com/Scorch)。默认为*否*。

> **注意**
> 不要在 `[AudioVisual]►SmallFire` 上设置 `Scorch=yes`，因为这会创建一个循环：如果动画结束，则会创建相同类型的新动画并将其附加到同一对象。它还会导致着火的树木永久燃烧。

`[Animation]►Flamer=` **(boolean)**

此动画结束时，是否在靠近此动画的位置随机创建新的 `[AudioVisual]►SmallFire` 和 `[AudioVisual]►LargeFire` 动画。有关行为和要求的完整描述，请参阅[ModEnc上的火焰喷射器](https://www.modenc.renegadeprojects.com/Flamer)。默认值为 *no*。

*版本 0.8 中的新功能。*