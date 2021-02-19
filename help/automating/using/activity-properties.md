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

## 活动{#global-properties-of-an-activity}的全局属性

每个活动都有一个&#x200B;**[!UICONTROL General]**&#x200B;选项卡，它允许您修改特定于活动的常规参数。

![](assets/activity-properties.png)

**[!UICONTROL Properties]**&#x200B;选项卡允许您修改活动的全局参数，特别是标签和ID。 配置此选项卡是可选的。

![](assets/activity-properties2.png)

## 管理活动的出站过渡{#managing-an-activity-s-outbound-transitions}

默认情况下，某些活动没有出站过渡。 您可以从&#x200B;**[!UICONTROL Transitions]**&#x200B;选项卡或活动的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡中添加一个，以将其他进程应用于同一工作流中的人口。

根据活动，您可以添加几种类型的出站过渡:

* **标准过渡**:由活动计算的人口
* **过渡无人口**:可以添加此类型的出站过渡以继续工作流，并且不包含任何填充以不占用系统上任何不必要的空间。
* **拒绝**:被拒绝。例如，如果由于活动的入站数据不正确或不完整而无法处理该数据。
* **补充**:执行活动后剩余人口。例如，如果分段活动配置为仅保存入站人口的百分比。

如果适用，请为活动的出站过渡指定&#x200B;**[!UICONTROL Segment code]**。 此段代码将允许您确定目标群体中的子集来自何处，并可能稍后用于消息个性化目的。

## 活动执行选项{#activity-execution-options}

在活动的属性屏幕中，有一个&#x200B;**[!UICONTROL Advanced options]**&#x200B;选项卡，允许您定义活动的执行模式和行为，以防发生错误。

要访问这些选项，请在工作流中选择一个活动，然后使用操作栏中的![](assets/edit_darkgrey-24px.png)按钮打开它。

![](assets/wkf_advanced_parameters.png)

**[!UICONTROL Execution]**&#x200B;字段允许您定义启动任务时要执行的操作。 有三种选择：

* **正常**:活动正常执行。
* **启用但不执行**:活动会暂停，因此后续的任何进程也会暂停。如果您希望在任务启动时出现，则此选项可能会很有用。
* **不启用**:活动不会执行，因此，后续的所有活动也不会执行（在同一分支中）。

通过&#x200B;**[!UICONTROL In case of error]**&#x200B;字段，可以指定活动遇到错误时要执行的操作。 有两个选项可用于此：

* **暂停进程**:工作流会自动挂起。然后，工作流状态为&#x200B;**错误**，且与颜色关联的颜色将变为红色。 问题解决后，请重新启动工作流。
* **忽略**:活动不会执行，因此后续的活动也不会执行（在同一分支中）。这可能对循环任务有用。 如果分支将调度程序放在上游，则应在下一个执行日期触发。

**[!UICONTROL Behavior]**&#x200B;字段允许您定义在使用异步任务时要遵循的过程。 有两个选项可用于此：

* **授权多个任务**:即使第一个任务未完成，也可以同时执行多个应用程序。
* **当前任务具有优先级**:一旦任务正在进行中，这就是当务之急。只要一个任务仍在进行中，就不会执行任何其他任务。

**[!UICONTROL Max. execution duration]**&#x200B;字段允许您指定持续时间，如“30s”或“1h”。 如果活动在经过指定的持续时间后未完成，将触发警报。 这不会影响工作流的工作方式。

**[!UICONTROL Affinity]**&#x200B;字段允许您强制在特定计算机上执行工作流或工作流活动。 为此，您必须为相关工作流或活动指定一个或多个关联。

**[!UICONTROL Time zone]**&#x200B;字段允许您选择活动的时区。 Adobe Campaign允许您管理同一实例上多个国家/地区之间的时差。 创建实例时将配置所应用的设置。

>[!NOTE]
>
>默认情况下，如果未选择时区，活动将使用在工作流属性中定义的时区。

**评论**&#x200B;字段是允许您添加注释的免费字段。
