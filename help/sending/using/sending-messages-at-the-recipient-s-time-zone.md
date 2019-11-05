---
title: 按收件人的时区发送消息
description: 了解如何在收件人的时区发送消息。
page-status-flag: 从未激活
uuid: 70228c07-451f-4ddb-8d26-92a5a4814e3a
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 发送
content-type: 参考
topic-tags: 调度消息
discoiquuid: daa980ba-8c7c-4673-a68f-379d63e4b8bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 按收件人的时区发送消息{#sending-messages-at-the-recipient-s-time-zone}

在管理日期和时间很重要的营销活动时，您可以计划将每个收件人的本地时间考虑在内的分发：他们将在您安排的时区收到电子邮件、短信或推送通知。

>[!NOTE]
>
>要使用此功能，请确保您的分发目标的所有配置文件在其属性的部分中都指定了 **[!UICONTROL Address]** 一个时区。 有关访问配置文件属性的详细信息，请参阅此 [部分](../../audiences/using/editing-profiles.md)。

要在收件人的时区发送分发，您还可以在工作流中 **[!UICONTROL Scheduler]** 使用活动。 For more on this, refer to this [page](../../automating/using/scheduler.md).

在以下示例中，我们希望向全世界所有客户发送仅在情人节有效的促销代码。 为了在白天提供足够的使用时间，所有客户必须在2月14日上午8:00收到您的消息，具体时间取决于其所在的时区。

1. 在选项卡 **[!UICONTROL Marketing activities]** 中，开始创建您的分发（以我们的例子来说），以电子邮件的形式。 要了解有关交付创建的更多信息，请参阅此 [部分](../../channels/using/creating-an-email.md)。
1. 在设计情人节电子邮件后，单击 **[!UICONTROL Create]** 以访问传送仪表板。 有关电子邮件设计的详细信息，请参阅此 [页](../../designing/using/personalization.md#example-email-personalization)。

   ![](assets/send-time_opt_valentine_1.png)

1. 从交付功能板中，选择 **[!UICONTROL Schedule]** 块。

   ![](assets/send-time_opt_valentine_2.png)

1. 选择以下 **[!UICONTROL Messages to be sent automatically on the date]** 指定的选项。 然后在现 **[!UICONTROL Start sending from]** 场中，设置联系日期，以我们的情况为例，2月14日上午8:00，这样每个接收者都会在情人节收到它。

   ![](assets/send-time_opt_valentine.png)

1. 在字 **[!UICONTROL Time zone of the contact date]** 段中，选择默认情况下应将交付发送到的时区。

   如果将配置文 **[!UICONTROL Time zone]** 件保留为 **[!UICONTROL Default]**，则收件人将根据此处选择的时区收到分发。

1. 从下 **[!UICONTROL Optimize the sending time per recipient]** 拉菜单中，选择 **[!UICONTROL Send at the recipient's time zone]**。 这样，收件人就可以在2月14日收到情人节电子邮件，具体时间取决于他们所在的时区。

   ![](assets/send-time_opt_valentine_3.png)

1. 在确认您的交付计划后，单击按 **[!UICONTROL Prepare]** 钮，然后 **[!UICONTROL Confirm]** 单击交付。

   确保至少提前24小时确认发送。 否则，某些收件人可能会在实际的情人节活动之前收到送货，具体取决于其位置。

   ![](assets/send-time_opt_valentine_4.png)

无论收件人位于何处，他们都将在当地时间2月14日上午8点收到邮件。
