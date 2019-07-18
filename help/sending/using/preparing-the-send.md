---
title: 准备发送
seo-title: 准备发送
description: 准备发送
seo-description: 了解如何在发送之前定义准备。
page-status-flag: 从未激活
uuid: 1038de2-164c-4579-9294-bdf2 a4 eb12 d6
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: 准备和测试消息
discoiquuid: 003abc83-7f07-471f-ab2 f-1d352 d22 c26 f
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Preparing the send{#preparing-the-send}

准备操作对应于计算目标人群和为目标中包含的每个配置文件生成消息内容的步骤。Once preparation is finished, the messages are ready to be sent, either immediately or at [the scheduled date and time](../../sending/using/about-scheduling-messages.md).

1. To start preparing the send, click the **Prepare** button located in the action bar.

   ![](assets/preparing_delivery_2.png)

1. **[!UICONTROL Deployment]** 此块显示准备进度，然后显示准备统计数据：目标消息数量、发送消息数量等。

   根据目标人群的大小，此操作可能需要一些时间。

   ![](assets/preparing_delivery.png)

1. Stop the preparation at any time using the **Stop** button, located in the action bar.

   在准备阶段，不发送邮件。因此，您可以开始或停止此操作，而不会影响任何内容。

   ![](assets/preparing_delivery_6.png)

1. 在准备交付阶段，您的消息会自动保存。If you need to make any changes to your message's schedule after the preparation step, you will need to make sure that you click the **[!UICONTROL Prepare]** button again for those changes to be taken into account. For more information on how to schedule a message, refer to this [page](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. 要查看准备日志，请单击位于该块右下角的按钮。

   ![](assets/preparing_delivery_4.png)

1. **[!UICONTROL Deployment]** 窗口将打开，更正任何错误，然后重新开始准备。

   最后一条日志消息会显示任何错误消息和错误数。特定图标显示遇到的错误类型：黄色图标表示非关键处理错误，红色图标表示一个关键错误，该错误导致交付无法开始。

   ![](assets/preparing_delivery_3.png)

1. 确认发送消息之前，请检查准备统计信息。If the number of messages to send does not correspond to your configuration, edit the targeted population (see [Selecting an audience in a message](../../audiences/using/selecting-an-audience-in-a-message.md)) and restart the preparation.

准备完毕后，您的消息便可以发送。For more on this, see [Confirming send](../../sending/using/confirming-the-send.md).

**Typology规则**

Adobe Campaign附带一系列在消息准备过程中应用的内置规则规则。它们用于检查消息是否有效并符合质量标准。See [Typologies](../../administration/using/about-typology-rules.md). 例如，您可以定义自己的排版规则，例如，可以设置全局跨渠道疲劳规则，该规则会自动将被覆盖的配置文件从营销活动中排除出来。See [Fatigue rules](../../administration/using/fatigue-rules.md).

**SMS消息检查**

如果您在SMS消息内容中插入了个性化字段或条件文本，则这些因素可能会引入GSM编码未考虑到的字符。运行准备时，消息长度会受到监视，如果它通过限制，将显示一条警告消息。

For more on this, refer to the [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) and [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) sections.
