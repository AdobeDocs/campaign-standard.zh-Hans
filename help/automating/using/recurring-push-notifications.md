---
solution: Campaign Standard
product: campaign
title: 使用工作流发送循环推送通知
description: 在此示例中，每月的第一天晚上8点会根据用户的时区，向用户发送个性化的推送通知。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---


# 使用工作流发送循环推送通知 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

在此示例中，每月的第一天晚上8点会根据用户的时区，向用户发送个性化的推送通知。

要构建工作流，请按照以下步骤操作：

1. 调度程序 [活动](../../automating/using/scheduler.md) 允许您在投放开始前的工作流天数内开始，以便能够在任何给定时区的晚上8点向每个订阅者发送通知：

   * In the **[!UICONTROL Execution frequency]** field, select Monthly.
   * 在字段中选择晚上8 **[!UICONTROL Time]** 点。
   * 选择每月发送投放的日期。
   * 为工作流选择开始日期，至少在投放开始前一天。 否则，如果所选时间已在其时区中过去，某些收件人可能会在一天后收到该消息。
   * 在选 **[!UICONTROL Execution options]** 项卡中，选择您的工作流将在哪个时区开始在 **[!UICONTROL Time zone]** 字段中。 例如，此处，工作流将在太平洋时间晚8点（即当月第一天前的一周）开始，以允许为所有适用时区创建投放一段时间。

   >[!NOTE]
   >
   >默认情况下，所选时区就是在工作流属性中定义的时区（请参阅[构建工作流](../../automating/using/building-a-workflow.md)）。

   ![](assets/wkf_push_example_5.png)

1. 查询 [](../../automating/using/query.md) 活动允许您目标年龄在20-30之间的VIP客户，这些客户已订阅您的移动应用程序且未打开您发送的电子邮件：

   * 选择受众(VIP客户)并按年龄进行筛选。
   * 将订阅拖放 **到工作区中的应** 用程序元素。 选 **择“存** 在”，然后选择要使用的手机应用程序。
   * 选择您发送给客户的电子邮件。
   * 将投放日志(日 **志)元素拖放到工作** 区中，并选择“存 **在”** ,目标收到电子邮件的所有客户。
   * 将跟踪日志(跟 **踪)元素拖放到工作** 区中，并选 **择“不存在** ”以目标所有未打开电子邮件的客户。

      ![](assets/wkf_push_example_2.png)

1. 通 [过推送通知投放](../../automating/using/push-notification-delivery.md) 活动，您可以输入消息的内容并选择要使用的个性化字段:

   * 选择选 **[!UICONTROL Recurring notification]** 项。
   * 定义推送通知内容。 For more information on push notification content, refer to this [section](../../channels/using/preparing-and-sending-a-push-notification.md).
   * In the **[!UICONTROL Schedule]** block, select **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. 在此，我们选择了 **[!UICONTROL Time zone of the contact date]** 太平洋作为工作流 **[!UICONTROL Scheduler]**。
   * 在 **[!UICONTROL Optimize the sending time per recipient]** 字段中，选择 **[!UICONTROL Send at the recipient's time zone]**。

      ![](assets/wkf_push_example_4.png)

1. 单击该 **[!UICONTROL Start]** 按钮以开始您的重复工作流。

   ![](assets/wkf_push_example_3.png)

您的工作流正在运行。 它将在太平洋时间晚8点的选 **[!UICONTROL Scheduler]** 定开始日开始，然后根据客户时区，每月的第一天8点发送循环推送。
