---
solution: Campaign Standard
product: campaign
title: 配置 Campaign-Experience Manager 集成
description: 通过Adobe Experience Manager集成，您可以直接在AEM中创建内容并在以后的Adobe Campaign中使用它。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 3%

---


# 配置 Campaign-Experience Manager 集成 {#configuration-aem}

Adobe Campaign Standard和Adobe Experience Manager之间的这一集成允许您在Adobe Campaign电子邮件中使用在Adobe Experience Manager创建的内容。

通过此用例，您将学习如何在Adobe Experience Manager创建和管理电子邮件内容，然后通过将电子邮件中的内容导入Adobe Campaign Standard，将其用于您的营销活动。

## 先决条件{#prerequisites}

您应事先确保具有以下元素：

* Adobe Experience Manager创 **作实例**
* Adobe Experience Manager **出版实** 例
* Adobe Campaign实例

## Adobe Campaign Standard配置 {#config-acs}

要同时使用这两个解决方案，您必须配置它们以彼此连接。
配置Adobe Campaign:

1. 您首先需要在> > **[!UICONTROL Adobe Experience Manager instance]** 下配置 **[!UICONTROL Administration]** 外部帐户 **[!UICONTROL Application settings]** 。 **[!UICONTROL External accounts menu]**

1. 使用您的URL配置Adobe Experience Manager **[!UICONTROL Server]** 类型外部帐户 **[!UICONTROL Account]** , **[!UICONTROL Password]**&#x200B;并

   ![](assets/aem_1.png)

1. 检查选项 **[!UICONTROL AEMResourceTypeFilter]** 是否已正确配置。 访问> **[!UICONTROL Options]** >菜单 **[!UICONTROL Administration]** 下 **[!UICONTROL Application settings]** 的菜 **[!UICONTROL Options]** 单。

1. 在该字 **[!UICONTROL Value (text)]** 段中，检查以下语法是否正确：

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. 然后，在> >下的高 **[!UICONTROL Resources]** 级菜 **[!UICONTROL Templates]** 单 **[!UICONTROL Delivery templates]**&#x200B;中，重复现有模板之一以创建特定于Adobe Experience Manager的电子邮件模板。

   ![](assets/aem_3.png)

1. 单击该 **[!UICONTROL Edit properties]** 图标。

   ![](assets/aem_4.png)

1. 在下拉 **[!UICONTROL Content]** 框下，选择字 **[!UICONTROL Adobe Experience Manager]** 段中 **[!UICONTROL Content source]** 的，然后在中选择之前创建的外部帐户 **[!UICONTROL Adobe Experience Manager account]**。

您现在需要在Adobe Experience Manager配置集成。

## Adobe Experience Manager配置 {#config-aem}

要配置Adobe Experience Manager与Adobe Campaign Standard，您必须执行以下步骤：

1. 您首先需要在Adobe Experience Manager创作和发布实例之间配置复制。 Refer to this [section](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. 然后，通过配置专用设备将Adobe Experience Manager与Adobe Campaign连 **[!UICONTROL Cloud Service]**&#x200B;接。 Refer to this [section](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. 您现在需要在创作实例上在Adobe Experience Manager配置外部器。 Refer to this [section](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).

