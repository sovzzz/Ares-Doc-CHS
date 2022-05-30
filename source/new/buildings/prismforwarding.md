# 光棱传递

在《红色警戒2》的预发布截图中，光棱塔沿着整个塔链将能量从一个塔输送到另一个塔。当然，这在发布的游戏中是不可能的（这表明这个截图是改出来的）。

![红色警戒 2 预发布截图](../../_images/prism1.jpg)

Ares完全取代了旧的光棱塔代码，以修复一些小错误，并对其进行扩展以提供全套光棱网络选项。

*版本 0.2 中的新功能。*

> **快速入门**
>
> 如果您只想保留现有的光棱塔，但将它们扩展到如上面的预发布屏幕截图所示多个链，只需设置`[ATESLA]►PrismForwarding.MaxChainLength=3`或您想要的向后链接数量（-1表示无限）。

`[BuildingType]►PrismForwarding=` **(enumeration - yes|no|forward|attack)**

指定此建筑物是否为光棱塔。

- `PrismForwarding=forward `意味着该建筑可以支持其他塔，但不能作为光棱塔进行攻击。

- `PrismForwarding=attack`意味着该建筑可以作为光棱塔进行攻击，但不能支持其他塔。

- `PrismForwarding=yes`意味着这座建筑是一个功能完全的光棱塔 - 它可以支持其他塔或攻击。

- `PrismForwarding=no`意味着该建筑不是光棱塔，不会包含在任何光棱网络中。

对于 `[General]►PrismType` 指定的建筑物，默认值为 *yes*，对于所有其他建筑物，默认值为 *no*。

`[BuildingType]►PrismForwarding.Targets=` **(list of BuildingTypes)**

  此塔可以支持的建筑类型列表。默认为仅建筑物类型本身，但如果您决定包含此标志，请不要忘记提及建筑物本身。

`[BuildingType]►PrismForwarding.MaxFeeds=` **(integer)**

  可以直接支持此塔的隶属（支持）塔（即相邻塔）的最大数量。-*1* 表示无限制。默认为 `[General]►PrismSupportMax`。

译者注：原文如此

`[BuildingType]►PrismForwarding.MaxChainLength=` **（integer）**

  可以在此塔之前的最大向后链路数。-*1* 表示无限制。默认为 *1*。为了实现上述预发布屏幕截图中显示的内容，您需要将其设置为至少 *3*。

译者注：即最远的支持塔和射击塔之间能有几次接力

`[BuildingType]►PrismForwarding.MaxNetworkSize=` **（integer）**

  如果这是射击塔，那么`PrismForwarding.MaxNetworkSize`是光棱网络中允许的塔总数，不包括射击塔本身。只有射击塔决定了最大网络大小，而不管网络中可能包含哪些其他塔类型。*-1* 表示无限制。默认值为 `[General]►PrismSupportMax`。

`[BuildingType]►PrismForwarding.SupportModifier=` **(float - multiplier)**

  这与旧的`PrismSupportModifier`的工作方式相同——这是该塔对射击光束的贡献的乘数。乘数以线性方式累积（即如果有2个支持塔，每个支持塔都有`PrismForwarding.SupportModifier=150%`，则伤害的总乘数将为*150%+ 150%+ 100%= 400%*。默认值为 `[General]►PrismSupportModifier`。

`[BuildingType]►PrismForwarding.DamageAdd=` **(integer - damage bonus)**

  在与`PrismForwarding.SupportModifier`相乘之前，向发射光束添加一个数值的伤害加成。这可以代替乘数使用，也可以与乘数结合使用，以随着网络中包含更多塔而逐渐调高或降低最终伤害。默认值为 *0*。

译者注：一个支持塔传递到此塔的伤害=（支持塔的伤害+DamageAdd)×SupportModifier

> **注意**
>
> 如果调低伤害加成，你需要限制网络中的塔数，否则发射光束最终可能会成为治疗武器。您可以在[`光棱接力电子表格`](../../_downloads/PrismForwarding.xls)中输入自己的值，以查看这对光棱网络造成的伤害的影响。

`[BuildingType]►PrismForwarding.ToAllies=` **(boolean)**

这个光棱塔是否允许支持盟友的塔。默认值为 *no*。

请注意，在长链光棱网络中，该塔必须与射击塔也就是目标塔是盟友。

`[BuildingType]►PrismForwarding.BreakSupport=` **（boolean）**

这个光棱塔能否在最后一刻中止支持另一座塔，以成为主塔（射击）塔。如果塔确实打断了支持，则不需要重新启动充能。默认值为 *no*。

`[BuildingType]►PrismForwarding.ChargeDelay=` **(integer - frames)**

> 警告
> 这仅适用于高级用户！

此选项仅用于测试目的，并没有真正增强支持光束的外观，因此建议您忽略此选项。在原版游戏中，主塔（射击塔）每帧只获得一个从隶属（支持）塔的从属。在此时每个从属的隶属塔开始充能，主塔开始重新充能。这给出了让隶属塔光束快速连续到达的效果，而不是一次全部到达。这种效果在游戏中几乎不明显，除非速度较慢或网络中有大量的塔。

在Ares中，这已被更改，以便所有相邻的隶属塔都在同一帧中从属。也就是说，引入了充能延迟，因此塔似乎不会全部立即开始充能。对于网络中的每个后向链，最远的正向塔在稍晚一点开始充能，以提供光束沿链行进的效果。每个塔将延迟开始充能的延迟可以通过`PrismForwarding.ChargeDelay`指定。此延迟会累积到光棱转发网络中的每个链中。

因此，例如，如果`PrismForwarding.ChargeDelay=2`并且您有一个由3个塔组成的光棱链，那么最远的塔（塔3）将立即开始充能，中间塔（塔2）将在2帧后开始充能，而射击塔（塔1）将在另外2帧后开始充能。所有塔将在第 4 帧上处于充能状态。在发射时，光束将从最远的塔过滤到射击塔。由于光束的实际功率通过光棱转发网络传输的新方式，最小电荷延迟为1，因此您不能让所有光束同时出现。但是，在正常的游戏速度下，除非网络中存在特别长的链，否则几乎不会注意到1帧的充能延迟。

译者注：接力的链里，离射击塔越远充能越晚

默认收费延迟为 1。增加此值以使支持波束在网络上的传播速度更慢（不建议这样做，因为较大的值往往会降低效果的质量）。

- `[建筑类型]►光棱前向.强度=`**（整数-激光厚度）**

  这使您可以控制激光束随着光棱网络尺寸的增加而增加的厚度。默认情况下，由1个或更多其他塔支撑的射击光棱塔的`激光眩光度`为5 - 比发射武器的默认`激光眩光度`（3）高2。`PrismForwarding.Intensity` 标志将负值视为对发射光束的绝对加法，因此默认值 -2 会使行为与原始游戏完全相同。另一方面，正值告诉战神，您希望光束的厚度取决于网络中后向链的数量，并且还以相同的方式增加支撑梁厚度。`PrismForwarding.Intensit` 值为 1 将导致最远的光束没有厚度增加，下一个光束的厚度增加为 1，下一个的光束的厚度增加为 2，依此类推。有关激光绘制方式的更多信息，请参阅激光眩`光`部分。

- `[建筑类型]►超能力=`**（布尔值）**

  在原版游戏中，射击的光棱塔总是发射其主要武器（其伤害根据支撑塔的数量成倍增加）。`压倒性的`旗帜被忽略了。战神允许射击光棱塔来利用压倒性的逻辑 - 你现在可以同时拥有一个支持和压倒性的光棱塔！请注意，压倒支持塔不会产生任何影响。

- `[建筑类型]►光棱前方.支持武器=`**（武器）**

  在原版游戏中，`[光棱支撑]`武器从未被直接引用，而光棱塔的`辅助`武器也只是被引用以获得塔可以支撑`的范围`。在战神中，光棱塔的`副`武器根本没有被提及。相反，我们使用`PrismForwarding.SupportWeapon`来显式引用武器对象，从中获取支撑光束的其他设置。没有必要指定支援武器 - 如果您不指定一个，将使用默认值。

- `[建筑类型]►光棱前行.精英支持武器=`**（武器）**

  如果塔成为精英，那么支撑光束将从这种武器中获得其属性。默认为 `PrismForwarding.SupportWeapon`。



## 自定义支撑梁

`PrismForwarding.SupportWeapon`不是传统意义上的武器，实际上不会被发射。光棱转发系统仅使用武器的特定属性，这些属性将在下面描述。请注意，提到的默认值**仅在**您未指定支援武器时使用。如果您指定了支援武器，则默认值与任何其他武器相同。

不建议使用现有的`[光棱支撑]`武器作为基础。如果要自定义默认值，则应改用以下标志列表末尾提供的示例。

- `[PrismForwarding.SupportWeapon]►Range=` **（integer - cell）**

  指定光棱塔可以支持另一个的最大范围。这不会影响最终的射程。-2 表示无限范围。如果未指定支援武器，则默认支援范围为防御塔`的主`武器范围加1个单元格（额外的单元格确保在射击塔的攻击半径圆圈内放置支持塔可确保支持塔在支持范围内）。这与原始游戏不同。

- `[PrismForwarding.SupportWeapon]►MinimumRange=` **（integer - cells）**

  指定光棱塔可以支持另一个的最小范围。这个光棱塔将无法支持比`最小范围更近的塔`。如果未指定支援武器，则默认情况下没有最小支援范围。

- `[PrismForwarding.SupportWeapon]►ROF=` **（integer - frames）**

  在支援塔发射支撑梁后，它将无法向目标射击或为这么多帧支撑另一个光棱塔。如果未指定支援武器，则默认持续时间为 `[常规]►光棱支持延迟`。

- `[PrismForwarding.SupportWeapon]►Report=` **（声音）**

  光棱塔发射支撑光束时要播放的声音。在原版游戏中，支撑光束没有引起点火声。请注意，许多光棱塔同时发射支撑光束可能会导致令人讨厌的重复或响亮的音量，因此您可能需要限制声音的实例数和/或使用更安静或更微妙的声音。如果未指定支撑武器，则默认情况下支撑光束没有发射声。

- `[PrismForwarding.SupportWeapon]►IsLaser=` **（布尔值）**

  指定在支撑另一个塔时是否应绘制激光束。其他激光控制（`LaserDuration`，`IsHouseColor`，`LaserInnerColor`，`LaserOuterColor`，`LaserOuterSpread`和`LaserThickness`）也受到尊重。如果未指定支援武器，则将绘制传统的支援激光器（`IsLaser=yes`，`LaserDuration=[General]PrismSupportDuration`，`IsHouseColor=yes`，`LaserThickness=3`）。

- `[PrismForwarding.SupportWeapon]►IsElectricBolt=` **（布尔值）**

  指定在支撑另一个塔时是否应拔出电动螺栓。其他电动螺栓控件（`IsAlternateColor`，`Bolt.Color1`，`Bolt.Color2`和`Bolt.Color3`）也受到尊重。如果未指定支撑武器，则不会抽取电动螺栓。

- `[PrismForwarding.SupportWeapon]►IsRadBeam=` **（布尔值）**

  指定在支撑另一个塔时是否应绘制一个辐射束。其他辐射束控件（`Beam.Duration`，`Beam.IsHouseColor`，`Beam.Color`和`Beam.Amplitude`）也受到尊重。如果未指定支撑武器，则不会绘制任何弧光束。

目前没有提到支援武器的其他属性，但是将来可能会改变。

支持武器示例：

```
[NewPrismSupportBeam]
Range=9 ;or 8 if you prefer the original
ROF=45
IsLaser=yes
IsHouseColor=yes
LaserDuration=15
LaserThickness=3
```

## 支撑梁 FLH

支撑光束的发射原点可以通过使用建筑物艺术条目上的FLH控件来设置 - `AlternateFLH0`指定新手支撑光束原点，`AlternateFLH1`指定精英支撑光束原点。如果其中任何一个设置为0，0，0（默认FLH值），那么它们将回退到使用`PrimaryFireFLH`或`ElitePrimaryFireFLH`，视情况而定。

## 光棱塔限制

不应允许光棱塔取消部署 - 在充能序列中取消部署光棱塔可能会导致内部错误。

## 关于光棱转发的特别说明

在测试期间报告的一个常见错误是光棱塔倾向于不自动瞄准并攻击敌方单位。解决这个问题的办法是确保确定弹头和/或损害。如果发生这种情况，请务必检查PF修改是否定义了弹头值或损坏值。（[错误 #896095](https://bugs.launchpad.net/ares/+bug/896095))