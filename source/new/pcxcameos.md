# PCX图标

新增的功能，可以从PCX文件而不是SHP加载侧边栏图标。

在`artmd.ini`中：

`[Image]►CameoPCX=` **(filename, \*包含\*.pcx扩展名)**

指定单位图标的文件名，格式为“filename.pcx”。

`[Image]►AltCameoPCX=` **(filename, \*包含\*.pcx扩展名)**

指定单位的替换（升级）图标的文件名，格式为“filename.pcx”。

在`rulesmd.ini`中：

`[SuperWeapon]►SidebarPCX=` **(filename, \*包含\*.pcx扩展名)**

指定包含超级武器浮雕的文件名，格式为“filename.pcx”。

> **注意**
>
> 像游戏使用的其他PCX文件一样，用于此功能的PCX文件*必须*具有256色和60x48像素的尺寸。

译者注：在PS中可以通过图像-模式-索引色将图片改为256色，也可以通过另一个兼容Ares的《尤里的复仇》扩展库“Phobos”解除256色限制

*版本 0.2 中的新功能。*