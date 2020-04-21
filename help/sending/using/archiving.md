---
title: 在Adobe Campaign标准版中存档消息
description: 了解如何使用密件抄送电子邮件地址使用Adobe Campaign标准存档电子邮件。
page-status-flag: never-activated
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 72366d56e21933bcd79e907e5f8d5a9ad5281725

---


# 通过电子邮件密送进行归档{#archiving-emails}

您可以配置Adobe Campaign，以保留通过电子邮件密送从您的平台发送的电子邮件副本。

特别是，如果您的组织需要存档所有出站电子邮件以符合要求，您可以启用此功能。 它允许您向密件抄送电子邮件地址发送相应已发送消息的完全隐藏副本(对于投放收件人而言不可见)，您必须指定该地址。

启用后，您需要从电子邮件投放模板中的选项 **[!UICONTROL Archive emails]** 激活电子邮件密送。

>[!NOTE]
>
>Adobe Campaign本身不管理存档的文件。 它确实允许您将您选择的消息发送到专用地址，从中可以使用外部系统处理和存档消息。

## 建议和限制 {#recommendations-and-limitations}

* 此功能是可选的。 请检查您的许可协议，并联系您的帐户管理员以激活它。
* 您选择的密件抄送地址必须提供给Adobe团队，由团队为您配置。
* 您只能使用一个密送电子邮件地址。
* 只有成功发送的电子邮件才会被考虑在内。 弹回次数不是。
* 出于隐私原因，密件抄送电子邮件必须由能够安全地存储个人身份信息(PII)的存档系统处理。
* 创建新投放模板时，默认情况下不启用电子邮件密送，即使已购买该选项也是如此。 您必须在要使用它的每个投放模板中手动启用它。

>[!NOTE]
>
>当前，归档的电子邮件无法与Adobe Campaign增强MTA一起发送，即使您已升级到增强MTA。

## 激活电子邮件存档 {#activating-email-archiving}

启用后，电子邮件密送会通过专用选 [项在电子邮件模板](../../start/using/marketing-activity-templates.md)中激活：

1. 转到“ **资源** ”>“ **模板** ” **>**“投放模板”。
1. 重复现成模 **[!UICONTROL Send via email]** 板。
1. 选择复制的模板。
1. 单击 **[!UICONTROL Edit properties]** 按钮可编辑模板的属性。
1. 展开该 **[!UICONTROL Send]** 部分。
1. 选中此 **[!UICONTROL Archive emails]** 框可保留每个投放基于此模板发送的所有消息的副本。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>如果打开并点进发送到密件抄送地址的电子邮件，则发送分析和发送中会考虑这一情况，这可能会导致一些错误计算。 **[!UICONTROL Total opens]****[!UICONTROL Clicks]**