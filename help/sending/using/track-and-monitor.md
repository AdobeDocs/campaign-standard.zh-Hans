---
title: 跟踪和监控消息
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 了解Adobe Campaign如何让您跟踪已发送的消息，并了解收件人如何对您的投放做出反应
feature: Deliverability
role: User
level: Intermediate
exl-id: dd3bd672-fb9d-4e82-bdf3-d319f372baaa
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 3%

---

# 跟踪和监视 {#track-and-monitor}

您单击了“发送”按钮吗？ 让我们看看会发生什么。 发送投放后，借助Adobe Campaign，您可以跟踪已发送的消息，并了解收件人对投放的反应。 这有助于您改进未来发送并优化下一个营销活动。

## 监控投放 {#monitoring-deliveries}

要控制活动，您必须确保消息确实已发送给收件人。

**提示**

* 您可以在投放日志中控制消息的状态。

* 为了跟踪投放是成功还是失败，Adobe Campaign提供了一个电子邮件警报系统，用于发送通知以告知用户重要的系统活动。

* 在消息仪表板中，您可以访问此特定消息的多个报表。

有关更多信息，请参阅 [监控投放](../../sending/using/monitoring-a-delivery.md).

## 跟踪 {#tracking-deliveries}

为了更好地了解定向用户档案的行为，您可以跟踪他们对投放的反应：接收、打开、单击链接、取消订阅等。 请参阅 **跟踪日志** 的选项卡。

**提示**：默认启用消息跟踪。 要配置URL，请选择投放向导下方的显示URL选项。 对于消息的每个URL，您可以选择是否激活跟踪。

有关详细信息，请参见 [跟踪消息](../../sending/using/tracking-messages.md) 部分和 [跟踪指标](../../reporting/using/tracking-indicators.md) 描述。

## 动态报告 {#dyn-reports}

动态报告允许您创建完全可自定义的实时报告来监控活动。 通过Dimension、量度和可视化图表，您可以衡量营销活动对收件人的影响和成功。

**提示**  — 您可以使用内置的报告来监测营销活动，但也可以通过将任何量度或维度拖放到报告中来自定义这些报告。

有关详细信息，请参见 [报告指南](../../reporting/using/about-dynamic-reports.md).

## 热门点击

“热门点击”报表显示消息内容(HTML和/或文本)以及每个链接上的点击百分比。 通过显示每个动态内容的点击百分比，您可以测量哪些内容对收件人最具吸引力。

有关详细信息，请参见 [点击式报告](../../reporting/using/hot-clicks.md).

## 投放性能提示 {#performance-tips}

* 请勿将投放置于实例上的失败状态，因为这样可维护临时表并影响性能。

* 从数据库中删除不再需要的投放和不活动的收件人，以维护地址质量。

* 不要试图一起安排大型投放。 请注意，将负载均匀分布到系统可能需要5到10分钟。

**相关主题：**

* [在失败时接收提醒](../../sending/using/receiving-alerts-when-failures-happen.md)
* [报告](../../reporting/using/about-dynamic-reports.md)
