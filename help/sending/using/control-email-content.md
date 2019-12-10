---
title: 在Adobe Campaign standard中控制电子邮件内容
description: 了解如何在编辑电子邮件内容时提高Adobe Campaign standard的可交付性。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f0580e1ab75d4250bfb1cb801ff08b31b91cdc5a

---


# 控制电子邮件内容{#control-email-content}

要提高电子邮件的发送率并确保电子邮件到达收件人，电子邮件必须遵守一定数量的规则。

* **发件人姓名和地址**:地址必须明确标识发送方。 域必须归发送方所有并注册。 域注册不得私有化。
* **主题**:避免大写和标点符号过多，以及垃圾邮件发送者经常使用的词语（“Win”、“免费”等）。
* **个性化您的电子邮件**:个性化电子邮件会增加您的消息打开的机率。
* **图像和文本**:遵守适当的文本／图像比率（例如，60%的文本和40%的图像）。
* **取消订阅链接和登录页面**:取消订阅链接是必需的。 它必须可见且有效，并且表单必须具有功能性。
* **使用** Adobe Campaign提供的工具优化电子邮件内容（分发分析、反垃圾邮件分析）。

有关编辑电子邮件内容的其他信息，请参阅 [Email Designer概述](../../designing/using/designing-content-in-adobe-campaign.md) ，以及 [Message设计最佳实践](../../designing/using/overview.md#content-design-best-practices)。

## 发件人姓名和地址 {#sender-name}

某些ISP在接受消息之前检查发送者地址（发件人）的有效性。 格式不良的地址可能导致接收服务器拒绝它。 您必须确保在实例级别或最常用的情况下提供正确的地址。 请联系您的管理员。

![](assets/delivery_content_edition16.png)

有关此内容的详细信息，请参 [阅个性化发送者姓名](../../designing/using/personalization.md#personalizing-the-sender)。

## 主题行 {#subject-line}

在编辑电子邮件时，您可以尝试不同的主题行并在发送电子邮件之前获得其打开率的估计。 有关此方面的详细信息，请 [参阅测试电子邮件的主题行](../../sending/using/testing-subject-line-email.md)。

![](assets/predictive_subject_line_example.png)

有关定义电子邮件主题行的详细信息，请参阅 [此部分](../../designing/using/subject-line.md)。

## 发送时间优化 {#send-time-optimization}

要提高消息的成功率，您可以手动定义每个收件人的发送时间。 每个配置文件都会在指定的日期和时间收到消息（如果可能）。

有关此问题的详细信息，请参 [阅优化发送时间](../../sending/using/optimizing-the-sending-time.md)。

## 退出链接和表单 {#opt-out}

默认情况下，在分析消息时，排版规则检查是否包含退出链接，并在消息缺失时生成警告。

在每次发送之前，您必须检查退出链接是否工作正常。 例如，发送证明时，请确保链接有效，表单联机，并验证此操作会更改“不再联系人”框的值。 您应该系统性地进行此检查，因为进入链接或更改表单时，总是可能出现人为错误。

如果在发送开始后检测到关于取消订阅的问题，则仍然可以为那些单击退出链接的接收者手动执行取消订阅（例如，使用成批更新功能），即使他们无法确认其选择。

通常，不要试图通过要求收件人填写电子邮件地址或姓名等字段来妨碍希望退出的收件人。 取消订阅登陆页面应仅具有一个验证按钮。 请求其他确认不可靠：用户可能有两个电子邮件地址被重定向到同一个框(例如：firstname.lastname@club.com和firstname.lastname@internet-club.com)。 如果配置文件只能记住第一个地址并希望通过发送给另一个地址的消息取消订阅，则表单将拒绝此项，因为输入的加密标识符和电子邮件地址不匹配。

## 反垃圾邮件分析 {#anti-spam-analysis}

Adobe Campaign的消息编辑器集成了 **Anti-spam分析** ，它允许您对电子邮件进行评分以确定邮件是否存在被收到时使用的防垃圾邮件工具视为垃圾邮件的风险。 有关此内容的详细信息，请参阅 [预览消息](../../sending/using/previewing-messages.md)。

在消息内容编辑器中，单击 **[!UICONTROL Preview]**。 如果防垃圾邮件检查检测到此邮件存在高风险，则会显示一条消息警告您。 单击 **[!UICONTROL Anti-spam analysis]** 可查看详细信息。

![](assets/sending_anti-spam_analysis.png)

## 检查消息响应性 {#message-responsiveness}

在发送消息之前，您可以检查消息在不同设备上的显示效果。 这旨在确保它以最佳方式显示在各种Web客户端、Web邮件和设备上。

为此，Adobe Campaign捕获渲染并在专用报告中提供。 这样，您就可以在接收消息的不同上下文中预览发送的消息。

有关此内容的详细信息，请参阅电 [子邮件渲染](../../sending/using/email-rendering.md)。

![](assets/inbox_rendering_report_3.png)
