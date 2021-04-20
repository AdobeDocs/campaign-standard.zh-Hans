---
solution: Campaign Standard
product: campaign
title: 跟踪和监视消息
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 了解Adobe Campaign如何使您能够跟踪已发送的消息并了解收件人对您的投放的反应
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 4%

---


# 跟踪和监视 {#track-and-monitor}

您单击了“发送”按钮？ 让我们看看会发生什么。 发送投放后，Adobe Campaign使您能够跟踪已发送的消息并了解收件人对您的投放的反应。 这将帮助您改进未来发送并优化您的下一个活动。

## 监控投放 {#monitoring-deliveries}

要控制您的活动，您必须确保消息确实已送达您的收件人。

**提示**

* 您可以控制投放日志中消息的状态。

* 为了跟踪投放成功或失败，Adobe Campaign提供电子邮件警报系统，用于发送通知以通知用户重要的系统活动。

* 在消息仪表板中，您可以访问此特定消息的多个报告。

有关详细信息，请参阅[监视投放](../../sending/using/monitoring-a-delivery.md)。

## 跟踪 {#tracking-deliveries}

要更好地了解目标用户档案的行为，您可以跟踪他们对投放的反应：接收、打开、点击链接、退订等。 请参阅投放的&#x200B;**跟踪日志**&#x200B;选项卡。

**提示**:默认情况下，消息跟踪处于启用状态。要配置URL，请选择投放向导下半部分的“显示URL”选项。 对于邮件的每个URL，您可以选择是否激活跟踪。

有关详细信息，请参阅[跟踪消息](../../sending/using/tracking-messages.md)部分和[跟踪指示器](../../reporting/using/tracking-indicators.md)说明。

## 动态报告 {#dyn-reports}

动态报表允许您创建完全可自定义的实时报表来监控活动。 Dimension、量度和可视化可让您衡量活动对收件人的影响和成功。

**提示**  — 内置报表可供您监控活动，但亦可透过将任何量度或维度拖放至报表来自订这些报表。

有关详细信息，请参阅[报告指南](../../reporting/using/about-dynamic-reports.md)。

## 热门点击

“热点点击”报表以每个链接的点击百分比显示消息内容（HTML和/或文本）。 通过显示每个动态内容的点击率，您可以衡量哪些内容最吸引收件人。

有关详细信息，请参阅[热点单击报告](../../reporting/using/hot-clicks.md)。

## 投放性能提示{#performance-tips}

* 请勿在实例上将投放保留为失败状态，因为这会保留临时表并影响性能。

* 删除不再需要的投放，并从数据库中删除非活动收件人以保持地址质量。

* 切勿尝试将大投放计划在一起。 请注意，可能需要5到10分钟才能将负载均匀地分布到系统上。

**相关主题：**

* [在失败时接收提醒](../../sending/using/receiving-alerts-when-failures-happen.md)
* [报告](../../reporting/using/about-dynamic-reports.md)
