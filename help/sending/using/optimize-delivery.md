---
title: 优化消息投放
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 了解如何保护和优化上游发送流程。
feature: Deliverability
role: User
level: Intermediate
exl-id: 28b0cf6d-c1f1-4d55-b9bc-0d6bfb063471
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 8%

---

# 优化投放 {#optimize-delivery}

在甚至开始创建投放之前，您可以采取多种操作来保护和优化上游发送流程。

以下部分概述了优化Adobe Campaign配置的最佳实践和建议过程。 遵循这些实践将最大程度地减少您可能在下游遇到的问题。

## 平台性能

有几个因素会直接影响服务器性能并拖慢平台运行速度：

* 个性化元素的数量和类型：电子邮件中的个性化会从数据库中提取每个收件人的数据。 如果存在许多个性化元素，则会增加准备投放所需的数据量。  在中了解有关电子邮件个性化的更多信息 [本节](../../designing/using/personalization.md)

* 服务器加载：当Campaign同时处理多个不同任务时，可能会降低性能。 服务器需要协调所有投放的所有传入和传出数据，以确保数据正确且及时。

   **笔尖**  — 为避免出现这种情况，请与团队的其他成员协调投放计划，以确保最佳性能。

* 此 [工作流执行](../../automating/using/about-workflow-execution.md)：监测工作流对于避免平台性能问题至关重要。 遵循列出的准则 [本页内容](../../automating/using/monitoring-workflow-execution.md). 了解详情，请参阅 [工作流最佳实践](../../automating/using/best-practices-workflows.md) 部分。

* 您可以利用 [Campaign控制面板功能](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=zh-Hans) 要监控您的平台，请使用 [性能监测](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=zh-Hans) 功能。

## 正在检查网络配置 {#network-config}

要在处理大量电子邮件时优化投放并避免被误认为垃圾邮件发送者，请确保您具有合法的网络配置，不会尝试隐藏服务器的标识。

**笔尖**：使用与品牌网站对应的透明发件人地址。 例如，旅行社公司经营瓦伦蒂诺连锁酒店。 其网站拥有valentino.com域。 为了推广巴黎的华伦天奴酒店，它使用paris.valentino.com子域。 因此，相关发件人地址可以是hotel@paris.valentino.com。

## 可投放性管理 {#deliverability-management}

要在不退回或标记为垃圾邮件的情况下到达收件人的收件箱，您需要提高邮件的可投放性。

* 什么是可投放性?

   * 它是指决定电子邮件被收件人的服务器接受能力的因素。 ISP（互联网服务提供商）会过滤掉他们识别为垃圾邮件的电子邮件，或者阻止图像下载。 如果他们确定某个域发送了太多电子邮件，则会限制他们将从该发件人接受的电子邮件数量。

   * 在检查电子邮件的可投放性时，您需要重点关注四个主要类别：数据质量、消息和内容、发送基础架构和信誉。 有关此主题的更深入探讨，请参阅 [本节](../../sending/using/about-deliverability.md).

* 在启动新平台时，请应用推荐中的详细信息 [此页面](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/switching-email-platforms.html#transition-process).

* 请联系您的Adobe代表寻求帮助。

## 隔离管理 {#quarantine-management}

保持良好的隔离管理流程符合您的最大利益。

开始在新平台上发送电子邮件时，您可以使用未完全限定的地址列表。 如果发送到无效地址或蜜罐地址（创建的邮箱仅用于欺骗垃圾邮件发送者），这将开始削弱您平台的声誉。 良好的隔离管理流程有助于：保持地址质量、避免Internet访问提供商的阻止列表并减少错误率、加快投放和吞吐量。

**提示**

* 在投放分析期间，默认情况下会排除其地址被隔离的收件人：这些收件人未定位。 这样可加快投放速度，因为错误率对投放速度有显著的影响。例如，当收件箱已满或地址不存在时，可以隔离电子邮件地址。 [了解详情](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

* Adobe Campaign根据返回的错误类型管理错误地址。 如需详细信息，请参阅[此部分](../../sending/using/understanding-quarantine-management.md)。

* 如果无效地址率过高，某些互联网访问提供商会自动将电子邮件判断为垃圾邮件。因此，隔离可让您避免被这些提供商添加到阻止列表。

* 隔离管理还将通过从投放中排除错误的电话号码来帮助降低短信发送成本。

## 双重选择加入机制 {#double-opt-in}

为避免将消息发送到无效地址、限制不当通信并提高发件人信誉，Adobe建议对订阅后确认实施双重选择加入机制。 这有助于确保收件人有意订阅。

有关实施此机制的详情，请参见 [本节](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

了解详情，请参阅 [用户档案和受众入门](../../audiences/using/get-started-profiles-and-audiences.md).
