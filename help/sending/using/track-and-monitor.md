---
solution: Campaign Standard
product: campaign
title: 跟踪和监视消息
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: tm+mt
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 4%

---


# 跟踪和监视 {#track-and-monitor}

您单击了“发送”按钮？ 让我们看看会发生什么。 发送投放后，Adobe Campaign使您能够跟踪已发送的消息并了解收件人对投放的反应。 这将帮助您改进未来发送并优化您的下一活动。

## 监控投放 {#monitoring-deliveries}

要控制活动，您必须确保消息确实已送达收件人。

**提示**

* 您可以控制投放日志中消息的状态。

* 为了跟踪投放成功或失败，Adobe Campaign提供电子邮件警报系统，用于发送通知以通知用户重要的系统活动。

* 在消息仪表板中，您可以访问此特定消息的多个报告。

有关详细信息，请参阅[监视投放](../../sending/using/monitoring-a-delivery.md)。

## 跟踪 {#tracking-deliveries}

要更好地了解目标用户档案的行为，您可以跟踪他们对投放的反应：接收、打开、点击链接、退订等。 请参阅跟踪日志的&#x200B;**投放**&#x200B;选项卡。

**提示**:默认情况下，消息跟踪处于启用状态。要配置URL，请选择投放向导下半部分的“显示URL”选项。 对于邮件的每个URL，您可以选择是否激活跟踪。

有关详细信息，请参阅[跟踪消息](../../sending/using/tracking-messages.md)部分和[跟踪指示器](../../reporting/using/tracking-indicators.md)说明。

## 动态报告 {#dyn-reports}

动态报告允许您创建完全可自定义的实时报告来监控活动。 Dimension、指标和可视化功能使您能够衡量活动对收件人的影响和成功。

**提示** -内置报表可供您监视活动，但也可以通过将任何指标或维度拖放到报表中来自定义这些报表。

有关详细信息，请参阅[报告指南](../../reporting/using/about-dynamic-reports.md)。

## 热门点击

热点单击报告以单击每个链接的百分比显示消息内容（HTML和／或文本）。 通过显示每个动态内容的点击率，您可以衡量哪些内容最吸引收件人。

有关详细信息，请参阅[热点单击报告](../../reporting/using/hot-clicks.md)。

## 投放性能提示{#performance-tips}

* 请勿在实例上使投放处于失败状态，因为这会维护临时表并影响性能。

* 从投放库中删除不再需要的收件人和非活动的，以保持地址质量。

* 不要试着计划大投放。 请注意，可能需要5到10分钟才能将负载均匀分布到系统上。

**相关主题：**

* [在失败时接收提醒](../../sending/using/receiving-alerts-when-failures-happen.md)
* [报告](../../reporting/using/about-dynamic-reports.md)
