# 飞行器尾烟

当飞行器因严重损坏而产生烟雾痕迹时，使用的动画是硬编码的，并且对于所有飞行器种类（*AircraftTypes*）都是相同的，但是无论如何，每次都会为每架飞行器重新查找它。当飞行器被摧毁时，它会产生大量的烟雾动画。此修复去除了了多余的查找。此外，烟雾已根据飞行器类型进行定制。

`[AircraftType]►Smoke.Anim=` **(animation)**

​	创建为烟雾轨迹的动画。默认为*SGRYSMK1*。

`[AircraftType]►Smoke.ChanceRed=` **(integer - percent)**

​	严重受损的飞行器每帧产生烟雾动画的几率。默认值为*10*。

`[AircraftType]►Smoke.ChanceDead=` **(integer - percent)**

​	坠毁的飞行器每帧创建烟雾动画的几率。默认值为*80*。

*0.7 版中的新功能。*