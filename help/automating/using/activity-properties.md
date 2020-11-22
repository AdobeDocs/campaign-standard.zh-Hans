---
solution: Campaign Standard
product: campaign
title: 管理活动属性
description: 了解如何管理工作流活动的属性。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---


# 管理活动属性 {#activity-properties}

## 活动的全局属性 {#global-properties-of-an-activity}

每个活动都有 **[!UICONTROL General]** 一个选项卡，通过该选项卡可以修改特定于活动的常规参数。

![](assets/activity-properties.png)

选 **[!UICONTROL Properties]** 项卡允许您修改活动的全局参数，特别是标签和ID。 配置此选项卡是可选的。

![](assets/activity-properties2.png)

## 管理活动的出站过渡 {#managing-an-activity-s-outbound-transitions}

默认情况下，某些活动没有出站过渡。 您可以从选项卡或活动 **[!UICONTROL Transitions]** 选项卡中添加一个， **[!UICONTROL Properties]** 以将其他进程应用到同一工作流中的人口。

根据活动，您可以添加几种类型的出站过渡:

* **标准过渡**:由活动计算的人口
* **过渡无人口**:可以添加此类型的出站过渡以继续工作流，并且不包含任何填充以不占用系统上任何不必要的空间。
* **拒绝**:人口被拒绝。 例如，如果由于活动不正确或不完整而无法处理该数据的入站数据。
* **补充**:执行活动后剩余人口。 例如，如果分段活动配置为仅保存入站人口的百分比。

如果适用，请为 **[!UICONTROL Segment code]** 活动的出站过渡指定。 此段代码将允许您确定目标群体的子集来自何处，并稍后可能用于消息个性化目的。

## 活动执行选项 {#activity-execution-options}

在活动的属性屏幕中，有一个选 **[!UICONTROL Advanced options]** 项卡，用于定义活动的执行模式和行为（如果出错）。

要访问这些选项，请在工作流中选择一个活动，然后使用操作栏 ![](assets/edit_darkgrey-24px.png) 中的按钮将其打开。

![](assets/wkf_advanced_parameters.png)

该 **[!UICONTROL Execution]** 字段允许您定义在启动任务时要执行的操作。 这有三种选择：

* **正常**:活动正常执行。
* **启用但不执行**:活动已暂停，因此后续的任何进程也将暂停。 如果您希望在任务启动时出现，则此功能可能会很有用。
* **不启用**:该活动不会执行，因此，（在同一分支中）后跟的所有活动也不会执行。

该 **[!UICONTROL In case of error]** 字段允许您指定在活动遇到错误时要执行的操作。 有两个选项可用于此：

* **暂停进程**:工作流会自动挂起。 然后，工作流状态 **为“** Errored”（错误），且与颜色关联的颜色将变为红色。 问题解决后，请重新启动工作流。
* **忽略**:活动不会执行，因此后面的任何活动（在同一分支中）也不会执行。 这可能对重复任务有用。 如果分支将调度程序放在上游，则应在下一个执行日期触发。

该 **[!UICONTROL Behavior]** 字段允许您定义在使用异步任务时要遵循的过程。 有两个选项可用于此：

* **多任务授权**:即使第一个任务未完成，也可以同时执行多个数据。
* **当前任务具有优先级**:一旦任务正在进行，这将优先。 只要一个任务仍在进行中，就不会执行任何其他任务。

字 **[!UICONTROL Max. execution duration]** 段允许您指定持续时间，如“30s”或“1h”。 如果活动在经过指定的持续时间后未完成，则会触发警报。 这不会影响工作流的工作方式。

该 **[!UICONTROL Affinity]** 字段允许您强制在特定计算机上执行工作流或工作流活动。 为此，您必须为相关工作流或关联指定一个或多个活动。

该 **[!UICONTROL Time zone]** 字段允许您选择活动的时区。 Adobe Campaign允许您管理同一实例上多个国家／地区之间的时间差。 创建实例时将配置所应用的设置。

>[!NOTE]
>
>默认情况下，如果未选择时区，活动将使用在工作流属性中定义的时区。

“注 **释** ”字段是允许您添加注释的免费字段。
