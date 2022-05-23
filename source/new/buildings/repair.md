# 维修和资金不足

此全局标签可用于更改维修模式的工作方式。默认情况下，一旦玩家点数不足，所有维修都会停止。只能在获得一些点数后，再次建筑维修。使用此标记，维修将暂停，但不会停止。

`[General]►RepairStopOnInsufficientFunds=` **(boolean)**

当拥有玩家资金不足时，维修是否会自动停止。如果不是，则不会关闭维修模式。扳手仍然可见，即使建筑物不再积极维修。当玩家获得更多资金时，维修将恢复。这只会影响人类玩家。默认为 *yes*。

*版本 0.D 中的新功能。*



# 不许工程师维修的建筑物

`[BuildingType]►EngineerRepairable=` **(boolean)**

工程师是否能维修这座建筑。如果不是，则建筑物可能仍由正常建筑物维修（`ClickRepairable=yes`）维修，但工程师不能用于立即恢复全部生命值。默认同`Repairable`。

*2.0 版中的新功能。*