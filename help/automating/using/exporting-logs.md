---
title: 导出日志
description: 日志数据（无论与投放还是订阅相关）可通过简单的工作流程导出。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 14%

---

# 导出日志{#exporting-logs}

日志数据（无论与投放还是订阅相关）可通过简单的工作流程导出。 它让您能够在自己的报告或BI工具中分析营销活动的结果。

>[!CAUTION]
>
>仅功能 [管理员](../../administration/using/users-management.md#functional-administrators)，替换为 **[!UICONTROL Administration]** 角色和访问权限 **全部** 单位可访问发送日志、消息日志、跟踪日志、排除或订阅日志。 非管理员用户可以定位这些日志，但从链接表（用户档案、投放）开始。

通过使用 **[!UICONTROL Incremental query]** ，它仅在每次执行工作流时检索新日志，并且执行简单 **[!UICONTROL Extract file]** 活动以定义输出列，您可以获得一个包含格式和所需所有数据的文件。 然后使用 **[!UICONTROL Transfer file]** 活动，以检索最终文件。 每个工作流执行都由 **[!UICONTROL Scheduler]**.

导出日志操作可由标准用户执行。 专用资源，例如：broadlog、跟踪日志、排除日志订阅日志和订阅历史记录日志 **配置文件** 只能由功能管理员管理。

1. 创建新工作流，如中所述 [本节](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. 添加 **[!UICONTROL Scheduler]** 活动，并根据您的需要进行设置。 以下是每月执行的示例。

   ![](assets/export_logs_scheduler.png)

1. 添加 **[!UICONTROL Incremental query]** 活动并对其进行配置，以便它可以选择您需要的日志。 例如，要选择所有新的或更新的broadlog（用户档案投放日志），请执行以下操作：

   * 在 **[!UICONTROL Properties]** 选项卡，将目标资源更改为 **投放日志** (broadLogRcp)。

     ![](assets/export_logs_query_properties.png)

   * 在 **[!UICONTROL Target]** 选项卡，设置条件以检索与2016年或之后发送的投放对应的所有投放日志。 欲了解更多信息，请参见 [编辑查询](../../automating/using/editing-queries.md#creating-queries) 部分。

     ![](assets/export_logs_query_target.png)

   * 在 **[!UICONTROL Processed data]** 选项卡，选择 **[!UICONTROL Use a date field]** 并选择 **lastModified** 字段。 在下次执行工作流时，将仅检索在上次执行后将修改或创建的日志。

     ![](assets/export_logs_query_processeddata.png)

     在第一次执行工作流后，您即可在此选项卡中看到将用于下一次执行的最后一次执行日期。每次执行工作流后，系统都会自动更新该日期。您仍然可以手动输入新值来覆盖此值，以使其符合您的需求。

1. 添加 **[!UICONTROL Extract file]** 将导出文件中查询数据的活动：

   * 在 **[!UICONTROL Extraction]** 选项卡，指定文件的名称。

     如果您选择 **[!UICONTROL Add date and time to the file name]** 选项，此名称将自动使用导出日期来完成，以确保所有提取的文件都是唯一的。 选择要在文件中导出的列。 您可以在此处选择来自相关资源（如投放或用户档案信息）的数据。

     >[!NOTE]
     >
     >要导出每个日志的唯一标识符，请选择 **[!UICONTROL Delivery log ID]** 元素。

     要组织最终文件，您可以应用排序。 例如，在日志日期，如以下示例所示。

     ![](assets/export_logs_extractfile_extraction.png)

   * 在 **[!UICONTROL File structure]** 选项卡，根据您的需要定义输出文件的格式。

     如果导出枚举值，请勾选 **[!UICONTROL Export labels instead of internal values of enumerations]** 选项。利用此选项，可检索易于理解的较短标签（而非 ID）。

1. 添加 **[!UICONTROL Transfer file]** 活动，并将其配置为将新创建的文件从Adobe Campaign服务器传输到另一个您可以访问它的位置，如SFTP服务器。

   * 在 **[!UICONTROL General]** 选项卡，选择 **[!UICONTROL File upload]** 因为其目的是将文件从Adobe Campaign发送到另一台服务器。
   * 在 **[!UICONTROL Protocol]** 选项卡，指定传输参数并选择 [外部帐户](../../administration/using/external-accounts.md#creating-an-external-account) 以使用。

1. 添加 **[!UICONTROL End]** 活动，以确保它正确结束并保存您的工作流。

   ![](assets/export_logs_example_workflow.png)

您现在可以执行工作流并在外部服务器上检索输出文件。

**相关主题：**

[工作流](../../automating/using/get-started-workflows.md)
