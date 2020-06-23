---
title: 关于 Adobe Experience Cloud 触发器
description: 通过Adobe Analytics跟踪客户的特定行为，您现在可以向Adobe Campaign客户发送个性化电子邮件。
page-status-flag: never-activated
uuid: 0aa4bd6e-1bb5-4d0b-913b-eca93f050acd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: e526b205-2d01-4a8b-9685-ba1d9a1f459f
context-tags: trigger,overview;trigger,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---


# 关于 Adobe Experience Cloud 触发器{#about-adobe-experience-cloud-triggers}

Experience Cloud激活核心服务与 **[!UICONTROL Triggers]** Adobe Campaign之间的集成允许您向客户发送个性化电子邮件，作为对AdobeAnalytics（15分钟内）在您的网站上跟踪的特定行为的回应。

在Adobe Experience Cloud中，您定义了不同的触发器，即您要监控的客户行为，例如所有放弃访问您网站的客户，在您的网站上搜索，但未进行购买，甚至未进行过会话的客户。 创建触发器时，您定义触发器的条件以及将在事件（上传）中发送到Adobe Campaign的数据。

在Adobe Campaign中，您选择之前创建的触发器，使用事件数据丰富事务性消息模板数据，并定义一个链接到该触发器的。 例如，当客户放弃其在您网站上的访问时，事件会发送到Adobe Campaign，然后会通过再营销电子邮件利用此事件，该电子邮件会在15分钟内发送给客户。

**相关主题：**

* 了解不同类型的触发器： [Adobe Experience Cloud文档](https://docs.adobe.com/content/help/en/core-services/interface/activation/triggers.html)。
* 观看“根 [据网站活动触发再营销消息](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) ”视频。
* 了解我们的两个 [废弃触发器使用案例](../../integrating/using/abandonment-triggers-use-cases.md)。

## 触发用户进程 {#triggers-user-process}

>[!CAUTION]
>
>在执行主用户步骤之前，需要配置该功能。 有关详细信息，请参 [阅激活功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)、 [配置解决方案和服务](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) ，以 [及在活动中创建映射触发器](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)。

用户进程的主要步骤是：Adobe Campaign:

1. 创建与现有Adobe Experience Cloud触发器链接的触发事件。
1. 发布触发器事件。
1. 定义事务性消息模板的内容。
1. 测试模板(创建测试用户档案并发送验证)。
1. 发布事务性消息模板。

本节将介绍完整的 [使用案例](../../integrating/using/abandonment-triggers-use-cases.md)。

## 重要说明 {#important-notes}

以下是在使用触发器-活动集成之前需要考虑的一些重要注意事项：

* 触发器不支持推送通知。 仅支持电子邮件和短信。
* 您可以使用通过Analytics捕获的元数据（如电子邮件ID、页面名称等）丰富触发器。
* 您可以将触发器协调到存储在Campaign Standard中的用户档案，并使用用户档案的字段个性化消息。
* 一旦接收到触发器，就会处理并协调并发出。 这大约需要5到15分钟，具体取决于收到的触发器数量、模板中使用的个性化字段数。

>[!NOTE]
>
>有关最佳实践和技术限制的更多信息，请参 [阅触发器最佳实践和限制](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations)。

