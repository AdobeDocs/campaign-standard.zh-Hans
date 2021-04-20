---
solution: Campaign Standard
product: campaign
title: 发送前检查
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: “在您的消息准备就绪后，了解如何在发送前执行所有检查”
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 15%

---


# 在发送{#perform-all-checks}之前执行所有检查

在您的消息准备就绪后，请确保其内容在所有设备上正确显示，并且不包含任何错误，如错误的个性化或中断的链接。

在发送消息之前，还要确保参数和配置与投放一致。

## 为什么验证是键{#validation-is-key}

在发送投放之前，您需要确保收件人将收到您真正希望发送的消息。 为此，您需要验证消息内容和投放参数。

通过此步骤，您可以检测可能的错误并修复它们，然后再将其提交到主目标。

本节](../../sending/using/get-started-sending-messages.md#prepare-test-send)介绍了验证投放的步骤[。

## 电子邮件渲染 {#email-rendering}

在点击 **[!UICONTROL Send]** 按钮之前，确保以最佳方式在各种 Web 客户端、Web 邮件和设备上显示您的消息。

为了实现此功能，Adobe Campaign 会捕捉渲染状态并提供在专用报告中。这样，您就可以预览不同消息接收环境下所收到之消息的显示情况。

**提示**:

* 您可以在收到邮件的不同上下文视图已发送的邮件：Web邮件、消息服务、移动等。

* 电子邮件呈现功能对于确定您的电子邮件活动是否成功使其超过主要ISP(Internet服务提供商)和Web邮件服务的过滤器至关重要。 此类工具会向测试收件箱网络发送电子邮件的预检副本，以便您能够查看邮件在这些服务中的显示或呈现方式。 它们还可能包括报告和代码更正选项，可帮助您快速识别和进行可改进交付性的修复。

请阅读本节](../../sending/using/email-rendering.md)了解更多信息。[

## 验证消息{#proof-messages}

发送验证使您能够检查退出链接、镜像页面和任何其他链接、验证消息、验证图像是否显示、检测可能的错误等。 您可能还希望在不同设备上检查您的设计和渲染。

请阅读本节](../../sending/using/sending-proofs.md)了解更多信息。[

## 设置A/B测试投放{#a-b-testing-deliveries}

如果您对电子邮件投放有多个内容，则可以使用A/B测试来确定哪个版本对目标人群的影响最大。

**提示**:

* 将不同版本发送到您的某些收件人

* 选择成功率最高的，并将其发送给您的其他目标

请阅读本节](../../channels/using/designing-an-a-b-test-email.md)了解更多信息。[

