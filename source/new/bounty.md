# 赏金

单位和建筑可以通过向敌人开火或碾压敌人来获得赏金。此赏金是可以为每个科技种类（*TechnoType*）自定义的积分数量。

以下标签是全局设置，仅当玩家拥有某些建筑物时才启用赏金，并定义默认显示赏金金额。

`[General]►BountyEnablers=` **(list of BuildingTypes)**

​	只有在玩家拥有此列表中某种类型的建筑后，才会启用赏金。如果列表为空，则将始终启用赏金。默认值为*none*。

`[AudioVisual]►BountyDisplay=` **(boolean)**

​	敌方单位和建筑是否会显示被此类对象摧毁时获得的赏金数量。默认为*no*。

以下标签是针对获得赏金的单位或建筑。

`[TechnoType]►Bounty=` **(boolean)**

​	当摧毁敌方单位或建筑时，此类对象是否会获得赏金，无论开火还是碾压。默认为*no*。

`[TechnoType]►Bounty.Display=` **(boolean)**

​	敌方单位和建筑是否会显示被此类对象摧毁时获得的赏金数量。默认为 `[AudioVisual]►BountyDisplay`。

以下标签定义了受害者的属性，被赏金猎人摧毁的单位和建筑。

`[TechnoType]►Bounty.Value=` **(integer - credits)**

​	如果被赏金猎人摧毁，赏金猎人获得的赏金金额。可以是负的，以惩罚玩家。如果设置了，重置老兵级别特定的值。默认值为 *0*。

`[TechnoType]►Bounty.RookieValue=` **(integer - credits)**

`[TechnoType]►Bounty.VeteranValue=` **(integer - credits)**

`[TechnoType]►Bounty.EliteValue=` **(integer - credits)**

​	如果摧毁具有此老兵等级的对象，赏金的金额。可以是负的，以惩罚玩家。默认为`Bounty.Value`。

以下标签可以实现摧毁某国家拥有的对象不获得赏金。

`[Country]►GivesBounty=` **(boolean)**

​	这个国家是否能提供赏金。如果*no*，摧毁这个国家的单位和建筑不会带来任何赏金。默认为*yes*。

*版本 0.C 中的新功能。*

