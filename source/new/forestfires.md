# 森林火灾

森林大火是《泰伯利亚之日》的一个特有功能。如果树木被`Sparky=yes`弹头击中，就会被点燃。在燃烧时，它们可以点燃附近的树木，因此随着时间的推移，它们会像野火一样蔓延开来。

Ares对森林火灾的使用与《泰伯利亚之日》的使用略有不同。目前还需要在每棵可能着火的树上设置以前未使用的标签`IsFlammable=yes`。这是唯一明显的变化。

请参阅 [ModEnc 上的 Sparky](https://www.modenc.renegadeprojects.com/Sparky)，了解逻辑的更详细说明，以及使其正常工作的要求。为了防止在发射`Sparky=yes`弹头时发生崩溃，请不要忘记给`[AudioVisual]►OnFire`设置三个有效动画，给`[AudioVisual]►TreeFire`设置两个有效动画。

> **注意**
>
> 如果树木没有燃烧，请确保用作`[AudioVisual]►SmallFire`的动画设置了`Scorch=no` 。

*版本 0.8 中的新功能。*