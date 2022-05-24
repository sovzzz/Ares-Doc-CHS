# 自我修复

单位的自我修复能力在《尤里的复仇》中是硬编码的，除了通过老兵等级启用它，并设定修复间隔，之后单位将获得固定量的生命值。

Ares使自我修复更加可定制，可以用来重现《泰伯利亚黎明》的猛犸坦克，它只恢复到一半的生命值。

`[TechnoType]►SelfHealing.Rate=` **(double - minutes)**

使用自我修复之间的分钟数。默认为 `[General]►RepairRate`。

`[TechnoType]►SelfHealing.Max=` **(double - percentage)**

此对象通过自我修复恢复到的生命值等级。生命值将限制在对象`Strength`的此百分比。如果已定义，则覆盖下面的老兵特定标记。默认为*100*%。

`[TechnoType]►SelfHealing.RookieMax=` **(double - percentage)**

`[TechnoType]►SelfHealing.VeteranMax=` **(double - percentage)**

`[TechnoType]►SelfHealing.EliteMax=` **(double - percentage)**

此对象通过自我修复恢复到的生命值级别，具体取决于其老兵等级。这些设置彼此完全独立。默认为 `SelfHealing.Max`。

`[TechnoType]►SelfHealing.Amount=` **（integer - hitpoints）**

自我修复时恢复的生命值。不能小于 *0*。如果已定义，则覆盖下面的老兵特定标记。默认值为 *1*。

`[TechnoType]►SelfHealing.RookieAmount=` **(integer - hitpoints)**

`[TechnoType]►SelfHealing.VeteranAmount=` **(integer - hitpoints)**

`[TechnoType]►SelfHealing.EliteAmount=` **(integer - hitpoints)**

自我修复时恢复的生命值数量，具体取决于其老兵等级。这些设置彼此完全独立。不能小于 *0*。默认为 `SelfHealing.Amount`。

可以让当单位受损时自我修复中断一段时间。

`[TechnoType]►SelfHealing.CombatDelay=` **(integer - frames)**

定义在发生产生伤害的攻击后，单位将无法自我修复的时间。治疗武器不会触发这种延迟。用 *0* 禁用此功能。默认为 *0*。

*版本 0.B 中的新功能。*

*在 2.0 版更改。*