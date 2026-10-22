---
title: 按收件人的时区发送消息
description: 了解如何按收件人的时区发送消息
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Proofs
role: User
level: Intermediate
exl-id: 48f222bd-9c2f-4eeb-a12b-bbfc62119024
TQID: 'https://experienceleague.adobe.com/0ZBuZihQqaowNG6y5gzkh5Vpz86e6pjmTRd5bNDPGxg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: 458b98fa-9d41-55f3-9c8e-3aeb5c95457a
    internal-label: Proofs
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 69%
---
# 按收件人的时区发送消息{#sending-messages-at-the-recipient-s-time-zone}

在管理日期和时间很重要的营销策划时，您可以计划一项考虑到每位收件人的当地时间的投放：他们将在自己的时区按您计划的时间收到电子邮件、短信或推送通知。

>[!NOTE]
>
>要使用此功能，请确保投放所定向的所有轮廓都在其属性的 **[!UICONTROL Address]** 部分中指定了时区。 有关访问轮廓属性的更多信息，请参阅此[章节](../../audiences/using/editing-profiles.md)。

要以收件人的时区时间发送投放，您还可以在工作流中使用 **[!UICONTROL Scheduler]** 活动。 有关更多信息，请参见此[页面](../../automating/using/scheduler.md)。

在下方的示例中，我们希望向全世界所有客户发送仅在情人节生效的促销代码。 为了让客户在当天有足够的时间使用该代码，所有客户必须于当地时区的2月14日上午8点收到您的消息。

1. 在 **[!UICONTROL Marketing activities]** 选项卡中开始创建您的投放，在本例中，就是一封电子邮件。 要了解有关投放创建的更多信息，请参阅本[章节](../../channels/using/creating-an-email.md)。
1. 设计情人节电子邮件完成后，单击 **[!UICONTROL Create]** 以访问投放仪表板。 有关电子邮件设计的更多信息，请参阅[此页面](../../designing/using/personalization.md#example-email-personalization)。

   ![](assets/send-time_opt_valentine_1.png)

1. 从投放仪表板中，选择 **[!UICONTROL Schedule]** 块。

   ![](assets/send-time_opt_valentine_2.png)

1. 选择下方指定的 **[!UICONTROL Messages to be sent automatically on the date]** 选项。 然后在&#x200B;**[!UICONTROL Start sending from]**&#x200B;字段中，设置联系日期，在本例中为2月14日上午8:00，这样每位收件人都会在情人节收到该邮件。

   ![](assets/send-time_opt_valentine.png)

1. 在 **[!UICONTROL Time zone of the contact date]** 字段中，选择发送投放的默认时区。

   如果轮廓的 **[!UICONTROL Time zone]** 保留为 **[!UICONTROL Default]**，则收件人将根据此处选择的时区接收投放。

1. 从 **[!UICONTROL Optimize the sending time per recipient]** 下拉菜单中，选择 **[!UICONTROL Send at the recipient's time zone]**。 这样，收件人就可以于当地时区的 2 月 14 日收到情人节电子邮件。

   ![](assets/send-time_opt_valentine_3.png)

1. 确认投放计划后，单击 **[!UICONTROL Prepare]** 按钮，然后 **[!UICONTROL Confirm]** 投放。

   确保至少提前 24 小时确认发送。 否则，根据收件人的位置，部分收件人可能会在当地的情人节到来之前收到该投放。

   ![](assets/send-time_opt_valentine_4.png)

无论其身在何处，所有收件人都将于当地时间2月14日上午8点收到消息。
