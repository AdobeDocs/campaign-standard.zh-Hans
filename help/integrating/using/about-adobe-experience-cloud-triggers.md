---
title: 关于 Adobe Experience Cloud 触发器
description: 通过使用Adobe Analytics跟踪客户的特定行为，您现在可以在Adobe Campaign中向客户发送个性化电子邮件。
page-status-flag: 从未激活
uuid: 0aa4bd6e-1bb5-4d0b-913b-eca93f050acd
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用系列活动和触发器
discoiquuid: e526b205-2d01-4a8b-9685-ba1d9a1f459f
context-tags: 触发器，概述；触发器，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 关于 Adobe Experience Cloud 触发器{#about-adobe-experience-cloud-triggers}

Experience Cloud Activation核心服务与Adobe Campaign之间的集成允许您向客户发送个性化电子邮件，作为对Adobe Analytics在您网站上跟踪的特定行为（15分钟内）的反应。 **[!UICONTROL Triggers]**

在Adobe Experience cloud中，您定义了不同的触发器，即您要监控的客户行为，例如放弃访问您网站的所有客户在您的网站上搜索，但没有购买，甚至没有购买会话过期的客户。 在创建触发器时，您定义触发器的条件和在活动（上传）中将发送到Adobe Campaign的数据。

 在Adobe Campaign中，您选择之前创建的触发器，使用数据库数据丰富活动数据，并定义一个链接到该触发器的交易消息模板。 例如，当客户放弃对您网站的访问时，会向Adobe Campaign发送一个活动，然后Adobe Campaign会通过再营销电子邮件利用此活动，该电子邮件在15分钟内发送给客户。

**相关主题：**

* 了解不同类型的触发器：Adobe [Experience cloud文档](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html)。
* 观看“根 [据网站活动触发再营销消息](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) ”视频。
* 了解我们的两个 [放弃触发器使用案例](../../integrating/using/abandonment-triggers-use-cases.md)。

## 触发用户进程 {#triggers-user-process}

>[!CAUTION]
>
>在执行主用户步骤之前，需要配置该功能。 有关详细信息，请参 [阅激活功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)、 [配置解决方案和服务](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) ，以 [及在Campaign中创建映射触发器](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)。

在Adobe Campaign中，用户流程的主要步骤有：

1. 创建一个链接到现有Adobe Experience cloud触发器的触发器事件。
1. 发布触发器事件。
1. 定义事务性消息模板的内容。
1. 测试模板（创建测试配置文件并发送证明）。
1. 发布交易消息模板。

本节将介绍完整的使 [用案例](../../integrating/using/abandonment-triggers-use-cases.md)。

## 重要说明 {#important-notes}

以下是在使用触发器——营销活动集成之前要考虑的一些重要注意事项：

* 触发器不支持推送通知。 仅支持电子邮件和短信。
* 您可以使用通过Analytics捕获的元数据（如电子邮件ID、页面名称等）来丰富触发器。
* 您可以将触发器协调到Campaign standard中存储的配置文件，并使用配置文件的字段个性化消息。
* 一旦接收了触发器，就处理并协调该触发器并发出。 这大约需要5到15分钟，具体取决于收到的触发器数量、模板中使用的个性化字段数。

>[!NOTE]
>
>有关最佳实践和技术限制的更多信息，请参阅 [触发器最佳实践和限制](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations)。

