---
title: 使用陷阱
description: 了解如何在消息中使用陷阱。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Seed Address
role: User
level: Intermediate
exl-id: 0482a946-35b1-426f-8505-42adcd1c3bbb
source-git-commit: ee3ab5304e80ea098f7e172f6b3f4af4324e8eb4
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 2%

---

# 使用陷阱 {#using-traps}

使用陷阱时，将消息发送到[测试用户档案](../../audiences/using/managing-test-profiles.md)，就像发送到主目标一样，以识别您的客户端文件是否被欺骗性使用。

陷阱最初用于直邮投放。 它们允许您：

* 验证直邮提供商是否确实在发送邮件。
* 以与客户相同的条件和时间接收邮件。
* 保留已发送邮件的精确副本。
* 检查您的客户端列表是否未被直邮提供商滥用。 事实上，如果将任何其他通信发送到测试用户档案的地址，则您的客户端文件可能在您不知道的情况下被使用。 因此，测试用户档案的地址只能用于此目的。

有关向直邮受众添加陷阱的更多信息，请参阅[添加测试和陷阱用户档案](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)。

对于其他通信渠道，可以将陷阱测试用户档案添加到主目标，以便：

* 检查您的消息是否发送成功。
* 获取并保留消息的确切副本。
* 跟踪其发送和接收时间。

要将测试用户档案用作陷阱，必须将其包含在消息的受众中。

>[!NOTE]
>
>与用于[验证](../../sending/using/sending-proofs.md)或[电子邮件渲染](../../sending/using/email-rendering.md)的测试用户档案不同，该消息将同时发送到主目标和用作陷阱的测试用户档案。

定义消息的受众时：

1. 从&#x200B;**[!UICONTROL Test profiles]**&#x200B;选项卡中，选择一个测试配置文件。 确保它具有&#x200B;**[!UICONTROL Trap]**&#x200B;作为预期用途。

   ![](assets/trap_select.png)

1. 消息内容准备就绪后，单击&#x200B;**[!UICONTROL Prepare]**&#x200B;按钮。 请参阅[准备发送](../../sending/using/preparing-the-send.md)。
   >[!NOTE]
   >
   >确保选择了主目标。 否则，无法发送您的消息。

1. 单击 **[!UICONTROL Confirm]** 按钮。请参阅[确认发送](../../sending/using/confirming-the-send.md)。

   ![](assets/trap_confirm.png)

该消息将发送到主目标和测试用户档案。

发送事务型消息时，可以使用陷阱。 在这种情况下，测试配置文件将在每个事件配置中收到一条消息。 有关事务型消息传递的详细信息，请参阅此[部分](../../channels/using/getting-started-with-transactional-msg.md)。

>[!NOTE]
>
>将测试用户档案用作陷阱时，消息中的任何扩充字段都将具有从真实目标用户档案中随机选择并分配给陷阱测试用户档案的相应附加数据。 但是，请注意，如果由于在首次消息准备期间应用分类规则而排除真正的目标用户档案，则投放准备将失败。 出现此故障的原因是，无法用扩充字段值替换陷阱用户档案。 因此，排除类型规则可能无法正确应用于实际的收件人。
>
>要防止出现这种情况，请避免在事务类型中将陷阱测试用户档案与筛选或疲劳规则同时使用。 了解有关扩充的更多信息。 有关扩充的详细信息，请参阅[此示例](../../automating/using/enriching-profile-data-file.md)。
