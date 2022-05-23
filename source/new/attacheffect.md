# *AttachEffect*（附着效果）

AttachEffect系统被设计为NPatch升级逻辑的精神续作，但它的不仅限于超级武器。除非另有说明，否则*AttachEffect*标签可以应用于四大科技种类（所有*TechnoTypes*）和弹头。

译者注：可以近似地理解为Buff

> **注意**
>
> 在超时空传送过程中、在超时空武器的冻结效果下等等情况，单位上的附着效果状态不会更新。这种情况和伊文的炸弹一样（*IvanBombs*）。

> **快速入门**
>
> 要创建治疗/修复或残留伤害效果，请附加具有相应弹头（`Warhead `）和伤害（` Damage `）设置的动画。这将在整个附加效果持续时间内影响目标单位，使用动画伤害机制施加伤害。

`[Section]►AttachEffect.Animation=` **(AnimationType)**

​	要在受影响的单位上播放的动画。动画将附加到单元并随之移动。默认为`none`。

​	当单位隐形时，动画将被删除。一旦单位再次显形，动画就会重新出现。在隐形时，仍会应用附着效果，但动画引起的效果不会应用。

> **注意**
>
> 动画始终循环播放，直到效果消退。循环次数（` LoopCount`）将被忽略。

`[Section]►AttachEffect.Duration=` **(integer - frames)**

​	效果的持续帧数。永久使用 *-1*。默认值为 *0*。

`[Section]►AttachEffect.TemporalHidesAnim=` **(boolean)**

​	应用了这种类型的附着效果的科技种类是否应该在被 `Temporal=yes` 武器扭曲时删除动画。否则，动画将保持活动状态，不受超时空武器的影响。默认值为 *no*。

`[Section]►AttachEffect.SpeedMultiplier=` **(float - multiplier)**

​	附着效果持续期间速度加成，默认为*1.0*。

`[Section]►AttachEffect.ArmorMultiplier=` **(float - multiplier)**

​	附着效果持续期间护甲加成，默认为*1.0*。

`[Section]►AttachEffect.FirepowerMultiplier=` **(float - multiplier)**

​	附着效果持续期间火力加成，默认为*1.0*。

> **注意**
>
> 请注意，这个与其他效果的工作方式完全不同，只要效果有效，就会在需要时立即起作用（例如子弹撞击的火力）：装弹时间在装弹开始时计算一次，但修改后的装弹时间可能比附着效果持续的时间长。
>
> 例如，一个单位受到会极大地减慢*ROF*（rate of fire, 射速）的效果，可能会使该单位无法发射的时间超过附着效果生效时间。因为当效果过期时，装弹计时不会重新加速。

`[Section]►AttachEffect.ROFMultiplier=` **(float - multiplier)**

​	附着效果持续期间射速加成，默认为*1.0*。

`[Section]►AttachEffect.Cloakable=` **(boolean)**

​	在附着效果持续期间，单位是否获得隐身能力。默认为*no*。

`[Section]►AttachEffect.ForceDecloak=` **（boolean）**

​	应用附着效果时，受影响的单位是否会强制脱离隐形（对于基于无破坏性的基于动画的附着效果很有用）。默认为*no*。

`[Section]►AttachEffect.PenetratesIronCurtain=` **(boolean)**

附着效果是否可以在铁幕或力场护盾的影响下附着在单位或建筑上。默认值为*no*。

以下标签仅在技术种类上有效：

`[TechnoType]►AttachEffect.Delay=` **（integer - frames）**

​	定义在上一个效果消退后，在单位本身上重新创建附着效果的帧数间隔。负值不会更新效果。默认为 *0*（立即）。

`[TechnoType]►AttachEffect.InitialDelay=` **（integer - frames）**

​	定义首次创建附着效果之前的延迟。后续延迟由 `AttachEffect.Delay` 定义。使用 *0* 立即创建效果。默认为 *0*。

以下标签仅对弹头有效：

`[Warhead]►AttachEffect.Cumulative=` **(boolean)**

如果设置为*yes*，则可以将无限量的来自此弹头的此类附着效果应用于目标（附着效果可堆叠）。如果不是，则一个单位只能有一个这种类型的附着效果，并且如果再次附着该效果，则该效果将更新。默认值为 *no*。

`[Warhead]►AttachEffect.AnimResetOnReapply=` **(boolean)**

如果这种类型的附着效果不可堆叠，则启用此标志会在每次重新应用时重置动画。默认值为 *no*。

*版本 0.4 中的新功能。*

*在 2.0 版更改。*