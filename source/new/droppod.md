# 空投舱

这些是汇总的适用于空投舱运动模式的全局设置，特定设置见[*Drop Pod超级武器*](superweapons/types/droppod.html)。

*版本 0.7 中的新功能。*



## 尾迹

原来的空投舱尾迹是不可自定义的，也没有理想的实现方式。现在，动画只查找一次，而不是为每个空投舱每六帧查找一次。此外，即使空投舱没有`[General]►DropPodWeapon`设置，现在也会创建烟雾尾迹。

`[General]►DropPodTrailer=` **(AnimationType)**

动画用作空投舱的烟雾尾迹。默认为 *SMOKEY*。



## 全局超级武器默认

以下标签定义了空投舱超级武器的默认设置。标签默认值无意义，但此处给出了《火线风暴》使用的值以供参考。

`[General]►DropPodTypes=` **(list of InfantryTypes)**

为空投舱超级武器生成单位时随机选择的类型。每种类型都有相等的选择机会。您可以多次添加类型。只支持步兵。默认为*none*，《火线风暴》使用等效的 E1，E2。

`[General]►DropPodMinimum=` **(integer)**

创建空投舱的最小数量。默认为 *0*，《火线风暴》使用 5。

`[General]►DropPodMaximum=` **(integer)**

创建空投舱的最大数量。默认为 *0*，《火线风暴》使用 8。

## 杂项

如果用作`[General]►DropPodWeapon `的武器没有至少一个有效的`Report `声音集，那么当空投舱生成时，游戏不再崩溃。