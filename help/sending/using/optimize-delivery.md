---
title: 优化消息投放
seo-title: 优化消息投放
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d5d9d50474142306457a8c76a24388c3c574791d
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 6%

---


# 优化投放 {#optimize-delivery}

在开始创建投放之前，您可以采取多项操作来保护并优化上游发送过程。

以下部分概述了最佳Adobe Campaign配置的最佳实践和建议步骤。 遵循这些做法将最大限度地减少您可能遇到的下游问题。

## 平台性能

几个因素会直接影响服务器性能并降低平台速度：

* 个性化元素的数量和类型：电子邮件中的个性化会为每个收件人从数据库中提取数据。 如果存在许多个性化元素，则会增加准备投放所需的数据量。  在本节中进一步了解电子邮 [件个性化](../../designing/using/personalization.md)

* 服务器加载：当活动同时处理许多不同的任务时，它会降低性能。 服务器需要协调所有投放的所有传入和传出数据，以确保数据准确、及时。

   **提示** -为避免这种情况，请与团队中的其他成员协调投放的安排以确保最佳性能。

* 工作流 [执行](../../automating/using/about-workflow-execution.md):监控工作流对于避免平台性能问题至关重要。 请遵循本页 [中列出的准则](../../automating/using/monitoring-workflow-execution.md)。 在工作流最佳实践部 [分了解更多](../../automating/using/best-practices-workflows.md) 信息。

* 您可以利用 [活动控制面板功能](https://docs.adobe.com/content/help/en/control-panel/using/discover-control-panel/key-features.html) ，使用性能监控功 [能监视您的平台](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/about-performance-monitoring.html) 。

## 检查网络配置 {#network-config}

要在处理大量电子邮件时优化投放并避免被误认为是垃圾邮件发送者，请确保您拥有合法的网络配置，该配置不会尝试隐藏服务器的标识。

**提示**: 使用与您品牌网站对应的透明发件人地址。 例如，旅行社公司管理华伦天奴连锁酒店。 它拥有其网站的valentino.com域。 为了推广巴黎的华伦天奴酒店，它使用paris.valentino.com子域。 因此，相关发件人地址可以是hotel@paris.valentino.com。

## 可交付性管理 {#deliverability-management}

要访问收件人的收件箱而不弹回或标记为垃圾邮件，您需要提高邮件的发送率。

* 什么是可交付性？

   * 它指决定电子邮件被收件人服务器接受的能力的因素。 ISP(Internet服务提供商)过滤其标识为垃圾邮件的电子邮件，或阻止图像下载。 如果他们确定某个域发送的电子邮件过多，他们将对接受该发件人的电子邮件数量设置限制。

   * 在检查电子邮件的可交付性时，您希望关注四个主要类别:数据质量、消息和内容、发送基础架构和声誉。 有关此主题的更深入介绍，请参 [阅此部分](../../sending/using/about-deliverability.md)。

* 启动新平台时，请应用本页中详 [细的推荐](../../sending/using/starting-new-platform.md)。

* 请与Adobe代表联系以获得帮助。

## 隔离管理 {#quarantine-management}

保持良好的隔离管理流程符合您的最佳利益。

开始在新平台上发送电子邮件时，您可能会使用列表未完全限定的地址。 如果您发送到无效地址或蜜罐地址（仅为欺骗垃圾邮件发送者而创建的邮箱），这将开始您平台的声誉。 良好的隔离管理流程有助于：保持地址质量，避阻止列表免Internet访问提供商的，并降低错误率，加快投放和吞吐量。

**提示**

* 在投放分析中，默认情况下将排除其地址被隔离的收件人:他们不是目标。 这样可加快投放速度，因为错误率对投放速度有显著的影响。可以隔离电子邮件地址，例如，当收件箱已满或地址不存在时。 [了解详情](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

* Adobe Campaign根据返回的错误类型管理错误地址。 如需详细信息，请参阅[此部分](../../sending/using/understanding-quarantine-management.md)。

* 如果无效地址率过高，某些互联网访问提供商会自动将电子邮件判断为垃圾邮件。因此，隔离允许您避免被这阻止列表些提供商添加到。

* 隔离管理还将通过排除投放的错误电话号码来帮助降低短信发送成本。

## 多次加入机制 {#double-opt-in}

为了避免向无效地址发送消息、限制不当通信并提高发送者信誉，Adobe建议实施多次选择加入机制以进行订阅后确认。 这有助于确保收件人有意订阅。

本节概述了实施这一机制 [的详细信息](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

通过用户档案和 [受众入门了解更多信息](../../audiences/using/get-started-profiles-and-audiences.md)。
