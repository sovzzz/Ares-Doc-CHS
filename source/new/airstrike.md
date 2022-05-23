# 空袭语音

Ares支持自定义空袭相关语音。这些标志可以在飞行器和指示单位如鲍里斯上定义（指示者的标志优先）。如果未在其中任何一个上设置标志，则使用相应的`[AudioVisual]`标志。要禁用空袭声音，请将其设置为空声音。

`[TechnoType]►VoiceAirstrikeAttack=` **(soundmd entry)**

​	指定在呼叫空袭和空袭小队进入地图时播放的声音。默认为`AirstrikeAttackVoice`。

`[TechnoType]►VoiceAirstrikeAbort=` **(soundmd entry)**

​	指定在飞机有机会开火之前，指示单位就被击毙时播放的声音。默认为 `AirstrikeAbortSound`。

*0.7 版中的新功能。*