---
solution: Campaign Standard
product: campaign
title: 控制Adobe Campaign Standard的电子邮件内容
description: 了解如何在Adobe Campaign Standard编辑电子邮件内容时提高交付能力。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1e7359db2de1a9c420af33ac85c0597c098ae3f8
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 8%

---


# 控制电子邮件内容{#control-email-content}

要提高电子邮件的发送率，并确保您的电子邮件能够送达收件人，该电子邮件必须遵守一定数量的规则。

* **发件人姓名和地址**:地址必须明确标识发件人。域必须由发送方拥有并注册。 域注册不得私有化。
* **主题**:避免大写和标点符号过多，以及垃圾邮件发送者经常使用的词语（“Win”、“免费”等）。
* **个性化您的电子邮件**:个性化电子邮件会增加打开邮件的机会。
* **图像和文本**:请遵循适当的文本／图像比率（例如，60%的文本和40%的图像）。
* **退订链接和登陆页**:退订链接至关重要。它必须可见且有效，并且表单必须有效。
* **使用** 由Adobe Campaign提供的工具优化电子邮件内容(投放分析、防垃圾邮件分析)。

有关编辑电子邮件内容的其他信息，请参阅[电子邮件设计器概述](../../designing/using/designing-content-in-adobe-campaign.md)和[邮件设计最佳实践](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)。

## 发件人姓名和地址{#sender-name}

某些ISP在接受消息前检查发送者地址（发件人）的有效性。 格式不良的地址可能导致接收服务器拒绝它。 您必须确保在实例级别或最常用情况下提供正确的地址。 与管理员联系。

![](assets/delivery_content_edition16.png)

有关详细信息，请参阅[个性化发件人姓名](../../designing/using/personalization.md#personalizing-the-sender)。

## 发送时间优化{#send-time-optimization}

要提高消息的成功率，您可以手动定义每个收件人的发送时间。 只要有可能，每个用户档案都将在指定的日期和时间收到消息。

有关详细信息，请参阅[优化发送时间](../../sending/using/optimizing-the-sending-time.md)。

## 退出链接和表单{#opt-out}

默认情况下，在分析消息时，类型规则会检查是否包含退出链接，并在消息缺失时生成警告。

每次发送之前，必须检查退出链接是否工作正常。 例如，发送验证时，请确保链接有效、表单联机且验证此更改会选中“不再联系人”框的值。 您应该系统性地进行此检查，因为在进入链接或更改表单时，总是可能出现人为错误。

如果在启动退订后检测到关于投放的问题，则仍然可以为那些单击退出链接的收件人手动执行退订（例如，使用成批更新功能），即使他们无法确认其选择。

通常，不要试图阻碍希望退出的收件人，例如要求他们填写电子邮件地址或姓名等字段。 退订登陆页应仅包含一个验证按钮。 请求其他确认不可靠：用户可能将两个电子邮件地址重定向到同一个框(例如：firstname.lastname@club.com和firstname.lastname@internet-club.com)。 如果用户档案只能记住第一个地址，并希望通过发送给另一个地址的消息取消订阅，则表单将拒绝此请求，因为输入的加密标识符和电子邮件地址不匹配。

## 防垃圾邮件分析{#anti-spam-analysis}

Adobe Campaign的邮件编辑器集成了&#x200B;**防垃圾邮件分析**，它允许您对电子邮件进行评分以确定邮件是否存在被收到时使用的防垃圾邮件工具视为垃圾邮件的风险。 有关详细信息，请参阅[预览消息](../../sending/using/previewing-messages.md)。

在消息内容编辑器中，单击&#x200B;**[!UICONTROL Preview]**。 如果防垃圾邮件检查检测到此邮件存在高风险，则会发出警告。 单击&#x200B;**[!UICONTROL Anti-spam analysis]**&#x200B;以视图详细信息。

![](assets/sending_anti-spam_analysis.png)

## 检查消息响应{#message-responsiveness}

在发送消息之前，您可以检查消息在不同设备上的显示效果。 这是为了确保它以最佳方式显示在各种Web客户端、Web邮件和设备上。

为了实现此功能，Adobe Campaign 会捕捉渲染状态并提供在专用报告中。这样，您就可以预览不同消息接收环境下所收到之消息的显示情况。

有关此方面的更多信息，请参阅[电子邮件呈现](../../sending/using/email-rendering.md)。

![](assets/inbox_rendering_report_3.png)
