---
solution: Campaign Standard
product: campaign
title: 导出日志
description: 无论日志数据是与投放还是订阅相关，都可以通过简单的工作流程导出。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 14%

---


# 导出日志{#exporting-logs}

无论日志数据是与投放还是订阅相关，都可以通过简单的工作流程导出。 它使您能够在自己的报告或BI工具中分析活动的结果。

>[!CAUTION]
>
>只有具有&#x200B;**[!UICONTROL Administration]**&#x200B;角色和对&#x200B;**所有**&#x200B;单元的功能[管理员](../../administration/using/users-management.md#functional-administrators)可访问发送日志、消息日志、跟踪日志、排除日志或订阅日志。 非管理员用户可以目标这些日志，但从链接的表(用户档案、投放)开始。

通过使用每次执行工作流时仅检索新日志的&#x200B;**[!UICONTROL Incremental query]**&#x200B;和用简单的&#x200B;**[!UICONTROL Extract file]**&#x200B;活动来定义输出列，您可以获得具有格式和所需所有数据的文件。 然后使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动检索最终文件。 每个工作流执行都由&#x200B;**[!UICONTROL Scheduler]**&#x200B;计划。

导出日志操作可由标准用户执行。 专用资源，例如：**用户档案**&#x200B;上的broadlog、跟踪日志、排除日志订阅日志和订阅历史记录日志只能由功能管理员管理。

1. 创建新工作流，详见[本节](../../automating/using/building-a-workflow.md#creating-a-workflow)。
1. 添加&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动，并根据您的需要进行设置。 以下是每月执行的示例。

   ![](assets/export_logs_scheduler.png)

1. 添加&#x200B;**[!UICONTROL Incremental query]**&#x200B;活动并对其进行配置，以便选择所需的日志。 例如，要选择所有新的或更新的广播(用户档案投放日志):

   * 在&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡中，将目标资源更改为&#x200B;**投放日志**(broadLogRcp)。

      ![](assets/export_logs_query_properties.png)

   * 在&#x200B;**[!UICONTROL Target]**&#x200B;选项卡中，设置一个条件以检索与2016年或之后发送的投放日志相对应的所有投放。 有关详细信息，请参阅[编辑查询](../../automating/using/editing-queries.md#creating-queries)部分。

      ![](assets/export_logs_query_target.png)

   * 在&#x200B;**[!UICONTROL Processed data]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL Use a date field]**&#x200B;并选择&#x200B;**lastModified**&#x200B;字段。 在工作流的下一个执行中，将只检索在上次执行后将修改或创建的日志。

      ![](assets/export_logs_query_processeddata.png)

      在第一次执行工作流后，您即可在此选项卡中看到将用于下一次执行的最后一次执行日期。每次执行工作流后，系统都会自动更新该日期。您仍然可以手动输入新值来覆盖此值，以使其符合您的需求。

1. 添加&#x200B;**[!UICONTROL Extract file]**&#x200B;活动，以将查询的数据导出到文件中：

   * 在&#x200B;**[!UICONTROL Extraction]**&#x200B;选项卡中，指定文件的名称。

      如果选择&#x200B;**[!UICONTROL Add date and time to the file name]**&#x200B;选项，则此名称将在导出日期自动完成，以确保所有提取的文件都是唯一的。 选择要在文件中导出的列。 您可以在此处选择来自相关资源(如投放或用户档案信息)的数据。

      >[!NOTE]
      >
      >要导出每个日志的唯一标识符，请选择&#x200B;**[!UICONTROL Delivery log ID]**&#x200B;元素。

      要组织最终文件，可以应用排序。 例如，在日志日期，如下例所示。

      ![](assets/export_logs_extractfile_extraction.png)

   * 在&#x200B;**[!UICONTROL File structure]**&#x200B;选项卡中，定义输出文件的格式以满足您的需求。

      如果导出枚举值，请勾选 **[!UICONTROL Export labels instead of internal values of enumerations]** 选项。利用此选项，可检索易于理解的较短标签（而非 ID）。

1. 添加&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动并配置它，将新创建的文件从Adobe Campaign服务器传输到您可以访问它的其他位置，如SFTP服务器。

   * 在&#x200B;**[!UICONTROL General]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL File upload]**，因为目的是将文件从Adobe Campaign发送到另一台服务器。
   * 在&#x200B;**[!UICONTROL Protocol]**&#x200B;选项卡中，指定传输参数并选择要使用的[外部帐户](../../administration/using/external-accounts.md#creating-an-external-account)。

1. 添加&#x200B;**[!UICONTROL End]**&#x200B;活动，确保正确结束并保存您的工作流。

   ![](assets/export_logs_example_workflow.png)

您现在可以在外部服务器上执行该工作流并检索输出文件。

**相关主题：**

[工作流](../../automating/using/get-started-workflows.md)
