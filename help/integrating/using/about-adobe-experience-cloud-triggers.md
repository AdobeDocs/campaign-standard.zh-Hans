---
solution: Campaign Standard
product: campaign
title: 关于 Adobe Experience Cloud 触发器
description: 现在您可通过使用 Adobe Analytics 跟踪客户的特定行为，从而在 Adobe Campaign 中向客户发送个性化电子邮件。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
context-tags: trigger,overview;trigger,main
feature: Triggers
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 99%

---


# 关于 Adobe Experience Cloud 触发器{#about-adobe-experience-cloud-triggers}

Experience Cloud Activation 核心服务 **[!UICONTROL Triggers]** 与 Adobe Campaign 之间的整合，允许您根据 Adobe Analytics 对网站上特定行为的跟踪，向客户发送个性化电子邮件作为回应（在 15 分钟内）。

在 Adobe Experience Cloud 中，您可定义不同的触发器，即想要监控的客户行为（例如所有放弃访问您网站的客户、在您的网站上进行搜索的客户、搜索但未进行购买的客户，甚至还有会话过期的客户）。创建触发器时，您可定义触发器的条件以及将在事件中发送（上传）到 Adobe Campaign 的数据。

在 Adobe Campaign 中，您可选择之前创建的触发器、使用数据集市扩充事件数据，并可定义链接到该触发器的事务型消息模板。例如，当客户放弃对您网站的访问时，即会向 Adobe Campaign 发送一个事件，随后 Adobe Campaign 会利用此事件，在 15 分钟内向该客户发送一封再营销电子邮件。

下图详细说明此集成的工作方式。

![](assets/triggers_diagram.png)

**相关主题：**

* 了解不同类型的触发器：[Adobe Experience Cloud 文档](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/activation/triggers.html)。
* 观看[“根据网站活动触发再营销消息”](https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html#step-two)视频。
* 了解两个[放弃触发器使用案例](../../integrating/using/abandonment-triggers-use-cases.md)。

## 触发器用户流程{#triggers-user-process}

>[!CAUTION]
>
>在执行主用户步骤之前，需要配置该功能。有关更多信息，请参阅[激活功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)、[配置解决方案和服务](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services)以及[在 Campaign 中创建映射触发器](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)。

Adobe Campaign 用户流程的主要步骤如下：

1. 创建与现有 Adobe Experience Cloud 触发器关联的触发事件。
1. 发布触发事件。
1. 定义事务型消息模板的内容。
1. 测试模板（创建测试用户档案并发送校样）。
1. 发布事务型消息模板。

有关完整的使用案例，请参见[本章节](../../integrating/using/abandonment-triggers-use-cases.md)。

## 重要说明{#important-notes}

以下是在使用“Triggers - Campaign”集成之前需要考虑的一些重要注意事项：

* 触发器不支持推送通知。仅支持电子邮件和短信。
* 您可以使用通过 Analytics 捕获的元数据（如电子邮件 ID、页面名称等）来扩充触发器。
* 您可以将触发器与存储在 Campaign Standard 中的用户档案相协调，并使用该用户档案的字段配置个性化消息。
* 触发之后，即会进行处理和协调，然后再发出。这大约需要 5 到 15 分钟，具体时间取决于被触发的触发器数量以及模板中使用的个性化字段数量。

>[!NOTE]
>
>有关最佳实践和技术限制的更多信息，请参阅[触发器最佳实践和限制](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations)。

