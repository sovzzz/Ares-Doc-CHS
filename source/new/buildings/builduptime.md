# 建成和变卖时间

译者注：注意和建造时间区分

全局设置`[General]►BuildupTime`已可以微观设置，并分为两个单独的标签，用于建成和变卖*BuildingTypes*。

此外，Ares现在支持使动画的帧数超过建成时间而不会出现故障。如果建成时间太短并且需要跳过帧，则建成时间会自动增加，因此也不发生故障。

`[BuildingType]►BuildupTime=` **(double - minutes)**

与帧数无关的建成动画的播放时间。默认为 `[General]►BuildupTime`。

> **注意**
>
> 请注意，某些建筑功能在放置后仍然立即可用，而不仅仅是在完全建造之后。

`[BuildingType]►SellTime=` **(double - minutes)**

类似于`BuildTime`的建筑变卖时间。默认值为 `BuildupTime`。

译者注：此处`BuildTime`可能是`BuildupTime`，但原文如此。

*版本 0.D 中的新功能。*