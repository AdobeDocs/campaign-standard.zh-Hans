---
title: 在Campaign中使用触发器
seo-title: 在Campaign中使用触发器
description: 在Campaign中使用触发器
seo-description: null
page-status-flag: 从未激活
uuid: d844d013-b38 a-4e69-9df5-0fa9 c6 e
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: 使用营销活动和触发器
discoiquuid: A524c700-bug6-4fcf-857a-c31 bfae4 d30 c
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Using Triggers in Campaign{#using-triggers-in-campaign}

## Creating a mapped trigger in Campaign {#creating-a-mapped-trigger-in-campaign}

You should make sure to define the behaviors that you want to monitor beforehand in Adobe Experience Cloud ( **[!UICONTROL Triggers]** core service). For more on this, refer to the [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html). 请注意，定义触发器时，您需要启用别名。对于每种行为(浏览/表单放弃、添加/删除产品、会话到期等)，必须在Adobe Experience Cloud中添加新触发器。

现在，必须根据现有Adobe Experience Cloud触发器在Adobe Campaign中创建触发事件。

You can watch this [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) to help you understand how triggers are set up in Adobe Campaign.

将此置于位置的步骤包括：

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Click the **[!UICONTROL Create]** button. 打开的创建向导将显示在Adobe Experience Cloud中定义的所有触发器的列表。**[!UICONTROL Fired by Analytics]** 列显示Adobe Experience Cloud触发器发送到Campaign的事件数。这是在Experience Cloud界面中创建的触发器的映射。

   ![](assets/remarketing_2.png)

1. Select the Adobe Experience Cloud trigger that you want to use and click **[!UICONTROL Next]**.
1. 配置触发器的常规属性。At this step of the wizard, also specify the channel and the targeting dimension to use for the trigger (see [targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)). 然后确认触发器创建。
1. Click the button to the right of the **[!UICONTROL Event content and enrichment]** field to view the content of the payload. 此屏幕还允许您使用存储在Adobe Campaign数据库中的配置文件数据丰富活动数据。丰富化的执行方式与标准的交易消息相同。

   ![](assets/remarketing_3.png)

1. **[!UICONTROL Transactional message validity duration]** 在字段中，定义在Analytics发送活动后消息将保持有效的持续时间。如果定义了天的持续时间，则在该持续时间过后不再发送消息。如果您暂停了多条消息，这将确保在特定时间段后恢复这些消息时不发送这些消息。

   ![](assets/remarketing_4.png)

1. If a propensity scoring is defined in Analytics (see the [Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/insight/client/c_visitor_propensity.html)), you can choose not to send the message if the customer has a high probability of coming back to the website in the near future. 分数内容和阈值在负载内容中可用，这样您可以使用这些值来个性化消息。要使用此选项，请选中屏幕底部的框。在不久的将来再次返回网站的客户将不会收到邮件。
1. Click the **[!UICONTROL Publish]** button to start publishing the trigger event.
1. If you need to make a change in your trigger schema even after publishing your trigger event, click the **[!UICONTROL Update schema]** button to retrieve the latest changes.

   请注意，此操作将取消发布触发器和交易消息，之后将需要重新发布。

   ![](assets/remarketing_11.png)

**[!UICONTROL Show Trigger in Experience Cloud]** 该按钮允许您查看Adobe Experience Cloud中的触发器定义。

活动发布后，将自动创建链接到新活动的事务模板。然后，必须修改和发布刚刚创建的模板。For more on this, refer to the [Editing the template](../../start/using/about-templates.md) section.

## Editing the transactional message template {#editing-the-transactional-message-template}

创建并发布触发器事件后，会自动创建相应的交易模板。For more on this, refer to the [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) section.

要使活动触发发送交易消息，您必须个性化模板，然后对其进行测试并发布。这些步骤与标准事务消息相同。For more on this, refer to the [Transactional template](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message) section.

>[!NOTE]
>
>如果您取消发布模板，它将自动取消发布触发器事件。

编辑内容时，您可以根据Analytics触发器发送的信息添加个性化字段。如果使用Adobe Campaign配置文件数据丰富活动数据，则可以根据此信息个性化消息。To personalize your message, select **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]** and select a field.

![](assets/remarketing_8.png)

## Accessing the reports {#accessing-the-reports}

To view the dedicated trigger report in Adobe Campaign, open the trigger event that you previously created, and click **[!UICONTROL Show trigger report]**.

![](assets/remarketing_9.png)

报告显示与Analytics发送的活动数量相比所处理的事件数。它还显示所有最近触发器的列表。

![](assets/trigger_uc_browse_14.png)

