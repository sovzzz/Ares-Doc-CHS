# 容量格点

在《尤里的复仇》中，`Pip`（载具格点）和`OccupyPip`（驻军建筑格点）接受的值被硬编码为已知名称的列表。在修复[*Pip Distortion Bug时*](../bugfixes/type1/pipdistortionbug.html)，Ares使这更加灵活。

任何定义格点的标签现在都接受替代表示法。如果无法使用已知名称列表（如 *personblue*）解析标记值，则该值将解析为整数。整数用作 pips 文件 （ `pips.shp`和 `pips2.shp`） 的帧索引。

如果该值既不是已知名称也不是整数，则会将解析错误放入 `debug.log`。

`[TechnoType]►Pip=` **(integer)**

格点文件中要用作格点图像的帧索引。有效值范围从 *0* 到 pip 文件的总帧数 - 1。

> **注意**
>
> 如果将标签读取为整数并且值超出范围，则不会在`debug.log`中记录任何错误。

*版本 0.4 中的新功能。*