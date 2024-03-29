---
title: 使用工作流发送定期推送通知
description: 在此示例中，将于每月第一天晚上8点向移动应用程序的订阅者发送个性化推送通知（取决于其时区）
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: 0ab950d4124bf459ba889e2f1c2954210dd350e0
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 4%

---

# 使用工作流发送定期推送通知 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

在此示例中，将于每月第一天晚上8点向移动应用程序的订阅者发送个性化推送通知（取决于其时区）。

要构建工作流，请执行以下步骤：

1. 此 [计划程序](../../automating/using/scheduler.md) 利用活动，您可以在投放开始前几天启动工作流，以便能够在任意给定时区的晚上8点向每个订阅者发送通知：

   * 在 **[!UICONTROL Execution frequency]** 字段中，选择“每月”。
   * 在中选择8点 **[!UICONTROL Time]** 字段。
   * 选择每月发送投放的日期。
   * 选择工作流的开始日期，至少先于投放开始一天。 否则，如果所选时间已在其时区中流过，则某些收件人可能在第二天后收到消息。
   * 在 **[!UICONTROL Execution options]** 选项卡中，选择工作流在哪个时区启动 **[!UICONTROL Time zone]** 字段。 例如，在此，工作流将在太平洋时间晚上8点（即每月第一天的前一周）开始，以便留出一些时间为所有适用的时区创建投放。

   >[!NOTE]
   >
   >默认情况下，所选时区就是在工作流属性中定义的时区（请参阅[构建工作流](../../automating/using/building-a-workflow.md)）。

   ![](assets/wkf_push_example_5.png)

1. 此 [查询](../../automating/using/query.md) VIP利用活动，可定向年龄在20到30岁之间、已订阅您的移动应用程序且未打开您发送的电子邮件的客户：

   * 选择受众(您的VIP客户)并根据其年龄进行过滤。
   * 拖放 **应用程序订阅** 元素。 选择 **存在** 并选择要使用的移动设备应用程序。
   * 选择您发送给客户的电子邮件。
   * 拖放 **投放日志（日志）** 元素并选择 **存在** 以定位收到电子邮件的所有客户。
   * 拖放 **跟踪日志（跟踪）** 元素并选择 **不存在** 以定位所有未打开电子邮件的客户。

     ![](assets/wkf_push_example_2.png)

1. 此 [推送通知投放](../../automating/using/push-notification-delivery.md) 利用活动，可输入消息的内容并选择要使用的个性化字段：

   * 选择 **[!UICONTROL Recurring notification]** 选项。
   * 定义推送通知内容。 有关推送通知内容的更多信息，请参阅此 [部分](../../channels/using/preparing-and-sending-a-push-notification.md).
   * 在 **[!UICONTROL Schedule]** 块，选择 **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. 这里，我们选择了 **[!UICONTROL Time zone of the contact date]** 与工作流中的太平洋相同 **[!UICONTROL Scheduler]**.
   * 在 **[!UICONTROL Optimize the sending time per recipient]** 字段中，选择 **[!UICONTROL Send at the recipient's time zone]**。

     ![](assets/wkf_push_example_4.png)

1. 单击 **[!UICONTROL Start]** 按钮以启动您的定期工作流。

   ![](assets/wkf_push_example_3.png)

您的工作流正在运行。 它将在的选定开始日期开始 **[!UICONTROL Scheduler]** 太平洋时间晚上8点，将根据客户所在时区，每月第一天晚上8点发送定期推送。
