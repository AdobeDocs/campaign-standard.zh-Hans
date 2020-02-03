---
title: 创建服务
description: 了解如何创建您的第一项服务并对其进行配置，以向订阅者发送电子邮件确认。
page-status-flag: never-activated
uuid: 0d95d852-0f22-4b7b-b301-8fb4844c3ca2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 6b7788fe-fa6c-472a-97db-765595ce1589
context-tags: service,wizard;service,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: de16bef6cfd0afa3f664c98fe77484044aac6610

---


# 创建服务{#creating-a-service}

为了能够管理订阅，您首先需要创建并配置服务。 通过配置新服务，您可以指定配置文件订阅或取消订阅服务时将收到的电子邮件确认。 您还将定义链接到该服务的订阅和取消订阅登录页面。 例如，插入到电子邮件中的服务订阅链接会自动将配置文件定向到服务中指定的订阅登录页面。

配置服务：

1. 从高级菜单 **[!UICONTROL Profiles & audiences]**>中，**[!UICONTROL Services]** 通过Adobe Campaign徽标添加新服务或选择现有服务。 如果创建新服务，只需按照屏幕上显示的步骤操作。

   默认服务模板可用。 此模板已预配置默认登录页面和确认电子邮件。 您可以创建其他模板来定义特定配置。 有关详细信息，请参阅管理模 [板部分](../../start/using/marketing-activity-templates.md) 。

1. 在通过 **[!UICONTROL Service properties]**服务功能板中的按钮![](assets/edit_darkgrey-24px.png)访问的部分中，为订阅和取消订阅配置确认消息。

   ![](assets/lp_service_parameters.png)

1. 选择选 **[!UICONTROL Subscriptions with an expiration date]**项可设置订阅的有效期。

   ![](assets/lp_service_expiration.png)

您可以在分段活动中使用到期日期来定位订阅未过期服务的配置文件。

1. 填写字 **[!UICONTROL Service label]**段。 使用自定义确认消息时，服务标签是必填的。

1. 为订阅和取消订阅选择确认消息模板。 有三种模式可用：

   * **[!UICONTROL No message]**:此模式允许您创建无确认消息的服务。
   * **[!UICONTROL Default message]**:此模式将使用默认订阅或取消订阅确认事务消息。 默认确认消息是通用消息，对于使用默认模式的所有服务，该消息都是相同的。

      >[!NOTE]
      >
      >在选中该框后，您可以通过单击部分中的默认消息标签或从 **[!UICONTROL Service properties]**Adobe Campaign事务性消息列表中选择默认消息来修改默认消**[!UICONTROL Show internal transactional messages]** 息。

   * **[!UICONTROL Custom message]**:此模式允许您处理特定于每个服务的自定义确认消息。 然后，选择与**[!UICONTROL Custom subscription event configuration]** 特定事务消息模板关 [联的](../../channels/using/about-transactional-messaging.md) 。 有关此功能的详细信息，请参 [阅确认订阅服务](../../audiences/using/confirming-subscription-to-a-service.md)。

1. 保存服务。 它现已准备好使用。

创建服务后，即可开始提升它。

**相关主题：**

* [管理服务和订阅视频](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/services-and-subscriptions.html)
* [推广服务](../../audiences/using/promoting-a-service.md)
* [创建由订阅者构成的受众](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [将登陆页面链接到服务](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)
