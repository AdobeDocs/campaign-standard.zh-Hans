---
title: 在Adobe Campaign Standard中控制电子邮件内容
description: 了解如何在编辑电子邮件内容时改进Adobe Campaign Standard中的可投放性。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: debbc70d-4094-44c0-b7cb-c999effda1a6
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 6%

---

# 控制电子邮件内容{#control-email-content}

<!--TO KEEP because specific to Campaign-->

为了确保您的电子邮件能够送达收件人并提高电子邮件可投放率，这些收件人必须遵守许多规则。 否则，某些邮件的内容可能会被检测为垃圾邮件。 Adobe Campaign提供了多种工具，用于使您的内容遵守这些规则。

设计消息内容时，请遵循下列原则：

* [发件人姓名和地址](#sender-name)：地址必须明确标识发件人。 域必须由发件人拥有并向其注册。 域注册表不得私有化。
  <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [个性化和发送时间优化](#perso-send-time-optimization)：个性化内容并定义每个收件人的发送时间会增加打开邮件的可能性。
* 图像和文本：遵循像样文本/图像比率（例如60%文本和40%图像）。
* [退订链接](#opt-out) 和登陆页面：退订链接至关重要。 它必须可见且有效，并且表单必须有效。
* 预览：使用Adobe Campaign提供的工具检查和优化电子邮件的内容([反垃圾邮件分析](#anti-spam-analysis)， [电子邮件渲染](#message-responsiveness))。

有关设计内容时优化可投放性的其他提示，请参阅 [Adobe可投放性最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html).

>[!NOTE]
>
>有关编辑电子邮件内容的更多信息，请参阅 [Email Designer概述](../../designing/using/designing-content-in-adobe-campaign.md) 和 [报文设计最佳实践](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

## 发件人姓名和地址 {#sender-name}

某些ISP会检查发件人地址的有效性(**[!UICONTROL From]**)。 格式错误的地址可能导致接收服务器拒绝该地址。

![](assets/delivery_content_edition16.png)

您必须确保在实例级别或在最常用的场景下提供了正确的地址。 为此，请与管理员联系。

有关此内容的更多信息，请参阅 [定义电子邮件的电子邮件发件人](../../designing/using/subject-line.md#email-sender).

## 个性化和发送时间优化 {#perso-send-time-optimization}

为了改善收件人的体验并让他们打开您的电子邮件，Adobe Campaign允许您个性化您的消息。 有关更多信息，请参阅[此小节](../../designing/using/personalization.md)。

为了提高消息的打开率，您还可以手动定义每个收件人的发送时间。 如有可能，每个用户档案都将在指定的日期和时间收到消息。 有关此内容的更多信息，请参阅 [优化发送时间](../../sending/using/optimizing-the-sending-time.md).

## 选择退出链接和表单 {#opt-out}

默认情况下，分析消息时，分类规则会检查是否包含选择退出链接，如果缺少该链接，则会生成警告。 有关管理链接的更多信息，请参阅 [本节](../../designing/using/links.md).

在每次发送之前，必须检查选择退出链接是否正常工作。 例如，当 [发送校样](../../sending/using/sending-proofs.md)，确保链接有效，表单处于联机状态，并且验证这时会检查 **[!UICONTROL No longer contact]** 盒子。 您应该系统地进行此检查，因为输入链接或更改表单时始终可能存在人为错误。 有关管理选择加入和选择退出的更多信息，请参阅 [本节](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md).

![](assets/optin_landingpage_3.png)

如果在开始投放后检测到有关退订的问题，则仍然可以为单击选择退出链接的收件人手动执行退订（例如使用批量更新功能），即使他们无法确认自己的选择。

通常，您不应通过要求希望选择退出的收件人填写电子邮件地址或姓名等字段来妨碍他们。 退订登陆页面应仅具有一个验证按钮。

请求额外确认不可靠：用户可能有两个电子邮件地址被重定向到同一个框(例如：firstname.lastname@club.com和firstname.lastname@internet-club.com)。 如果配置文件只能记住第一个地址，并且希望通过发送给另一个配置文件的消息取消订阅，则表单将拒绝此操作，因为加密标识符和输入的电子邮件地址不匹配。

## 反垃圾邮件分析 {#anti-spam-analysis}

Adobe Campaign的消息编辑器集成了 **反垃圾邮件分析** 它允许您对电子邮件进行评分，以确定邮件在接收时是否会被反垃圾邮件工具视为垃圾邮件。 有关此内容的更多信息，请参阅 [预览消息](../../sending/using/previewing-messages.md).

在消息内容编辑器中，单击 **[!UICONTROL Preview]**. 如果反垃圾邮件检查检测到此邮件有高风险，则会显示邮件警告。 单击 **[!UICONTROL Anti-spam analysis]** 以查看详细信息。

![](assets/sending_anti-spam_analysis.png)

## 电子邮件渲染 {#message-responsiveness}

在发送消息之前，您可以通过检查消息在不同设备上的外观来测试消息的响应能力。 这是为了确保以最佳方式在各种Web客户端、Web邮件和设备上显示该内容。

![](assets/inbox_rendering_report_3.png)

为了实现此功能，Adobe Campaign 会捕捉渲染状态并提供在专用报告中。这样，您就可以预览不同消息接收环境下所收到之消息的显示情况。

有关此方面的更多信息，请参阅[电子邮件呈现](../../sending/using/email-rendering.md)。
