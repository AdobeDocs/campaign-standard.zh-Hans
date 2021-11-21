---
title: 在 Adobe Experience Manager 中创建电子邮件内容.
description: 通过Adobe Experience Manager集成，您可以直接在AEM中创建内容，稍后在Adobe Campaign中使用它。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 72b99864-d9d9-4cf4-be06-dc5719a2e4f2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 2%

---

# 将Adobe Experience Manager内容导入Adobe Campaign电子邮件 {#creating-email-aem}

通过本文档，您将了解如何在Adobe Experience Manager中创建和管理电子邮件内容，然后将这些内容导入Adobe Campaign Standard中，以用于您的营销活动。

先决条件包括：

* 访问为集成配置的AEM实例。
* 访问为集成配置的Adobe Campaign实例。
* 配置为接收AEM内容的Adobe Campaign电子邮件模板。

## 在Adobe Experience Manager中访问电子邮件 {#email-content-aem}

登录到Adobe Experience Manager创作实例，然后浏览您的网站以访问包含电子邮件内容的文件夹。

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## 在Adobe Experience Manager中创建新电子邮件内容 {#creating-email-content-aem}

提供了多个特定于Adobe Campaign的模板。 您必须使用其中一个模板，因为它们包含Adobe Campaign支持的预定义组件。

默认情况下，利用两个预定义模板，可为Adobe Campaign创建电子邮件内容。

* **[!UICONTROL Adobe Campaign Email]**:此模板包含可进行个性化的标准内容。 您可以在“Adobe Campaign电子邮件(AC6.1)”和“Adobe Campaign电子邮件(ACS)”之间进行选择。
* **[!UICONTROL Importer Page]**:利用此模板，可导入包含HTML文件的ZIP文件，其中包含您随后可以个性化的内容。

1. 在Adobe Experience Manager中，创建新 **[!UICONTROL Page]**.

1. 选择 **[!UICONTROL Adobe Campaign Email]** 模板。 有关详细步骤，请参阅以下视频。
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 打开新的电子邮件内容。

1. 在 **[!UICONTROL Page properties]**，设置 **[!UICONTROL Adobe Campaign]** 作为 **[!UICONTROL Cloud Service Configuration]**. 这样，您就可以在内容与Adobe Campaign实例之间进行通信。

   有关更多信息，请观看以下视频：

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## 编辑和发送电子邮件 {#editing-email-aem}

您可以通过添加组件和资产来编辑电子邮件内容。 个性化字段可用于根据Adobe Campaign中的收件人数据提供更相关的消息。

要在Adobe Experience Manager中创建电子邮件内容，请执行以下操作：

1. 编辑主题以及 **[!UICONTROL Plain text]** 通过访问 **[!UICONTROL Page properties]** > **[!UICONTROL Email]** 选项卡。

1. 添加 **[!UICONTROL Personalization fields]** 到 **[!UICONTROL Text & Personalization]** 组件。 每个组件都对应于一个特定用法：插入图像、添加个性化等。

   有关更多信息，请观看以下视频：
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. 从 **[!UICONTROL Workflow]** 选项卡，选择 **[!UICONTROL Approve for Adobe Campaign]** 验证工作流。 如果电子邮件使用的内容未获得批准，则将无法在Adobe Campaign中发送电子邮件。

1. 定义内容和发送参数后，您可以继续在Adobe Campaign Standard中批准、准备和发送电子邮件。

   有关更多信息，请观看以下视频：

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
