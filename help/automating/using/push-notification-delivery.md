---
title: 推送通知投放
description: 推送通知投放活动允许您配置在工作流中发送单个发送推送通知或重复的推送通知。
page-status-flag: never-activated
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e689e6bc362f4e948593c3b251f3825aab20ac
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 0%

---


# 推送通知投放{#push-notification-delivery}

## 说明 {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

该 **[!UICONTROL Push notification]** 活动允许您配置在工作流中发送推送通知。 这可以是单 **个发送** 通知，只发送一次，也可以是循环 **通知** 。

单个发送通知是标准的移动应用推送通知投放，发送一次。

循环通知允许您在定义的时间段内将同一移动应用程序推送通知投放多次发送到不同目标。 您可以聚合每个时段的投放，以获得与您的需求对应的报告。

## 使用环境 {#context-of-use}

活动 **[!UICONTROL Push notification]** 通常用于自动向在同一工作流中计算的目标发送通知。

链接到调度程序时，您可以定义循环推送通知。

收件人是在同一工作流中通过活动、交叉点等定位活动在查询上游定义的。

根据工作流执行参数触发消息准备。 在消息仪表板中，您可以选择是否请求手动确认以发送消息（默认情况下为必需）。 您可以手动开始工作流，或在工作流中放置调度程序活动以自动执行。

**相关主题**

* [使用工作流发送循环推送通知](../../automating/using/recurring-push-notifications.md)

## Configuration {#configuration}

1. 将活动拖放 **[!UICONTROL Push notification]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。

   >[!NOTE]
   >
   >您可以通过活动快速操作中的按钮访问投放(而非活动本身)的常规属 ![](assets/dlv_activity_params-24px.png) 性和高级选项。 此按钮特定于 **[!UICONTROL Push notification]** 活动。 推送通知的属性可以通过推送仪表板中的操作栏进行访问。

1. 选择推送通知发送模式：

   * **[!UICONTROL Single notification]**: 推送通知只发送一次。 您可以在此处指定是否要向活动添加出站过渡。 不同的过渡类型在此过程的步骤7中详细介绍。
   * **[!UICONTROL Recurring notification]**: 根据活动中定义的频率，推送通知被发送多次 **[!UICONTROL Scheduler]** 。 选择发送的聚合期间。 这样，您就可以在一个推送通知(也称为重复执行 **** )中重新分组定义期间发送的所有发送，并可以从应用程序的营销活动列表访问。

      例如，对于每天发送的循环生日通知，您可以选择聚合每月发送的生日通知。 这样，尽管通知每天都会发送，您仍可以按月接收投放报告。

1. 选择通知类型。 这些类型来自在> >菜单中定义的推 **[!UICONTROL Resources]** 送通 **[!UICONTROL Templates]** 知模 **[!UICONTROL Delivery templates]** 板。
1. 输入推送通知的常规属性。 您还可以将其附加到现有活动。 工作流的投放活动的标签将更新为推送通知标签。
1. 定义推送通知内容。 请参 [阅创建推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
1. 默认情况下， **[!UICONTROL Push notification]** 活动不包含任何出站过渡。 如果要向过渡添加出站活动，请转 **[!UICONTROL Push Notification]** 到高级活动 **[!UICONTROL General]** 选项的选项卡( ![](assets/dlv_activity_params-24px.png) 活动快速操作中的按钮)，然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**: 这样，您就可以生成一个出站过渡，其包含与入站过渡完全相同的人口。
   * **[!UICONTROL Add outbound transition with the population]**: 这样，您就可以生成一个出站过渡，其中包含接收通知的人群。 在准备目标时排除的投放成员不在此过渡中。

1. 确认活动的配置并保存工作流。

重新打开活动时，您将直接转到推送通知仪表板。 只能编辑其内容。

默认情况下，启动投放工作流只会触发消息准备。 在工作流启动后，仍需要确认从工作流创建的消息的发送。 但是，从消息仪表板中，并且仅当消息是通过工作流创建的，您才能禁用该 **[!UICONTROL Request confirmation before sending messages]** 选项。 取消选中此选项后，消息在准备完成后即发送，无需进一步通知。

## 备注 {#remarks}

在工作流中创建的投放可以在应用程序的营销活动列表中访问。 您可以使用视图仪表板来工作流的执行状态。 推送通知摘要窗格中的链接允许您直接访问链接的元素(工作流、活动等)。

在可从营销投放列表访问的父活动中，您可以视图已处理的发送总数(根据配置活动时指定的汇总期间)。 **[!UICONTROL Push notification]** 为此，请通过选择打开父投放块的详细 **[!UICONTROL Deployment]** 视图 ![](assets/wkf_dlv_detail_button.png)。
