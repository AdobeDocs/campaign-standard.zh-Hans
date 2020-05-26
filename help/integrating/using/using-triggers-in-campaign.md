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
source-git-commit: 3aa987c423181180a5c20bcca04cde04a2bf6086
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 1%

---


# 在 Campaign 中使用触发器{#using-triggers-in-campaign}

## 在活动中创建映射触发器 {#creating-a-mapped-trigger-in-campaign}

您应确保在Adobe Experience Cloud（核心服务）中定义要预先监 **[!UICONTROL Triggers]** 控的行为。 For more on this, refer to the [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html). 请注意，定义触发器时，需要启用别名。 对于每种行为（浏览／表单放弃、添加／删除产品、会话过期等），必须在Adobe Experience Cloud中添加新触发器。

您现在必须基于现有Adobe Experience Cloud触发器在Adobe Campaign中创建触发器事件。

您可以观看此 [视频](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) ，以帮助您了解如何在Adobe Campaign中设置触发器。

将其落实到位的步骤有：

1. 单击左 **[!UICONTROL Adobe Campaign]** 上角的标志，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Experience Cloud Triggers]**。

   ![](assets/remarketing_1.png)

1. Click the **[!UICONTROL Create]** button. 此时将打开的创建向导显示Adobe Experience Cloud中定义的所有触发器的列表。 该 **[!UICONTROL Fired by Analytics]** 列显示由Adobe Experience Cloud触发器发送给活动的数量。 这是在Experience Cloud界面中创建的触发器的映射。

   ![](assets/remarketing_2.png)

1. 选择要使用的Adobe Experience Cloud触发器，然后单击 **[!UICONTROL Next]**。
1. 配置触发器的常规属性。 在向导的此步骤中，还指定用于触发器的渠道和定位维度(请参 [阅定位维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources))。 然后确认创建触发器。
1. 单击字段右侧的按 **[!UICONTROL Event content and enrichment]** 钮以视图有效负荷的内容。 此屏幕还允许您使用存储在事件库中的用户档案数据丰富Adobe Campaign数据。 扩充的执行方式与标准事务性消息相同。

   ![](assets/remarketing_3.png)

1. 在字 **[!UICONTROL Transactional message validity duration]** 段中，定义在Analytics发送事件后消息保持有效的持续时间。 如果定义了2天的持续时间，则消息在该持续时间过后将不再发送。 如果将多条消息置于保留状态，这可确保在特定时间段后恢复这些消息时不会发送这些消息。

   ![](assets/remarketing_4.png)

1. 单击按 **[!UICONTROL Publish]** 钮以开始发布触发器事件。
1. 如果您需要在发布触发器模式后对触发器事件进行更改，请单击 **[!UICONTROL Update schema]** 按钮以检索最新更改。

   请注意，此操作将取消发布您的触发器和事务性消息，之后您将需要重新发布它们。

   ![](assets/remarketing_11.png)

通 **[!UICONTROL Show Trigger in Experience Cloud]** 过该按钮可视图Adobe Experience Cloud中的触发器定义。

发布事件后，将自动创建链接到新事件的事务模板。 然后，您必须修改并发布刚刚创建的模板。 有关此内容的详细信息，请参 [阅编辑模板](../../start/using/marketing-activity-templates.md) 。

## 编辑事务性消息模板 {#editing-the-transactional-message-template}

创建并发布触发器事件后，将自动创建相应的事务模板。 有关此内容的详细信息，请参 [阅在活动中创建映射触发器](#creating-a-mapped-trigger-in-campaign) 。

为了让事件触发发送事务性消息，您必须对模板进行个性化设置，然后测试并发布它。 这些步骤与标准事务性消息相同。 有关此内容的详细信息，请参 [阅“事务模板](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message) ”部分。

>[!NOTE]
>
>如果取消发布模板，该模板将自动取消发布触发器事件。

在编辑内容时，您可以根据Analytics触发器发送的信息添加个性化字段。 如果您使用事件用户档案数据丰富Adobe Campaign数据，则可以根据此信息个性化信息。 要个性化您的消息，请选 **[!UICONTROL Transactional event]** 择> **[!UICONTROL Event context]** 并选择一个字段。

![](assets/remarketing_8.png)

## 访问报告 {#accessing-the-reports}

要在Adobe Campaign中视图专用触发器报告，请打开您之前创建的触发器事件，然后单击 **[!UICONTROL Show trigger report]**。

![](assets/remarketing_9.png)

报告显示与Analytics发送的事件数相比，已处理的事件数。 它还显示所有最近触发器的列表。

![](assets/trigger_uc_browse_14.png)

