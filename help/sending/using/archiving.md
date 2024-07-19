---
title: 在Adobe Campaign Standard中存档消息
description: 了解如何使用密送电子邮件地址在Adobe Campaign Standard中存档电子邮件。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7bf380d7-195e-413d-b14e-85e78b07ba8b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 5%

---

# 通过电子邮件密送进行归档{#archiving-emails}

您可以将Adobe Campaign配置为保留通过电子邮件密件抄送从您的平台发送的电子邮件副本。

特别是，如果您的组织需要存档所有出站电子邮件以实现合规性，则可以启用此功能。 它允许您向您必须指定的密件抄送电子邮件地址（投放收件人不可见）发送相应已发送消息的完全隐藏副本。

启用后，您需要从电子邮件投放模板的&#x200B;**[!UICONTROL Archive emails]**&#x200B;选项激活电子邮件密件抄送。

>[!NOTE]
>
>Adobe Campaign本身不会管理存档文件。 它使您能够将选择的消息发送到一个专用地址，可以从该地址使用外部系统处理和存档这些消息。

## Recommendations和限制 {#recommendations-and-limitations}

* 此功能属于可选功能。请核实您的许可协议并联系您的帐户管理员以将其激活。
* 您选择的密件抄送地址必须提供给将为您配置该地址的Adobe团队。
* 您只能使用一个密件抄送电子邮件地址。
* 只考虑已成功发送的电子邮件。 跳出不是。
* 出于隐私原因，密件抄送电子邮件必须由能够安全存储个人身份信息(PII)的归档系统处理。
* 创建新投放模板时，默认情况下不启用电子邮件密送，即使已购买该选项也是如此。 您必须在要使用的每个投放模板中手动启用它。

>[!NOTE]
>
>目前，使用简单SMTP中继的旧版归档模块仍会发送归档电子邮件。

## 正在激活电子邮件存档 {#activating-email-archiving}

启用后，将在[电子邮件模板](../../start/using/marketing-activity-templates.md)中通过专用选项激活电子邮件密件抄送：

1. 转到&#x200B;**资源** > **模板** > **投放模板**。
1. 复制现成的&#x200B;**[!UICONTROL Send via email]**&#x200B;模板。
1. 选择复制的模板。
1. 单击&#x200B;**[!UICONTROL Edit properties]**&#x200B;按钮编辑模板的属性。
1. 展开&#x200B;**[!UICONTROL Send]**&#x200B;部分。
1. 选中&#x200B;**[!UICONTROL Archive emails]**&#x200B;框以根据此模板保留每个投放的所有已发送消息的副本。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>如果发送到密件抄送地址的电子邮件被打开并被点进，则发送分析中的&#x200B;**[!UICONTROL Total opens]**&#x200B;和&#x200B;**[!UICONTROL Clicks]**&#x200B;会考虑这一点，这可能会导致某些计算错误。
