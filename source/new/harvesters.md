# 矿车、奴隶矿场和奴隶

以下新标签对定义采矿行为的设置进行微观定义，例如矿车和奴隶的扫描范围以及唤醒奴隶矿场的时间间隔。

`[TechnoType]►Harvester.LongScan=` **（integer - cell）**

覆盖远距扫描（寻找下一片矿石）要考虑的距离。对于 `Harvester=yes` 单位，默认为 `[General]►TiberiumLongScan`。对于奴隶矿场，默认为`[General]►SlaveMinerLongScan`。

`[TechnoType]►Harvester.ShortScan=` **（integer - cell）**

覆盖短距扫描（采集一片矿石时）要考虑的距离。对于 `Harvester=yes` 单位，默认为 `[General]►TiberiumShortScan`。对于 奴隶矿场，默认为 `[General]►SlaveMinerShortScan`，对于奴隶，默认为 `[General]►SlaveMinerSlaveScan`。

`[建筑类型]►Harvester.ScanCorrection=` **（integer - cell）**

覆盖距离，以便在向前行驶时考虑得更好。仅适用于奴隶矿场建筑。默认为 `[General]►SlaveMinerScanCorrection`。

`[VehicleType]►Harvester.TooFarDistance=` **(integer - cells)**

覆盖认为别的精炼厂太远的距离。会暂时停靠在卸矿中的精炼厂边上，而不是去太远的精炼厂。需要`Harvester=yes`。对于 `Teleporter=yes` 单位，默认为 `[General]►ChronoHarvTooFarDistance` ，其他为 `[General]►HarvesterTooFarDistance`。

`[VehicleType]►Harvester.KickDelay=` **(integer - frames)**

覆盖唤醒奴隶矿场的间隔。（在守卫模式下静置一段时间后，扫描矿石）仅适用于奴隶矿场。使用 *-1* 不自动唤醒奴隶矿场。默认为 `[General]►SlaveMinerKickFrameDelay`。

*3.0 版中的新功能。*