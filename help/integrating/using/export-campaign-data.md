---
solution: Campaign Standard
product: campaign
title: 将数据从活动导出到Adobe Experience Platform
description: 了解如何将数据从Campaign Standard导出到Adobe Experience Platform。
audience: integrating
content-type: reference
feature: Sources and Destinations
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: bf442b12506ef71cc76aa7fffb0e4c8bb2ce70da
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---


# 将数据从活动导出到Adobe Experience Platform {#sources}

要将Campaign Standard数据导出到Adobe实时客户数据平台(RTCDP)，您首先需要在Campaign Standard中构建一个工作流，以导出到要共享的数据的S3或Azure blob存储位置。

配置工作流并将数据发送到您的存储位置后，您需要将S3或Azure blob存储位置连接为Adobe体验平台中的&#x200B;**Source**。

>[!NOTE]

请注意，我们建议仅导出活动生成的数据（例如发送、打开、单击等） Adobe Experience Platform。 从第三方源（如您的CRM）中摄取的数据应直接导入Adobe Experience Platform。

## 在Campaign Standard中创建导出工作流

要将Campaign Standard从存储导出到S3或Azure Blob位置，您需要构建一个工作流来目标要导出的数据并将其发送到存储位置。

为此，添加和配置：

* **[!UICONTROL Extract file]**&#x200B;活动，用于将目标数据提取到CSV文件中。 有关如何配置此活动的详细信息，请参阅[此部分](../../automating/using/extract-file.md)。

   ![](assets/rtcdp-extract-file.png)

* **[!UICONTROL Transfer file]**&#x200B;活动，用于将CSV文件传输到您的存储位置。 有关如何配置此活动的详细信息，请参阅[此部分](../../automating/using/transfer-file.md)。

   ![](assets/rtcdp-transfer-file.png)

例如，下面的工作流会定期将日志提取到CSV文件中，然后将文件传输到存储位置。

![](assets/aep-export.png)

[数据管理用例](../../automating/using/about-workflow-use-cases.md#management)部分提供了工作流工作流示例。

相关主题：

* [数据管理活动](../../automating/using/about-data-management-activities.md)
* [关于数据导入和导出](../../automating/using/about-data-import-and-export.md)


## 将存储位置连接为源

以下列出了将S3或Azure Blob存储位置连接为Adobe体验平台中的&#x200B;**源**&#x200B;的主要步骤。 [源连接器文档](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html)中提供了有关这些步骤中每个步骤的详细信息。

1. 在Adobe Experience Platform **[!UICONTROL Sources]**&#x200B;菜单中，创建到存储位置的连接：

   * [创建Amazon S3源连接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html)
   * [Azure Blob连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html)

   >[!NOTE]
   >
   >存储位置可以是Amazon S3、带密码的SFTP、带SSH密钥的SFTP或Azure Blob连接。 向Adobe Campaign发送数据的首选方法是通过Amazon S3或Azure Blob:

   ![](assets/rtcdp-connector.png)

1. 为云存储批处理连接配置数据流。 存储流是一个计划任务，它从数据位置检索数据并将数据引入Adobe Experience Platform数据集。 此步骤允许您从存储位置配置数据摄取，包括数据选择和CSV字段到XDM模式的映射。

   有关详细信息，请参阅[此页](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html)。

   ![](assets/rtcdp-map-xdm.png)

1. 配置源后，Adobe Experience Platform将从您提供的存储位置导入文件。

   此操作可以根据您的需要进行计划。 根据实例上已存在的负载，我们建议每天执行最多6次导出。
