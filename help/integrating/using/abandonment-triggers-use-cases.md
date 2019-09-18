---
title: 放弃触发器使用案例
seo-title: 放弃触发器使用案例
description: 放弃触发器使用案例
seo-description: 了解如何将Experience Cloud Triggers与这些不同的使用案例集成。
page-status-flag: 从未激活
uuid: 9e236165-afd5-4155-9151-c1941dc0af99
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用系列活动和触发器
discoiquuid: 1b9aeec5-70bb-4d72-a3e9-12342abf08f7
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4b69c92a8c877ecaf05e87b728009104066a38dc

---


# 放弃触发器使用案例{#abandonment-triggers-use-cases}

本节介绍了可通过Adobe Campaign和Experience Cloud触发器之间的集成实现的不同用例。 您将找到两个使用案例示例：

* [浏览放弃触发器](../../integrating/using/abandonment-triggers-use-cases.md#browse-abandonment-trigger):向放弃访问您网站的客户发送通信。
* [搜索放弃触发器](../../integrating/using/abandonment-triggers-use-cases.md#search-abandonment-trigger):重新吸引在您的网站上搜索但未购买的访客。

>[!NOTE]
>
>本节中描述的用例依赖于Experience cloud访客ID。 还可以使用Experience Cloud Declared ID实施这些功能。 还支持散列和加密的声明ID。 您可以通过直接解密加密的电子邮件地址／移动号码，将电子邮件／短信发送到Campaign中不存在的配置文件。 但在这种情况下，无法使用配置文件数据进行个性化。

## 先决条件 {#pre-requisites}

为了实施这些使用案例，您需要访问以下解决方案／核心服务：

* Adobe Campaign
* Adobe Analytics Ultimate、Premium、Foundation、OD、Select、Prime、Mobile Apps、Select或Standard。
* Experience Cloud触发核心服务
* Experience Cloud DTM Core Service
* Experience Cloud访客ID和Experience Cloud人员核心服务

您还需要有一个有效的网站。

有关详细信息，请参阅配 [置解决方案和服务](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services)。

## 浏览放弃触发器 {#browse-abandonment-trigger}

在此用例中，我们将创建一个简单的触发器，每次客户端放弃对网站的访问时都会触发该触发器。 此示例假定您已经有DTM收集数据并将其推送到Adobe Analytics，并且已创建您的所有事件。

### 创建Experience Cloud触发器 {#creating-an-experience-cloud-trigger}

1. 从Experience **[!UICONTROL Manage Triggers]** Cloud激活核心服务菜单中进行选择。

   ![](assets/trigger_uc_browse_1.png)

1. 选择触发器类型(在我 **[!UICONTROL Abandonment]** 们的用例中)。

   ![](assets/trigger_uc_browse_2.png)

1. 对于这个使用案例，我们需要一个简单的放弃触发器。 其业务目的是识别浏览我们旅行预订网站、查看“交易”页面但不预订任何旅行的访客。 一旦我们识别了这些受众，我们就希望在很短的时间内与他们联系。 在此示例中，我们选择在10分钟后发送触发器。

   ![](assets/trigger_uc_browse_3.png)

### 在Adobe Campaign中使用触发器 {#using-the-trigger-in-adobe-campaign}

既然我们已经创建了Experience Cloud触发器，我们就将它用在Adobe Campaign中吧。

在Adobe Campaign中，您需要创建一个与您在Experience Cloud中创建的触发器链接的触发器。

1. 要在Adobe Campaign中创建触发器，请单击左 **[!UICONTROL Adobe Campaign]** 上角的徽标，然后选择 **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud triggers]**。

   ![](assets/remarketing_1.png)

1. Click **[!UICONTROL Create]**.
1. 选择您之前创建的触发器，然后单击 **[!UICONTROL Next]**。

   ![](assets/trigger_uc_browse_5.png)

1. 选择渠 **[!UICONTROL Email]** 道和定位 **[!UICONTROL Real-time event]** 维并单击 **[!UICONTROL Create]**。

   ![](assets/trigger_uc_browse_6bis.png)

1. 在Adobe Campaign中发布触发器。 此过程将自动创建事务消息模板。

   ![](assets/trigger_uc_browse_6.png)

1. 要显示消息模板，请单击右 **[!UICONTROL More]** 上方的按钮，然后单击 **[!UICONTROL Trigger Transactional Template]**。

1. 个性化其内容和发送方详细信息。

   ![](assets/trigger_uc_browse_8.png)

1. 发布消息模板。 触发器现在可以实时工作。

   ![](assets/trigger_uc_browse_0.png)

### 运行方案 {#running-the-scenario}

1. 此用例从使用Adobe Campaign发送给受众的初始电子邮件开始。

   ![](assets/trigger_uc_browse_9.png)

1. 收件人将打开电子邮件。

   ![](assets/trigger_uc_browse_10.png)

1. 他点击链接，将他带到您的网站。 在此示例中，横幅将收件人带到行程预订网站的主页。

   ![](assets/trigger_uc_browse_11.png)

1. 收件人转到“交易”页面，但突然停止访问。 在10分钟后，Adobe Campaign会触发交易消息的发送。

   ![](assets/trigger_uc_browse_12.png)

1. 您可以随时检查Experience cloud日志，查看触发器的触发次数。

   ![](assets/trigger_uc_browse_13.png)

1. 您还可以显示Adobe Campaign触发器报告。

   ![](assets/trigger_uc_browse_14.png)

## 搜索放弃触发器 {#search-abandonment-trigger}

在此用例中，我们将创建一个触发器，以便与访问我们的旅行预订网站、搜索目的地、找不到成功结果且此后未预订任何内容的访客重新互动。 一般过程与上一个使用案例中的过程相同(请参阅浏览 [放弃触发器](../../integrating/using/abandonment-triggers-use-cases.md#browse-abandonment-trigger))。 我们将在此集中讨论如何个性化再营销电子邮件。

### 创建Experience Cloud触发器 {#creating-an-experience-cloud-trigger-1}

按照上一个用例中所述的步骤创建Experience cloud触发器。 请参 [阅创建Experience cloud触发器](../../integrating/using/abandonment-triggers-use-cases.md#creating-an-experience-cloud-trigger)。 主要区别在于触发器的定义。

![](assets/trigger_uc_search_1.png)

该部 **[!UICONTROL Include Meta Data]** 分允许您将从Analytics收集的任何数据传递到触发器有效负荷。 在此示例中，我们创建一个自定义eVar（例如，eVar 3）来收集访客输入的搜索词。 此术语随后将用于发送给同一访客的交易电子邮件。

### 在Adobe Campaign中使用触发器 {#using-the-trigger-in-adobe-campaign-1}

1. 按照上一个用例中所述的步骤，在Adobe Campaign中创建触发器。 请参 [阅在Adobe Campaign中使用触发器](../../integrating/using/abandonment-triggers-use-cases.md#using-the-trigger-in-adobe-campaign)。 主要区别在于我们如何访问和使用触发器有效负荷中推送的元数据。
1. 在您在Adobe Campaign中创建的搜索放弃触发器中，单击图 **[!UICONTROL Event content and enrichment]** 标以查看推送到Adobe Campaign的有效负荷。

   ![](assets/trigger_uc_search_2.png)

1. 如您所见，自定义eVar在触发器有效负荷中传递并映射到 **Event Context** table(ctx)。 我们现在可以访问它来个性化交易信息。

   ![](assets/trigger_uc_search_3.png)

1. 在此示例中，我们选择在主题行和电子邮件正文中包含目标搜索词。

   ![](assets/trigger_uc_search_4.png)

1. 在选择个性化字段时，请在 **Transactional event** (rtEvent)表中查找有效负荷元数据，然后在 **Event context** (ctx)子表中查找。

   ![](assets/trigger_uc_search_5.png)

### 运行方案 {#running-the-scenario-1}

1. 访客访问旅行预订网站并搜索目标。 在此示例中，访客正在寻找日本之旅，但没有找到任何结果。 这是我们与此访客联系并推荐其他旅游计划的机会。

   ![](assets/trigger_uc_search_6.png)

   >[!NOTE]
   >
   >在此用例中，我们假定访客／收件人已打开并单击来自同一网站的电子邮件。 这样，我们便可以使用和收集VisitorID，并将其映射到收件人。 我们只需做一次。

1. 稍后，同一访客／收件人会收到一条再营销消息。 该消息包括最近搜索的目标。

   ![](assets/trigger_uc_search_7.png)

