---
title: 导出日志
description: 日志数据（无论与投放还是订阅相关）可通过简单的工作流程导出。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 14%

---

# 导出日志{#exporting-logs}

日志数据（无论与投放还是订阅相关）可通过简单的工作流程导出。 它让您能够在自己的报告或BI工具中分析营销活动的结果。

>[!CAUTION]
>
>只有具有[角色并有权访问](../../administration/using/users-management.md#functional-administrators)所有&#x200B;**[!UICONTROL Administration]**&#x200B;单位的功能&#x200B;**管理员**&#x200B;才能访问发送日志、消息日志、跟踪日志、排除或订阅日志。 非管理员用户可以定位这些日志，但从链接表（用户档案、投放）开始。

通过使用每次执行工作流时仅检索新日志的&#x200B;**[!UICONTROL Incremental query]**&#x200B;和定义输出列的简单&#x200B;**[!UICONTROL Extract file]**&#x200B;活动，可以获得格式和所需所有数据的文件。 然后使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动检索最终文件。 每个工作流执行都由&#x200B;**[!UICONTROL Scheduler]**&#x200B;计划。

导出日志操作可由标准用户执行。 **配置文件**&#x200B;上的专用资源（如：broadlog、跟踪日志、排除日志订阅日志和订阅历史记录日志）只能由功能管理员管理。

1. 按照[此部分](../../automating/using/building-a-workflow.md#creating-a-workflow)中的详细说明创建新工作流。
1. 添加&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动，并根据您的需求进行设置。 以下是每月执行的示例。

   ![](assets/export_logs_scheduler.png)

1. 添加&#x200B;**[!UICONTROL Incremental query]**&#x200B;活动并进行配置，使其选择您需要的日志。 例如，要选择所有新的或更新的broadlog（用户档案投放日志），请执行以下操作：

   * 在&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡中，将目标资源更改为&#x200B;**投放日志** (broadLogRcp)。

     ![](assets/export_logs_query_properties.png)

   * 在&#x200B;**[!UICONTROL Target]**&#x200B;选项卡中，设置条件以检索与2016年或之后发送的投放对应的所有投放日志。 有关详细信息，请参阅[编辑查询](../../automating/using/editing-queries.md#creating-queries)部分。

     ![](assets/export_logs_query_target.png)

   * 在&#x200B;**[!UICONTROL Processed data]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL Use a date field]**&#x200B;并选择&#x200B;**lastModified**&#x200B;字段。 在下次执行工作流时，将仅检索在上次执行后将修改或创建的日志。

     ![](assets/export_logs_query_processeddata.png)

     在第一次执行工作流后，您即可在此选项卡中看到将用于下一次执行的最后一次执行日期。每次执行工作流后，系统都会自动更新该日期。您仍然可以手动输入新值来覆盖此值，以使其符合您的需求。

1. 添加将导出文件中查询数据的&#x200B;**[!UICONTROL Extract file]**&#x200B;活动：

   * 在&#x200B;**[!UICONTROL Extraction]**&#x200B;选项卡中，指定文件的名称。

     如果选择&#x200B;**[!UICONTROL Add date and time to the file name]**&#x200B;选项，此名称将使用导出日期自动完成，以确保所有提取的文件都是唯一的。 选择要在文件中导出的列。 您可以在此处选择来自相关资源（如投放或用户档案信息）的数据。

     >[!NOTE]
     >
     >要导出每个日志的唯一标识符，请选择&#x200B;**[!UICONTROL Delivery log ID]**&#x200B;元素。

     要组织最终文件，您可以应用排序。 例如，在日志日期，如以下示例所示。

     ![](assets/export_logs_extractfile_extraction.png)

   * 在&#x200B;**[!UICONTROL File structure]**&#x200B;选项卡中，定义输出文件的格式以符合您的需要。

     如果导出枚举值，请勾选 **[!UICONTROL Export labels instead of internal values of enumerations]** 选项。利用此选项，可检索易于理解的较短标签（而非 ID）。

1. 添加&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动并将其配置为将新创建的文件从Adobe Campaign服务器传输到另一个可访问它的位置，如SFTP服务器。

   * 在&#x200B;**[!UICONTROL General]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL File upload]**&#x200B;以将文件从Adobe Campaign发送到另一台服务器。
   * 在&#x200B;**[!UICONTROL Protocol]**&#x200B;选项卡中，指定传输参数并选择要使用的[外部帐户](../../administration/using/external-accounts.md#creating-an-external-account)。

1. 添加&#x200B;**[!UICONTROL End]**&#x200B;活动以确保它正确结束并保存您的工作流。

   ![](assets/export_logs_example_workflow.png)

您现在可以执行工作流并在外部服务器上检索输出文件。

**相关主题：**

[工作流](../../automating/using/get-started-workflows.md)
