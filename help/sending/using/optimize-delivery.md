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

在开始创建投放之前，您可以采取多项操作来保护和优化上游发送流程。

以下部分概述了最佳配置Adobe Campaign的最佳实践和建议步骤。 遵循这些做法将最大限度地减少您在下游可能遇到的问题。

## 平台性能

以下几个因素可能会直接影响服务器性能并降低平台速度：

* 个性化元素的数量和类型：电子邮件中的个性化会从数据库中提取每个收件人的数据。 如果存在多个个性化元素，则会增加准备投放所需的数据量。  在中了解有关电子邮件个性化的更多信息 [此部分](../../designing/using/personalization.md)

* 服务器负载：当Campaign同时处理多个不同的任务时，可能会降低性能。 服务器需要协调所有投放的所有传入和传出数据，以确保数据准确无误。

   **笔尖**  — 为避免这种情况，请与团队的其他成员协调投放计划，以确保获得最佳性能。

* 的 [工作流执行](../../automating/using/about-workflow-execution.md):监控工作流对于避免平台性能问题至关重要。 遵循所列准则 [本页](../../automating/using/monitoring-workflow-execution.md). 在 [工作流最佳实践](../../automating/using/best-practices-workflows.md) 中。

* 您可以利用 [Campaign控制面板功能](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=zh-Hans) 监视您的平台，使用 [性能监控](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=zh-Hans) 功能。

## 检查网络配置 {#network-config}

要在处理大量电子邮件时优化投放，并避免被误认为是垃圾邮件发送者，请确保您具有不会尝试隐藏服务器身份的合法网络配置。

**笔尖**:使用与您的品牌网站对应的透明发件人地址。 例如，旅行社公司管理着华伦天奴连锁酒店。 它拥有其网站的valentino.com域。 为推广巴黎的华伦天奴酒店，它使用paris.valentino.com子域。 因此，相关发件人地址可以是hotel@paris.valentino.com。

## 可投放性管理 {#deliverability-management}

要访问收件人的收件箱而不会弹出或标记为垃圾邮件，您需要提高邮件的投放率。

* 什么是可投放性?

   * 它是指决定收件人服务器是否能够接受电子邮件的因素。 ISP（互联网服务提供商）会过滤掉其识别为SPAM的电子邮件，或阻止下载图像。 如果他们确定某个域发送的电子邮件过多，则会对从该发件人接收的电子邮件数量设置限制。

   * 检查电子邮件的投放能力时，您希望重点关注四个主要类别：数据质量、消息和内容、发送基础结构和信誉。 有关此主题的更深入分析，请参阅 [此部分](../../sending/using/about-deliverability.md).

* 启动新平台时，请应用 [本页](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/switching-email-platforms.html#transition-process).

* 请联系您的Adobe代表以获取帮助。

## 隔离管理 {#quarantine-management}

保持良好的隔离管理流程符合您的最佳利益。

开始在新平台上发送电子邮件时，您可以使用未完全限定的地址列表。 如果您将发送到无效地址或蜜罐地址（邮箱仅用于欺骗垃圾邮件发送者），这将开始削弱您平台的声誉。 良好的隔离管理流程有助于：保持地址质量，避阻止列表免Internet访问提供商的，并降低错误率，从而加快投放和吞吐量。

**提示**

* 在投放分析期间，默认情况下会将地址被隔离的收件人排除在外：它们不是目标。 这样可加快投放速度，因为错误率对投放速度有显著的影响。例如，当收件箱已满或地址不存在时，可以隔离某个电子邮件地址。 [了解详情](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

* Adobe Campaign会根据返回的错误类型管理错误地址。 如需详细信息，请参阅[此部分](../../sending/using/understanding-quarantine-management.md)。

* 如果无效地址率过高，某些互联网访问提供商会自动将电子邮件判断为垃圾邮件。因此，隔离可让您避免被这些提阻止列表供商添加到。

* 隔离管理还可通过将错误电话号码排除在投放之外，帮助降低短信发送成本。

## 双重选择加入机制 {#double-opt-in}

为避免向无效地址发送消息、限制不当通信并提高发件人信誉，Adobe建议实施双重选择加入机制以进行订阅后确认。 这有助于确保收件人有意订阅。

有关实施此机制的详细信息，请参阅 [此部分](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

在 [用户档案和受众快速入门](../../audiences/using/get-started-profiles-and-audiences.md).
