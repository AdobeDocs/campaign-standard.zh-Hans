---
title: 导出日志
description: 无论日志数据是与分发相关还是与订阅相关，都可以通过一个简单的工作流导出。
page-status-flag: never-activated
uuid: 954e919c-0a33-47c3-9a3c-63c7a2a4edc4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: ca8a95d8-523f-4085-a2fc-e1d8262cfbae
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5ec3497161e89bad4d2ef1ef8a80a87df69860b6

---


# 导出日志{#exporting-logs}

无论日志数据是与分发相关还是与订阅相关，都可以通过一个简单的工作流导出。 它使您能够在自己的报告或BI工具中分析营销活动的结果。

通过使 **[!UICONTROL Incremental query]****[!UICONTROL Extract file]** 用每次执行工作流时只检索新日志和定义输出列的简单活动，您可以获得具有格式和所需所有数据的文件。 然后使用活 **[!UICONTROL Transfer file]**动检索最终文件。 每个工作流执行都由一个计划**[!UICONTROL Scheduler]**。

导出日志操作可由标准用户执行。 私有资源，例如：broadlogs、跟踪日志、排除日志订阅日志和 **Profiles** 上的订阅历史记录日志只能由职能管理员管理。

1. 创建新的工作流，如本节 [中所述](../../automating/using/building-a-workflow.md#creating-a-workflow)。
1. 添加活 **[!UICONTROL Scheduler]**动，然后根据您的需求进行设置。 以下是每月执行的示例。

   ![](assets/export_logs_scheduler.png)

1. 添加活 **[!UICONTROL Incremental query]**动并对其进行配置，以便它选择您需要的日志。 例如，要选择所有新的或更新的广播日志（配置文件交付日志），请执行以下操作：

   * 在选 **[!UICONTROL Properties]**项卡中，将目标资源更改为**&#x200B;交付日志&#x200B;**(broadLogRcp)。

      ![](assets/export_logs_query_properties.png)

   * 在该选 **[!UICONTROL Target]**项卡中，设置条件以检索与2016年或之后发送的交付相对应的所有交付日志。 有关详细信息，请参阅编辑[查询部分](../../automating/using/editing-queries.md#creating-queries)。

      ![](assets/export_logs_query_target.png)

   * 在选项卡 **[!UICONTROL Processed data]**中，选择并**[!UICONTROL Use a date field]** 选择上次修 **改的字段** 。 在工作流的下一次执行中，将只检索在上次执行后将修改或创建的日志。

      ![](assets/export_logs_query_processeddata.png)

      在工作流的第一次执行之后，您可以在此选项卡中看到用于下一次执行的最后一个执行日期。 每次执行工作流时，系统都会自动更新它。 您仍然可以手动输入新值来覆盖此值，以便它符合您的需求。

1. 添加一 **[!UICONTROL Extract file]**个活动，该活动将导出文件中查询的数据：

   * 在选 **[!UICONTROL Extraction]**项卡中，指定文件的名称。

      如果选择该选 **[!UICONTROL Add date and time to the file name]**项，则此名称将在导出日期自动完成，以确保所有提取的文件都是唯一的。 选择要在文件中导出的列。 您可以在此处选择来自相关资源（如交付或配置文件信息）的数据。

      >[!NOTE]
      >
      >要导出每个日志的唯一标识符，请选择该 **[!UICONTROL Delivery log ID]**元素。

      要组织最终文件，可以应用排序。 例如，在日志日期，如下例所示。

      ![](assets/export_logs_extractfile_extraction.png)

   * 在选项卡 **[!UICONTROL File structure]**中，定义输出文件的格式以满足您的需求。

      如果导 **[!UICONTROL Export labels instead of internal values of enumerations]**出枚举值，请选中此选项。 此选项允许检索更短的标签，这些标签易于理解，而不是ID。

1. 添加活 **[!UICONTROL Transfer file]**动并对其进行配置，以将新创建的文件从Adobe Campaign服务器传输到您可以访问它的其他位置，如SFTP服务器。

   * 在选项 **[!UICONTROL General]**卡中，选**[!UICONTROL File upload]** 择以将文件从Adobe Campaign发送到另一台服务器。
   * 在选项卡 **[!UICONTROL Protocol]**中，指定传输参数并选择要使[用的外部帐户](../../administration/using/external-accounts.md#creating-an-external-account)。

1. 添加活 **[!UICONTROL End]**动，确保活动正确结束并保存您的工作流。

   ![](assets/export_logs_example_workflow.png)

您现在可以在外部服务器上执行该工作流并检索输出文件。

**相关主题：**

[工作流](../../automating/using/discovering-workflows.md)
