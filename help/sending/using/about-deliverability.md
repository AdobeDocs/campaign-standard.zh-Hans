---
title: 关于Adobe Campaign Standard中的投放能力
description: 了解与投放能力相关的概念和最佳实践，以及Adobe Campaign Standard为优化投放提供的工具。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 5e523519-7192-4031-9d96-559af23074d9
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 7%

---

# 什么是可投放性{#about-deliverability}

投放能力允许测量营销活动到达收件人收件箱的成功情况，而不会出现弹回或标记为垃圾邮件。 [了解投放能力为何重要](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html#why-deliverability-matters).

更准确地说，电子邮件投放能力是指一组特征，这些特征决定了邮件在短时间内通过个人电子邮件地址到达其目的地的能力，并在内容和格式方面具有预期质量。 <!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

要更深入地了解什么是可投放性，并了解有关关键可投放性术语、概念和方法的更多信息，请参阅 [Adobe投放能力最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hans).

## 如何提高投放能力 {#deliverability-key-points}

投放能力问题通常与互联网服务提供商和邮件服务器管理员实施的针对垃圾邮件的保护措施有关。

* 有关如何设计成功的电子邮件营销活动的一般建议，请参阅 [投放能力策略和定义](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html).

* 有关如何优化Adobe Campaign电子邮件投放能力的更多具体建议，我们建议使用此部分中列出的最佳实践。

>[!NOTE]
>
>由于ISP必须不断开发新的复杂过滤技术来保护其客户免受垃圾邮件发送者的攻击，因此电子邮件投放能力的特点是标准和规则不断变化。 请确保您参考 [Adobe投放能力最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html) 定期更新。

### 投放能力率

投放能力率是指点击收件人收件箱的消息数量与投放的消息数量之比。 要提高投放能力，您可能会努力提高此投放率。

对于Adobe Campaign，投放能力率取决于多种因素，特别是：

* 正确配置实例：请联系您的Adobe代表以获取帮助。
* 合法的网络配置：请参阅 [此部分](../../sending/using/optimize-delivery.md#network-config) 和 [域设置和策略](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#domain-setup-and-strategy).
* 您的IP地址信誉：请参阅 [IP策略](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#ip-strategy).
* 目标地址的质量：请参阅 [隔离管理](../../sending/using/optimize-delivery.md#quarantine-management).
* 低 [投诉](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html) 和 [硬退回](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces) 比率。
* 您的消息内容：请参阅 [控制电子邮件内容](../../sending/using/control-email-content.md).
* 报文验证(SPF、DKIM、DMARC):请参阅 [此部分](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).
* 发件人声誉：要了解主ISP如何评估发件人的信誉，请参阅 [此部分](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html).

## Campaign投放能力工具 {#deliverability-tools}

Adobe Campaign提供了许多用于跟踪和改进平台可交付性性能的工具。 本页还重点介绍了在使用Campaign时，您应当牢记的主要原则，以优化投放能力。

### 仔细构建消息

配置、设计和测试消息时，请确保遵循下面所列部分中提到的最佳实践。 利用Adobe Campaign提供的所有功能，可帮助您提高投放能力。

* [投放最佳实践](../../sending/using/delivery-best-practices.md)
* [控制电子邮件内容](../../sending/using/control-email-content.md)
* [预览消息](../../sending/using/previewing-messages.md)
* [发送校样](../../sending/using/sending-proofs.md)

### 通过双重选择加入验证同意 {#double-opt-in}

为避免向无效地址发送消息、限制不当通信并提高发件人信誉，Adobe建议实施双重选择加入机制。 这样，您就可以确保收件人有意订阅。

有关此内容的更多信息，请参阅 [关于Campaign中的选择启用和选择禁用](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

有关从客户收集数据时的最佳实践的更多信息，请参阅 [Adobe投放能力最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html#data-quality-and-hygiene).

### 利用隔离管理

Adobe Campaign会管理一个列表，以收集持续发生的垃圾邮件投诉、硬退回和软退回。

为了保护您的投放能力，默认情况下，该列表中包含地址的收件人将被排除在所有未来投放之外，因为发送给这些联系人可能会损害您的发送声誉。

如果无效地址率过高，某些互联网访问提供商会自动将电子邮件判断为垃圾邮件。因此，隔离可让您避免被这些提阻止列表供商添加到。

有关更多信息，请参阅以下章节：

* [了解投放失败](../../sending/using/understanding-delivery-failures.md)
* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)
* [隔离与阻止列表](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### 使用监控和报告工具

使用Adobe Campaign提供的功能监控您的投放能力。

Adobe Campaign允许您通过一组内置的实时指示器来检查投放的执行情况。 <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->您还可以构建完全可自定义的实时报表，以改进对投放的洞察。

有关更多信息，请参阅以下章节：

* [监测可投放性](../../sending/using/monitor-deliverability.md)

   <!--[Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)-->
* [在失败时接收提醒](../../sending/using/receiving-alerts-when-failures-happen.md)
* [动态报告](../../reporting/using/about-dynamic-reports.md)

<!--## General recommendations

NOT SURE TO KEEP

Here are a few additional recommendations when it comes to deliverability.

### Send to valid addresses {#valid-addresses}

Spammers often use address generators based on lists of frequent names and first names; in addition, they rarely process technical notifications sent back by mail servers. A high rate of invalid addresses is often interpreted as a sign of spam.

Double opt-in mechanisms and effective handling of technical bounce messages make it possible to avoid this.

### Reduce complaint rate {#reduce-complaint-rate}

ISPs usually have a prominent means of reporting a received message as spam. This makes it possible to identify unreliable sources. By rapidly honoring opt-out requests, making regular use of a given list, verifying consent through a double opt-in system, and implementing feedback loops, you can reduce complaint rates.

<!--Sending to honeypot addresses {#honeypot-addresses}
ISPs and other organizations (refer to https://www.projecthoneypot.org/) make use of mailboxes that do not correspond to physical persons but are created simply to trick spammers. These so-called "honey pot" addresses are published on the Web in order to be collected by spambots and thus catch illegitimate senders. The use of a double opt-in mechanism precludes this sort of address being added to a list. When using a third-party list, you must be sure of the methods employed by its maintainer.-->

<!--## Sending on a regular basis {#regular-deliveries}

Spammers make programmed deliveries to maintain their reputation over time. They sometimes need to adapt their marketing plan to meet the best practices imposed by the ISPs and so, after a peak in reputation (ramp-up), they configure regular deliveries.-->
