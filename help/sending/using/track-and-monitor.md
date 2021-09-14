---
title: 跟踪和监视消息
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 了解Adobe Campaign如何让您跟踪已发送的消息，并了解收件人对您的投放有何反应
feature: Deliverability
role: User
level: Intermediate
exl-id: dd3bd672-fb9d-4e82-bdf3-d319f372baaa
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 4%

---

# 跟踪和监测 {#track-and-monitor}

您单击了“发送”按钮？ 让我们看看会发生什么。 发送投放后，Adobe Campaign允许您跟踪已发送的消息，并了解收件人对您的投放有何反应。 这将帮助您改进将来的发送并优化后续促销活动。

## 监控投放 {#monitoring-deliveries}

要控制您的营销活动，您必须确保已将消息发送给收件人。

**提示**

* 您可以控制投放日志中消息的状态。

* 为了跟踪投放是成功还是失败，Adobe Campaign提供了电子邮件警报系统，用于发送通知以告知用户重要的系统活动。

* 在消息仪表板中，您可以访问此特定消息的多个报表。

有关更多信息，请参阅[监控投放](../../sending/using/monitoring-a-delivery.md)。

## 跟踪 {#tracking-deliveries}

为了更好地了解定向用户档案的行为，您可以跟踪用户档案对投放的反应：接收、打开、链接点击、退订等。 请参阅投放的&#x200B;**跟踪日志**&#x200B;选项卡。

**提示**:默认启用消息跟踪。要配置URL，请在投放向导的下半部分选择显示URL选项。 对于消息的每个URL，您可以选择是否激活跟踪。

有关更多信息，请参阅[跟踪消息](../../sending/using/tracking-messages.md)部分和[跟踪指示器](../../reporting/using/tracking-indicators.md)描述。

## 动态报告 {#dyn-reports}

动态报告允许您创建完全可自定义的实时报告来监控您的营销活动。 Dimension、量度和可视化图表让您能够衡量促销活动对收件人的影响和成功程度。

**提示**  — 内置报表可用于监控营销活动，但也可以通过将任何量度或维度拖放到报表中来自定义这些报表。

有关更多信息，请参阅[Reporting guide](../../reporting/using/about-dynamic-reports.md)。

## 热门点击

“热门点击”报表显示消息内容（HTML和/或文本）以及每个链接的点击百分比。 通过显示每个动态内容的点击百分比，您可以衡量哪些内容最吸引收件人。

有关更多信息，请参阅[热点点击报告](../../reporting/using/hot-clicks.md)。

## 投放性能提示 {#performance-tips}

* 请勿在实例上将投放保持为失败状态，因为这会维护临时表并影响性能。

* 从数据库中删除不再需要的投放和不活动的收件人，以保持地址质量。

* 请勿尝试同时计划大型投放。 请注意，可能需要5到10分钟才能将负载均匀地分布到系统上。

**相关主题：**

* [在失败时接收提醒](../../sending/using/receiving-alerts-when-failures-happen.md)
* [报告](../../reporting/using/about-dynamic-reports.md)
