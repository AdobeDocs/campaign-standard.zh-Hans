---
title: 发送前检查
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: “消息准备就绪后，了解如何在发送之前执行所有检查”
feature: Deliverability
role: User
level: Intermediate
exl-id: dfc5fc00-87aa-4d22-ad7c-cc0ba1ee21be
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 15%

---

# 发送前执行所有检查 {#perform-all-checks}

消息准备就绪后，请确保其内容在所有设备上均正确显示，并且不包含任何错误，例如错误的个性化或断开的链接。

在发送消息之前，还要确保参数和配置与投放一致。

## 为什么验证是关键 {#validation-is-key}

在发送投放之前，您需要确保收件人将收到您确实想要发送的消息。 要实现此目的，您需要验证消息内容和投放参数。

此步骤允许您检测可能的错误，并在将其交付到主目标之前修复它们。

本节[&#128279;](../../sending/using/get-started-sending-messages.md#prepare-test-send)中介绍了验证投放的步骤。

## 电子邮件渲染 {#email-rendering}

在点击 **[!UICONTROL Send]** 按钮之前，确保以最佳方式在各种 Web 客户端、Web 邮件和设备上显示您的消息。

为了实现此功能，Adobe Campaign 会捕捉渲染状态并提供在专用报告中。这样，您就可以预览不同消息接收环境下所收到之消息的显示情况。

**提示**：

* 您可以在接收消息的不同上下文中查看已发送的消息：Web邮件、消息服务、移动设备等。

* 电子邮件渲染功能对于确定电子邮件促销活动是否成功超越主要ISP（Internet服务提供商）和Web邮件服务的过滤器至关重要。 此类工具会将电子邮件的预检副本发送到测试收件箱网络，以便您了解消息在这些服务中的显示或呈现方式。 它们可能还包括报表和代码更正选项，帮助您快速识别并进行修复以改善可投放性。

在本节[&#128279;](../../sending/using/email-rendering.md)中了解更多。

## 验证消息 {#proof-messages}

通过发送校样，可检查选择退出链接、镜像页面和任何其他链接、验证消息、验证是否显示图像、检测可能存在的错误等。 您可能还希望检查您的设计和在不同设备上的渲染。

在本节[&#128279;](../../sending/using/sending-proofs.md)中了解更多。

## 设置A/B测试投放 {#a-b-testing-deliveries}

如果您的电子邮件投放包含多个内容，则可以使用A/B测试来找出哪个版本将对目标群体产生最大影响。

**提示**：

* 将不同的版本发送给某些收件人

* 选择成功率最高的项目并将其发送到目标的其余部分

在本节[&#128279;](../../channels/using/designing-an-a-b-test-email.md)中了解更多。
