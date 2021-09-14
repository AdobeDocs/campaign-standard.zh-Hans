---
title: 准备发送
description: 了解如何在发送之前定义准备。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: 0140c41a-7255-4b77-a1b7-c6f7b1135e51
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 2%

---

# 准备发送{#preparing-the-send}

准备对应于计算目标群体并为目标中包含的每个用户档案生成消息内容的步骤。 准备完成后，即可立即或在[计划日期和时间](../../sending/using/about-scheduling-messages.md)发送消息。

1. 要开始准备发送，请单击操作栏中的&#x200B;**Prepare**&#x200B;按钮。

   ![](assets/preparing_delivery_2.png)

1. **[!UICONTROL Deployment]**&#x200B;块显示准备进度，然后显示准备统计信息：目标消息数、要发送的消息数等。

   根据目标群体的大小，此操作可能需要一些时间。

   ![](assets/preparing_delivery.png)

1. 使用位于操作栏中的&#x200B;**Stop**&#x200B;按钮，随时停止准备工作。

   在准备阶段期间，不会发送任何消息。 因此，您可以启动或停止此操作，而不会产生任何影响。

   ![](assets/preparing_delivery_6.png)

1. 在准备投放阶段时，会自动保存您的消息。 如果在准备步骤后需要对消息的计划进行任何更改，则需要确保再次单击&#x200B;**[!UICONTROL Prepare]**&#x200B;按钮以考虑这些更改。 有关如何计划消息的更多信息，请参阅此[页面](../../sending/using/about-scheduling-messages.md)。

   ![](assets/preparing_delivery_5.png)

1. 要查看准备日志，请单击位于块右下方的按钮。

   ![](assets/preparing_delivery_4.png)

1. 将打开&#x200B;**[!UICONTROL Deployment]**&#x200B;窗口，更正所有错误，然后重新开始准备。

   最后一个日志消息显示所有错误消息和错误数。 特定图标显示遇到的错误类型：黄色图标表示非关键处理错误，红色图标表示阻止投放启动的关键错误。

   ![](assets/preparing_delivery_3.png)

1. 在确认发送消息之前，请检查准备统计信息。 如果要发送的消息数与您的配置不对应，请编辑目标群体（请参阅[在消息中选择受众](../../audiences/using/selecting-an-audience-in-a-message.md)）并重新开始准备。

准备完成后，即可发送您的消息。 有关更多信息，请参阅[确认发送](../../sending/using/confirming-the-send.md)。

**分类规则**

Adobe Campaign附带了一组在消息准备期间应用的内置分类规则。 它们用于检查消息是否有效且符合您的质量标准。 请参阅[分类](../../sending/using/about-typology-rules.md)。 例如，您可以定义自己的分类规则，以设置全局跨渠道疲劳规则，从而自动从营销活动中排除过度投放的用户档案。 请参阅[疲劳规则](../../sending/using/fatigue-rules.md)。

**短信消息检查**

如果在短信消息内容中插入了个性化字段或条件文本，则这些因素可能会引入GSM编码无法识别的字符。 运行准备时，会监控消息长度，并在消息超过限制时显示警告消息。

有关更多信息，请参阅[短信编码、长度和音译](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)和[个性化短信消息](../../channels/using/personalizing-sms-messages.md)章节。
