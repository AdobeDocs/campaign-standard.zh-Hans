---
title: 推送通知投放
description: 推送通知交付活动允许您配置在工作流中发送单个发送推送通知或重复的推送通知。
page-status-flag: 从未激活
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 渠道活动
discoiquuid: e61bdaee-4b48-4845-a2a5-574b57ea796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 推送通知投放{#push-notification-delivery}

## 说明 {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

该活 **[!UICONTROL Push notification]** 动允许您配置在工作流中发送推送通知。 这可以是单 **个发送通知** ，只发送一次，也可以是循环通 **知** 。

单个发送通知是标准的移动App推送通知发送，发送一次。

循环通知允许您在定义的时间段内多次向不同目标发送相同的移动应用程序推送通知传送。 您可以汇总每个时段的交货数，以获得与您的需求对应的报表。

## 使用环境 {#context-of-use}

活动 **[!UICONTROL Push notification]** 通常用于自动向同一工作流中计算的目标发送通知。

链接到调度程序时，您可以定义循环推送通知。

收件人通过查询、交叉点等定位活动在同一工作流中活动的上游进行定义。

根据工作流执行参数触发消息准备。 在消息功能板中，您可以选择是否请求手动确认以发送消息（默认情况下为必需）。 您可以手动启动工作流，或将调度程序活动放入工作流中以自动执行。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Push notification]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。

   >[!NOTE]
   >
   >您可以通过活动快速操作中的按钮访问活动（而非交付本身）的 ![](assets/dlv_activity_params-24px.png) 常规属性和高级选项。 此按钮特定于活 **[!UICONTROL Push notification]** 动。 推送通知的属性可以通过推送功能板中的操作栏进行访问。

1. 选择推送通知发送模式：

   * **[!UICONTROL Single notification]**:推送通知只发送一次。 您可以在此处指定是否要向活动添加出站过渡。 此过程的步骤7中详细介绍了不同的过渡类型。
   * **[!UICONTROL Recurring notification]**:根据活动中定义的频率，推送通知被发送多次 **[!UICONTROL Scheduler]** 。 选择发送的聚合期。 这样，您就可以在一个推送通知中重新分组在定义期间发生的所有发送，该通知也称为重复执行 **** ，并且可以从应用程序的营销活动列表中访问。

      例如，对于每天发送的循环生日通知，您可以选择每月汇总发送。 这样，尽管通知每天都会发送，但您仍可以每月收到有关发送情况的报告。

1. 选择通知类型。 这些类型来自在&gt; **[!UICONTROL Resources]** &gt;菜单中定义的推送通 **[!UICONTROL Templates]****[!UICONTROL Delivery templates]** 知模板。
1. 输入推送通知的常规属性。 您还可以将其附加到现有营销活动。 工作流的交付活动的标签将更新为推送通知标签。
1. 定义推送通知内容。 请参 [阅创建推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
1. 默认情况下，活 **[!UICONTROL Push notification]** 动不包括任何出站过渡。 如果要向活动添加出站过渡，请转到高级活动选项的选 **[!UICONTROL Push Notification]** 项卡( **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) 活动快速操作中的按钮)，然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**:这样，您就可以生成一个出站过渡，其中包含与入站过渡完全相同的人数。
   * **[!UICONTROL Add outbound transition with the population]**:这允许您生成包含接收通知的人群的出站转移。 在交付准备过程中被排除的目标成员不在此过渡中。

1. 确认活动的配置并保存工作流。

重新打开活动时，您会直接转到推送通知功能板。 只能编辑其内容。

默认情况下，启动传送工作流只会触发消息准备。 在工作流启动后，仍需要确认从工作流创建的消息的发送。 但是，在消息功能板中，并且仅当消息是从工作流创建的时候，您才能禁用该选 **[!UICONTROL Request confirmation before sending messages]** 项。 取消选中此选项后，准备完成后，消息将发送，无需进一步通知。

## 评论 {#remarks}

在工作流中创建的交货可以在应用程序的营销活动列表中访问。 您可以使用功能板查看工作流的执行状态。 推送通知摘要窗格中的链接允许您直接访问链接的元素（工作流、营销活动等）。

在可从营销活动列表访问的父分发中，您可以查看已处理的发送的总数（根据配置活动时指定的汇总期间）。 **[!UICONTROL Push notification]** 为此，请选择以打开父分发块的详细信 **[!UICONTROL Deployment]** 息视图 ![](assets/wkf_dlv_detail_button.png)。

## 使用工作流发送循环推送通知 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

在此示例中，每月的第一天晚上8点，会根据用户的时区，向用户发送个性化的推送通知。 操作步骤：

1. 该活 **[!UICONTROL Scheduler]** 动允许您在交付开始前的几天开始工作流，以便能够在任何给定时区的晚上8点向每个订阅者发送通知：

   * 在字段 **[!UICONTROL Execution frequency]** 中，选择“每月”。
   * 在字段中选择晚上8 **[!UICONTROL Time]** 点。
   * 选择每月发送送货的日期。
   * 为工作流选择开始日期，至少在交货开始前一天。 否则，如果选定的时间已经过其时区，某些收件人可能会在一天后收到该消息。
   * 在选 **[!UICONTROL Execution options]** 项卡中，从字段中选择工作流将开始的时 **[!UICONTROL Time zone]** 区。 例如，此处的工作流将在太平洋时间晚上8点（即当月第一天前的一周）开始，以允许为所有适用时区创建交付的一段时间。
   ![](assets/wkf_push_example_5.png)

1. 通过 **查询** ，您可以定位20-30岁的VIP客户，这些客户已订阅您的移动应用程序且未打开您发送的电子邮件：

   * 选择受众（您的VIP客户）并按年龄进行筛选。
   * 将“订阅”拖 **放到应用程序元素** ，进入工作区。 选择 **“存在** ”，然后选择要使用的手机应用程序。
   * 选择您发送给客户的电子邮件。
   * 将交付日志( **日志)元素拖放到工作区中** ，然后选择 **Exists** ，以定位收到电子邮件的所有客户。
   * 将跟踪日志(跟 **踪)元素拖放到工作区中，然后选择** Does not exist **** （不存在）以定位所有未打开电子邮件的客户。

      ![](assets/wkf_push_example_2.png)

1. 通过 **推送通知** ，您可以输入消息内容并选择要使用的个性化字段：

   * 选择选 **[!UICONTROL Recurring notification]** 项。
   * 定义推送通知内容。 有关推送通知内容的详细信息，请参阅此 [部分](../../channels/using/preparing-and-sending-a-push-notification.md)。
   * 在块 **[!UICONTROL Schedule]** 中，选择 **[!UICONTROL Messages to be sent automatically on the time zone specified below]**。 在此，我们选择了 **[!UICONTROL Time zone of the contact date]** 太平洋作为工作流 **[!UICONTROL Scheduler]**。
   * 在字段 **[!UICONTROL Optimize the sending time per recipient]** 中，选择 **[!UICONTROL Send at the recipient's time zone]**。

      ![](assets/wkf_push_example_4.png)

1. 单击该 **[!UICONTROL Start]** 按钮以启动您的循环工作流。

   ![](assets/wkf_push_example_3.png)

您的工作流正在运行。 它将从太平洋时间晚上8点的选定开始日期开始，然后根据客户时区，每月的第一天8点发送重复推送。 **[!UICONTROL Scheduler]**
