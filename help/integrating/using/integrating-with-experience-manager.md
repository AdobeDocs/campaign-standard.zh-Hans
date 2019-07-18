---
title: 与Experience Manager集成
seo-title: 与Experience Manager集成
description: 与Experience Manager集成
seo-description: 通过Adobe Experience Manager集成，您可以直接在AEM中创建内容并稍后在Adobe Campaign中使用它。
page-status-flag: 从未激活
uuid: ed6c1b76-87f7-4d23-b5 e2-0765997a905 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: customing-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06 bb7 d633 d2
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Integrating with Experience Manager{#integrating-with-experience-manager}

通过Adobe Campaign Standard与Adobe Experience Manager之间的集成，您可以在Adobe Campaign电子邮件中使用在Adobe Experience Manager中创建的内容。

因此，您可以充分利用Adobe Experience Manager内容编辑功能以及Adobe Campaign的交付和数据管理功能。

>[!NOTE]
>
>您无法对从Adobe Experience Manager导入的内容执行A/B测试。

Adobe Campaign Standard与Adobe Experience Manager6.1、6.2、6.3和6.4兼容。以下部分概述了可执行的操作。For more information, refer to the sections dedicated to [configuration](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html) and the [use](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/campaign.html) of the integration.

## Prerequisites {#prerequisites}

应事先确保具有以下元素：

* An Adobe Experience Manager **authoring** instance
* An Adobe Experience Manager **publishing** instance
* Adobe Campaign实例

## Use case {#use-case}

要在Adobe Experience Manager中创建电子邮件内容，请执行以下操作：

1. 使用专为Adobe Campaign创建的模板创建电子邮件内容。
1. In the content properties, select the **[!UICONTROL Cloud Service]** corresponding to your Adobe Campaign instance.
1. 通过插入文本、图像、个性化等内容来编辑内容。
1. 验证内容。

For more information, refer to the [detailed documentation](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/campaign.html).

![](assets/aem_content.png)

要在Adobe Campaign中检索内容，请执行以下操作：

1. 创建基于Adobe Experience Manager类型内容模板的电子邮件。
1. 使用Adobe Campaign电子邮件内容定义屏幕链接使用Adobe Experience Manager创建的内容。

![](assets/aem_linked_content.png)

## Configuration {#configuration}

要将这两个解决方案结合使用，您必须将它们配置为互相连接。

1. 配置Adobe Campaign。要执行此操作，请执行以下操作：

   * 配置Adobe Experience Manager类型外部帐户。
   * Configure the **AEMResourceTypeFilter** option, which recognizes the content types created in Adobe Experience Manager for Adobe Campaign.
   * 创建一个电子邮件模板，指定它是Adobe Experience Manager内容，并将先前创建的外部帐户链接到此模板。

1. 配置Adobe Experience Manager。要执行此操作，请执行以下操作：

   * 在Adobe Experience Manager创作和发布实例之间配置复制。
   * Connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**.

