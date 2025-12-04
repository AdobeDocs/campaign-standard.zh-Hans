---
title: 使用工作流发送定期推送通知
description: 在此示例中，将于每月第一天晚上8点向移动应用程序的订阅者发送个性化推送通知（取决于其时区）
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 5%

---

# 使用工作流发送定期推送通知 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

在此示例中，将于每月第一天晚上8点向移动应用程序的订阅者发送个性化推送通知（取决于其时区）。

要构建工作流，请执行以下步骤：

1. [调度程序](../../automating/using/scheduler.md)活动允许您在投放开始前启动工作流天，以便能够在任意给定时区的晚上8点将通知发送给每个订阅者：

   * 在&#x200B;**[!UICONTROL Execution frequency]**&#x200B;字段中，选择“每月”。
   * 在&#x200B;**[!UICONTROL Time]**&#x200B;字段中选择8pm。
   * 选择每月发送投放的日期。
   * 选择工作流的开始日期，至少先于投放开始一天。 否则，如果所选时间已在其时区中流过，则某些收件人可能在第二天后收到消息。
   * 在&#x200B;**[!UICONTROL Execution options]**&#x200B;选项卡的&#x200B;**[!UICONTROL Time zone]**&#x200B;字段中选择工作流将启动的时区。 例如，在此，工作流将在太平洋时间晚上8点（即每月第一天的前一周）开始，以便留出一些时间为所有适用的时区创建投放。

   >[!NOTE]
   >
   >默认情况下，所选时区就是在工作流属性中定义的时区（请参阅[构建工作流](../../automating/using/building-a-workflow.md)）。

   ![](assets/wkf_push_example_5.png)

1. VIP通过[查询](../../automating/using/query.md)活动，可定向年龄在20到30岁之间、已订阅您的移动应用程序且未打开您发送的电子邮件的客户：

   * 选择一个受众(您的VIP客户)，并根据其年龄进行过滤。
   * 将&#x200B;**应用程序**&#x200B;订阅元素拖放到工作区中。 选择&#x200B;**存在**&#x200B;并选择要使用的移动应用程序。
   * 选择您发送给客户的电子邮件。
   * 将&#x200B;**投放日志（日志）**&#x200B;元素拖放到工作区中，并选择&#x200B;**存在**&#x200B;以定向收到电子邮件的所有客户。
   * 将&#x200B;**跟踪日志（跟踪）**&#x200B;元素拖放到工作区中，并选择&#x200B;**不存在**&#x200B;以定向所有未打开电子邮件的客户。

     ![](assets/wkf_push_example_2.png)

1. [推送通知投放](../../automating/using/push-notification-delivery.md)活动允许您输入消息的内容并选择要使用的个性化字段：

   * 选择 **[!UICONTROL Recurring notification]** 选项。
   * 定义推送通知内容。 有关推送通知内容的更多信息，请参阅此[部分](../../channels/using/preparing-and-sending-a-push-notification.md)。
   * 在&#x200B;**[!UICONTROL Schedule]**&#x200B;块中，选择&#x200B;**[!UICONTROL Messages to be sent automatically on the time zone specified below]**。 在此，我们在工作流&#x200B;**[!UICONTROL Time zone of the contact date]**&#x200B;中选择了&#x200B;**[!UICONTROL Scheduler]** Pacific。
   * 在 **[!UICONTROL Optimize the sending time per recipient]** 字段中，选择 **[!UICONTROL Send at the recipient's time zone]**。

     ![](assets/wkf_push_example_4.png)

1. 单击&#x200B;**[!UICONTROL Start]**&#x200B;按钮以启动定期工作流。

   ![](assets/wkf_push_example_3.png)

您的工作流正在运行。 它将于&#x200B;**[!UICONTROL Scheduler]**&#x200B;的选定开始日期太平洋时间晚上8点开始，然后每月第一天晚上8点发送定期推送，具体取决于客户时区。
