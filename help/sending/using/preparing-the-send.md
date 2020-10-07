---
title: 准备发送
description: 了解如何在发送前定义准备。
page-status-flag: never-activated
uuid: 1038dae2-164c-4579-9294-bdf2a4eb12d6
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 003abc83-7f07-471f-ab2f-1d352d22c26f
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 准备发送{#preparing-the-send}

准备对应于计算目标群和为包括在目标中的每个用户档案生成消息内容的步骤。 准备完成后，即可立即发送消息，或在预定的日 [期和时间发送消息](../../sending/using/about-scheduling-messages.md)。

1. 要开始准备发送，请单 **击操** 作栏中的“准备”按钮。

   ![](assets/preparing_delivery_2.png)

1. 块 **[!UICONTROL Deployment]** 显示了准备进度，然后是准备统计：目标消息数、要发送的消息数等。

   此操作可能需要一些时间，具体取决于目标人口的大小。

   ![](assets/preparing_delivery.png)

1. 使用操作栏中的“停止” **按钮** ，随时停止准备工作。

   在准备阶段，不会发送任何消息。 因此，您可以开始或停止此操作，而不会影响任何内容。

   ![](assets/preparing_delivery_6.png)

1. 您的消息将在准备投放阶段自动保存。 如果您需要在准备步骤后对邮件的计划进行任何更改，则需要确保再次单击该按钮 **[!UICONTROL Prepare]** ，以便考虑这些更改。 For more information on how to schedule a message, refer to this [page](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. 要视图准备日志，请单击位于块右下方的按钮。

   ![](assets/preparing_delivery_4.png)

1. 窗口 **[!UICONTROL Deployment]** 将打开，更正所有错误，然后重新开始准备。

   最后一条日志消息显示所有错误消息和错误数。 特定图标显示遇到的错误类型：黄色图标表示非关键处理错误，红色图标表示阻止投放启动的关键错误。

   ![](assets/preparing_delivery_3.png)

1. 在确认发送消息之前，请检查准备统计信息。 如果要发送的消息数与您的配置不对应，请编辑目标人群(请参 [阅在消息中选择受众](../../audiences/using/selecting-an-audience-in-a-message.md))并重新开始准备。

准备完成后，即可发送邮件。 有关此方面的详细信息，请参 [阅确认发送](../../sending/using/confirming-the-send.md)。

**分类规则**

Adobe Campaign附带一组在消息准备过程中应用的内置类型规则。 它们用于检查邮件是否有效并满足质量标准。 请参 [阅类型](../../sending/using/about-typology-rules.md)。 例如，您可以定义自己的类型规则，设置全局交叉渠道疲劳规则，该规则将自动从活动中排除过度激发的用户档案。 请参阅[疲劳规则](../../sending/using/fatigue-rules.md)。

**SMS消息检查**

如果已将个性化字段或条件文本插入SMS消息的内容，这些因素可能会引入GSM编码未考虑的字符。 运行准备时，将监视消息长度，如果消息通过限制，将显示一条警告消息。

有关详细信息，请参 [阅SMS编码、长度和音译](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)[以及个性化SMS消息](../../channels/using/personalizing-sms-messages.md) 。
