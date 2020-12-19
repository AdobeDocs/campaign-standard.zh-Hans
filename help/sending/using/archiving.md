---
solution: Campaign Standard
product: campaign
title: 在Adobe Campaign Standard存档消息
description: 了解如何使用密件抄送电子邮件地址将电子邮件存档到Adobe Campaign Standard。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 5%

---


# 通过电子邮件密送进行归档{#archiving-emails}

您可以配置Adobe Campaign以保留通过电子邮件密送从您的平台发送的电子邮件副本。

尤其是，如果您的组织需要存档所有出站电子邮件以符合要求，您可以启用此功能。 它允许您将相应已发送消息的确切隐藏副本发送到必须指定的密件抄送电子邮件地址(对投放收件人不可见)。

启用后，您需要从电子邮件投放模板的&#x200B;**[!UICONTROL Archive emails]**&#x200B;选项激活电子邮件密送。

>[!NOTE]
>
>Adobe Campaign本身不管理已存档的文件。 它确实允许您将您选择的邮件发送到专用地址，从那里，可以使用外部系统处理和存档邮件。

## Recommendations和限制{#recommendations-and-limitations}

* 此功能属于可选功能。请核实您的许可协议并联系您的帐户管理员以将其激活。
* 您选择的密件抄送地址必须提供给将为您配置该地址的Adobe团队。
* 只能使用一个密送电子邮件地址。
* 只考虑成功发送的电子邮件。 弹回不是。
* 出于隐私原因，密件抄送电子邮件必须由能够安全地存储个人身份信息(PII)的存档系统处理。
* 创建新投放模板时，默认情况下不启用电子邮件密送，即使已购买该选项也是如此。 您必须在要使用它的每个投放模板中手动启用它。

>[!NOTE]
>
>当前，无法通过Adobe Campaign增强型MTA发送归档的电子邮件，即使您已升级到增强型MTA。

## 激活电子邮件存档{#activating-email-archiving}

启用后，电子邮件密送会通过专用选项在[电子邮件模板](../../start/using/marketing-activity-templates.md)中激活：

1. 转至&#x200B;**资源** > **模板** > **投放模板**。
1. 重复现成的&#x200B;**[!UICONTROL Send via email]**&#x200B;模板。
1. 选择复制的模板。
1. 单击&#x200B;**[!UICONTROL Edit properties]**&#x200B;按钮以编辑模板的属性。
1. 展开&#x200B;**[!UICONTROL Send]**&#x200B;部分。
1. 选中&#x200B;**[!UICONTROL Archive emails]**&#x200B;框，保留每个投放基于此模板发送的所有消息的副本。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>如果打开并点击发送到密送地址的电子邮件，则在发送分析的&#x200B;**[!UICONTROL Total opens]**&#x200B;和&#x200B;**[!UICONTROL Clicks]**&#x200B;中会考虑这一情况，这可能会导致一些错误计算。