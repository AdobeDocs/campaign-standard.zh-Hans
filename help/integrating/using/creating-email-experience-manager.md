---
solution: Campaign Standard
product: campaign
title: 在 Adobe Experience Manager 中创建电子邮件内容.
description: 通过Adobe Experience Manager集成，您可以直接在AEM中创建内容并在以后的Adobe Campaign中使用它。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 2%

---


# 将Adobe Experience Manager内容导入Adobe Campaign电子邮件 {#creating-email-aem}

使用此文档，您将学习如何在Adobe Experience Manager创建和管理电子邮件内容，然后将这些内容导入到Adobe Campaign Standard，以便用于您的营销活动。

先决条件包括：

* 访问为集成配置的AEM实例。
* 访问为集成配置的Adobe Campaign实例。
* 配置为接收AEM内容的Adobe Campaign电子邮件模板。

## 访问Adobe Experience Manager的电子邮件 {#email-content-aem}

登录到您的Adobe Experience Manager创作实例，浏览您的站点以访问包含您的电子邮件内容的文件夹。

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Creating new email content in Adobe Experience Manager {#creating-email-content-aem}

有几个特定于Adobe Campaign的模板可用。 您必须使用其中一个模板，因为它们包含Adobe Campaign支持的预定义组件。

默认情况下，两个预定义的模板允许您创建电子邮件内容以进行Adobe Campaign。

* **[!UICONTROL Adobe Campaign Email]**:此模板包含可进行个性化的标准内容。 您可以选择Adobe Campaign电子邮件(AC6.1)和Adobe Campaign电子邮件(ACS)。
* **[!UICONTROL Importer Page]**:通过此模板，可导入包含HTML文件的ZIP文件，其中包含内容，随后您便可以进行个性化。

1. 在Adobe Experience Manager，创建新 **[!UICONTROL Page]**。

1. 选择模 **[!UICONTROL Adobe Campaign Email]** 板。 有关详细步骤，请参阅以下视频。
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 打开您的新电子邮件内容。

1. 在 **[!UICONTROL Page properties]**&#x200B;中， **[!UICONTROL Adobe Campaign]** 设置为 **[!UICONTROL Cloud Service Configuration]**。 这允许内容与Adobe Campaign实例之间进行通信。

   有关详细信息，请观看以下视频：

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## 编辑和发送电子邮件 {#editing-email-aem}

您可以通过添加组件和资产来编辑电子邮件内容。 个性化字段可以根据Adobe Campaign中的收件人数据来提供更相关的消息。

要在Adobe Experience Manager创建电子邮件内容，请执行以下操作：

1. 通过访问Sidekick中的>选 **[!UICONTROL Plain text]** 项卡，编辑电子邮件的主 **[!UICONTROL Page properties]** 题 **[!UICONTROL Email]** 和版本。

1. 通 **[!UICONTROL Personalization fields]** 过组件 **[!UICONTROL Text & Personalization]** 添加。 每个组件对应于一个特定用法：插入图像、添加个性化等。

   有关详细信息，请观看以下视频：
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. 从选项卡 **[!UICONTROL Workflow]** 中，选择验证 **[!UICONTROL Approve for Adobe Campaign]** 工作流。 如果电子邮件使用的内容未经批准，您将无法以Adobe Campaign发送电子邮件。

1. 定义内容和发送参数后，您可以继续在Adobe Campaign Standard批准、准备和发送电子邮件。

   有关详细信息，请观看以下视频：

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
