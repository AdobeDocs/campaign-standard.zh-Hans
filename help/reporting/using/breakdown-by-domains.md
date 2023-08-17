---
title: 按域细分
description: 使用按域划分现成报表，根据客户的每个域了解投放的性能数据。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 513d74ae-10c0-4d41-a7d1-8ed655e1a2d1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# 按域细分{#breakdown-by-domains}

此报表包含电子邮件投放的受众中表示的每个域的性能数据。 如果是营销活动或项目报表，则性能数据适用于多个受众。 此数据允许您分析每个域在响应特定事件时的行为。 例如，链接显示、阻止列表上的URL等。

![](assets/delivery_reports_6.png)

表 **广播统计信息** 包含每个域可能遇到的错误的可用数据，例如：

* **已处理/已发送**：发送的电子邮件数。
* **已投放**：投放的电子邮件数。
* **退回+错误**：无法投放的消息数。
* **硬退回**：永久错误的总数，如错误的电子邮件地址。
* **软退回**：临时错误的总数，如收件箱已满。

第二张桌子， **跟踪统计数据**，包含可用于投放的收件人反应性数据，例如：

* **已投放**：投放的电子邮件数
* **打开**：投放中打开消息的次数。
* **单击**：在投放中单击内容的次数。
* **已取消订阅**：订阅链接的点击次数。
* **镜像页面**：镜像页面链接的点击次数。
* **在阻止列表**：将电子邮件声明为垃圾邮件或垃圾邮件的收件人数量。 [了解详情](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
