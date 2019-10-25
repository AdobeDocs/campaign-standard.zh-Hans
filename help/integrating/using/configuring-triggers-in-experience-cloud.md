---
title: 在Experience cloud中配置触发器
seo-title: 在Experience cloud中配置触发器
description: 在Experience cloud中配置触发器
seo-description: '了解如何配置Adobe Experience Cloud Triggers集成，以开始根据客户先前的行为向客户发送个性化的交付。 '
page-status-flag: 从未激活
uuid: 8fd7b804-9528-46a5-a060-bf16b8dc555d
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用系列活动和触发器
discoiquuid: 4163dc0c-8103-4425-b8bf-7aa45c4d3a06
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 在Experience cloud中配置触发器{#configuring-triggers-in-experience-cloud}

## 激活功能 {#activating-the-functionality}

该功能必须由Adobe在Adobe Campaign中激活。 请联系您的Adobe客户经理或专业服务合作伙伴。

Adobe团队需要以下信息才能激活触发器：

* Marketing cloud公司名称
* IMS组织ID
* Analytics登录公司（可以与Marketing cloud公司名称相同）

## 配置解决方案和服务 {#configuring-solutions-and-services}

要使用此功能，您需要访问以下解决方案／核心服务：

* Adobe Campaign
* Adobe Analytics Ultimate、Premium、Foundation、OD、Select、Prime、Mobile Apps、Select或Standard。
* Experience Cloud触发核心服务

   ![](assets/trigger_uc_prereq_1.png)

* Experience Cloud DTM Core Service

   ![](assets/trigger_uc_prereq_2.png)

* Experience Cloud访客ID和Experience Cloud人员核心服务

   ![](assets/trigger_uc_prereq_3.png)

您还需要有一个有效的网站。

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>子域委派是可交付性的关键元素。 确保Adobe Campaign电子邮件与网站使用的电子邮件来自同一域。

您需要配置 [Experience Cloud DTM Core Service](#configuring-experience-cloud-dtm-core-service)、 [Experience Cloud People Core Service](#configuring-experience-cloud-people-core-service) 和 [Campaign](#configuring-triggers-and-aliases-in-campaign) ，才能运行这些用例。

### 配置Experience Cloud DTM核心服务 {#configuring-experience-cloud-dtm-core-service}

1. 在Experience Cloud DTM核心服务（动态标签管理）中，为您的网站页面激活Experience Cloud ID和Adobe Analytics。

   ![](assets/trigger_uc_conf_1.png)

1. 网站、Adobe Analytics和Adobe Campaign之间的ID协调需要使用别名。 创建别名，例如“visitorid”。

   ![](assets/trigger_uc_conf_2.png)

### 配置Experience Cloud People核心服务 {#configuring-experience-cloud-people-core-service}

之前在DTM中引用的别名需要通过客户属性在Experience Cloud People Core service中创建。 确保创建一个新别名，并在集成代码中引用相同的DTM别名（例如“visitorid”）。

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>我们将在Adobe Campaign的数据源中使用此客户属性（下一步）。

### 在Campaign中配置触发器和别名 {#configuring-triggers-and-aliases-in-campaign}

1. 确保Adobe Campaign standard实 **[!UICONTROL Experience Cloud triggers]** 例中显示您的内容。 如果您没有，请与Adobe Campaign管理员联系。

   ![](assets/remarketing_1.png)

1. 别名使Analytics中的联系人能够与Campaign中的配置文件协调。 您需要将Experience Cloud ID服务中定义的别名与Campaign中的共享数据源相匹配。 您需要通过数据源( **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Shared Data Sources]** )在Adobe Campaign中配置别名解析。 确保在下拉菜单中选择正确的数 **[!UICONTROL Data Source/Alias]** 据源，该下拉菜单将映射到在上一步中创建的同一客户属性数据源。

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >您可以协调匿名用户和登录用户的触发器。 对于匿名用户，Adobe Campaign中应存在该配置文件，并且以前已向用户发送电子邮件。 对于此，访客ID配置已足够。 但是，如果要协调登录用户的触发器，则需要设置Declared ID数据源。 有关详细信息，请参阅 [数据源配置](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)。

## 在Experience cloud界面中创建触发器 {#creating-a-trigger-in-the-experience-cloud-interface}

需要创建Adobe Experience cloud触发器，以便您在Campaign中使用它。

在Experience cloud中创建新触发器，并确保选择网站上使用的报表包。 确保选择正确的尺寸，以便触发器启动。

请参阅 [Adobe Experience cloud文档](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html) ，观看此 [视频](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two)。

## 触发最佳实践和限制 {#triggers-best-practices-and-limitations}

以下是使用Campaign - Triggers集成的最佳实践和限制列表：

* 如果您有多个Campaign standard实例，则只要触发器位于同一IMS组织ID中，所有实例都可以接收它们。 Analytics还需要位于同一IMS组织ID上。
* 不能使用两个不同报表包中的事件在触发器核心服务中创建触发器。
* 触发器基于交易消息。 只要您必须非常快速地发送消息，就会使用交易消息。 您不能将事务性消息排队，然后批量循环这些消息。
* 触发器本质上并非确定性的。 当触发器生成时，它会发送与Cookie关联的所有别名，因此，如果共享浏览器（如在零售亭、图书馆、网吧或家中的共享设备中）（丈夫和妻子从同一设备登录），则无法映射到正确的ID。 使用浏览器登录的所有ID都会发送到营销活动，该营销活动根据第一次对帐发送消息。 如果有多个“电子邮件ID”可进行对帐，则营销活动不会发送电子邮件。 除非Analytics捕获并发送正确的电子邮件ID，否则Campaign无法了解该ID的含义。
* 不能在Campaign中存储有效负荷的内容。 触发器不能用于更新配置文件的数据。
* 触发器中不支持客户属性（这意味着，只有报表包数据可用于定义触发器业务规则）。
* 集合集合在Campaign中不受支持。

>[!CAUTION]
>
>您的网站必须与Adobe Campaign服务器在同一域上运行。 否则，将无法使用访客ID协调并联系匿名访问网站的用户。

