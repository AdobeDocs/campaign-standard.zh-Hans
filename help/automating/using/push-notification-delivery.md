---
title: 推送通知投放
description: 利用推送通知投放活动，可在工作流中配置发送单次发送推送通知或定期推送通知。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b6a43d51-32d4-4806-b4e4-33236f1e27f5
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 46%

---

# 推送通知投放{#push-notification-delivery}

## 说明 {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

此 **[!UICONTROL Push notification]** 利用活动，可在工作流中配置发送推送通知。 这可以是只发送一次的单次发送通知，也可以是定期通知。

* **单身** 发送通知是标准的移动应用程序推送通知投放，只发送一次。
* **周期性** 通知允许您在定义的时间段内，多次向不同的目标发送相同的移动应用程序推送通知投放。 您可以按时段聚合投放，以获得对应于您需求的报告。

## 使用环境 {#context-of-use}

此 **[!UICONTROL Push notification]** 活动通常用于向在同一工作流中算出的目标自动发送通知。

链接到调度程序时，您可以定义定期推送通知。

同一工作流中的上游活动，通过查询、交集之类的定向活动，定义了收件人。

根据工作流执行参数，触发消息准备。在消息仪表板中，您可以选择是否请求手动确认以发送消息（默认要求）。您可以手动启动工作流，或在工作流中放置调度程序活动以自动执行。

**相关主题**

* [使用工作流发送定期推送通知](../../automating/using/recurring-push-notifications.md)

## 配置 {#configuration}

1. 将 **[!UICONTROL Push notification]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。

   >[!NOTE]
   >
   >您可以通过活动快速操作中的 ![](assets/dlv_activity_params-24px.png) 按钮，访问活动的常规属性和高级选项（而非投放本身）。此按钮专用于 **[!UICONTROL Push notification]** 活动。可以通过推送仪表板中的操作栏，访问推送通知的属性。

1. 选择推送通知发送模式：

   * **[!UICONTROL Single notification]**：推送通知只发送一次。 您可以在此处指定是否向活动添加叫客过渡。此程序的第 7 步详细介绍了各种过渡类型。
   * **[!UICONTROL Recurring notification]**：根据中定义的频率，多次发送推送通知 **[!UICONTROL Scheduler]** 活动。 选择发送的聚合期。这样，您可以将规定时间段内发生的所有发送重组到一封单独的推送通知中(也称为 **定期执行** 可以从应用程序的营销活动列表访问和。

     例如，对于每天发送的定期生日通知，您可以选择聚合每月的发送。 这样，尽管每天都会发送通知，但您可以按月接收投放报告。

1. 选择通知类型。 这些类型来自在中定义的推送通知模板 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** 菜单。
1. 输入推送通知的常规属性。 您还可以将其连接到现有营销策划。工作流投放活动的标签将更新为推送通知标签。
1. 定义推送通知内容。 请参阅 [创建推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
1. 默认情况下，**[!UICONTROL Push notification]** 活动不包含任何叫客过渡。如果要向 **[!UICONTROL Push Notification]** 互动添加叫客过渡，请转到高级活动选项的 **[!UICONTROL General]** 选项卡（活动快速操作中的 ![](assets/dlv_activity_params-24px.png) 按钮），然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**：通过此选项可生成叫客过渡，其中包含的群体与集客过渡完全相同。
   * **[!UICONTROL Add outbound transition with the population]**：通过此选项可生成叫客过渡，其中包含接收通知的群体。 在投放准备期间被排除的目标成员将从此过渡中排除。

1. 确认活动的配置并保存工作流。

重新打开活动时，您将直接转到推送通知仪表板。 只能编辑其内容。

默认情况下，启动投放工作流只会触发消息准备。在工作流启动后，发送从工作流创建的消息，仍需要确认。但是在消息仪表板中，仅当通过工作流创建消息时，才能禁用 **[!UICONTROL Request confirmation before sending messages]** 选项。取消选中此选项后，消息在准备完成后即发送，不会进一步通知。

## 备注 {#remarks}

可以在应用程序的营销活动列表中，访问在工作流中创建的投放。您可以使用仪表板查看工作流的执行状态。利用推送通知摘要窗格中的链接，可直接访问链接的元素（工作流、活动等）。

在可从营销活动列表访问的父投放中，您可以查看已处理的发送总数（基于以下时间时指定的聚合期） **[!UICONTROL Push notification]** 活动已配置)。 要执行此操作，请通过选择 **[!UICONTROL Deployment]** 以打开父投放 ![](assets/wkf_dlv_detail_button.png) 块的详细视图。
