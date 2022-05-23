# 额外的*ArmorTypes*（护甲种类）和*Verses*（伤害倍率）

译者注：verses一词是versus的笔误，versus的简写大家可能更熟悉：VS。Verses其实就是弹头vs（对上）护甲 的效果，实际体现为伤害倍率。

新增的节`[ArmorTypes]`可用于为对象定义新的*ArmorTypes*（除了11个现有的*ArmorTypes*：*none*, *flak*, *plate*, *light*, *medium*, *heavy*, *wood*, *steel*, *concrete*, *special_1*和*special_2*）。

```
[ArmorTypes]
paper=steel
magic=11%
```

`paper=steel`声明一种名为“paper”的新护甲种类，每个弹头对它的伤害倍率默认与该弹头对steel的伤害倍率相同。`magic=11%`声明一种名为“magic”的新护甲种类，所有弹头对它的伤害倍率默认为11%。这些护甲种类可以按照与标准护甲种类相同的方式分配给对象（不区分大小写）。它们对特定弹头的效果可以具体说明如下：

`[Warhead]►Versus.magic=` **(float - modifier)**

​	设置弹头对于名为“magic”的护甲的效果。

请注意，每个单独的护甲种类的伤害倍率值都是使用新的 `Versus.*` 标志指定的，而原始的11个护甲种类伤害倍率值是使用原始 `Verses` 标志指定的（请注意 Westwood 的拼写错误）。

如果指定的值少于 11 个，则原始 `Verses` 标志分析器不再崩溃。

*0.1 版中的新功能。*

## 弹头*Verses*的特殊值

Verses 标签有三个特殊情况值，可用于定义其他行为：

- 0%表示不能强制开火开火，不会报复，不会被动索敌
- 1%表示不会报复，不会被动索敌
- 2% 表示不会被动索敌

这些行为现在可以独立于伤害倍率打开或关闭（因此，您现在可以拥有对护甲种类100%伤害的弹头，但同时不会直接瞄准具有该护甲种类的单位）。

`[Warhead]►Versus.magic.ForceFire=` **(boolean)**

这种弹头是否允许在`magic`护甲上强行发射。

`[Warhead]►Versus.steel.Retaliate=` **(boolean)**

是否允许使用这种弹头来报复 `steel` 护甲。

`[Warhead]►Versus.clingfilm.PassiveAcquire=` **(boolean)**

这种弹头是否被允许用于自动攻击`clingfilm`装甲。

注意 Ares 的正确拼写“acquire”。

## 免疫能力

原始游戏有一种方法可以使某些单位对某些弹头免疫，但这受到严重限制。例如，`[DESO]`步兵（辐射工兵）的标志是`ImmuneToRadiation=yes`（免疫辐射），而`[RadBeamWarhead]`弹头（辐射光束弹头）的旗帜是`Radiation=yes`（具有放射性）。这意味着辐射工兵不受其他辐射工兵发射的辐射光束的伤害。这种免疫系统有两个限制：

1. 只存在少数几对有效标志存在
2. 免疫能力只能防止单位从弹头中受到伤害。它不会阻止该单位成为目标。在上面的例子中，辐射工兵可以无伤地相互射击。

如上所述，Ares通过新的装甲类型克服了这些限制。如果你想拥有额外的“旧式”免疫能力，仍然允许单位瞄准他们无法伤害的东西（例如，因为它们会影响目标周围区域的敌人），那么你可以创建一个新的护甲种类，如下例：

```
[ArmorTypes]
flakImmuneToFrost=flak

[IceMan]
Armor=flakImmuneToFrost
Primary=IceBlast

[IceBlast]
Warhead=IceBlastWH

[IceBlastWH]
Versus.flakImmuneToFrost=0%
Versus.flakImmuneToFrost.ForceFire=yes
Versus.flakImmuneToFrost.Retaliate=yes
Versus.flakImmuneToFrost.PassiveAcquire=yes
```

上述设置使IceMan单位对IceBlast武器具有伤害免疫能力，即使他仍然可以被该武器攻击。

*0.1 版中的新功能。*