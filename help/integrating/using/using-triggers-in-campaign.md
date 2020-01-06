---
title: 在 Campaign 中使用触发器
description: null
page-status-flag: never-activated
uuid: d844d013-b38a-4e69-9df5-0edc01fa9c6e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: a524c700-bad6-4fcf-857a-c31bfae4d30c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# 在 Campaign 中使用触发器{#using-triggers-in-campaign}

## 在Campaign中创建映射触发器 {#creating-a-mapped-trigger-in-campaign}

您应确保定义要在Adobe Experience Cloud（核心服务）中预先监控 **[!UICONTROL Triggers]**的行为。 For more on this, refer to the[Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html). 请注意，定义触发器时，您需要启用别名。 对于每种行为（浏览／表单放弃、添加／删除产品、会话过期等），必须在Adobe Experience cloud中添加新的触发器。

您现在必须基于现有的Adobe Experience cloud触发器在Adobe Campaign中创建触发器事件。

您可以观看此 [视频](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) ，以帮助您了解如何在Adobe Campaign中设置触发器。

落实这些步骤包括：

1. 单击左 **[!UICONTROL Adobe Campaign]**上角的标志，然后选择**[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**>**[!UICONTROL Experience Cloud Triggers]**。

   ![](assets/remarketing_1.png)

1. Click the **[!UICONTROL Create]**button. 打开的创建向导会显示Adobe Experience cloud中定义的所有触发器的列表。 该**[!UICONTROL Fired by Analytics]** 列显示由Adobe Experience cloud触发器发送到Campaign的事件数。 这是在Experience cloud界面中创建的触发器的映射。

   ![](assets/remarketing_2.png)

1. 选择您要使用的Adobe Experience cloud触发器，然后单击 **[!UICONTROL Next]**。
1. 配置触发器的常规属性。 在向导的此步骤中，还指定要用于触发器的渠道和定位维(请参 [阅定位维和资源](../../automating/using/query.md#targeting-dimensions-and-resources))。 然后确认创建触发器。
1. 单击字段右侧的按 **[!UICONTROL Event content and enrichment]**钮可查看有效负荷的内容。 此屏幕还允许您使用Adobe Campaign数据库中存储的配置文件数据丰富活动数据。 以与标准事务消息相同的方式执行该扩充。

   ![](assets/remarketing_3.png)

1. 在字段 **[!UICONTROL Transactional message validity duration]**中，定义Analytics发送事件后消息将保持有效的持续时间。 如果定义了2天的持续时间，则消息在该持续时间过后将不再发送。 如果将多条消息置于保留状态，这可确保在特定时间段后恢复这些消息时不会发送这些消息。

   ![](assets/remarketing_4.png)

1. 如果倾向评分在Analytics中定义(请参阅 [Experience Cloud文档](https://marketing.adobe.com/resources/help/en_US/insight/client/c_visitor_propensity.html))，则如果客户在不久的将来很有可能返回网站，则您可以选择不发送消息。 得分内容和阈值在有效负荷内容中可用，这样您就可以使用这些值个性化消息。 要使用此选项，请选中屏幕底部的框。 在不久的将来，返回网站的可能性很大的客户不会收到消息。
1. 单击该 **[!UICONTROL Publish]**按钮以开始发布触发器事件。
1. 如果您需要在发布触发器事件后在触发器架构中进行更改，请单击该 **[!UICONTROL Update schema]**按钮以检索最新更改。

   请注意，此操作将取消发布您的触发器和交易消息，之后您需要重新发布这些消息。

   ![](assets/remarketing_11.png)

通过 **[!UICONTROL Show Trigger in Experience Cloud]**此按钮，您可以在Adobe Experience cloud中查看触发器定义。

发布活动后，将自动创建链接到新活动的交易模板。 然后，您必须修改并发布刚刚创建的模板。 有关详细信息，请参阅编辑 [模板部分](../../start/using/marketing-activity-templates.md) 。

## 编辑事务消息模板 {#editing-the-transactional-message-template}

创建并发布触发器事件后，将自动创建相应的事务模板。 有关详细信息，请参阅在“营销活 [动”中创建映射触发器](#creating-a-mapped-trigger-in-campaign) 。

为了使活动触发发送交易消息，您必须对模板进行个性化设置，然后测试并发布模板。 这些步骤与标准事务消息的步骤相同。 有关详细信息，请参阅“事务模 [板”部分](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message) 。

>[!NOTE]
>
>如果取消发布模板，模板将自动取消发布触发器事件。

在编辑内容时，您可以根据Analytics触发器发送的信息添加个性化字段。 如果您使用Adobe Campaign配置文件数据丰富活动数据，则可以根据这些信息个性化消息。 要个性化您的消息，请选择 **[!UICONTROL Transactional event]**>并**[!UICONTROL Event context]** 选择一个字段。

![](assets/remarketing_8.png)

## 访问报告 {#accessing-the-reports}

要在Adobe Campaign中查看专用触发器报告，请打开您之前创建的触发器事件，然后单击 **[!UICONTROL Show trigger report]**。

![](assets/remarketing_9.png)

报告显示与Analytics发送的事件数相比，已处理的事件数。 它还显示所有最近触发器的列表。

![](assets/trigger_uc_browse_14.png)

