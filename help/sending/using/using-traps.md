---
solution: Campaign Standard
product: campaign
title: 使用陷阱
description: 了解如何在消息中使用陷印。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Seed Address
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 2%

---


# 使用陷阱 {#using-traps}

当使用陷阱时，消息将发送到[测试用户档案](../../audiences/using/managing-test-profiles.md)，就像发送到主目标一样，作为确定您的客户端文件是否被欺骗性地使用的手段。

陷印最初是为直邮投放设计的。 它们允许您：

* 验证您的直邮提供商是否确实在发送通信。
* 在与客户相同的条件下同时接收邮件。
* 保留已发送邮件的确切副本。
* 检查您的客户列表是否未被您的直邮提供商滥用。 事实上，如果向测试用户档案的地址发送了任何其他通信，您可能在不知情的情况下使用了客户端文件。 这就是测试用户档案的地址只能用于此目的的原因。

有关向直邮受众添加陷印的详细信息，请参阅[添加测试和陷印用户档案](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)。

对于其他通信渠道，您可以向主目标添加陷印测试用户档案，以便：

* 检查您的消息是否已成功发送。
* 获取并保留您的消息的精确副本。
* 跟踪发送和接收时间。

要将测试用户档案用作陷阱，必须将其包含在消息的受众中。

>[!NOTE]
>
>与用于[验证](../../sending/using/sending-proofs.md)或[电子邮件呈现](../../sending/using/email-rendering.md)的测试用户档案不同，消息同时发送到主目标和用作陷阱的测试用户档案。

定义消息的受众时：

1. 从&#x200B;**[!UICONTROL Test profiles]**&#x200B;选项卡中，选择测试用户档案。 确保它具有&#x200B;**[!UICONTROL Trap]**&#x200B;作为预期用途。

   ![](assets/trap_select.png)

1. 消息内容准备就绪后，单击&#x200B;**[!UICONTROL Prepare]**&#x200B;按钮。 请参阅[准备发送](../../sending/using/preparing-the-send.md)。
   >[!NOTE]
   >
   >确保您选择了主目标。 否则，无法发送您的消息。

1. 单击 **[!UICONTROL Confirm]** 按钮。请参阅[确认发送](../../sending/using/confirming-the-send.md)。

   ![](assets/trap_confirm.png)

消息将发送到主目标和测试用户档案。

在发送事务性消息时可使用陷印。 在这种情况下，测试用户档案将收到每个事件配置一条消息。 有关事务消息的详细信息，请参阅此[部分](../../channels/using/getting-started-with-transactional-msg.md)。

>[!NOTE]
>
>当使用测试用户档案作为陷阱时，对于消息中的任何富集字段，从实际目标用户档案随机选取相应的附加数据并分配给陷阱测试用户档案。 有关扩充的详细信息，请参阅[此示例](../../automating/using/enriching-profile-data-file.md)。
