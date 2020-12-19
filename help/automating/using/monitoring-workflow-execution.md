---
solution: Campaign Standard
product: campaign
title: 监控工作流执行
description: 了解如何监控工作流的执行。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 3%

---


# 监控工作流执行 {#monitoring}

## 工作流日志和任务{#workflow-log-and-tasks}

![](assets/printpreview_darkgrey-24px.png)图标会打开工作流日志和任务菜单。

在工作流执行选项中指定的持续时间内保存工作流历史记录（请参阅[工作流属性](../../automating/using/managing-execution-options.md)）。 因此，在此期间，即使在重新启动后，也会保存所有消息。 如果不希望保存上次执行中的消息，则必须单击![](assets/delete_darkgrey-24px.png)按钮来清除历史记录。

**[!UICONTROL Log]**&#x200B;选项卡包含所有活动或任何选定活动的执行历史记录。 工作流日志按时间顺序对执行的操作和执行错误进行索引。

![](assets/wkf_execution_4.png)

**[!UICONTROL Tasks]**&#x200B;选项卡详细介绍了活动的执行顺序。 单击任务可获取更多信息。

![](assets/wkf_execution_5.png)

在这两个列表中：

* 单击计数器，根据所应用的筛选器查看活动总数。 如果列表中的元素数少于30，则默认显示计数器。
* **[!UICONTROL Configure list]**&#x200B;按钮允许您选择显示的信息、定义列顺序和对列表排序。
* 您可以使用过滤器更快地查找所需的信息。 使用搜索字段在工作流活动名称中查找特定文本(例如：“查询”)和日志。

## 错误管理{#error-management}

发生错误时，工作流暂停，遇到错误时正在执行的活动闪烁红色。

工作流状态将变为红色，错误将记录在日志中。

您可以配置工作流，使其不暂停并继续执行，而不会出现任何错误。 为此，请通过![](assets/edit_darkgrey-24px.png)按钮转到工作流属性，并在&#x200B;**[!UICONTROL Execution]**&#x200B;部分的&#x200B;**如果出现错误**&#x200B;字段中选择&#x200B;**忽略**&#x200B;选项。

在这种情况下，将中止错误任务。 此模式特别适用于设计为稍后重新尝试操作（定期操作）的工作流。

>[!NOTE]
>
>您可以对每个活动单独应用此配置。 为此，请选择一个活动，然后使用快速操作![](assets/edit_darkgrey-24px.png)将其打开。 然后，在&#x200B;**执行选项**&#x200B;选项卡中选择错误管理模式。 请参阅[活动执行选项](../../automating/using/activity-properties.md)。

在[工作流的属性](../../automating/using/managing-execution-options.md)中，提供了与错误管理相关的其他选项。

![](assets/wkf_execution_error.png)

可能的选项包括：

* **[!UICONTROL Supervisors]**:允许您定义在工作流遇到错误时要通知的人员组（电子邮件和应用程序内通知）。如果未定义任何组，则不会通知任何人。 有关Adobe Campaign通知的详细信息，请参阅[Adobe Campaign通知](../../administration/using/sending-internal-notifications.md)。

* **[!UICONTROL In case of error]**:允许您指定在活动遇到错误时要执行的操作。有两个选项可用于此：

   * **暂停进程**:工作流会自动挂起。然后，工作流状态为&#x200B;**错误**，且与颜色关联的颜色将变为红色。 问题解决后，请重新启动工作流。
   * **忽略**:活动不会执行，因此后面的任何活动（在同一分支中）也不会执行。这可能对重复任务有用。 如果分支将调度程序放在上游，则应在下一个执行日期触发。

* **[!UICONTROL Consecutive errors]** :允许您定义在工作流执行自动挂起之前已授权的多个连续错误。

   * 如果指定的数字为&#x200B;**[!UICONTROL 0]**，或者只要未达到指定的数字，就会忽略遇到错误的活动。 其他工作流分支正常执行。

   * 如果达到指定的数量，则整个工作流将挂起并变为&#x200B;**[!UICONTROL Erroneous]**。 如果已定义主管，则会通过电子邮件自动通知他们。 请参阅 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。
