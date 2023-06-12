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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 2%

---

# 使用陷阱 {#using-traps}

使用陷阱时，消息将发送到 [测试配置文件](../../audiences/using/managing-test-profiles.md) 就像发送到主目标一样，作为一种标识您的客户端文件是否正遭到欺诈使用的手段。

陷阱最初用于直邮投放。 它们允许您：

* 验证直邮提供商是否确实在发送通信。
* 以与客户相同的条件和时间接收邮件。
* 保留已发送邮件的精确副本。
* 检查您的客户端列表是否未被直邮提供商滥用。 事实上，如果将任何其他通信发送到测试用户档案的地址，则您的客户端文件可能在您不知道的情况下被使用。 因此，测试用户档案的地址只能用于此目的。

有关向直邮的受众添加陷阱的更多信息，请参阅 [添加测试和陷阱用户档案](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles).

对于其他通信渠道，可以将陷阱测试用户档案添加到主目标，以便：

* 检查您的消息是否已成功发送。
* 获取并保留消息的确切副本。
* 跟踪其发送和接收时间。

要将测试用户档案用作陷阱，必须将其包含在消息的受众中。

>[!NOTE]
>
>与测试配置文件使用的不同 [验证](../../sending/using/sending-proofs.md) 或 [电子邮件渲染](../../sending/using/email-rendering.md)，则该消息会同时发送到主目标和用作陷阱的测试用户档案。

定义消息的受众时：

1. 从 **[!UICONTROL Test profiles]** 选项卡，选择测试用户档案。 确保它具有 **[!UICONTROL Trap]** 作为预期用途。

   ![](assets/trap_select.png)

1. 消息内容准备就绪后，单击 **[!UICONTROL Prepare]** 按钮。 参见 [准备发送](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >确保选择了主目标。 否则，无法发送您的消息。

1. 单击 **[!UICONTROL Confirm]** 按钮。请参阅[确认发送](../../sending/using/confirming-the-send.md)。

   ![](assets/trap_confirm.png)

消息将发送到主目标和测试用户档案。

发送事务型消息时，可以使用陷阱。 在这种情况下，测试用户档案将收到每个事件配置一条消息。 有关事务型消息传递的更多信息，请参阅此 [部分](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>当使用测试用户档案作为陷阱时，对于消息中的任何扩充字段，相应的附加数据从真实的目标用户档案中随机选取并分配给陷阱测试用户档案。 有关扩充的更多信息，请参阅 [此示例](../../automating/using/enriching-profile-data-file.md).
