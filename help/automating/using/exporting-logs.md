---
title: 导出日志
seo-title: 导出日志
description: 导出日志
seo-description: 日志数据(无论它们与交付还是订阅相关)都可以通过简单的工作流程导出。
page-status-flag: 从未激活
uuid: 954e919c -a33-47c3-9a3c-63c7a2a4a4edc4
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 导入和导出数据
discoiquuid: ca8a95d8-523f-4085-a2 fc-e1 d8262 cfbae
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Exporting logs{#exporting-logs}

日志数据(无论它们与交付还是订阅相关)都可以通过简单的工作流程导出。它使您能够在自己的报表或BI工具中分析营销活动的结果。

By using an **[!UICONTROL Incremental query]** that only retrieves new logs every time the workflow is executed and a simple **[!UICONTROL Extract file]** activity to define the output columns, you can get a file with the format and all the data you need. Then use a **[!UICONTROL Transfer file]** activity to retrieve the final file. Each workflow execution is planned by a **[!UICONTROL Scheduler]**.

导出日志操作可由标准用户执行。Private resources such as: broadlogs, tracking logs, exclusion logs subscription logs and subscription history logs on **Profiles** can only be managed by functional administrator.

1. Create a new workflow as detailed in [this section](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Add a **[!UICONTROL Scheduler]** activity and set it according to your needs. 以下是每月执行的示例。

   ![](assets/export_logs_scheduler.png)

1. Add an **[!UICONTROL Incremental query]** activity and configure it so that it selects the logs you need. 例如，要选择所有新的或更新过的日志(配置文件交付日志)，请执行以下操作：

   * In the **[!UICONTROL Properties]** tab, change the target resource to **Delivery logs** (broadLogRcp).

      ![](assets/export_logs_query_properties.png)

   * **[!UICONTROL Target]** 在选项卡中，设置一个条件，以检索与2016年或之后发送的分发相对应的所有交付日志。For more information, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

      ![](assets/export_logs_query_target.png)

   * In the **[!UICONTROL Processed data]** tab, select **[!UICONTROL Use a date field]** and choose the **lastModified** field. 在工作流的下一个执行过程中，只能在检索上次执行后修改或创建的日志。

      ![](assets/export_logs_query_processeddata.png)

      在第一次执行工作流后，您可以在此选项卡中看到将用于下一次执行的最后一个执行日期。每次执行工作流时，都会自动更新它。您仍可以手动输入新值来覆盖此值，从而满足您的需求。

1. Add an **[!UICONTROL Extract file]** activity that will export the queried data in a file:

   * In the **[!UICONTROL Extraction]** tab, specify the name of the file. 此名称将自动完成导出之日，以确保所有提取的文件都是唯一的。

      选择要在文件中导出的列。您可以在此处选择来自相关资源的数据，例如交付或配置文件信息。要组织最终文件，您可以应用排序。例如，日志日期上的示例，如下面的示例所示。

      ![](assets/export_logs_extractfile_extraction.png)

      >[!NOTE]
      >
      >无法导出日志资源的唯一标识符(主键)。

   * **[!UICONTROL File structure]** 在选项卡中，定义输出文件的格式以满足您的需求。

      Check the **[!UICONTROL Export labels instead of internal values of enumerations]** option in case you export enumeration values. 此选项可检索更短的标签，便于理解而不是ID。

1. Add a **[!UICONTROL Transfer file]** activity and configure it to transfer the newly created file from the Adobe Campaign server to another location where you can access it, such as a SFTP server.

   * In the **[!UICONTROL General]** tab, select **[!UICONTROL File upload]** as the purpose is to send the file from Adobe Campaign to another server.
   * In the **[!UICONTROL Protocol]** tab, specify the transfer parameters and select the [external account](../../administration/using/external-accounts.md#creating-an-external-account) to use.

1. Add an **[!UICONTROL End]** activity to make sure it properly ends and save your workflow.

   ![](assets/export_logs_example_workflow.png)

您现在可以执行工作流并检索外部服务器上的输出文件。

**相关主题：**

[工作流](../../automating/using/discovering-workflows.md)
