# 隧道网络

这是《将军》的那种隧道系统。隧道是允许将单位从一个地方快速移动到另一个地方的建筑。可以有许多入口建筑，但它们都共享相同的占用者队列。单位实际上并不在隧道之间移动；在他们进入一个入口后，他们可以立即从另一个入口弹出。

居住者将保持存活，直到同一玩家拥有的相同类型的最后一个入口被摧毁。隧道占用者的击杀会被算在最后一个入口的摧毁者也头上。如果最后一个入口被变卖，单位将尝试撤离。

在`[TunnelTypes]`部分下的列表声明不同隧道，它们具有以下选项：

`[TunnelType]►Passengers=` **(integer)**

​	此隧道系统可以拥有的最大占据者数。这不考虑单位`Size`大小。每个单位占用一格空间。默认为 *0*。

`[TunnelType]►MaxSize=` **(double)**

​	必须允许最大 `Size=` 单位进入此隧道。默认为 *0.0*。

然后，可以通过设置以下标签将建筑种类（*BuildingType*）转换为隧道入口。多个建筑种类可以共享相同的隧道种类（*TunnelTypes*）。只有`Size`小于或等于隧道入口`SizeLimit`的单位才允许通过该入口进入。

> **注意**
>
> 目前撤出时未根据 `MaxSize` 检查`Size`。这在将来的版本中可能会更改。
>

> **快速入门**
>
> 如果在隧道入口上没有出现进入光标，请检查您是否在隧道种类上正确设置了`Passengers=` 和 `MaxSize`。
>

隧道入口播放 `EnterTransportSound` 和 `LeaveTransportSound`，每当单位进入或离开建筑时。入口建筑将显示代表隧道系统内容的点。

`[BuildingType]►Tunnel=` **(TunnelType)**

​	该建筑是哪种隧道系统的入口。

> **注意**
>
> 隧道建筑不允许拥有武器或炮塔，也不能被俘虏或心灵控制。

> **警告**
>
> 悬停单位在隧道入口建筑中具有与进入`UnitAbsorb=yes`建筑物相同的问题。

例：

```ini
; Tunnel declarations 
[TunnelTypes]
0=GLATunnel 
1=CivilianTunnel 
2=LoveTunnel 
; Tunnel definition 
[GLATunnel] 
Passengers=8 
MaxSize=4.0 
; Civilian Tunnel Entrance Building 
[CATNNL] 
Tunnel=CivilianTunnel 
```

*版本 0.E 中的新功能*