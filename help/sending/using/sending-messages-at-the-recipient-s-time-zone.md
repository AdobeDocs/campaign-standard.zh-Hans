---
title: 在收件人的时区发送消息
seo-title: 在收件人的时区发送消息
description: 在收件人的时区发送消息
seo-description: 了解如何在收件人的时区发送消息。
page-status-flag: 从未激活
uuid: 70228c07-451f-4ddb-8d26-92a5a4814e3a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: sheduling-messages
discoiquuid: daa980ba-8c-4673-a68 f-379d63 e4 b8 bd
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Sending messages at the recipient's time zone{#sending-messages-at-the-recipient-s-time-zone}

在管理日期和时间很重要的营销活动时，您可以安排将每个收件人的当地时间计入帐户的交付：他们将在您预定的时区接收电子邮件、短信或推送通知。

>[!NOTE]
>
>To use this functionality, make sure that all profiles targeted by your delivery have a time zone specified in the **[!UICONTROL Address]** section of their properties. For more information on accessing profile properties, refer to this [section](../../audiences/using/editing-profiles.md).

To send a delivery at the recipient's time zone, you can also use the **[!UICONTROL Scheduler]** activity in a workflow. For more on this, refer to this [page](../../automating/using/scheduler.md).

在以下示例中，我们希望向全球所有客户发送仅对Valentine Day有效的促销代码。为了在一天内使用该产品，所有客户必须在月14日上午8：00根据时区收到您的消息。

1. **[!UICONTROL Marketing activities]** 在选项卡中，开始创建您的交付，在我们的案例中为电子邮件。To learn more on delivery creation, refer to this [section](../../channels/using/creating-an-email.md).
1. After designing your Valentine's Day email, click **[!UICONTROL Create]** to access the delivery dashboard. For more on email designing, refer to this [page](../../designing/using/example--email-personalization.md).

   ![](assets/send-time_opt_valentine_1.png)

1. From the delivery dashboard, select the **[!UICONTROL Schedule]** block.

   ![](assets/send-time_opt_valentine_2.png)

1. Select the **[!UICONTROL Messages to be sent automatically on the date]** option specified below. Then in the **[!UICONTROL Start sending from]** field, set the contact date, in our case February 14th at 8:00 AM so that every recipient receives it on Valentine's Day.

   ![](assets/send-time_opt_valentine.png)

1. In the **[!UICONTROL Time zone of the contact date]** field, select at which time zone your delivery should be sent by default.

   If a profile's **[!UICONTROL Time zone]** is left as **[!UICONTROL Default]**, the recipients will receive the delivery depending on the chosen time zone here.

1. From the **[!UICONTROL Optimize the sending time per recipient]** drop-down menu, choose **[!UICONTROL Send at the recipient's time zone]**. 这允许收件人根据他们的时区在二月14日收到Valentine的电子邮件。

   ![](assets/send-time_opt_valentine_3.png)

1. After confirming your schedule for your delivery, click the **[!UICONTROL Prepare]** button then **[!UICONTROL Confirm]** your delivery.

   确保至少提前24小时确认发送。否则，某些收件人可能会在实际Valentine的天试用活动之前收到分发。

   ![](assets/send-time_opt_valentine_4.png)

无论他们位于何处，所有收件人都将在月14日上午8：00收到此消息。
