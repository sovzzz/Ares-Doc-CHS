# *AlternateTheaterArt*（根据场景切换外观）

海豹突击队设置了 `AlternateArcticArt=yes`，这会导致游戏在极地地图上使用`seala.shp`图像文件，而不是`seal.shp`。此逻辑适用于任何步兵种类，但这仅适用于极地地图，仅适用于步兵种类（`InfantryTypes`）。

`[TechnoType]►AlternateTheaterArt=` **(boolean)**

​	指定此基于 SHP 的单位是否可以具有可替换外观，具体取决于当前地图的场景。例如，在单位上设置`Image=JUNK`和`AlternativeTheaterArt=yes`将使单位加载`artmd.ini`的不同节，在北极加载`[JUNKA]`，在沙漠加载`[JUNKD]`，依此类推。如果这些部分中的任何一个不存在，则该单元将加载`[JUNK]`。与`AlternativeArcticArt`非常相似，只是自动且更智能。默认为否。

> **注意**
>
> 这仅适用于基于 SHP 的单位。体素不使用这个系统，也不能有场景特定的外观（你必须使用`Prerequisite.RequiredTheaters`来实现这一点）。

*0.2 版中的新功能。*