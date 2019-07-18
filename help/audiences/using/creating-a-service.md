---
title: 创建服务
seo-title: 创建服务
description: 创建服务
seo-description: 了解如何创建您的第一个服务并对其进行配置，以向用户发送电子邮件确认。
page-status-flag: 从未激活
uuid: 0d95d852-0f2-4b7b-b301-8fb4844 c3 ca2
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受众
content-type: reference
topic-tags: 管理订阅
discoiquuid: 6b7788fe-fa6 c-472a-97db-765595ce1589
context-tags: service，wizard；service，main
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Creating a service{#creating-a-service}

为了能够管理订阅，您首先需要创建一个服务并配置它。配置新服务允许您指定配置文件订阅或取消订阅服务时将接收的电子邮件确认。您还将定义链接到该服务的订阅和取消订阅登录页面。例如，插入到电子邮件中的服务订阅链接会自动将配置文件定向到服务中指定的订阅登陆页面。

配置服务：

1. From the advanced menu **Profiles &amp; audiences** &gt; **Services** via the Adobe Campaign logo, add a new service or select an existing service. 如果您创建新服务，只需按照屏幕上显示的步骤操作。

   提供默认服务模板。此模板预先配置了默认登录页面和确认电子邮件。您可以创建其他模板来定义特定配置。For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. In the **Service properties** section, accessed via the ![](assets/edit_darkgrey-24px.png) button in the service dashboard, configure the confirmation messages for subscriptions and unsubscriptions.

   ![](assets/lp_service_parameters.png)

1. 为订阅和取消订阅选择确认消息模板。有三种模式：

   * **[!UICONTROL No message]**：此模式允许您创建服务，而无需确认消息。
   * **[!UICONTROL Default message]**：此模式将使用默认订阅或取消订阅确认消息。默认确认消息是通用的，对于使用默认模式的所有服务都是相同的。
   * **[!UICONTROL Custom message]**：此模式允许您处理每个服务特定的自定义确认消息。You then select the **[!UICONTROL Custom subscription event configuration]** which is associated with a specific transactional message template. Refer to [Transactional messages](../../channels/using/about-transactional-messaging.md) for more information on transactional event and message configuration.

1. 保存服务。现已准备好使用。

创建服务后，您可以开始提升它。

**相关主题：**

* [管理服务和订阅](https://helpx.adobe.com/campaign/kt/acs/using/acs-services-and-subscriptions-feature-video-use.html) 视频
* [提升服务](../../audiences/using/promoting-a-service.md)
* [创建由订阅者创建的受众](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [将表单链接到登陆页面中的服务](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service)

