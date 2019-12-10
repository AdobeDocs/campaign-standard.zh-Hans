---
title: 关于Adobe Campaign standard中的可交付性
description: 了解与交付性相关的概念和最佳实践，以及Adobe Campaign standard提供的工具，以优化发送您的交付。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# 关于可交付性{#about-deliverability}

交付能力，或如何评估营销活动在到达收件人收件箱时的成功程度，而不会弹跳或标记为垃圾邮件。

Adobe Campaign可交付性是一项付费服务，它提供不同的优惠。 联系交付能力或商业服务。

交付率取决于诸多因素，特别是：

* 正确配置实例
* 您的IP地址声誉
* 目标地址的质量
* 低投诉和高反弹率
* 您的消息内容
* 消息身份验证(SPF、DKIM、DMARC)
* 发件人声誉

## 要检查的关键点 {#deliverability-key-points}

为优化Adobe Campaign电子邮件的可交付性，我们建议使用下面列出的最佳实践。 传送能力问题通常与互联网服务提供商和邮件服务器管理员实施的防止垃圾邮件的措施有关。

电子邮件发送能力是指一系列特征，这些特征决定了邮件在短时间内通过个人电子邮件地址到达其目的地的能力，以及在内容和格式方面达到预期质量的能力。 这些特征分为四大类：数据质量、消息和内容、发送基础架构和声誉。 它们共同构成了成功电子邮件交付计划的基础。

可交付性比率是已发送电子邮件的数量，已成功发送给收件人。
以下是要检查的要点列表，以确保良好的交付性。

## 可交付性工具 {#deliverability-tools}

首先，请查阅与Campaign standard一起提供的可交付性工具相关的文档：
* [交付最佳实践](https://helpx.adobe.com/campaign/kb/delivery-best-practices.html)
* [个性化发件人姓名](../../designing/using/personalization.md#personalizing-the-sender)
* [测试电子邮件的主题行](../../sending/using/testing-subject-line-email.md)
* [优化发送时间](../../sending/using/optimizing-the-sending-time.md)
* [预览消息](../../sending/using/previewing-messages.md)
* [电子邮件渲染](../../sending/using/email-rendering.md)
* [监控投放](../../sending/using/monitoring-a-delivery.md)
* [在失败时接收提醒](../../sending/using/receiving-alerts-when-failures-happen.md)
* [了解投放失败](../../sending/using/understanding-delivery-failures.md)
* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)
* [隔离与黑名单](../../sending/using/understanding-quarantine-management.md#quarantine-vs-blacklisting)
* [动态报告](../../reporting/using/about-dynamic-reports.md)

## 检查网络配置 {#network-configuration}

垃圾邮件发送者试图隐藏他们的真实身份，结果导致他们的服务器难以识别。 不尝试隐藏服务器标识的合法网络配置对于在大量电子邮件中发送至关重要。

## 发送到有效地址 {#valid-addresses}

垃圾邮件发送者经常根据频繁姓名和名字列表使用地址生成器；此外，他们很少处理邮件服务器发送回的技术通知。 无效地址的高率通常被解释为垃圾邮件的标志。 双重选择加入机制和对技术弹回消息的有效处理使得避免这种情况成为可能。

## 降低投诉率 {#reduce-complaint-rate}

ISP通常以一种突出的方式将收到的消息报告为垃圾邮件。 这使得能够识别不可靠的来源。 通过快速执行退出请求、定期使用给定列表、通过双选入系统验证同意并实施反馈循环，您可以降低投诉率。

## 发送到蜜罐地址 {#honeypot-addresses}

ISP和其他组织(请参阅http://www.projecthoneypot.org/)使用的邮箱与实际人员不对应，而只是为了欺骗垃圾邮件发送者。 这些所谓的“蜜罐”地址发布在Web上，以便由垃圾邮件程序收集，从而捕获非法发送者。 使用双选择加入机制将这种地址添加到列表中。 使用第三方列表时，您必须确保其维护人员使用的方法。

## 改编消息内容 {#adapt-message-content}

某些消息的内容会导致某些过滤器将其检测为垃圾信息，但程度较低。 使用某些单词、在主题行中和邮件中使用感叹号会被视为垃圾邮件的告诉符号。 众所周知，垃圾邮件发送者会用图像替换文本，以阻止恶意文本被反垃圾邮件过滤器自动分析。 为此，以高比例图像或图像作为附件的消息（HTML格式）最终可能被阻止。

## 定期发送 {#regular-deliveries}

垃圾邮件发送者通过编程方式发送信息来保持其长期的声誉。 他们有时需要调整其营销计划，以符合ISP实施的最佳实践，因此，在声誉达到顶峰（加速）后，他们会配置定期交付。
