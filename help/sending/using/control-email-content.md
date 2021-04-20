---
solution: Campaign Standard
product: campaign
title: 在Adobe Campaign Standard中控制电子邮件内容
description: 了解如何在编辑电子邮件内容时提高Adobe Campaign Standard中的交付能力。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 8%

---


# 控制电子邮件内容{#control-email-content}

<!--TO KEEP because specific to Campaign-->

要确保您的电子邮件能够触及您的收件人并提高您的电子邮件发送率，他们必须遵守许多规则。 否则，某些消息的内容可被检测为垃圾邮件。 Adobe Campaign为您提供多种工具，使您的内容符合这些规则。

在设计消息内容时，请遵循以下列出的原则：

* [发件人姓名和地址](#sender-name):地址必须明确地识别发件人。域必须由发送方拥有并注册。 域注册不得私有化。

   <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [个性化和发送时间优化](#perso-send-time-optimization):个性化内容并为每个收件人定义发送时间会增加打开消息的机会。
* 图像和文本：请遵守适当的文本/图像比率（例如，60%的文本和40%的图像）。
* [退订](#opt-out) 链接和登陆页:退订链接至关重要。它必须可见且有效，并且表单必须能够正常工作。
* 预览:使用Adobe Campaign提供的工具检查并优化您的电子邮件内容([反垃圾邮件分析](#anti-spam-analysis)、[电子邮件呈现](#message-responsiveness))。

有关在设计内容时优化交付性的其他提示，请参阅[《Adobe交付性最佳实践指南》](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html)。

>[!NOTE]
>
>有关编辑电子邮件内容的详细信息，请参阅[电子邮件设计器概述](../../designing/using/designing-content-in-adobe-campaign.md)和[邮件设计最佳实践](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)。

## 发件人姓名和地址{#sender-name}

某些ISP在接受消息前检查发送者地址(**[!UICONTROL From]**)的有效性。 格式不良的地址可能导致接收服务器拒绝它。

![](assets/delivery_content_edition16.png)

您必须确保在实例级别或最频繁使用的情况下提供正确的地址。 要执行此操作，请与管理员联系。

有关详细信息，请参阅[定义电子邮件的电子邮件发件人](../../designing/using/subject-line.md#email-sender)。

## 个性化和发送时间优化{#perso-send-time-optimization}

为了改善收件人的体验并使他们打开您的电子邮件，Adobe Campaign使您能够个性化您的信息。 有关更多信息，请参阅[此章节](../../designing/using/personalization.md)。

要提高消息的打开率，您还可以手动定义每个收件人的发送时间。 只要有可能，每个用户档案都将在指定的日期和时间收到消息。有关详细信息，请参阅[优化发送时间](../../sending/using/optimizing-the-sending-time.md)。

## 退出链接和表单{#opt-out}

默认情况下，在分析消息时，类型规则会检查是否包含退出链接，并在消息缺失时生成警告。 有关管理链接的详细信息，请参阅[此部分](../../designing/using/links.md)。

在每次发送之前，您必须检查退出链接是否工作正常。 例如，在[发送验证](../../sending/using/sending-proofs.md)时，请确保链接有效，表单联机，并验证该表单会检查&#x200B;**[!UICONTROL No longer contact]**&#x200B;框。 您应系统性地进行此检查，因为进入链接或更改表单时总是可能出现人为错误。 有关管理加入和退出的详细信息，请参阅[本节](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)。

![](assets/optin_landingpage_3.png)

如果在启动退订后检测到有关投放的问题，则仍然可以手动（例如，使用成批更新功能）对单击退出链接的收件人执行退订，即使他们无法确认其选择。

通常，您不应试图阻止希望退出的收件人，例如要求他们填写电子邮件地址或姓名等字段。 退订登陆页应仅包含一个验证按钮。

请求其他确认是不可靠的：用户可能有两个电子邮件地址被重定向到同一框(例如：firstname.lastname@club.com和firstname.lastname@internet-club.com)。 如果用户档案只能记住第一个地址，并希望通过发送给另一个地址的消息取消订阅，则表单将拒绝此请求，因为输入的加密标识符和电子邮件地址不匹配。

## 防垃圾邮件分析{#anti-spam-analysis}

Adobe Campaign的消息编辑器集成了&#x200B;**反垃圾邮件分析**，它允许您对电子邮件进行评分以确定消息是否存在被接收时使用的反垃圾邮件工具视为垃圾邮件的风险。 有关详细信息，请参阅[预览消息](../../sending/using/previewing-messages.md)。

在消息内容编辑器中，单击&#x200B;**[!UICONTROL Preview]**。 如果防垃圾邮件检查检测到此邮件存在高风险，则会发出警告。 单击&#x200B;**[!UICONTROL Anti-spam analysis]**&#x200B;以视图详细信息。

![](assets/sending_anti-spam_analysis.png)

## 电子邮件渲染 {#message-responsiveness}

在发送消息之前，您可以通过检查消息在不同设备上的显示情况来测试消息响应。 这是为了确保以最佳方式在各种Web客户端、Web邮件和设备上显示。

![](assets/inbox_rendering_report_3.png)

为了实现此功能，Adobe Campaign 会捕捉渲染状态并提供在专用报告中。这样，您就可以预览不同消息接收环境下所收到之消息的显示情况。

有关此方面的更多信息，请参阅[电子邮件呈现](../../sending/using/email-rendering.md)。