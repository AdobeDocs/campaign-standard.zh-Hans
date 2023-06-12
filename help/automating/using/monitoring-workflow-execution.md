---
title: 监控工作流执行
description: 了解如何监测工作流的执行。
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
ht-degree: 6%

---

# 监控工作流执行 {#monitoring}

## 工作流日志和任务 {#workflow-log-and-tasks}

此 ![](assets/printpreview_darkgrey-24px.png) 图标打开工作流日志和任务菜单。

工作流历史记录会保存在工作流执行选项中指定的持续时间内(请参阅 [工作流属性](../../automating/using/managing-execution-options.md))。 因此，在此持续时间内，所有消息都会被保存，即使在重新启动后也是如此。 如果不想保存上一次执行的消息，则必须通过单击 ![](assets/delete_darkgrey-24px.png) 按钮。

此 **[!UICONTROL Log]** 选项卡包含所有活动或任何选定活动的执行历史记录。 工作流日志按时间顺序对执行的操作和执行错误进行索引。

![](assets/wkf_execution_4.png)

此 **[!UICONTROL Tasks]** 选项卡详细介绍了活动的执行顺序。 单击任务以获取更多信息。

![](assets/wkf_execution_5.png)

在以下两个列表中：

* 单击计数器可查看根据应用的过滤器而定的活动总数。 如果列表中的元素数少于30，则默认显示计数器。
* 此 **[!UICONTROL Configure list]** 按钮允许您选择显示的信息、定义列顺序以及对列表进行排序。
* 您可以使用过滤器更快地查找所需的信息。 使用搜索字段在工作流活动名称（例如：“query”）和日志中查找特定文本。

## 错误管理 {#error-management}

发生错误时，工作流将暂停，并且在遇到错误时执行的活动将呈红色闪烁。

工作流状态将变为红色，并在日志中记录错误。

您可以配置工作流，使其不会暂停并继续执行，而不会出现任何错误。 要实现此目的，请通过 ![](assets/edit_darkgrey-24px.png) 按钮，在 **[!UICONTROL Execution]** 部分，选择 **忽略** 中的选项 **发生错误时** 字段。

在这种情况下，错误任务将中止。 此模式特别适合用于稍后重新尝试操作（定期操作）的工作流。

>[!NOTE]
>
>您可以为每个活动单独应用此配置。 要实现此目的，请选择一个活动，然后使用快速操作将其打开 ![](assets/edit_darkgrey-24px.png). 然后，在中选择错误管理模式 **执行选项** 选项卡。 参见 [活动执行选项](../../automating/using/activity-properties.md).

在 [工作流的属性](../../automating/using/managing-execution-options.md)，提供了其他与错误管理相关的选项。

![](assets/wkf_execution_error.png)

可能的选项为：

* **[!UICONTROL Supervisors]**：用于定义工作流遇到错误时要通知的人员组（电子邮件和应用程序内通知）。 如果未定义组，则不会通知任何人。 有关 Adobe Campaign 通知的更多信息，请参阅 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。

* **[!UICONTROL In case of error]**：用于指定活动遇到错误时要执行的操作。 有两个选项可用于此目的：

   * **暂停进程**：工作流自动挂起。 然后，工作流状态为 **错误** 而关联的颜色会变红。 问题解决后，请重新启动工作流。
   * **忽略**：活动不会执行，因此它之后的任何活动都不会执行（在同一分支中）。 这可能已被证明对周期性任务有用。 如果分支具有放置在上游的调度程序，这应在下一个执行日期触发。

* **[!UICONTROL Consecutive errors]** ：用于定义在工作流执行自动暂停之前获得授权的连续错误数。

   * 如果指定的数字为 **[!UICONTROL 0]**，或者只要未达到指定的数字，则会忽略遇到错误的活动。 其他工作流分支正常执行。

   * 如果达到指定的数量，则整个工作流将挂起，并变为 **[!UICONTROL Erroneous]**. 如果已经定义了主管，则会自动通过电子邮件通知他们。 请参阅 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。
