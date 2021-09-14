---
title: 在 Experience Cloud 中配置触发器
description: '了解如何配置Adobe Experience Cloud Triggers集成，以便根据客户以前的行为开始向客户发送个性化投放。 '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 50e9fb7a-b28a-40b0-9f2c-3673c792529a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 7%

---

# 在 Experience Cloud 中配置触发器{#configuring-triggers-in-experience-cloud}

## 激活功能 {#activating-the-functionality}

必须在Adobe Campaign中通过Adobe激活该功能。 请联系您的Adobe客户经理或专业服务合作伙伴。

Adobe团队需要以下信息才能激活触发器：

* Marketing Cloud公司名称
* IMS 组织 ID
* Analytics登录公司(可以与Marketing Cloud公司名称相同)

## 配置解决方案和服务 {#configuring-solutions-and-services}

要使用此功能，您需要有权访问以下解决方案/核心服务：

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
>子域配置是可投放性关键元素。 确保Adobe Campaign电子邮件从与网站使用的电子邮件相同的域发送。

您需要配置[Experience CloudDTM核心服务](#configuring-experience-cloud-dtm-core-service)、[Experience Cloud人员核心服务](#configuring-experience-cloud-people-core-service)和[Campaign](#configuring-triggers-and-aliases-in-campaign)来运行这些用例。

### 配置Experience CloudDTM核心服务 {#configuring-experience-cloud-dtm-core-service}

1. 在Experience CloudDTM核心服务（动态标签管理）中，为您的网站页面激活Experience CloudID和Adobe Analytics。

   ![](assets/trigger_uc_conf_1.png)

1. 在网站、Adobe Analytics和Adobe Campaign之间进行ID协调时，需要使用别名。 创建别名，例如“visitorid”。

   ![](assets/trigger_uc_conf_2.png)

### 配置Experience Cloud人员核心服务 {#configuring-experience-cloud-people-core-service}

之前在DTM中引用的别名需要通过Experience Cloud属性在客户人员核心服务中创建。 确保在集成代码中创建新别名并引用相同的DTM别名（例如“visitorid”）。

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>我们将在Adobe Campaign的数据源中使用此客户属性（下一步）。

### 在Campaign中配置触发器和别名 {#configuring-triggers-and-aliases-in-campaign}

1. 确保&#x200B;**[!UICONTROL Experience Cloud triggers]**&#x200B;在Adobe Campaign Standard实例上可见。 如果没有，请联系Adobe Campaign管理员。

   ![](assets/remarketing_1.png)

1. 别名可让Analytics中的联系人与Campaign中的用户档案协调。 您需要将Experience CloudID服务中定义的别名与Campaign中的共享数据源进行匹配。 您需要通过数据源(**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]**)在Adobe Campaign中配置别名解析。 确保在&#x200B;**[!UICONTROL Data Source/Alias]**&#x200B;下拉菜单中选择正确的数据源，该数据源将映射到上一步骤中创建的相同客户属性数据源。

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >您可以为匿名用户和已登录用户协调触发器。 对于匿名用户，该用户档案应存在于Adobe Campaign中，且之前已向该用户发送过电子邮件。 因此，访客ID配置就足够了。 但是，如果要为已登录的用户协调触发器，则需要设置声明的ID数据源。 有关更多信息，请参阅[数据源配置](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)。

## 在Experience Cloud界面中创建触发器 {#creating-a-trigger-in-the-experience-cloud-interface}

需要创建Adobe Experience Cloud触发器，以便在Campaign中使用。

在Experience Cloud中创建新触发器，并确保选择网站上使用的报表包。 确保选择正确的维度，以便触发器触发。

请参阅[Adobe Experience Cloud文档](https://experienceleague.adobe.com/docs/core-services/interface/activation/triggers.html)并观看此[视频](https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html#step-two)。

## 触发器最佳实践和限制 {#triggers-best-practices-and-limitations}

以下是使用Campaign - Triggers集成的最佳实践和限制列表：

* 如果您有多个Campaign Standard实例，则只要触发器位于同一IMS组织ID中，所有实例都可以接收触发器。 Analytics还需要使用相同的IMS组织ID。
* 您无法使用两个不同报表包中的事件在触发器核心服务中创建触发器。
* 触发器基于事务型消息。 只要您必须非常快地发送消息，就会使用事务型消息。 不能对事务型消息进行排队，然后批量循环。
* 触发器本质上并非确定性的。 在生成触发器后，它会发送与Cookie关联的所有别名，因此如果存在共享的浏览器(例如在零售网亭、图书馆、网吧或家中的共享设备（从同一设备登录的夫妻）中)，则无法映射到正确的ID。 所有用于通过浏览器登录的ID都会发送到Campaign，Campaign会根据首次协调发送消息。 如果有多个“电子邮件ID”符合协调条件，则Campaign不会发送电子邮件。 除非由Analytics捕获并发送正确的电子邮件ID，否则Campaign将无法知道该ID是什么。
* 无法在Campaign中存储有效负载的内容。 触发器无法用于更新用户档案的数据。
* 触发器不支持客户属性（这意味着，只能使用报表包数据来定义触发器业务规则）。
* Campaign不支持收藏集集合。

>[!CAUTION]
>
>您的网站必须在与Adobe Campaign服务器相同的域上运行。 如果没有，则无法使用访客ID来协调并联系匿名访问网站的用户。
