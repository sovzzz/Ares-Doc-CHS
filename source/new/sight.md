# 视野

`Sight`使用的查找表与`CellSpread`类似，因此它被限制为最大值10。Ares增加了这一点，现在可以使用更大的值。

> **警告**
>
> 出于性能原因，应明智地使用大于 10 的`Sight`值。它不是为显示完整地图而设计的。

> 注意
>
> 使用较大的`Sight`将产生明显的的八角形视野。这是`CellSpread`逻辑的工作原理导致的，因此不是错误。用于大于 10 的 `Sight` 值的逻辑将来可能会更改。

*版本 0.6 中的新功能。*