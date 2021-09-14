---
title: 在Adobe Campaign Standard中控制电子邮件内容
description: 了解如何在编辑电子邮件内容时提高Adobe Campaign Standard中的投放能力。
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
source-wordcount: '790'
ht-degree: 8%

---

# 控制电子邮件内容{#control-email-content}

<!--TO KEEP because specific to Campaign-->

为确保您的电子邮件能够到达收件人并提高电子邮件的投放率，收件人必须遵守许多规则。 否则，某些消息的内容可能会被检测为垃圾邮件。 Adobe Campaign为您提供了多种工具，可让您的内容符合这些规则。

设计消息内容时，请遵循以下所列原则：

* [发件人姓名和地址](#sender-name):地址必须明确识别发件人。域必须由发件人拥有并注册。 域注册表不得私有化。

   <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [个性化和发送时间优化](#perso-send-time-optimization):个性化内容并定义每个收件人的发送时间会增加打开消息的可能性。
* 图像和文本：应遵循适当的文本/图像比率（例如，60%的文本和40%的图像）。
* [退订](#opt-out) 链接和登陆页面：退订链接至关重要。它必须可见且有效，并且表单必须有效。
* 预览：使用Adobe Campaign提供的工具检查并优化电子邮件的内容([Anti-spam analysis](#anti-spam-analysis)、[Email rendering](#message-responsiveness))。

有关在设计内容时优化投放能力的其他提示，请参阅[Adobe投放能力最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html)。

>[!NOTE]
>
>有关编辑电子邮件内容的更多信息，请参阅[Email Designer概述](../../designing/using/designing-content-in-adobe-campaign.md)和[消息设计最佳实践](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)。

## 发件人姓名和地址 {#sender-name}

某些ISP在接受消息之前先检查发件人地址(**[!UICONTROL From]**)的有效性。 地址格式不正确可能导致接收服务器拒绝该地址。

![](assets/delivery_content_edition16.png)

您必须确保在实例级别或最常用的情况下给出正确的地址。 为此，请与管理员联系。

有关更多信息，请参阅[定义电子邮件](../../designing/using/subject-line.md#email-sender)的电子邮件发件人。

## 个性化和发送时间优化 {#perso-send-time-optimization}

为了改善收件人的体验并使其打开您的电子邮件，Adobe Campaign允许您个性化邮件。 有关更多信息，请参阅[此章节](../../designing/using/personalization.md)。

要提高消息的打开率，您还可以手动定义每个收件人的发送时间。 只要有可能，每个用户档案都将在指定的日期和时间收到消息。有关更多信息，请参阅[优化发送时间](../../sending/using/optimizing-the-sending-time.md)。

## 选择退出链接和表单 {#opt-out}

默认情况下，分析消息时，分类规则会检查是否包含选择退出链接，并在消息缺失时生成警告。 有关管理链接的更多信息，请参阅[此部分](../../designing/using/links.md)。

在每次发送之前，您必须检查选择退出链接是否正常工作。 例如，在[发送校样](../../sending/using/sending-proofs.md)时，确保链接有效、表单已联机并且验证会选中&#x200B;**[!UICONTROL No longer contact]**&#x200B;框。 您应该系统性地进行此检查，因为进入链接或更改表单时始终可能出现人为错误。 有关管理选择加入和选择退出的更多信息，请参阅[此部分](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)。

![](assets/optin_landingpage_3.png)

如果在投放开始后检测到与退订有关的问题，则仍然可以为单击选择退订链接的收件人手动执行退订（例如使用批量更新功能），即使他们无法确认其选择。

通常，您不应尝试通过要求收件人填写诸如其电子邮件地址或姓名之类的字段来阻止希望选择退出的收件人。 退订登陆页面应仅具有一个验证按钮。

请求附加确认不可靠：用户可能具有两个重定向到同一框的电子邮件地址(例如：firstname.lastname@club.com和firstname.lastname@internet-club.com)。 如果用户档案只能记住第一个地址，并希望通过发送给另一个地址的消息取消订阅，则表单将拒绝此请求，因为加密的标识符与输入的电子邮件地址不匹配。

## 反垃圾邮件分析 {#anti-spam-analysis}

Adobe Campaign的消息编辑器集成了&#x200B;**反垃圾邮件分析**，该分析允许您对电子邮件进行评分，以确定邮件是否存在被接收时使用的反垃圾邮件工具视为垃圾邮件的风险。 有关更多信息，请参阅[预览消息](../../sending/using/previewing-messages.md)。

在消息内容编辑器中，单击&#x200B;**[!UICONTROL Preview]**。 如果防垃圾邮件检查检测到此邮件存在高风险，则会向您发出警告。 单击&#x200B;**[!UICONTROL Anti-spam analysis]**&#x200B;查看详细信息。

![](assets/sending_anti-spam_analysis.png)

## 电子邮件渲染 {#message-responsiveness}

在发送消息之前，您可以通过检查消息在不同设备上的外观来测试消息的响应速度。 这是为了确保以最佳方式在各种Web客户端、Web邮件和设备上显示它。

![](assets/inbox_rendering_report_3.png)

为了实现此功能，Adobe Campaign 会捕捉渲染状态并提供在专用报告中。这样，您就可以预览不同消息接收环境下所收到之消息的显示情况。

有关此方面的更多信息，请参阅[电子邮件呈现](../../sending/using/email-rendering.md)。
