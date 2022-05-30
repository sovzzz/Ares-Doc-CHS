# 假建筑

假建筑是《红色警戒》中的建筑，它们看起来像原来的对应物，但较脆弱，没有任何功能。它们的目的仅仅是隐藏真实建筑物的位置。

拥有玩家及其盟友选择假建筑时显示由*TXT_FAKE*定义的字符串，如果敌人渗透到建筑物中并且启用了[显示生产间谍效果](spyeffects.html#spybehavior-revealproduction)，也会显示。

`[BuildingType]►Fake=` **(boolean)**

这座建筑是否是假的。默认值为 *no*。

请参阅 [*EnemyUIName*](../enemyuiname.html)，了解如何对敌方玩家隐藏建筑物的真实姓名。

*版本 0.B 中的新功能。*