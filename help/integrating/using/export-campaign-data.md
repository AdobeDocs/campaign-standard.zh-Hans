---
title: 将数据从 Campaign 导出到 Adobe Experience Platform
description: 了解如何将数据从Campaign Standard导出到Adobe Experience Platform。
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: eccd2922-0e75-4525-9b60-b48f628deeae
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---

# 将数据从 Campaign 导出到 Adobe Experience Platform {#sources}

要将Campaign Standard数据导出到Adobe Real-time Customer Data Platform (RTCDP)，您首先需要在Campaign Standard中构建一个工作流，以将要共享的数据导出到Amazon Storage Service (S3)或Azure Blob存储位置。

配置工作流并将数据发送到存储位置后，您需要在Adobe Experience Platform中将S3或Azure Blob存储位置连接为&#x200B;**Source**。

>[!NOTE]
>
>请注意，我们建议仅将Campaign生成的数据（例如发送、打开、点击等）导出到Adobe Experience Platform。 从第三方源（如您的CRM）摄取的数据应直接导入Adobe Experience Platform。

## 在Campaign Standard中创建导出工作流

要将数据从Campaign Standard导出到S3或Azure Blob存储位置，您需要构建一个工作流以定向要导出的数据，并将其发送到您的存储位置。

为此，请添加并配置：

* 将目标数据提取到CSV文件中的&#x200B;**[!UICONTROL Extract file]**&#x200B;活动。 有关如何配置此活动的详细信息，请参阅[此部分](../../automating/using/extract-file.md)。

  ![](assets/rtcdp-extract-file.png)

* 用于将CSV文件传输到存储位置的&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动。 有关如何配置此活动的详细信息，请参阅[此部分](../../automating/using/transfer-file.md)。

  ![](assets/rtcdp-transfer-file.png)

例如，以下工作流会定期将日志提取到CSV文件中，然后将文件传输到存储位置。

![](assets/aep-export.png)

数据管理工作流的示例可在[工作流用例](../../automating/using/about-workflow-use-cases.md#management)部分中使用。

相关主题：

* [数据管理活动](../../automating/using/about-data-management-activities.md)
* [关于数据导入和导出](../../automating/using/about-data-import-and-export.md)


## 将存储位置连接为Source

下面列出了在Adobe Experience Platform中将Amazon Storage Service (S3)或Azure Blob存储位置作为&#x200B;**Source**&#x200B;连接的主要步骤。 有关每个步骤的详细信息，请参阅[Source连接器文档](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hans)。

1. 在Adobe Experience Platform **[!UICONTROL Sources]**&#x200B;菜单中，创建与存储位置的连接：

   * [创建Amazon S3源连接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html?lang=zh-Hans)
   * [Azure Blob连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html?lang=zh-Hans)

   >[!NOTE]
   >
   >存储位置可以是Amazon S3、使用密码的SFTP、使用SSH密钥的SFTP或Azure Blob连接。 将数据发送到Adobe Campaign的首选方法是通过Amazon S3或Azure Blob：

   ![](assets/rtcdp-connector.png)

1. 为云存储批处理连接配置数据流。 数据流是一种计划任务，用于在存储位置检索数据并将其摄取到Adobe Experience Platform数据集。 此步骤允许您从存储位置配置数据摄取，包括数据选择和CSV字段到XDM架构的映射。

   [此页面](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html?lang=zh-Hans)中提供了详细信息。

   ![](assets/rtcdp-map-xdm.png)

1. 配置Source后，Adobe Experience Platform将从您提供的存储位置导入文件。

   可以根据您的需要计划此操作。 我们建议每天执行导出多达6次，具体取决于实例中已存在的负载。
