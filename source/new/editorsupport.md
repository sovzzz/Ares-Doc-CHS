# 编辑器支持

在使用Ares新增的[*小队脚本*](scripts.html)、[*触发事件*](triggerevents.html)和[*操作*](triggeractions.html)之前，必须让地图编辑器知道它们的名称和数据格式。

## FinalAlert2

将 [`FinalAlert2`](../_downloads/FADataCode.txt) 的定义（由 Starkku 提供）合并到`FAData.ini`，即可在编辑器中使用新的触发动作和触发事件，这样您就可以在创建的地图和任务中舒适地使用它们。

要从用户界面访问新的小队脚本，您需要使用`FA2Ext.dll` ，一个未与 Ares 捆绑的第三方扩展 dll。

如果已将新的*ParamTypes*添加到`FAData.ini`中，则可能必须先相应地更新定义，然后才能使用它们。

*3.0 版中的新功能。*