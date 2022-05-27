# 粒子



## 优化

Ares的粒子处理已经大大优化。像素粒子 （ 即 `BehavesLike=` 设置为 *Spark* 或 *Railgun* 的类型） 即使涉及的粒子相对较少，也会导致性能下降。也就是说，即使是稀疏的轨道光柱也会产生明显的运行减速。在整个游戏中经常产生*Smoke*粒子。

在Ares中，如果满足以下所有条件，则会自动激活优化。如果任何一个不满足，则不会应用优化，并且将像早期版本中一样处理粒子。也就是说，混合和匹配仍然是可能的。

1. `[ParticleSystem]►BehavesLike=` 要么是 *Spark*、*Railgun* 或 *Smoke*
2. ParticleType和 `[ParticleSystemType]►HoldsWhat=`具有完全相同的设置
3. ParticleType 不使用 alpha images或线状尾迹

> **注意**
>
> 请注意，混合 *Spark* 和 *Railgun* 将阻止应用优化。

游戏现有的粒子也得到了优化，即使没有应用优化，粒子的处理效率也会更高。

*版本 0 中的新功能.C。*

*在 0.D 版中更改。*



## 气体颗粒的伤害距离

气体粒子只能破坏与自身位于同一格子上的物体，无论粒子的图像有多大。Ares允许自定义这一点。

`[ParticleType]►DamageRange=` **(double - cells)**

气体粒子周围所有对象受到粒子伤害的距离。如果小于或等于 *0.0*，则气体颗粒所在的格子中的所有对象都会受到影响。每个对象最多受影响一次。默认为 *0.0*。

*版本 0 中的新功能.C。*



## SHP粒子的自定义调色板

绘制形状图像（SHP）的粒子（即`BehavesLike=`设置为*Gas*, *Smoke*或 *Fire*的类型）现在支持使用自定义调色板进行绘制。

`[ParticleType]►Palette=` **(带.pal扩展名的文件名)**

用于绘制此类型的形状粒子粒子的调色板。默认为 *ANIM.PAL*。

*版本 0 中的新功能.C。*