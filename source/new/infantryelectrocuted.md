# *InfantryElectrocuted*（步兵触电死亡动画）

步兵被具有`InfDeath=5`的弹头击杀时的死亡动画曾经被硬编码为`[Animations]`列表中的第二个动画。您现在可以指定 `[AudioVisual]►InfantryElectrocuted=` 。

`[AudioVisual]►InfantryElectrocuted=` **(animation)**

如果未定义`InfantryElectrocuted`，则游戏将搜索名为*ELECTRO*的动画，如果该动画不存在，会像以前一样使用动画列表的第二个动画。

*0.1 版中的新功能。*