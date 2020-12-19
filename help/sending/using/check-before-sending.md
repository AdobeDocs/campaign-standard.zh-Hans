---
solution: Campaign Standard
product: campaign
title: 发送前检查
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: tm+mt
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 16%

---


# 发送{#perform-all-checks}之前执行所有检查

消息准备就绪后，请确保其内容在所有设备上均正确显示，且不包含任何错误，如错误的个性化或中断的链接。

在发送消息之前，还应确保参数和配置与投放一致。

## 验证为什么是关键{#validation-is-key}

在发送投放之前，您需要确保收件人将收到您真正希望发送的消息。 为此，您需要验证消息内容和投放参数。

通过此步骤，您可以检测可能的错误并修复它们，然后再将其传送到主目标。

本节](../../sending/using/get-started-sending-messages.md#prepare-test-send)介绍了验证投放的步骤[。

## 电子邮件渲染 {#email-rendering}

在点击 **[!UICONTROL Send]** 按钮之前，确保以最佳方式在各种 Web 客户端、Web 邮件和设备上显示您的消息。

为了实现此功能，Adobe Campaign 会捕捉渲染状态并提供在专用报告中。这样，您就可以预览不同消息接收环境下所收到之消息的显示情况。

**提示**:

* 您可以在收到邮件的不同视图中上下文发送的邮件：Web邮件、邮件服务、移动等。

* 电子邮件呈现功能对于确定您的电子邮件活动是否成功地使其超越主要ISP(Internet服务提供商)和Web邮件服务的过滤器至关重要。 此类工具会将电子邮件的预检副本发送到测试收件箱网络，以便您能够查看消息在这些服务中的显示或呈现方式。 它们还可能包括报告和代码更正选项，可帮助您快速识别并进行可改进交付性的修复。

请阅读本节[了解更多信息。](../../sending/using/email-rendering.md)

## 验证消息{#proof-messages}

发送验证使您能够检查退出链接、镜像页面和任何其他链接、验证消息、验证图像是否显示、检测可能的错误等。 您可能还希望检查在不同设备上的设计和渲染。

请阅读本节[了解更多信息。](../../sending/using/sending-proofs.md)

## 设置A/B测试投放{#a-b-testing-deliveries}

如果电子邮件投放有多个内容，则可以使用A/B测试找出哪个版本对目标人群的影响最大。

**提示**:

* 将不同版本发送给您的某些收件人

* 选择成功率最高的目标，并将其发送至其他

请阅读本节[了解更多信息。](../../channels/using/designing-an-a-b-test-email.md)

