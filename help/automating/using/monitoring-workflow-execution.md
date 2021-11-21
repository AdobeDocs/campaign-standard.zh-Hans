---
title: 监控工作流执行
description: 了解如何监控工作流的执行。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d2ce702b-92d1-4b94-bd47-34ef46a8bd9f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 3%

---

# 监控工作流执行 {#monitoring}

## 工作流日志和任务 {#workflow-log-and-tasks}

的 ![](assets/printpreview_darkgrey-24px.png) 图标，打开工作流日志和任务菜单。

工作流历史记录会在工作流执行选项中指定的持续时间内保存(请参阅 [工作流属性](../../automating/using/managing-execution-options.md))。 因此，在此时间段内，即使重新启动后，也会保存所有消息。 如果不想保存上次执行的消息，则必须通过单击 ![](assets/delete_darkgrey-24px.png) 按钮。

的 **[!UICONTROL Log]** 选项卡包含所有活动或任何选定活动的执行历史记录。 工作流日志按时间顺序对执行的操作和执行错误进行索引。

![](assets/wkf_execution_4.png)

的 **[!UICONTROL Tasks]** 选项卡详细列出了活动的执行顺序。 单击任务可获取更多信息。

![](assets/wkf_execution_5.png)

在以下两个列表中：

* 单击计数器可查看根据所应用的过滤器划分的活动总数。 如果列表中的元素数少于30，则默认情况下会显示计数器。
* 的 **[!UICONTROL Configure list]** 按钮可选择显示的信息、定义列顺序和对列表进行排序。
* 您可以使用过滤器更快地找到所需的信息。 使用搜索字段可在工作流活动名称中查找特定文本(例如：“query”)和日志。

## 错误管理 {#error-management}

发生错误时，工作流暂停，遇到错误时正在执行的活动闪烁红色。

工作流状态将变为红色，并且错误会记录在日志中。

您可以配置工作流，使其不会暂停并继续执行，而不会出现任何错误。 为此，请通过 ![](assets/edit_darkgrey-24px.png) 按钮和 **[!UICONTROL Execution]** 选择 **忽略** 选项 **出错** 字段。

在这种情况下，错误任务被中止。 此模式特别适用于设计为稍后重新尝试操作（定期操作）的工作流。

>[!NOTE]
>
>您可以为每个活动单独应用此配置。 要执行此操作，请选择活动，然后使用快速操作将其打开 ![](assets/edit_darkgrey-24px.png). 然后，在 **执行选项** 选项卡。 请参阅 [活动执行选项](../../automating/using/activity-properties.md).

在 [工作流的属性](../../automating/using/managing-execution-options.md)，提供了与错误管理相关的其他选项。

![](assets/wkf_execution_error.png)

可能的选项包括：

* **[!UICONTROL Supervisors]**:允许您定义在工作流遇到错误时要通知的人员组（电子邮件和应用程序内通知）。 如果未定义任何组，则不会通知任何人。 有关Adobe Campaign通知的更多信息，请参阅 [Adobe Campaign通知](../../administration/using/sending-internal-notifications.md).

* **[!UICONTROL In case of error]**:允许您指定在活动遇到错误时要执行的操作。 有两个选项可用于：

   * **暂停进程**:工作流自动挂起。 然后，工作流状态为 **错误** 关联的颜色会变为红色。 问题解决后，请重新启动工作流。
   * **忽略**:不会执行活动，因此其后（在同一分支中）也不会执行任何活动。 这可能对定期任务非常有用。 如果分支具有上游的调度程序，则应在下一个执行日期触发该事件。

* **[!UICONTROL Consecutive errors]** :允许您定义在工作流执行自动暂停之前已授权的连续错误数。

   * 如果指定的编号为 **[!UICONTROL 0]**，或者，只要未达到指定的数字，就会忽略遇到错误的活动。 其他工作流分支会正常执行。

   * 如果达到指定的数字，则整个工作流将挂起并变为 **[!UICONTROL Erroneous]**. 如果已定义主管，则会通过电子邮件自动通知他们。 请参阅 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。
