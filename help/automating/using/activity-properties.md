---
title: 管理活动属性
description: 了解如何管理工作流活动的属性。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 9c47ef72-59af-4b55-8e65-d8f687fb5fbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---

# 管理活动属性 {#activity-properties}

## 活动的全局属性 {#global-properties-of-an-activity}

每个活动都有 **[!UICONTROL General]** 选项卡，用于修改特定于活动的常规参数。

![](assets/activity-properties.png)

的 **[!UICONTROL Properties]** 选项卡，用于修改活动的全局参数，特别是标签和ID。 配置此选项卡是可选的。

![](assets/activity-properties2.png)

## 管理活动的叫客过渡 {#managing-an-activity-s-outbound-transitions}

默认情况下，某些活动不具有叫客过渡。 您可以从 **[!UICONTROL Transitions]** 选项卡或活动的 **[!UICONTROL Properties]** 选项卡，将其他流程应用到同一工作流中的群体。

根据活动，可以添加多种类型的叫客过渡：

* **标准过渡**:由活动计算的群体
* **无人口过渡**:可以添加此类型的叫客过渡以继续工作流，并且不包含任何群体，以免占用系统上任何不必要的空间。
* **拒绝**:群体被拒绝。 例如，如果由于活动的集客数据不正确或不完整而无法处理该活动的集客数据。
* **补码**:执行活动后剩余的群体。 例如，如果将分段活动配置为仅保存集客群体的百分比。

如果适用，请指定 **[!UICONTROL Segment code]** ，用于活动的叫客过渡。 利用此段代码，可确定目标群体中子集的来源，并稍后可用于消息个性化。

## 活动执行选项 {#activity-execution-options}

在活动的“属性”屏幕中， **[!UICONTROL Advanced options]** 选项卡，用于定义活动的执行模式和在发生错误时的行为。

要访问这些选项，请在工作流中选择一个活动，然后使用 ![](assets/edit_darkgrey-24px.png) 按钮。

![](assets/wkf_advanced_parameters.png)

的 **[!UICONTROL Execution]** 字段，用于定义在启动任务时要执行的操作。 有三个选项可用：

* **正常**:活动正常执行。
* **启用但不执行**:活动会暂停，因此后续的任何后续进程也会暂停。 如果您希望在任务启动时显示该对象，则此选项会非常有用。
* **不启用**:不会执行活动，因此，（在同一分支中）之后的所有活动也不会执行。

的 **[!UICONTROL In case of error]** 字段中，您可以指定在活动遇到错误时要执行的操作。 有两个选项可用于：

* **暂停进程**:工作流自动挂起。 然后，工作流状态为 **错误** 关联的颜色会变为红色。 问题解决后，请重新启动工作流。
* **忽略**:不会执行活动，因此其后（在同一分支中）也不会执行任何活动。 这可能对定期任务非常有用。 如果分支具有上游的调度程序，则应在下一个执行日期触发该事件。

的 **[!UICONTROL Behavior]** 字段，用于定义在使用异步任务时要遵循的过程。 有两个选项可用于：

* **已授权多项任务**:即使第一个任务没有完成，也可以同时执行多个任务。
* **当前任务具有优先级**:任务进行后，将优先执行此操作。 只要一个任务仍在进行中，就不会执行其他任务。

的 **[!UICONTROL Max. execution duration]** 字段，可指定持续时间，如“30秒”或“1h”。 如果活动在指定的持续时间后未完成，则会触发警报。 这对工作流的工作方式没有影响。

的 **[!UICONTROL Affinity]** 字段，可强制在特定计算机上执行工作流或工作流活动。 为此，您必须为相关工作流或活动指定一个或多个相关性。

的 **[!UICONTROL Time zone]** 字段，可选择活动的时区。 Adobe Campaign允许您在同一实例上管理多个国家/地区之间的时间差异。 创建实例时会配置应用的设置。

>[!NOTE]
>
>默认情况下，如果未选择时区，则活动将使用工作流属性中定义的时区。

的 **注释** 字段是用于添加注释的自由字段。
