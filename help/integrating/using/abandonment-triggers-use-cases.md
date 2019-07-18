---
title: 放弃触发器使用案例
seo-title: 放弃触发器使用案例
description: 放弃触发器使用案例
seo-description: 了解如何使用Experience Cloud触发器与这些不同的使用案例相集成。
page-status-flag: 从未激活
uuid: e236165-afd5-4155-9151-c1941 dc0 af99
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: 使用营销活动和触发器
discoiquuid: 1b aeec5-70bb-4d72-a3 e9-12342abf08 f7
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Abandonment Triggers use cases{#abandonment-triggers-use-cases}

本节介绍不同的使用案例，这些用例可使用Adobe Campaign和Experience Cloud触发器之间的集成实现。您将找到两个用例示例：

* [浏览放弃触发器](../../integrating/using/abandonment-triggers-use-cases.md#browse-abandonment-trigger)：向放弃访问您网站的客户发送通信。
* [搜索放弃触发器](../../integrating/using/abandonment-triggers-use-cases.md#search-abandonment-trigger)：与在您的网站上进行搜索的访客重新互动，但没有购买。

>[!NOTE]
>
>本节所述的使用案例依赖Experience Cloud访客ID。也可以使用Experience Cloud声明ID实施这些操作。还支持散列和加密的声明ID。您可以直接解密加密的电子邮件地址/移动号码，以将电子邮件/SMS发送到Campaign中不存在的配置文件。但在这种情况下，无法使用个人资料数据进行个性化。

## Pre-requisites {#pre-requisites}

要实现这些使用案例，您需要访问以下解决方案/核心服务：

* Adobe Campaign
* Adobe Analytics Ultimate、Premium、Foundation、OD、Select、Prime、Mobile Apps、Select或Standard。
* Experience Cloud触发器核心服务
* Experience Cloud DTM核心服务
* Experience Cloud访客ID和Experience Cloud People Core Service

您还需要有一个工作网站。

For more information, refer to [Configuring solutions and services](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services).

## Browse abandonment Trigger {#browse-abandonment-trigger}

在此用例中，我们将创建一个简单触发器，客户端每次放弃访问网站上的访问时将触发它。此示例假定您已将DTM收集并推送到Adobe Analytics，并将所有活动都创建了。

### Creating an Experience Cloud Trigger {#creating-an-experience-cloud-trigger}

1. Select **[!UICONTROL Manage Triggers]** from the Experience Cloud Activation Core Service menu.

   ![](assets/trigger_uc_browse_1.png)

1. Choose a trigger type ( **[!UICONTROL Abandonment]** in our use case).

   ![](assets/trigger_uc_browse_2.png)

1. 对于此用例，我们需要一个简单的放弃触发器。业务目的是识别浏览旅行预订网站的访客，看看“交易”页面，但不要看书。识别此受众后，我们希望在很短的时间内触及这些受众。在此示例中，我们选择在10分钟后发送触发器。

   ![](assets/trigger_uc_browse_3.png)

### Using the trigger in Adobe Campaign {#using-the-trigger-in-adobe-campaign}

现在我们创建了Experience Cloud触发器，让我们在Adobe Campaign中使用它。

在Adobe Campaign中，您需要创建与在Experience Cloud中创建的触发器相关联的触发器。

1. To create the Trigger in Adobe Campaign, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud triggers]**.

   ![](assets/remarketing_1.png)

1. Click **[!UICONTROL Create]**.
1. Select the Trigger you created earlier and click **[!UICONTROL Next]**.

   ![](assets/trigger_uc_browse_5.png)

1. Select the **[!UICONTROL Email]** channel and the **[!UICONTROL Real-time event]** targeting dimension and click **[!UICONTROL Create]**.

   ![](assets/trigger_uc_browse_6bis.png)

1. 在Adobe Campaign中发布触发器。此过程将自动创建交易消息模板。

   ![](assets/trigger_uc_browse_6.png)

1. To dislay the message template, click the **[!UICONTROL More]** button, on the top right, then click **[!UICONTROL Trigger Transactional Template]**.
1. 个性化内容和发送方详细信息。

   ![](assets/trigger_uc_browse_8.png)

1. 发布消息模板。触发器现在是实时的和功能的。

   ![](assets/trigger_uc_browse_0.png)

### Running the scenario {#running-the-scenario}

1. 此用例以Adobe Campaign发送给受众的初始电子邮件开头。

   ![](assets/trigger_uc_browse_9.png)

1. 收件人将打开电子邮件。

   ![](assets/trigger_uc_browse_10.png)

1. 他点击了一个链接，将其带到您的网站。在此示例中，横幅将收件人带到旅行预订网站的主页。

   ![](assets/trigger_uc_browse_11.png)

1. 收件人转到“交易”页面，但突然停止访问。在10分钟后，Adobe Campaign会触发交易消息的发送。

   ![](assets/trigger_uc_browse_12.png)

1. 您可以随时检查Experience Cloud日志，查看触发触发次数。

   ![](assets/trigger_uc_browse_13.png)

1. 您还可以显示Adobe Campaign触发器报告。

   ![](assets/trigger_uc_browse_14.png)

## Search abandonment Trigger {#search-abandonment-trigger}

在此用例中，我们将创建一个触发器，该触发器可重新吸引访问我们旅行预订网站、搜索目标的访客、发现没有成功的结果，并且此后没有预订任何内容。The general process is the same as in the previous use case (see [Browse abandonment Trigger](../../integrating/using/abandonment-triggers-use-cases.md#browse-abandonment-trigger)). 我们将重点介绍如何个性化再营销电子邮件。

### Creating an Experience Cloud Trigger {#creating-an-experience-cloud-trigger-1}

按照上一用例中所述的步骤创建Experience Cloud触发器。See [Creating an Experience Cloud Trigger](../../integrating/using/abandonment-triggers-use-cases.md#creating-an-experience-cloud-trigger). 主要区别在于触发器定义。

![](assets/trigger_uc_search_1.png)

**[!UICONTROL Include Meta Data]** 此部分允许您将从Analytics收集的任何数据传递给触发有效负荷。在此示例中，我们创建一个自定义eVar(例如eVar3)，以收集访客输入的搜索词。随后将在发送给同一访客的交易电子邮件中使用此术语。

### Using the trigger in Adobe Campaign {#using-the-trigger-in-adobe-campaign-1}

1. 按照上一用例中的说明，在Adobe Campaign中创建触发器。See [Using the trigger in Adobe Campaign](../../integrating/using/abandonment-triggers-use-cases.md#using-the-trigger-in-adobe-campaign). 主要区别是我们如何在Adobe Campaign中访问和使用推送有效负荷中推送的元数据。
1. In the Search Abandonment trigger you created in Adobe Campaign, click on the **[!UICONTROL Event content and enrichment]** icon to view the payload pushed to Adobe Campaign.

   ![](assets/trigger_uc_search_2.png)

1. As you can see, the custom eVar is passed in the Trigger payload and mapped to the **Event Context** table (ctx). 我们现在可以访问它来个性化交易消息。

   ![](assets/trigger_uc_search_3.png)

1. 在此示例中，我们选择在主题行中和电子邮件正文中包括目标搜索词。

   ![](assets/trigger_uc_search_4.png)

1. When selecting a personalized field, look for your payload meta data in the **Transactional event** (rtEvent) table then in the **Event context** (ctx) sub table.

   ![](assets/trigger_uc_search_5.png)

### Running the scenario {#running-the-scenario-1}

1. 访客进入旅行预订网站并搜索目标。在此示例中，访客正在寻找去往日本的旅行，但找不到任何结果。我们有机会联系此访客并推荐一个替代旅游计划。

   ![](assets/trigger_uc_search_6.png)

   >[!NOTE]
   >
   >在此用例中，我们假设访客/接收方已打开并单击来自同一网站的电子邮件。这允许我们使用和收集visitorID并将其映射到收件人。我们只需要执行一次。

1. 不久之后，同一访客/接收方收到再营销消息。消息包括最近搜索的目标。

   ![](assets/trigger_uc_search_7.png)

