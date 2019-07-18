---
title: 在Experience Cloud中配置触发器
seo-title: 在Experience Cloud中配置触发器
description: 在Experience Cloud中配置触发器
seo-description: '了解如何配置Adobe Experience Cloud触发器集成，以根据客户先前的行为向客户发送个性化分发。 '
page-status-flag: 从未激活
uuid: 8fd7b804-9528-46a5-a060-bf16 b8 dc555 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: 使用营销活动和触发器
discoiquuid: 4163dc0c-8103-4425-b8 bf-7aa45 c4 d06 a06
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configuring Triggers in Experience Cloud{#configuring-triggers-in-experience-cloud}

## Activating the functionality {#activating-the-functionality}

Adobe Campaign中必须激活该功能。请联系您的Adobe客户经理或专业服务合作伙伴。

Adobe团队需要以下信息才能激活触发器：

* Marketing Cloud公司名称
* IMS ORG ID
* Analytics登录公司(可以与Marketing Cloud公司名称相同)

## Configuring solutions and services {#configuring-solutions-and-services}

要使用此功能，您需要访问以下解决方案/核心服务：

* Adobe Campaign
* Adobe Analytics Ultimate、Premium、Foundation、OD、Select、Prime、Mobile Apps、Select或Standard。
* Experience Cloud触发器核心服务

   ![](assets/trigger_uc_prereq_1.png)

* Experience Cloud DTM核心服务

   ![](assets/trigger_uc_prereq_2.png)

* Experience Cloud访客ID和Experience Cloud People Core Service

   ![](assets/trigger_uc_prereq_3.png)

您还需要有一个工作网站。

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>子域委派是一个可交付性关键元素。确保Adobe Campaign电子邮件与网站使用的同一域发送。

You need to configure [Experience Cloud DTM Core Service](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-experience-cloud-dtm-core-service), [Experience Cloud People Core Service](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-experience-cloud-people-core-service) and [Campaign](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-triggers-and-aliases-in-campaign) to run these use cases.

### Configuring Experience Cloud DTM Core Service {#configuring-experience-cloud-dtm-core-service}

1. 在Experience Cloud DTM核心服务(动态标签管理)中，为您的网站页面激活Experience Cloud ID和Adobe Analytics。

   ![](assets/trigger_uc_conf_1.png)

1. 网站之间的ID对帐，Adobe Analytics和Adobe Campaign需要使用别名。创建别名，“visitorid”。

   ![](assets/trigger_uc_conf_2.png)

### Configuring Experience Cloud People Core Service {#configuring-experience-cloud-people-core-service}

DTM中之前引用的别名需要通过客户属性在Experience Cloud People Service中创建。确保创建一个新的，并引用集成代码中相同的DTM别名(例如“visitororid”)。

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>我们将在Adobe Campaign中的数据源(下一步)中使用此客户属性。

### Configuring triggers and aliases in Campaign {#configuring-triggers-and-aliases-in-campaign}

1. Make sure you have **[!UICONTROL Experience Cloud triggers]** visible on your Adobe Campaign Standard instance. 如果没有，请与Adobe Campaign管理员联系。

   ![](assets/remarketing_1.png)

1. 别名使Analytics中的联系人能够与Campaign中的配置文件协调。您需要将Experience Cloud ID服务中定义的别名与Campaign中的共享数据源相匹配。You need to configure the aliases resolution in Adobe Campaign via a Data source ( **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Shared Data Sources]** ). Make sure you choose the correct data source in the **[!UICONTROL Data Source/Alias]** drop-down menu, which is mapped with the same Customer Attribute data source created in previous step.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >您可以将触发器调整为匿名和登录用户。对于匿名用户，Adobe Campaign中应存在该配置文件，此前将向该用户发送一封电子邮件。为此，访客ID配置足以完成。但是，如果要协调触发器中记录的触发器，则需要设置声明ID数据源。For more on this, refer to [Data Source configuration](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Creating a trigger in the Experience Cloud interface {#creating-a-trigger-in-the-experience-cloud-interface}

需要创建Adobe Experience Cloud触发器，以便在Campaign中使用它。

在Experience Cloud中创建新触发器，并确保选择网站上使用的报表包。确保选择正确的尺寸，以便触发器触发。

Refer to the [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html) and watch this [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

## Triggers best practices and limitations {#triggers-best-practices-and-limitations}

以下列出了Campaign-触发器集成的最佳实践和限制：

* 如果您有多个Campaign Standard实例，则所有实例都可以接收到触发器，只要它们位于同一IMS组织ID中。Analytics还需要使用相同的IMS组织ID。
* 不能使用来自两个不同报表包的事件在触发器核心服务中创建触发器。
* 触发器基于交易消息。每当必须快速发送消息时，都可以使用交易消息。您不能排队发送事务消息，然后再循环播放它们。
* 触发器本质上不是确定的。生成触发器后，它会发送与cookie关联的所有别名，因此，如果共享浏览器如零售报亭、库、网络咖啡厅或家中共享的设备(从同一设备登录)，则无法映射到正确的ID。用于登录浏览器的所有ID都将发送到Campaign，以便在第一个调解的基础上发送消息。如果有多个有资格进行调解的“电子邮件ID”，则Campaign不发送电子邮件。Campaign无法了解正确的电子邮件ID是什么，除非由Analytics捕获并发送。
* 您无法在Campaign中存储有效负荷的内容。触发器不能用于更新配置文件的数据。
* 触发器中不支持客户属性(意味着，只能使用报表包数据定义触发器业务规则)。
* Campaign不支持集合集合。

>[!CAUTION]
>
>您的网站必须与Adobe Campaign服务器在同一域上运行。否则，您不能使用访客id协调和联系访问网站的用户。

