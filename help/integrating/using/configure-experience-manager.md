---
title: 配置 Campaign-Experience Manager 集成
description: 通过Adobe Experience Manager集成，您可以直接在AEM中创建内容，并在以后的Adobe Campaign中使用它。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: f56f5a19-6283-4eef-8127-c69a16a42a37
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 6%

---

# 配置 Campaign-Experience Manager 集成 {#configuration-aem}

Adobe Campaign Standard与Adobe Experience Manager之间的这种集成允许您在Adobe Campaign电子邮件中使用在Adobe Experience Manager中创建的内容。

通过此用例，您将了解如何在Adobe Experience Manager中创建和管理电子邮件内容，然后通过将内容导入到Adobe Campaign Standard中，将其用于营销活动。

## 先决条件 {#prerequisites}

您应确保预先具备以下元素：

* Adobe Experience Manager **创作** 实例
* Adobe Experience Manager **发布** 实例
* Adobe Campaign实例

## Adobe Campaign Standard中的配置 {#config-acs}

要同时使用这两种解决方案，必须将其配置为相互连接。
要配置Adobe Campaign，请执行以下操作：

1. 您首先需要配置 **[!UICONTROL Adobe Experience Manager instance]** 外部帐户位于 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. 使用配置Adobe Experience Manager类型外部帐户 **[!UICONTROL Server]** URL， **[!UICONTROL Account]** 和 **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. 检查 **[!UICONTROL AEMResourceTypeFilter]** 选项已正确配置。 访问 **[!UICONTROL Options]** 下的菜单 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** 菜单。

1. 在 **[!UICONTROL Value (text)]** 字段中，检查以下语法是否正确：

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. 然后，在下的高级菜单中 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**，复制其中一个现有模板以创建特定于Adobe Experience Manager的电子邮件模板。

   ![](assets/aem_3.png)

1. 单击 **[!UICONTROL Edit properties]** 图标。

   ![](assets/aem_4.png)

1. 在 **[!UICONTROL Content]** 下拉列表，选择 **[!UICONTROL Adobe Experience Manager]** 在 **[!UICONTROL Content source]** 字段，则您之前在 **[!UICONTROL Adobe Experience Manager account]**.

您现在需要在Adobe Experience Manager中配置集成。

## Adobe Experience Manager中的配置 {#config-aem}

要使用Adobe Campaign Standard配置Adobe Experience Manager，您必须执行以下步骤：

1. 您首先需要配置Adobe Experience Manager创作实例和发布实例之间的复制。 请参阅此[章节](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager)。

1. Adobe Experience Manager Adobe Campaign然后，通过配置专用的 **[!UICONTROL Cloud Service]**. 请参阅此[章节](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign)。

1. 您现在需要在创作实例上配置Adobe Experience Manager中的外部化器。 请参阅此[章节](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer)。
