# 杀死驾驶员

为满足实现“贾曼卡尔”的能力的请求，此功能允许特定的弹头杀死车辆的驾驶员而不是摧毁它，并允许其他人接管现在中立的车辆。

*版本 0.2 中的新功能。*

*在 2.0 版更改。*

## 弹头设置

这种逻辑支持`CellSpread`，并像任何其他常规弹头一样尊重所有免疫能力，如`ImmunyToPoison`，以及它们的老兵能力，`AffectsAllies`和`AffectsEnemies`。

可以定制在没有造成常规损害的情况下是否仍应用这种效果是。参见[弹头效果](warheads/general.html#wh-effects)。

`[Warhead]►KillDriver=` **(boolean)**

指定此弹头是否杀死车辆驾驶员，而不是摧毁车辆本身。与车辆`Operator`匹配的第一个乘客被视为驾驶员。所有其他乘客将被弹出。默认为 *no*。

`[Warhead]►KillDriver.Owner=` **(enumeration - civilian,special,neutral)**

指定单位分配到的所属。默认为*special*。

`[Warhead]►KillDriver.KillBelowPercent=` **(float)**

指定单位驾驶员被`KillDriver=yes`弹头杀死的生命值百分比。高于此生命值等级的单位只会受到伤害，驾驶员不会被杀死。默认为 *100%*。

`[Warhead]►KillDriver.KillBelowPercent=` **(float)**

指定被 `KillDriver=yes` 弹头击中的单位的驾驶员击毙的几率。默认值为 *100%*。

`[Warhead]►KillDriver.RemoveVeterancy=` **(boolean)**

当驾驶员被杀且单位更换所有者时，单位是否会恢复到新手等级。如果所有者未更改，则不应用。默认值为 *no*。





## 受保护的驾驶员

以下设置可以使单位不受杀死驾驶员逻辑的影响：

`[TechnoType]►ProtectedDriver=` **(boolean)**

这辆载具的驾驶员是否不能被杀死，即这辆车是否对`KillDriver`免疫。`Organic=yes` 和 `Natural=yes` 的单位始终不受 `KillDriver `的影响。默认为 *no*。

`[TechnoType]►ProtectedDriver.MinHealth=` **(double - percentage)**

单位低于此最低生命值时驾驶员可以被杀死。如果单位的生命值高于此值，则无法杀死驾驶员。如果`KillDriver.KillBelowPercent`也在弹头上定义，则使用两个值中的最小值，即此标签可以使单位对驾驶员杀死武器的抵抗力更强。如果 `ProtectedDriver=yes`，则默认为 *0.0*，否则为 *1.0*。

也可以通过在r `VeteranAbilities` 或 `EliteAbilities`下指定*PROTECTED_DRIVER*授予保护驾驶员能力。如果指定，该单元的驾驶员将无条件地受到保护，免受`KillDriver`的伤害（这意味着不再检查`ProtectedDriver.MinHealth`），但单位仍会受到常规伤害或其他特殊弹头效果。



## 占领车辆

驾驶员是步兵单位，可以占领中立车辆，例如驾驶员被杀的车辆。

`[TechnoType]►CanDrive=` **(boolean)**

这种*InfantryType* 是否可以充当驾驶员被杀的车辆的驾驶员，有占领车辆的能力。如果车辆需要`Operator`，步兵驾驶员将启动单位并作为以后可以弹出的乘客进入。其他情况下驾驶员进去后，成为车辆的永久驾驶员。默认值为 *no*。

`[TechnoType]►CanBeDriven=` **(boolean)**

此单位是否可以由驾驶员占领。如果*no*，则在原始驾驶员被杀后，驾驶员无法占领该单位。如果*yes*，所有权和其他一些限制仍然可能阻止该单位被占领。默认值为 *yes*。

`[Country]►CanBeDriven=` **(boolean)**

这个国家拥有的单位是否可以被`CanDrive=yes`步兵占领。这可以用来在地图上放置中立国家拥有的单位，而不会被占领。默认同`MultiplayPassive`。

> **注意**
>
> 默认情况下，偷车贼不能驾驶中立车辆，但 `VehicleThief=yes` 可以与 `CanDrive=yes` 结合使用而不会出现问题。

有关`与 CanDrive` 相关的更多选项，请参阅[*劫持者*](hijackers.html)。