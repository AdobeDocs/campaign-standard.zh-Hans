---
title: 将 Adobe Experience Platform 受众引入 Campaign
description: 了解如何将Adobe Experience Platform受众纳入Campaign Standard。
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 7%

---

# 将 Adobe Experience Platform 受众引入 Campaign {#destinations}

要将Adobe Experience Platform受众摄取到Campaign并在您的工作流中使用它们，您首先需要将Adobe Campaign as a Adobe Experience Platform **目标**&#x200B;连接起来，并使用要导出的区段对其进行配置。

目标配置完成后，数据将导出到您的存储位置，您将需要在Campaign Standard中构建专用工作流来摄取数据。

## 连接Adobe Campaign作为目标

在AdobeExperience Platform中，通过为导出的区段选择存储位置来配置与Adobe Campaign的连接。 此步骤还允许您选择要导出的区段并指定要包含的其他XDM字段。

有关详细信息，请参阅[目标文档](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html?lang=zh-Hans)。

配置目标后，Adobe Experience Platform会在您提供的存储位置创建一个以制表符分隔的.txt或.csv文件。 每24小时安排并执行一次此操作。

您现在可以配置Campaign Standard工作流以将区段摄取到Campaign。

## 在Campaign Standard中创建导入工作流

将Campaign Standard配置为目标后，您需要构建一个专用工作流来导入Adobe Experience Platform已导出的文件。

为此，您需要添加和配置&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动。 有关如何配置此活动的详细信息，请参阅[此部分](../../automating/using/transfer-file.md)。

![](assets/rtcdp-transfer-file.png)

然后，您可以根据需要构建工作流（使用区段数据更新数据库，向区段发送跨渠道投放等）

例如，以下工作流每天从您的存储位置下载文件，然后使用区段数据更新Campaign数据库。

![](assets/rtcdp-workflow.png)

数据管理工作流的示例可在[工作流用例](../../automating/using/about-workflow-use-cases.md#management)部分中使用。

相关主题：

* [数据管理活动](../../automating/using/about-data-management-activities.md)
* [关于数据导入和导出](../../automating/using/about-data-import-and-export.md)
