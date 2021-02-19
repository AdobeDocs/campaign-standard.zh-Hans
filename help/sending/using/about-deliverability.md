---
solution: Campaign Standard
product: campaign
title: 关于Adobe Campaign Standard中的可交付性
description: 了解与交付性相关的概念和最佳实践，以及Adobe Campaign Standard为优化发送投放而提供的工具。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1e7359db2de1a9c420af33ac85c0597c098ae3f8
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 5%

---


# 关于投放能力{#about-deliverability}

可交付性允许您衡量活动到达收件人收件箱时的成功程度，而不会出现弹跳或标记为垃圾邮件。

交付率取决于诸多因素，特别是：

* 实例的正确配置
* 您的IP地址信誉
* 目标地址的质量
* 低投诉和高反弹率
* 您的消息内容
* 邮件身份验证(SPF、DKIM、DMARC)
* 发件人声誉

## 要检查的要点 {#deliverability-key-points}

为优化Adobe Campaign电子邮件的发送能力，我们建议使用下面列出的最佳实践。 传送能力问题通常与互联网服务提供商和邮件服务器管理员实施的防垃圾邮件措施有关。

电子邮件可发送性是指一系列特征，这些特征决定了邮件在短时间内通过个人电子邮件地址到达其目的地的能力，并且在内容和格式方面具有预期的质量。 这些特征分为四个主要类别:数据质量、消息和内容、发送基础架构和声誉。 它们共同构成了成功的电子邮件交付项目的基础。

交付率是已发送电子邮件的数量，已成功发送给收件人。
以下是要检查的要点列表，以确保良好的交付能力。

## 交付工具{#deliverability-tools}

首先，开始通过查阅随Campaign Standard提供的可交付工具的相关文档：
* [投放最佳实践](../../sending/using/delivery-best-practices.md)
* [个性化发件人姓名](../../designing/using/personalization.md#personalizing-the-sender)
* [优化发送时间](../../sending/using/optimizing-the-sending-time.md)
* [预览消息](../../sending/using/previewing-messages.md)
* [电子邮件渲染](../../sending/using/email-rendering.md)
* [监控投放](../../sending/using/monitoring-a-delivery.md)
* [在失败时接收提醒](../../sending/using/receiving-alerts-when-failures-happen.md)
* [了解投放失败](../../sending/using/understanding-delivery-failures.md)
* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)
* [隔离与阻止列表](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)
* [动态报告](../../reporting/using/about-dynamic-reports.md)

## 正在检查网络配置{#network-configuration}

垃圾邮件发送者试图隐藏他们的真实身份，结果导致他们的服务器难以识别。 不尝试隐藏服务器标识的合法网络配置对于以大容量发送电子邮件至关重要。

## 发送到有效地址{#valid-addresses}

垃圾邮件发送者经常使用基于频繁姓名和名字列表的地址生成器；此外，他们很少处理邮件服务器发送的技术通知。 无效地址的高率通常被解释为垃圾邮件的标志。 多次选择加入机制和对技术弹回消息的有效处理使避免这种情况成为可能。

## 降低投诉率{#reduce-complaint-rate}

ISP通常将收到的消息报告为垃圾邮件。 这使得能够识别不可靠的来源。 通过快速满足选择退出请求、定期使用给定列表、通过多次选择加入系统验证同意并实施反馈循环，您可以降低投诉率。

## 发送到蜜罐地址{#honeypot-addresses}

ISP和其他组织(请参阅https://www.projecthoneypot.org/)利用的邮箱与物理人员不对应，而只是为了欺骗垃圾邮件发送者。 这些所谓的“蜜罐”地址发布在Web上，以便由垃圾邮件程序收集，从而捕获非法发送者。 使用多次选择加入机制可阻止此类地址添加到列表。 使用第三方列表时，必须确定其维护器使用的方法。

## 改编消息内容{#adapt-message-content}

某些邮件的内容会导致某些过滤器将其检测为垃圾邮件。 使用某些单词，在主题行和邮件中使用感叹号被解读为垃圾邮件的告诉信号。 众所周知，垃圾邮件发送者会用图像替换文本，以阻止防垃圾邮件过滤器自动分析违规文本。 为此，具有高比例图像或图像作为附件的消息（HTML格式）最终可能被阻止。

## 定期发送{#regular-deliveries}

垃圾邮件发送者会通过编程投放来保持自己的声誉。 他们有时需要调整营销计划以符合ISP强加的最佳实践，因此，在声誉达到高峰（加速）后，他们会配置常规投放。
