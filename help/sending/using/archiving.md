---
title: 在Adobe Campaign Standard中存档消息
description: 了解如何使用密件抄送电子邮件地址通过Adobe Campaign Standard存档电子邮件。
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

您可以配置Adobe Campaign以保留通过电子邮件密送从您的平台发送的电子邮件副本。

特别是，如果贵组织需要存档所有出站电子邮件以符合要求，则可以启用此功能。 利用该功能，可将相应已发送消息的确切隐藏副本发送到您必须指定的密件抄送电子邮件地址（投放收件人不可见）。

启用后，您需要从 **[!UICONTROL Archive emails]** 选项。

>[!NOTE]
>
>Adobe Campaign本身不管理已存档的文件。 它确实允许您将您选择的消息发送到专用地址，从中可以使用外部系统处理和存档这些消息。

## Recommendations和限制 {#recommendations-and-limitations}

* 此功能属于可选功能。请核实您的许可协议并联系您的帐户管理员以将其激活。
* 您选择的密件抄送地址必须提供给Adobe团队，由团队为您配置。
* 您只能使用一个密件抄送电子邮件地址。
* 只考虑成功发送的电子邮件。 跳出次数不是。
* 出于隐私原因，密件抄送电子邮件必须由能够存储安全的个人身份信息(PII)的存档系统处理。
* 创建新投放模板时，默认情况下不启用“电子邮件密送”，即使已购买选项也是如此。 您必须在要在其中使用它的每个投放模板中手动启用它。

>[!NOTE]
>
>当前，存档的电子邮件仍由旧版存档模块发送，该模块使用简单的SMTP中继。

## 激活电子邮件存档 {#activating-email-archiving}

启用后，会在 [电子邮件模板](../../start/using/marketing-activity-templates.md)，通过专用选项：

1. 转到 **资源** > **模板** > **投放模板**.
1. 复制现成的 **[!UICONTROL Send via email]** 模板。
1. 选择复制的模板。
1. 单击 **[!UICONTROL Edit properties]** 按钮以编辑模板的属性。
1. 展开 **[!UICONTROL Send]** 中。
1. 检查 **[!UICONTROL Archive emails]** 框中，可为基于此模板的每次投放保留所有已发送消息的副本。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>如果打开并点进发送到密件抄送地址的电子邮件，则在 **[!UICONTROL Total opens]** 和 **[!UICONTROL Clicks]** 来自发送分析，这可能会导致一些错误计算。
