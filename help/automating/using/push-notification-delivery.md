---
solution: Campaign Standard
product: campaign
title: 推送通知投放
description: 推送通知投放活动允许您配置在工作流中发送单个发送推送通知或重复的推送通知。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 47%

---


# 推送通知投放{#push-notification-delivery}

## 说明{#description}

![](assets/push.png)

![](assets/recurrentpush.png)

The **[!UICONTROL Push notification]** activity allows you to configure sending a push notification in a workflow. 这可以是单个发送通知并且只发送一次，也可以是循环通知。

* **单次发送** 通知是标准的移动应用推送通知投放，发送一次。
* **循环通知** 允许您在定义的时间段内多次向不同投放发送同一移动应用推送通知目标。 您可以按时段聚合投放，以获得对应于您需求的报告。

## 使用环境{#context-of-use}

The **[!UICONTROL Push notification]** activity is generally used to automate sending a notification to a target calculated in the same workflow.

链接到调度程序时，您可以定义循环推送通知。

收件人是在同一工作流中通过活动、交叉点等定位活动在查询上游定义的。

根据工作流执行参数，触发消息准备。在消息仪表板中，您可以选择是否请求手动确认以发送消息（默认要求）。您可以手动启动工作流，或在工作流中放置调度程序活动以自动执行。

**相关主题**

* [使用工作流发送循环推送通知](../../automating/using/recurring-push-notifications.md)

## 配置{#configuration}

1. 将 **[!UICONTROL Push notification]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。

   >[!NOTE]
   >
   >您可以通过活动快捷操作中的 ![](assets/dlv_activity_params-24px.png) 按钮，访问活动的常规属性和高级选项（而非投放本身）。此按钮专用于 **[!UICONTROL Push notification]** 活动。推送通知的属性可以通过推送仪表板中的操作栏进行访问。

1. 选择推送通知发送模式：

   * **[!UICONTROL Single notification]**:推送通知只发送一次。 您可以在此处指定是否向活动添加叫客过渡。此程序的第 7 步详细介绍了各种过渡类型。
   * **[!UICONTROL Recurring notification]**:根据活动中定义的频率，推送通知被发送多次 **[!UICONTROL Scheduler]** 。 选择发送的聚合期。This allows you to regroup all the sends that occur during the defined period in one single push notification that is also called **recurring execution** and can be accessed from the application&#39;s marketing activity list.

      例如，对于每天发送的循环生日通知，您可以选择聚合每月发送的生日通知。 这样，尽管通知每天都会发送，您仍可以按月接收投放报告。

1. 选择通知类型。 这些类型来自在> >菜单中定义的推 **[!UICONTROL Resources]** 送通 **[!UICONTROL Templates]** 知模 **[!UICONTROL Delivery templates]** 板。
1. 输入推送通知的常规属性。 您还可以将其连接到现有营销策划。工作流的投放活动的标签将更新为推送通知标签。
1. 定义推送通知内容。 请参 [阅创建推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
1. 默认情况下，**[!UICONTROL Push notification]** 活动不包含任何叫客过渡。如果要向 **[!UICONTROL Push Notification]** 互动添加叫客过渡，请转到高级活动选项的 **[!UICONTROL General]** 选项卡（活动快捷操作中的 ![](assets/dlv_activity_params-24px.png) 按钮），然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**：通过此选项可生成叫客过渡，其中包含的群体与集客过渡完全相同。
   * **[!UICONTROL Add outbound transition with the population]**:这样，您就可以生成一个出站过渡，其中包含接收通知的人群。 在准备目标时排除的投放成员不在此过渡中。

1. 确认活动的配置并保存工作流。

重新打开活动时，您将直接转到推送通知仪表板。 只能编辑其内容。

默认情况下，启动投放工作流只会触发消息准备。在工作流启动后，发送从工作流创建的消息，仍需要确认。但是在消息仪表板中，仅当通过工作流创建消息时，才能禁用 **[!UICONTROL Request confirmation before sending messages]** 选项。取消选中此选项后，消息在准备完成后即发送，不会进一步通知。

## 备注{#remarks}

可以在应用程序的营销活动列表中，访问在工作流中创建的投放。您可以使用仪表板查看工作流的执行状态。推送通知摘要窗格中的链接允许您直接访问链接的元素(工作流、活动等)。

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL Push notification]** activity was configured). 要执行此操作，请通过选择 **[!UICONTROL Deployment]** 以打开父投放 ![](assets/wkf_dlv_detail_button.png) 块的详细视图。
