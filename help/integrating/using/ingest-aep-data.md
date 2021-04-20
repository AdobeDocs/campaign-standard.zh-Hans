---
solution: Campaign Standard
product: campaign
title: 将Adobe Experience Platform受众引入活动
description: 了解如何将Adobe Experience Platform受众引入Campaign Standard。
audience: integrating
content-type: reference
feature: Sources and Destinations
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 894d691f1df3a613bacc74e149e5fdf7f4531d92
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---


# 将Adobe Experience Platform受众收录到活动 {#destinations}

要将Adobe Experience Platform受众引入活动并在工作流中使用它们，您首先需要将Adobe Campaign作为Adobe Experience Platform **Destination**&#x200B;连接，并配置要导出的区段。

配置目标后，数据将导出到您的存储位置，您需要在Campaign Standard中构建专用工作流才能收集它。

## 将Adobe Campaign连接为目标

在Adobe Experience平台中，通过为导出的区段选择存储位置，配置与Adobe Campaign的连接。 此步骤还允许您选择要导出的区段，并指定要包含的其他XDM字段。

有关详细信息，请参阅[目标文档](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html)。

配置目标后，Adobe Experience Platform会在您提供的存储位置创建制表符分隔的.txt或.csv文件。 此操作计划在每24小时执行一次。

您现在可以配置Campaign Standard工作流，以将区段引入活动。

## 在Campaign Standard中创建导入工作流

将Campaign Standard配置为目标后，您需要构建专用工作流以导入Adobe Experience Platform导出的文件。

为此，您需要添加并配置&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动。 有关如何配置此活动的详细信息，请参阅[此部分](../../automating/using/transfer-file.md)。

![](assets/rtcdp-transfer-file.png)

然后，您可以根据自己的需要构建工作流(使用区段投放更新数据库，向区段发送跨渠道等)

例如，下面的工作流每天从您的存储位置下载文件，然后使用区段数据更新活动数据库。

![](assets/rtcdp-workflow.png)

[数据管理用例](../../automating/using/about-workflow-use-cases.md#management)部分提供了工作流工作流示例。

相关主题：

* [数据管理活动](../../automating/using/about-data-management-activities.md)
* [关于数据导入和导出](../../automating/using/about-data-import-and-export.md)
