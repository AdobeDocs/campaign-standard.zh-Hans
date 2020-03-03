---
title: 在 Adobe Experience Manager 中创建电子邮件内容.
description: 通过Adobe Experience manager集成，您可以直接在AEM中创建内容，然后在Adobe Campaign中使用它。
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9efce905cd767013a22afb2a4d642e42b6616ef1

---


# 将Adobe Experience manager内容导入Adobe Campaign电子邮件 {#creating-email-aem}

使用本文档，您将学习如何在Adobe Experience manager中创建和管理电子邮件内容，然后将电子邮件中的内容导入Adobe Campaign standard以将其用于您的营销活动。

先决条件是：

* 访问为集成配置的AEM实例。
* 访问为集成配置的Adobe Campaign实例。
* 配置为接收AEM内容的Adobe Campaign电子邮件模板。

## 在Adobe Experience Manager中访问电子邮件 {#email-content-aem}

登录到Adobe Experience Manager创作实例，然后浏览您的站点以访问包含电子邮件内容的文件夹。

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Creating new email content in Adobe Experience Manager {#creating-email-content-aem}

提供了特定于Adobe Campaign的多个模板。 您必须使用其中一个模板，因为这些模板包含Adobe Campaign支持的预定义组件。

默认情况下，两个预定义的模板允许您为Adobe Campaign创建电子邮件内容。

* **[!UICONTROL Adobe Campaign Email]**:此模板包含可进行个性化设置的标准内容。 您可以选择Adobe Campaign电子邮件(AC6.1)和Adobe Campaign电子邮件(ACS)。
* **[!UICONTROL Importer Page]**:通过此模板，可导入包含HTML文件的ZIP文件，其中包含内容，然后您便可以对其进行个性化设置。

1. 在Adobe Experience manager中，创建新内容 **[!UICONTROL Page]**。

1. 选择模 **[!UICONTROL Adobe Campaign Email]** 板。 有关详细步骤，请参阅以下视频。
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 打开您的新电子邮件内容。

1. 在中 **[!UICONTROL Page properties]**，将 **[!UICONTROL Adobe Campaign]** 设置为 **[!UICONTROL Cloud Service Configuration]**。 这样，您的内容与Adobe Campaign实例之间便可进行通信。

   有关详细信息，请观看以下视频：

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## 编辑和发送电子邮件 {#editing-email-aem}

您可以通过添加组件和资产来编辑电子邮件内容。 个性化字段可用于根据Adobe Campaign中收件人的数据提供更相关的消息。

要在Adobe Experience manager中创建电子邮件内容，请执行以下操作：

1. 通过访问Sidekick中的>选 **[!UICONTROL Plain text]** 项卡，编辑主题和电子邮件 **[!UICONTROL Page properties]** 的 **[!UICONTROL Email]** 版本。

1. 通过 **[!UICONTROL Personalization fields]** 组件添 **[!UICONTROL Text & Personalization]** 加。 每个组件对应于一个特定用法：插入图像、添加个性化等。

   有关详细信息，请观看以下视频：
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. 从选项卡 **[!UICONTROL Workflow]** 中，选择验证工 **[!UICONTROL Approve for Adobe Campaign]** 作流。 如果Adobe Campaign使用的内容未经批准，您将无法在其中发送电子邮件。

1. 定义内容和发送参数后，您可以在Adobe Campaign standard中继续批准、准备和发送电子邮件。

   有关详细信息，请观看以下视频：

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
