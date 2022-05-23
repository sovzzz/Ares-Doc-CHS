# 前置需求

前置需求系统已通过多种方式得到增强。下面介绍了新标志，并且已解决有关建筑升级作为前置需求的问题（请参阅 [*BuildingType 升级不是可行的前置需求*](../bugfixes/type2/buildingtypeupgradesarenotviableprerequisites.html)）。



## 需要作战地区

译者注：theater n.剧院;剧场;戏剧;战场;(某一国,某一作家的)戏剧作品

`[TechnoType]►Prerequisite.RequiredTheaters=` **(list of theater names)**

提供该类型的地图作战地区。默认为所有作战地区。例如，如果仅指定了 *SNOW*（雪地）作战地区，则该类型将仅在极地地图上可用。例如，这允许您实现海豹突击队上使用的`AlternativeArcticArt`功能，但适用于所有类型和所有战区（但是这可能会给您的AI带来挑战）。作战地区名称是：温带 - 大多数地图雪 - 北极/雪地图城市 - 部分城市地图沙漠 - 一些沙漠地图，较旧的地图使用温带月球 - 苏联任务 6NEWURBAN - 大多数YR城市地图注意`前置需求优先`*不*覆盖`前置需求。必需的参与者`。

*0.1 版中的新功能。*



## 反前置需求

- `[TechnoType]►Prerequisite.Negative=` **（BuildingTypes列表）**

  阻止建造该类型的建筑物。如果玩家拥有此列表中的一个或多个建筑物，则该类型将不可用。默认值为无。注意`前置需求优先`*不*覆盖`前置需求。否定`。

*0.1 版中的新功能。*



## 多个备选前置需求列表

Ares 支持多个前置需求列表。每个前置需求列表都充当现有`前置需求`标志的独立副本，并且必须至少满足一个前置需求列表，此类型才能成为可生成类型。

例如，如果您设置`了Prospisel=GAPILE，GATECH`和`Presprestival.List1=NAHAND，NATECH，`那么该对象将可供任何同时拥有盟军营房和战斗实验室或苏联军营和战斗实验室的玩家使用。

注意

必须指定“`前置需求`”或“`前置需求”。List0`，因为这些只是*附加*列表，并且仍使用原始前置需求列表。如果忽略这一点并将列表留空，则对象将始终可生成，因为始终满足空列表。

- `[TechnoType]►Prerequisite.Lists=` **（integer）**

  指定有多少个额外的前置需求列表与一个默认列表相辅相成。默认值为 0。

- `[TechnoType]►Prerequisite.List#=` **（BuildingTypes 列表（其中 # 是前置需求列表的从 1 开始的索引，由 Prerequisite.Lists 指定的最大值））**

  满足此前置需求所需的构建类型列表。每个列表都单独检查，如果满足任何列表，则满足前置需求要求。注意`前置需求。List0`（如果已指定）将覆盖现有的`前置需求`标志。

*0.1 版中的新功能。*



## 需要被盗技术

- `[TechnoType]►Prerequisite.StolenTechs=` **（整数列表）**

  在构建此对象之前必须窃取的可窃取技术类型的列表。有关详细信息[，请参阅被盗技术](buildings/spyeffects.html#spybehavior-stolentech)。

*0.1 版中的新功能。*



## 要求按国家/地区建造的工厂

满足前置需求可以与工厂建筑的初始所有者相关联。最初的所有者是首先拥有它的玩家：建造它的玩家，或者预先放置在地图上的建筑物的所有者。对于中立结构，这将是中立国。

- `[BuildingType]►FactoryOwners.HasAllPlans=` **（布尔值）**

  该建筑是否为初始所有者的所有工厂类型提供计划。如果是，则此建筑物满足所有对象类型的工厂所有者要求。如果建筑物丢失，则计划将丢失。默认值为 no。

- `[建筑类型]►FactoryOwners.Permanent=` **（布尔值）**

  玩家是否捕获这种类型的建筑物将永久获得其初始所有者的所有计划。支持升级。默认值为 no。

- `[TechnoType]►FactoryOwners=` **（房屋列表）**

  其工厂可以建造此对象的国家/地区列表。如果为空，则允许每个国家/地区构建此对象。否则，玩家需要拥有此列表中的某个国家建造的至少一家工厂，或者至少一个国家的计划来生产它。

- `[TechnoType]►FactoryOwners.Forbidden=` **（房屋列表）**

  其工厂无法构建此对象的国家/地区列表。仅拥有此列表中的国家/地区建造的工厂并且仅拥有这些国家/地区的计划的玩家将无法生产它。

注意

AI忽略了`工厂所有者`和`工厂所有者，`禁止建筑物使用，但不允许在单位上使用。

*0.6 版中的新功能。*

*在 2.0 版更改。*

## 概述

以下是当前必备系统的流程图。蓝色部分与原始系统相同。粉色部分已被战神修改或添加。



## 通用前置需求组

您现在可以创建自定义通用前置需求组，如现有的 POWER（`PrerequisitePower`）、FACTORY（`PrerequisiteFactory`）、BARRACKS（`PrerequisiteBarracks`）、RADAR（`PrerequisiteRadar`）、TECH（`PrerequisiteTech`）和 PROC （`前置需求过程`和`前置需求过程Alternate`）组。

要创建新组，只需包含新的 `[GenericPrerequisite] 部分，`并添加格式为 `GROUPNAME=`（建筑类型列表）的标志。例如：

```
[GenericPrerequisites]
NAVALYARD=GAYARD,NAYARD,YAYARD
etc...
[TechnoType]
...
Prerequisites=NAVALYARD
...
```

如果声明任何现有组（POWER/FACTORY/BARRACKS/RADAR/TECH/PROC），则将使用 `[GenericPrerequisite]` 部分中指定的 BuildingTypes*，而不是*在原始 PrerequisiteGroup 标志上指定的构建类型（即 `[GenericPrerequisite]►POWER=`，如果指定，将覆盖 `[General]►PrerequisitePower=`).请注意，`[GenericPrerequisites]►PROC=` 不会覆盖或取消 `[General]►PrerequisiteProcAlternate=`。

*0.1 版中的新功能。*



## 非建筑物的备用前置需求

为了支持奴隶矿工作为前置需求，尤里的复仇增加了一个选项，通过拥有已部署的建筑物或未部署的奴隶矿工车辆来满足PROC的要求。这仅通过添加`[常规]►PrerequisiteProcAlternate=（`接受一种车辆类型）来为炼油厂组完成。

Ares 为所有通用前置需求组添加了备用前置需求支持，并扩展了此功能以支持任意技术类型的多个项目。

- `[常规]►前置需求XAlternate=`**（技术类型列表）**

  如果玩家不拥有 `[常规]►PrerequisiteX=` 列表中的建筑物，则这些类型可以替代满足此要求。将 `X` 替换为 `[GenericPrerequisites]` 中的键，第一个字符大写，所有其他字符都小写。例如，上面的NAVALYARD将成为Navalyard。注意不支持使用 BuildingTypes，在此处添加它们可能会产生意外结果。例如，升级将不起作用。

*版本 0.B 中的新功能。*