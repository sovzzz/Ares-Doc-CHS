# 油井（*ProduceCash*）

## 主要更改

建筑升级现在支持`ProduceCashDelay`，`ProduceCashAmount`和`ProductionCashStartup`，就像普通建筑一样。每个升级各自处理自己的计时器，因此它们将独立于主体建筑或其他升级授予金额。

`ProduceCashStartup`已扩展为支持负值。该金额将从占领的玩家的帐户中扣除。如果可用的点数小于指定的这个点数，则仍然可以占领或放置建筑物。此外，如果建筑物被`MultiplayPassive=yes`所属占领，则不再授予`ProfedecashStartup`。

与原始游戏不同，`ProduceCashStartup`即便空的，`ProduceCashDelay`和`ProducteCashAmount`也能生效。

*版本 0.9 中的新功能。*

*在版本 0.B 中更改。*



## 显示产生的金钱

产生现金的建筑物可以将它们产生的金额显示为建筑物上方的文本。文本将显示在建筑物上方，然后略微向上移动。

`[BuildingType]►ProduceCashDisplay=` **(boolean)**

​	该建筑是否会显示其产出的点数。建筑升级不适用，而是套用主体建筑类型的设置。默认为 *no*。

`[AudioVisual]►DisplayCreditsDelay=` **(double - minutes)**

​	建筑产出点数的两次文本显示之间的间隔。显示间隔期间收集的数量。默认为 *0.02*。

目前，对于正量，颜色被硬编码为绿色，对于负量，颜色被硬编码为红色。格式被硬编码为带有加号或减号前缀的金额。

> **警告**
>
> 将来可能会扩展或更改此功能。不要认为这些文本的外观是理所当然的。颜色、位置和移动速度可能会发生变化。
>

*版本 0.B 中的新功能。*