---
title: 管理活动属性
description: 了解如何管理工作流活动的属性。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 9c47ef72-59af-4b55-8e65-d8f687fb5fbe
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---

# 管理活动属性 {#activity-properties}

## 活动的全局属性 {#global-properties-of-an-activity}

每个活动都有一个&#x200B;**[!UICONTROL General]**&#x200B;选项卡，通过该选项卡可修改特定于活动的常规参数。

![](assets/activity-properties.png)

**[!UICONTROL Properties]**&#x200B;选项卡允许您修改活动的全局参数，特别是标签和ID。 配置此选项卡是可选的。

![](assets/activity-properties2.png)

## 管理活动的叫客过渡 {#managing-an-activity-s-outbound-transitions}

默认情况下，某些活动没有叫客过渡。 您可以从&#x200B;**[!UICONTROL Transitions]**&#x200B;选项卡或活动的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡添加一个进程，以将其他进程应用到同一工作流中的群体。

根据活动，您可以添加多种类型的叫客过渡：

* **标准过渡**：由活动计算的群体
* **没有填充的过渡**：可以添加此类型的叫客过渡以继续工作流，并且不包含任何填充以不占用系统上任何不必要的空间。
* **拒绝**：填充被拒绝。 例如，如果活动的集客数据因不正确或不完整而无法处理。
* **补充**：执行活动后剩余的填充。 例如，如果分段活动配置为仅保存集客群体的某个百分比。

如果适用，请为活动的叫客过渡指定&#x200B;**[!UICONTROL Segment code]**。 利用此段代码，可识别目标群体的子集来自何处，并且以后可用于消息个性化目的。

## 活动执行选项 {#activity-execution-options}

在活动的属性屏幕中，有一个&#x200B;**[!UICONTROL Advanced options]**&#x200B;选项卡，可让您定义活动在出现错误时的执行模式和行为。

要访问这些选项，请在工作流中选择活动，然后使用操作栏中的![](assets/edit_darkgrey-24px.png)按钮将其打开。

![](assets/wkf_advanced_parameters.png)

**[!UICONTROL Execution]**&#x200B;字段允许您定义启动任务时要执行的操作。 这有三个选项：

* **正常**：活动正常执行。
* **启用但不执行**：活动已暂停，因此后续的任何进程都将暂停。 如果您希望在任务启动时出席，这可能会很有用。
* **不启用**：该活动未执行，因此（在同一分支中）之后的所有活动也不执行。

**[!UICONTROL In case of error]**&#x200B;字段允许您指定活动遇到错误时要执行的操作。 有两个选项可用于此目的：

* **挂起进程**：工作流已自动挂起。 然后，工作流状态为&#x200B;**错误**，关联的颜色变为红色。 问题解决后，请重新启动工作流。
* **忽略**：该活动未执行，因此，它之后的任何活动也不执行（在同一分支中）。 事实可能会证明，这对于周期性任务非常有用。 如果分支具有置于上游的调度程序，这应在下一个执行日期触发。

**[!UICONTROL Behavior]**&#x200B;字段允许您定义在使用异步任务时要遵循的过程。 有两个选项可用于此目的：

* **授权了多个任务**：即使第一个任务未完成，也可以同时执行多个任务。
* **当前任务具有优先级**：一旦任务正在进行中，该优先级就更高。 只要一项任务仍在进行中，就不会执行其他任务。

**[!UICONTROL Max. execution duration]**&#x200B;字段允许您指定持续时间，如“30s”或“1h”。 如果活动在指定的持续时间过后未完成，则会触发警报。 这对工作流的运行方式没有影响。

**[!UICONTROL Affinity]**&#x200B;字段允许您强制在特定计算机上执行工作流或工作流活动。 要实现此目的，必须为相关工作流或活动指定一个或多个任务相关性。

**[!UICONTROL Time zone]**&#x200B;字段允许您选择活动的时区。 Adobe Campaign允许您在同一实例上管理多个国家/地区之间的时差。 应用的设置将在创建实例时配置。

>[!NOTE]
>
>默认情况下，如果未选择时区，活动将使用工作流属性中定义的时区。

**评论**&#x200B;字段是允许您添加注释的空闲字段。
