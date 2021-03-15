---
solution: Campaign Standard
product: campaign
title: 准备发送
description: 了解如何在发送前定义准备。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: 发送时间优化
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 2%

---


# 准备发送{#preparing-the-send}

准备对应于计算目标群和为目标中包括的每个用户档案生成消息内容的步骤。 准备完成后，即可立即或在预定日期和时间[发送消息。](../../sending/using/about-scheduling-messages.md)

1. 要开始准备发送，请单击操作栏中的&#x200B;**准备**&#x200B;按钮。

   ![](assets/preparing_delivery_2.png)

1. **[!UICONTROL Deployment]**&#x200B;块显示准备进度，然后显示准备统计数据：目标消息数、要发送的消息数等。

   此操作可能需要一些时间，具体取决于目标人口的大小。

   ![](assets/preparing_delivery.png)

1. 使用操作栏中的&#x200B;**停止**&#x200B;按钮，随时停止准备工作。

   在准备阶段，不会发送任何消息。 因此，您可以开始或停止此操作，而不会影响任何内容。

   ![](assets/preparing_delivery_6.png)

1. 您的消息将在准备投放阶段自动保存。 如果您需要在准备步骤后对邮件的计划进行任何更改，则需要确保再次单击&#x200B;**[!UICONTROL Prepare]**&#x200B;按钮，以便将这些更改考虑在内。 有关如何计划消息的详细信息，请参阅此[页面](../../sending/using/about-scheduling-messages.md)。

   ![](assets/preparing_delivery_5.png)

1. 要视图准备日志，请单击位于块右下角的按钮。

   ![](assets/preparing_delivery_4.png)

1. 将打开&#x200B;**[!UICONTROL Deployment]**&#x200B;窗口，更正所有错误，然后重新开始准备。

   最后一条日志消息显示所有错误消息和错误数。 特定图标显示遇到的错误类型：黄色图标表示非关键处理错误，红色图标表示阻止投放启动的关键错误。

   ![](assets/preparing_delivery_3.png)

1. 在确认发送消息之前检查准备统计信息。 如果要发送的消息数与您的配置不对应，请编辑目标群体(请参阅[在消息](../../audiences/using/selecting-an-audience-in-a-message.md)中选择受众)并重新开始准备。

准备完毕后，即可发送您的消息。 有关详细信息，请参阅[确认发送](../../sending/using/confirming-the-send.md)。

**分类规则**

Adobe Campaign附带一组在消息准备过程中应用的内置类型规则。 它们用于检查消息是否有效并符合您的质量标准。 请参阅[类型](../../sending/using/about-typology-rules.md)。 例如，您可以定义自己的类型规则，设置全局跨渠道疲劳规则，这些规则会自动从活动中排除过度激活的用户档案。 请参阅[疲劳规则](../../sending/using/fatigue-rules.md)。

**SMS消息检查**

如果已将个性化字段或条件文本插入到SMS消息的内容中，这些因素可能会引入GSM编码未考虑的字符。 运行准备时，将监视消息长度，并在消息超过限制时显示警告消息。

有关详细信息，请参阅[SMS编码、长度和音译](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)和[个性化SMS消息](../../channels/using/personalizing-sms-messages.md)部分。
