---
solution: Campaign Standard
product: campaign
title: 配置 Campaign-Experience Manager 集成
description: 借助Adobe Experience Manager集成，您可以直接在AEM中创建内容，然后在Adobe Campaign中使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 3672f0bc4ebc551c4eb34660a3a55d44fa726f1a
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 3%

---


# 配置 Campaign-Experience Manager 集成 {#configuration-aem}

Adobe Campaign Standard和Adobe Experience Manager之间的这一集成允许您在Adobe Campaign电子邮件中使用Adobe Experience Manager中创建的内容。

通过此用例，您将学习如何在Adobe Experience Manager中创建和管理电子邮件内容，然后将电子邮件中的内容导入Adobe Campaign Standard，以将其用于您的营销活动。

## 先决条件{#prerequisites}

您应该事先确保具有以下元素：

* Adobe Experience Manager **创作**&#x200B;实例
* Adobe Experience Manager **publishing**&#x200B;实例
* Adobe Campaign实例

## Adobe Campaign Standard中的配置{#config-acs}

要同时使用这两个解决方案，您必须配置它们以彼此连接。
配置Adobe Campaign:

1. 您首先需要在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**&#x200B;下配置&#x200B;**[!UICONTROL Adobe Experience Manager instance]**&#x200B;外部帐户。

1. 使用&#x200B;**[!UICONTROL Server]** URL、**[!UICONTROL Account]**&#x200B;和&#x200B;**[!UICONTROL Password]**&#x200B;配置Adobe Experience Manager类型外部帐户。

   ![](assets/aem_1.png)

1. 检查&#x200B;**[!UICONTROL AEMResourceTypeFilter]**&#x200B;选项是否已正确配置。 访问&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;菜单下的&#x200B;**[!UICONTROL Options]**&#x200B;菜单。

1. 在&#x200B;**[!UICONTROL Value (text)]**&#x200B;字段中，检查以下语法是否正确：

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. 然后，在&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;下的高级菜单中，重复现有模板之一以创建特定于Adobe Experience Manager的电子邮件模板。

   ![](assets/aem_3.png)

1. 单击&#x200B;**[!UICONTROL Edit properties]**&#x200B;图标。

   ![](assets/aem_4.png)

1. 在&#x200B;**[!UICONTROL Content]**&#x200B;下拉列表下，在&#x200B;**[!UICONTROL Content source]**&#x200B;字段中选择&#x200B;**[!UICONTROL Adobe Experience Manager]**，然后在&#x200B;**[!UICONTROL Adobe Experience Manager account]**&#x200B;中选择之前创建的外部帐户。

您现在需要在Adobe Experience Manager中配置集成。

## Adobe Experience Manager中的配置{#config-aem}

要在Adobe Experience Manager中配置Adobe Campaign Standard，必须执行以下步骤：

1. 您首先需要在Adobe Experience Manager创作和发布实例之间配置复制。 请参阅此[部分](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager)。

1. 然后，通过配置专用的&#x200B;**[!UICONTROL Cloud Service]**&#x200B;将Adobe Experience Manager连接到Adobe Campaign。 请参阅此[部分](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign)。

1. 您现在需要在创作实例的Adobe Experience Manager中配置externalizer。 请参阅此[部分](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer)。

