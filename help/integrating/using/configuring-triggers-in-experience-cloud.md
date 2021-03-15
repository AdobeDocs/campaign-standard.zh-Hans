---
solution: Campaign Standard
product: campaign
title: 在 Experience Cloud 中配置触发器
description: '了解如何将Adobe Experience Cloud Triggers集成配置为开始根据客户先前的行为向客户发送个性化投放。 '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: 触发器
role: 数据架构师
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 8%

---


# 在 Experience Cloud 中配置触发器{#configuring-triggers-in-experience-cloud}

## 激活功能{#activating-the-functionality}

必须通过Adobe在Adobe Campaign中激活该功能。 请联系您的Adobe客户经理或专业服务合作伙伴。

Adobe团队需要以下信息才能激活触发器：

* Marketing Cloud公司名称
* IMS 组织 ID
* Analytics登录公司(可以与Marketing Cloud公司名称相同)

## 配置解决方案和服务{#configuring-solutions-and-services}

要使用此功能，您需要能够访问以下解决方案/核心服务：

* Adobe Campaign
* Adobe Analytics Ultimate、Premium、Foundation、OD、Select、Prime、Mobile Apps、Select 或 Standard。
* Experience Cloud Triggers Core Service

   ![](assets/trigger_uc_prereq_1.png)

* Experience Cloud DTM Core Service

   ![](assets/trigger_uc_prereq_2.png)

* Experience Cloud Visitor ID 和 Experience Cloud People Core Service

   ![](assets/trigger_uc_prereq_3.png)

您还需要拥有可用的网站。

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>子域配置是可交付性关键元素。 确保Adobe Campaign电子邮件与网站使用的域相同。

您需要配置[Experience Cloud DTM核心服务](#configuring-experience-cloud-dtm-core-service)、[Experience Cloud人核心服务](#configuring-experience-cloud-people-core-service)和[活动](#configuring-triggers-and-aliases-in-campaign)来运行这些用例。

### 配置Experience Cloud DTM核心服务{#configuring-experience-cloud-dtm-core-service}

1. 在Experience Cloud DTM核心服务（动态标签管理）中，为您的网站页面激活Experience CloudID和Adobe Analytics。

   ![](assets/trigger_uc_conf_1.png)

1. 网站、Adobe Analytics和Adobe Campaign之间的ID协调需要使用锯齿。 创建别名，例如“visitorid”。

   ![](assets/trigger_uc_conf_2.png)

### 配置Experience Cloud人核心服务{#configuring-experience-cloud-people-core-service}

以前在DTM中引用的别名需要在Experience Cloud People Core Service中通过Customer Attribute创建。 请确保新建一个并引用集成代码中的相同DTM别名（例如“visitorid”）。

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>我们将在Adobe Campaign中的数据源中使用此客户属性（下一步）。

### 在活动 {#configuring-triggers-and-aliases-in-campaign}中配置触发器和别名

1. 确保&#x200B;**[!UICONTROL Experience Cloud triggers]**&#x200B;在Adobe Campaign Standard实例上可见。 如果您没有，请与Adobe Campaign管理员联系。

   ![](assets/remarketing_1.png)

1. 别名使Analytics中的联系人能够与活动中的用户档案协调。 您需要将Experience CloudID服务中定义的别名与活动中的共享数据源匹配。 您需要通过数据源(**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]**)在Adobe Campaign中配置别名解析。 确保在&#x200B;**[!UICONTROL Data Source/Alias]**&#x200B;下拉菜单中选择正确的数据源，该菜单将与在上一步中创建的相同“客户属性”数据源进行映射。

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >您可以协调匿名用户和登录用户的触发器。 对于匿名用户，用户档案应存在于Adobe Campaign中，并且之前已向用户发送过电子邮件。 对于此，访客ID配置已足够。 但是，如果要协调已登录用户的触发器，则需要设置Declared ID数据源。 有关详细信息，请参阅[数据源配置](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)。

## 在Experience Cloud接口{#creating-a-trigger-in-the-experience-cloud-interface}中创建触发器

需要创建Adobe Experience Cloud触发器，以便您可以在活动中使用它。

在Experience Cloud中创建新触发器，并确保选择网站上使用的报表包。 确保您选择了正确的尺寸，以使触发器触发。

请参阅[Adobe Experience Cloud文档](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/activation/triggers.html)并观看此[视频](https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html#step-two)。

## 触发最佳实践和限制{#triggers-best-practices-and-limitations}

以下是使用活动的最佳实践和限制的列表 — 触发器集成：

* 如果您有多个Campaign Standard实例，则只要触发器位于同一IMS组织ID中，所有实例都可以接收它们。 Analytics还需要位于相同的IMS组织ID上。
* 不能使用来自两个不同报表包的事件在触发器核心服务中创建触发器。
* 触发器基于事务性消息。 只要您必须非常快速地发送消息，就会使用事务性消息。 您不能将事务性消息排入队列，然后批量循环。
* 触发器本质上并不是确定性的。 当触发器生成时，它会发送与Cookie关联的所有别名，因此，如果共享浏览器(如在零售亭、图书馆、网吧或家中的共享设备（从同一设备登录的丈夫和妻子）中)，则无法映射到正确的ID。 用于使用浏览器登录的所有ID都被发送到活动，该ID基于第一次对帐发送消息。 如果有多个“电子邮件ID”可进行对帐，则活动不会发送电子邮件。 除非Analytics捕获并发送正确的电子邮件ID，否则活动无法了解该ID是什么。
* 不能以活动存储有效负荷的内容。 触发器不能用于更新用户档案的数据。
* 触发器中不支持客户属性（这意味着，只能使用报表包数据定义触发器业务规则）。
* 集合在活动中不受支持。

>[!CAUTION]
>
>您的网站必须与Adobe Campaign服务器在同一域中运行。 否则，您无法使用访客id协调并联系匿名访问网站的用户。

