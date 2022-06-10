# 科技建筑回归中性

在多人游戏中，玩家占领的中立科技建筑和可占领建筑可以回归中立方，让拥有玩家被击败或弃权的情况下不摧毁它们。

只有最初属于 `MultiplayPassive=yes` 房屋的建筑物才有资格被归还。在单人游戏模式下，这些设置将被忽略。

建筑物被归还的国家是其最初的所有者。

`[General]►ReturnStructures=` **(boolean)**

当玩家被击败或弃权时，建筑是否默认会返回到平民方。默认值为 *no*。

`[BuildingType]►Returnable=` **(boolean)**

当拥有玩家被击败或弃权时，这种建筑是否会回到平民方。默认为 `[General]►ReturnStructures`。

*版本 0.6 中的新功能。*

# 科技建筑通知

《尤里的复仇》具有 `CaptureEvaEvent` 设置，该设置定义了如果占领了具有` NeedsEngineer=yes` 类型的建筑，将播放哪个 EVA 事件。Ares 使相应的丢失事件可自定义，并为每个事件添加可选的文本消息。

`[BuildingType]►LostEvaEvent=` **(EVA event)**

从玩家处占领这种类型的建筑物时，会播放EVA消息。需要`NeedsEngineer=yes`。默认值为 *EVA_TechBuildingLost*。

`[BuildingType]►Message.Capture=` **(CSF label)**

当玩家占领此类型的建筑时显示的文本。需要`NeedsEngineer=yes`。默认值为 *none*。

`[BuildingType]►Message.Lost=` **(CSF label)**

当这种类型的建筑物被敌人占领时显示的文本。需要`NeedsEngineer=yes`。默认值为 *none*。

*版本 0.9 中的新功能。*