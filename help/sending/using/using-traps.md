---
solution: Campaign Standard
product: campaign
title: 使用陷阱
description: 了解如何在消息中使用陷阱。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 2%

---


# 使用陷阱 {#using-traps}

当使用陷阱时，消息将发送 [到测试用户档案](../../audiences/using/managing-test-profiles.md) ，就像发送到主目标一样，作为确定您的客户端文件是否被欺骗性地使用的一种手段。

陷阱最初是为直邮投放设计的。 它们允许您：

* 验证您的直邮提供商是否确实在发送通信。
* 在与客户相同的条件下同时接收邮件。
* 保留已发送邮件的确切副本。
* 检查您的直邮提供商是否未滥用您的客户列表。 事实上，如果将任何其他通信发送到测试用户档案的地址，您的客户文件可能已在您不知情的情况下被使用。 因此，测试用户档案的地址应仅用于此目的。

有关向直邮受众添加陷阱的详细信息，请参阅 [添加测试和陷阱用户档案](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)。

对于其他通信渠道，您可以向主目标添加陷阱测试用户档案，以便：

* 检查邮件是否已成功发送。
* 获取并保留消息的精确副本。
* 跟踪发送和接收时间。

要将测试用户档案用作陷阱，必须将其包含在邮件的受众中。

>[!NOTE]
>
>与用于用户档案或电 [子邮](../../sending/using/sending-proofs.md) 件渲染 [](../../sending/using/email-rendering.md)的测试验证不同，消息将同时发送到主目标和用作陷阱的测试用户档案。

定义消息的受众时：

1. 从选项卡 **[!UICONTROL Test profiles]** 中，选择一个测试用户档案。 确保它已 **[!UICONTROL Trap]** 达到预期用途。

   ![](assets/trap_select.png)

1. 消息内容准备就绪后，单击 **[!UICONTROL Prepare]** 按钮。 See [Preparing the send](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >确保您选择了主目标。 否则，将无法发送您的消息。

1. 单击 **[!UICONTROL Confirm]** 按钮。请参阅[确认发送](../../sending/using/confirming-the-send.md)。

   ![](assets/trap_confirm.png)

消息将发送到主目标和测试用户档案。

发送事务性消息时可使用陷阱。 在这种情况下，测试用户档案将收到每个事件配置一条消息。 For more on transactional messaging, see this [section](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>当使用测试用户档案作为陷阱时，对于消息中的任何富集字段，从实际目标用户档案随机选取相应的附加数据并分配给陷阱测试用户档案。 有关扩充的更多信息，请 [参阅此示例](../../automating/using/enriching-profile-data-file.md)。
