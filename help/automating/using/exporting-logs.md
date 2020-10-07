---
title: 导出日志
description: 无论日志数据是与投放还是订阅相关，都可以通过简单的工作流程导出。
page-status-flag: never-activated
uuid: 954e919c-0a33-47c3-9a3c-63c7a2a4edc4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: ca8a95d8-523f-4085-a2fc-e1d8262cfbae
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 14%

---


# 导出日志{#exporting-logs}

无论日志数据是与投放还是订阅相关，都可以通过简单的工作流程导出。 它允许您在自己的报告或BI工具中分析活动结果。

>[!CAUTION]
>
>只有具有角 [色和](../../administration/using/users-management.md#functional-administrators)访问所 **[!UICONTROL Administration]** 有单元的功能管 **理员** ，才能访问发送日志、消息日志、跟踪日志、排除日志或订阅日志。 非管理员用户可以目标这些日志，但从链接的表(用户档案、投放)开始。

通过使 **[!UICONTROL Incremental query]** 用每次执行工作流时只检索新日志的活动和定义输出列的简单 **[!UICONTROL Extract file]** ，您可以获得具有所需格式和所有数据的文件。 然后使用 **[!UICONTROL Transfer file]** 活动检索最终文件。 每个工作流执行都由一个计划 **[!UICONTROL Scheduler]**。

导出日志操作可由标准用户执行。 私有资源，例如：广播日志、跟踪日志、排除日志订阅日志和订阅历史 **记录日志** ，只能由职能管理员管理。

1. 创建新的工作流，如本 [节所述](../../automating/using/building-a-workflow.md#creating-a-workflow)。
1. 添加 **[!UICONTROL Scheduler]** 活动并根据需要进行设置。 以下是每月执行的示例。

   ![](assets/export_logs_scheduler.png)

1. 添加 **[!UICONTROL Incremental query]** 活动并进行配置，以便选择所需的日志。 例如，要选择所有新的或更新的广播(用户档案投放日志):

   * 在选 **[!UICONTROL Properties]** 项卡中，将目标资源更 **改为** 投放日志(broadLogRcp)。

      ![](assets/export_logs_query_properties.png)

   * 在选项 **[!UICONTROL Target]** 卡中，设置一个条件以检索与2016年或之后发送的投放日志相对应的所有投放。 For more information, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

      ![](assets/export_logs_query_target.png)

   * 在选项卡 **[!UICONTROL Processed data]** 中，选择 **[!UICONTROL Use a date field]** 并选择“上次修 **改时间** ”字段。 在工作流的下一个执行中，将只检索在上次执行后将被修改或创建的日志。

      ![](assets/export_logs_query_processeddata.png)

      在第一次执行工作流后，您即可在此选项卡中看到将用于下一次执行的最后一次执行日期。每次执行工作流后，系统都会自动更新该日期。您仍然可以手动输入新值来覆盖此值，以使其符合您的需求。

1. 添加一 **[!UICONTROL Extract file]** 个活动，它将导出文件中查询的数据：

   * 在选 **[!UICONTROL Extraction]** 项卡中，指定文件的名称。

      如果您选择 **[!UICONTROL Add date and time to the file name]** 此选项，则此名称将在导出日期自动完成，以确保所有提取的文件都是唯一的。 选择要在文件中导出的列。 您可以选择此处来自相关资源(如投放或用户档案信息)的数据。

      >[!NOTE]
      >
      >要导出每个日志的唯一标识符，请选择该 **[!UICONTROL Delivery log ID]** 元素。

      要组织最终文件，可以应用排序。 例如，在日志日期，如下例所示。

      ![](assets/export_logs_extractfile_extraction.png)

   * 在选项卡 **[!UICONTROL File structure]** 中，定义输出文件的格式以满足您的需求。

      如果导出枚举值，请勾选 **[!UICONTROL Export labels instead of internal values of enumerations]** 选项。利用此选项，可检索易于理解的较短标签（而非 ID）。

1. 添加 **[!UICONTROL Transfer file]** 活动并配置它，将新创建的文件从Adobe Campaign服务器传输到您可以访问它的其他位置，如SFTP服务器。

   * 在选 **[!UICONTROL General]** 项卡中， **[!UICONTROL File upload]** 选择以将文件从Adobe Campaign发送到另一台服务器。
   * 在选 **[!UICONTROL Protocol]** 项卡中，指定传输参数并选择要 [使用的](../../administration/using/external-accounts.md#creating-an-external-account) 外部帐户。

1. 添加活动 **[!UICONTROL End]** ，以确保它正确结束并保存您的工作流。

   ![](assets/export_logs_example_workflow.png)

您现在可以在外部服务器上执行该工作流并检索输出文件。

**相关主题：**

[工作流](../../automating/using/get-started-workflows.md)
