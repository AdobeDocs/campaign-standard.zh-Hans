---
solution: Campaign Standard
product: campaign
title: 在 Adobe Experience Manager 中创建电子邮件内容.
description: 借助Adobe Experience Manager集成，您可以直接在AEM中创建内容，然后在Adobe Campaign中使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 2%

---


# 将Adobe Experience Manager内容导入Adobe Campaign电子邮件{#creating-email-aem}

使用此文档，您将学习如何在Adobe Experience Manager中创建和管理电子邮件内容，然后将电子邮件中的内容导入Adobe Campaign Standard，以将其用于您的营销活动。

先决条件包括：

* 访问为集成配置的AEM实例。
* 访问为集成配置的Adobe Campaign实例。
* 配置为接收AEM内容的Adobe Campaign电子邮件模板。

## 访问Adobe Experience Manager {#email-content-aem}中的电子邮件

登录到您的Adobe Experience Manager创作实例并浏览您的站点以访问包含您的电子邮件内容的文件夹。

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## 在Adobe Experience Manager {#creating-email-content-aem}中创建新电子邮件内容

有几个特定于Adobe Campaign的模板可用。 您必须使用其中一个模板，因为它们包含Adobe Campaign支持的预定义组件。

默认情况下，两个预定义的模板允许您创建电子邮件内容以进行Adobe Campaign。

* **[!UICONTROL Adobe Campaign Email]**:此模板包含一个可进行个性化设置的标准内容。您可以在Adobe Campaign电子邮件(AC6.1)和Adobe Campaign电子邮件(ACS)之间进行选择。
* **[!UICONTROL Importer Page]**:通过此模板，您可以导入包含HTML文件的ZIP文件，其中包含内容，随后您便可以进行个性化设置。

1. 在Adobe Experience Manager中，新建一个&#x200B;**[!UICONTROL Page]**。

1. 选择&#x200B;**[!UICONTROL Adobe Campaign Email]**&#x200B;模板。 有关详细步骤，请参阅以下视频。
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 打开新的电子邮件内容。

1. 在&#x200B;**[!UICONTROL Page properties]**&#x200B;中，将&#x200B;**[!UICONTROL Adobe Campaign]**&#x200B;设置为&#x200B;**[!UICONTROL Cloud Service Configuration]**。 这可实现内容与Adobe Campaign实例之间的通信。

   有关更多信息，请观看以下视频：

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## 编辑和发送电子邮件{#editing-email-aem}

您可以通过添加组件和资产来编辑电子邮件内容。 个性化字段可用于根据Adobe Campaign中的收件人数据提供更相关的消息。

要在Adobe Experience Manager中创建电子邮件内容，请执行以下操作：

1. 通过访问Sidekick中的&#x200B;**[!UICONTROL Page properties]** > **[!UICONTROL Email]**&#x200B;选项卡，编辑主题以及电子邮件的&#x200B;**[!UICONTROL Plain text]**&#x200B;版本。

1. 通过&#x200B;**[!UICONTROL Text & Personalization]**&#x200B;组件添加&#x200B;**[!UICONTROL Personalization fields]**。 每个组件对应一个特定用法：插入图像、添加个性化等。

   有关更多信息，请观看以下视频：
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. 从&#x200B;**[!UICONTROL Workflow]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL Approve for Adobe Campaign]**&#x200B;验证工作流。 如果电子邮件使用的内容未经批准，您将无法以Adobe Campaign发送。

1. 定义内容和发送参数后，您可以继续在Adobe Campaign Standard中批准、准备和发送电子邮件。

   有关更多信息，请观看以下视频：

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
