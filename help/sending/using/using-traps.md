---
title: 使用陷印
description: 了解如何在消息中使用陷印。
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a7c2d444b7d971124b676fa2392b51aab40e5629

---


# 使用陷印 {#using-traps}

使用陷阱时，消息会像发送到主目标一样发送到 [测试配置文件](../../audiences/using/managing-test-profiles.md) ，作为确定客户端文件是否被欺骗性地使用的一种手段。

陷阱最初设计用于直接邮寄。 它们允许您：

* 验证您的直邮提供商是否确实在发送通信。
* 在与客户相同的条件下同时接收邮件。
* 保留已发送的邮件的精确副本。
* 检查您的直邮提供商是否未滥用您的客户列表。 事实上，如果将任何其他通信发送到您的测试配置文件的地址，您的客户端文件可能在您不知情的情况下被使用。 因此，测试配置文件的地址只能用于此目的。

有关向直邮受众添加陷印的详细信息，请参阅添 [加测试和陷印配置文件](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)。

对于其他通信渠道，您可以向主目标添加陷印测试配置文件，以便：

* 检查您的消息是否已成功发送。
* 获取并保留消息的精确副本。
* 跟踪发送和接收时间。

要将测试配置文件用作陷阱，它必须包含在消息的受众中。

>[!NOTE]
>
>与用于校样或电子邮 [件渲染](../../sending/using/sending-proofs.md)[的测试配置文件不同](../../sending/using/email-rendering.md)，消息将同时发送到主目标和用作陷阱的测试配置文件。

定义消息的受众时：

1. 从选项卡 **[!UICONTROL Test profiles]** 中，选择测试配置文件。 确保其已作 **[!UICONTROL Trap]** 为预期用途。

   ![](assets/trap_select.png)

1. 消息内容准备就绪后，单击该 **[!UICONTROL Prepare]** 按钮。 See [Preparing the send](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >确保选择了主目标。 否则，将无法发送您的消息。

1. Click the **[!UICONTROL Confirm]** button. See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

消息将发送到主目标和测试配置文件。

在发送事务性消息时，可以使用陷阱。 在这种情况下，测试配置文件将收到一条消息，每条事件配置。 有关事务性消息传递的更多信息，请参 [阅此部分](../../channels/using/about-transactional-messaging.md)。

>[!NOTE]
>
>当使用测试配置文件作为陷印时，对于消息中的任何富集字段，从实际目标配置文件随机选取相应的附加数据并分配给陷印测试配置文件。 有关丰富化的更多信息，请参 [阅此示例](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file)。
