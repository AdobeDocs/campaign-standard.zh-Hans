---
solution: Campaign Standard
product: campaign
title: 在Adobe Campaign Standard中存档消息
description: 了解如何使用密件抄送电子邮件地址使用Adobe Campaign Standard存档电子邮件。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: 性能监控
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 5%

---


# 通过电子邮件密送进行归档{#archiving-emails}

您可以配置Adobe Campaign，以保留通过电子邮件密送从您的平台发送的电子邮件副本。

特别是，如果您的组织需要存档所有出站电子邮件以符合要求，您可以启用此功能。 它允许您将相应已发送消息的确切隐藏副本发送到您必须指定的密件抄送电子邮件地址(投放收件人不可见)。

启用后，您需要从电子邮件投放模板的&#x200B;**[!UICONTROL Archive emails]**&#x200B;选项中激活电子邮件密送。

>[!NOTE]
>
>Adobe Campaign本身不管理已存档的文件。 它确实允许您将您选择的消息发送到专用地址，从此处可以使用外部系统处理和存档这些消息。

## Recommendations和限制{#recommendations-and-limitations}

* 此功能属于可选功能。请核实您的许可协议并联系您的帐户管理员以将其激活。
* 您选择的密件抄送地址必须提供给将为您配置该地址的Adobe团队。
* 只能使用一个密件抄送电子邮件地址。
* 只将成功发送的电子邮件考虑在内。 弹回次数不是。
* 出于隐私考虑，密件抄送电子邮件必须由能够安全存储个人身份信息(PII)的存档系统处理。
* 创建新投放模板时，默认情况下不启用电子邮件密送，即使已购买此选项。 必须在要使用它的每个投放模板中手动启用它。

>[!NOTE]
>
>当前，无法使用Adobe Campaign增强的MTA发送存档的电子邮件。

## 激活电子邮件存档{#activating-email-archiving}

启用后，电子邮件密送会通过专用选项在[电子邮件模板](../../start/using/marketing-activity-templates.md)中激活：

1. 转到&#x200B;**资源** > **模板** > **投放模板**。
1. 重复现成的&#x200B;**[!UICONTROL Send via email]**&#x200B;模板。
1. 选择复制的模板。
1. 单击&#x200B;**[!UICONTROL Edit properties]**&#x200B;按钮以编辑模板的属性。
1. 展开&#x200B;**[!UICONTROL Send]**&#x200B;部分。
1. 选中&#x200B;**[!UICONTROL Archive emails]**&#x200B;框，保留每个投放基于此模板发送的所有消息的副本。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>如果打开并点击发送到密件抄送地址的电子邮件，则在发送分析的&#x200B;**[!UICONTROL Total opens]**&#x200B;和&#x200B;**[!UICONTROL Clicks]**&#x200B;中会将其考虑在内，这可能会导致某些错误计算。