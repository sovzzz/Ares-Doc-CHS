# 钻地动画和声音

`Dig`和`DigSound`的全局设置已经去除全局化，并拆分为单独的标签，在具有隧道运动方式的单位上用于钻入地下和钻出地表。

`[TechnoType]►DigIn=` **(animation)**

当该单位钻入地下时使用的可选动画。默认为`[AudioVisual]►Dig`。

`[TechnoType]►DigOut=` **(animation)**

此单位钻出地表时使用的可选动画。默认为 `[AudioVisual]►Dig`。

`[TechnoType]►DigInSound=` **(sound entry)**

当该单位钻入地下时播放可选的声音。默认为 `[AudioVisual]►DigSound`。

`[TechnoType]►DigOutSound=` **(sound entry)**

当该单位钻出地表时播放的可选声音。默认为 `[AudioVisual]►DigSound`。

*版本 0.D 中的新功能。*