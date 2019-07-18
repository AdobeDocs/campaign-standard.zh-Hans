---
title: 关于Adobe Experience Cloud触发器
seo-title: 关于Adobe Experience Cloud触发器
description: 关于Adobe Experience Cloud触发器
seo-description: 通过使用Adobe Analytics跟踪客户的特定行为，您现在可以在Adobe Campaign中向客户发送个性化电子邮件。
page-status-flag: 从未激活
uuid: 0aa4bd6e-1bb5-4d0b-913b-ica93 f050 acd
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: 使用营销活动和触发器
discoiquuid: e526b205-2d01-4a8b-9685-ba1 d9 f459 f
context-tags: 触发器，概述；触发器，main
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# About Adobe Experience Cloud Triggers{#about-adobe-experience-cloud-triggers}

Integration between the Experience Cloud Activation core service **[!UICONTROL Triggers]** and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).

在Adobe Experience Cloud中，您定义了不同触发器，即您要监测的客户行为，例如，所有放弃网站访问、在您的网站上进行搜索但不进行购买的客户，甚至是其会话过期的客户。创建触发器时，您可以定义触发器的条件以及将在事件(plo子)中发送到Adobe Campaign的数据。

在Adobe Campaign中，您可以选择之前创建的触发器，使用datamart数据丰富事件数据，并定义链接到该触发器的事务消息模板。例如，客户端在您的网站上放弃访问时，将会向Adobe Campaign发送一个事件，然后通过再营销电子邮件将此事件利用在15分钟内发送给客户端。

**相关主题：**

* Learn about the different types of triggers: [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html).
* Watch the [Trigger Remarketing Messages based on Site Activity](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) video.
* Discover our two [Abandonment Triggers use cases](../../integrating/using/abandonment-triggers-use-cases.md).

## Triggers user process {#triggers-user-process}

>[!CAUTION]
>
>执行主要用户步骤之前，需要配置功能。For more on this refer to [Activating the functionality](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Configuring solutions and services](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) and [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

在Adobe Campaign中，用户流程的主要步骤包括：

1. 创建链接到现有Adobe Experience Cloud触发器的触发器事件。
1. 发布触发器事件。
1. 定义交易消息模板的内容。
1. 测试模板(创建测试配置文件并发送凭据)。
1. 发布交易消息模板。

Complete use cases are described in [this section](../../integrating/using/abandonment-triggers-use-cases.md).

## Important notes {#important-notes}

在使用触发器之前需要考虑一些重要注意事项- Campaign集成：

* 触发器不支持推送通知。仅支持电子邮件和短信。
* 您可以使用通过Analytics捕获的元数据(如电子邮件ID、页面名称等)丰富触发器。
* 您可以将触发器调整到Campaign Standard中存储的配置文件，并使用配置文件的字段来个性化消息。
* 一旦收到触发器，就会对其进行处理和协调并发出。根据收到的触发器数量(模板中使用的个性化字段数量)，它需要大约到15分钟。

>[!NOTE]
>
>For more on best practices and technical limitations, refer to [Triggers best practices and limitations](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations).

