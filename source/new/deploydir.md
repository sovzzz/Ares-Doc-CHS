# 部署方向

最初，此设置用于 `DeployToLand=yes` 单位。当被命令部署时，他们会首先转向这个方向。

使用Ares，所有具有`DeployingAnim`的单位在部署时将首先转向这个方向，除了`DeployToLand`。这样，部署动画可以更好地隐藏单位类型的转换，而没有`DeployingAnim`的单位不会不必要地转向。

`[TechnoType]►DeployDir=` **（integer - facing）**

部署时单位将面向的方向。有效值范围从 0（北）到 7（西北）。默认为 `[General]►DeployDir`。

*2.0 版中的新功能。*