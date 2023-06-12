---
title: Sources 与 Destinations 入门
description: 了解有关Adobe Experience Platform Sources和Destinations的更多信息。
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 17%

---

# Sources 与 Destinations 入门 {#rtcdp}

## 关于源和目标

借助Adobe Experience Platform，您可以在Campaign Standard和Adobe Real-time Customer Data Platform (RTCDP)之间共享数据。 这允许您在营销活动工作流中定位Adobe Experience Platform受众，然后发送回Adobe Real-time Customer Data Platform与这些受众相关的数据，如发送、打开和点击。

* 替换为 **目标**，将受众从Adobe Experience Platform摄取到Campaign Standard中。 这允许您为营销活动激活已知和未知数据。
* 替换为 **源**，将Campaign Standard数据（例如发送、打开、单击）导出到Adobe Experience Platform。 这样，您就可以将从不同来源收集的数据集中到一个位置，并利用从中获得的见解做更多事情。


>[!IMPORTANT]
>
>在执行此集成时，请记住Adobe Campaign合同中规定的SFTP存储限制、数据库存储限制和活动配置文件限制。

有关Adobe Real-time Customer Data Platform、目标和源的更多详细概述，请参阅以下页面：

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hans)
* [Destinations（目标）文档](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=zh-Hans)
* [Sources（源）文档](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hans)

## 将Campaign Standard与Adobe Experience Platform连接

为了能够在Adobe Experience Platform和Campaign Standard之间共享数据，您首先需要将Adobe Campaign as a **目标**，并将您的AWS S3或Azure Blob存储位置连接为 **来源** 在AdobeExperience Platform中。

配置连接器后，您可以使用工作流设置数据导入或导出到Campaign Standard。

![](assets/rtcdp-schema.png)

有关如何设置这些导入和导出流程的更多详细信息，请参阅以下章节：

* [将 Adobe Experience Platform 受众引入 Campaign](../../integrating/using/ingest-aep-data.md)
* [将数据从 Campaign 导出到 Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
