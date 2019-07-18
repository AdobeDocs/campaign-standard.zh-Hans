---
title: 准备和发送应用程序内消息
seo-title: 准备和发送应用程序内消息
description: 准备和发送应用程序内消息
seo-description: 创建应用程序内消息以向应用程序用户定向特定内容。
page-status-flag: 从未激活
uuid: a79b0466-8641-46cc-a70 f-e4 e839587 bb2
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 应用程序内消息传递
discoiquuid: 18bf5297-a688-4302-aba4-e2 fbcafdb515
context-tags: 交付、触发器、返回；Delivery创建，向导
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 90b478d1d58b67e763b8b6685c12530a5b5ee9c3

---


# Preparing and sending an In-App message{#preparing-and-sending-an-in-app-message}

>[!NOTE]
>
>应用程序内个性化依赖于链接字段，该字段通常是CRM ID和/或移动App登录ID。在与Adobe Campaign相关时，您自行负责保护此链接字段。如果您无法保证链接字段的安全，您的个性化信息可能会受到攻击。如果您未能遵循安全链接字段构成、管理和保护实践，Adobe不会对因未经授权访问或使用任何个人资料数据而造成的损害负责。

Adobe Campaign中提供三种类型的应用程序内消息：

* **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**：此消息类型允许您定位已订阅移动应用程序的Adobe Campaign配置文件(CRM配置文件)。可以使用Adobe Campaign中的所有可用配置文件属性个性化此消息类型，但需要在Mobile SDK和Campaign的应用程序内消息服务之间安全握手，以确保仅授权用户使用具有个人和敏感信息的消息。

   要在用户设备上下载此消息类型，Mobile SDK必须发送链接字段，用于将移动配置文件连接到Adobe Campaign中的CRM配置文件。For more information on SDK APIs required to support In-App, refer to this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference).

* **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**：此消息类型允许您向移动应用程序的所有用户(当前或未来)发送消息，即使Adobe Campaign中没有现有配置文件也是如此。自定义消息时无法实现个性化，因为Adobe Campaign中甚至不存在用户配置文件。
* **[!UICONTROL Target users based on their Mobile profile (inApp)]**：此消息类型使您能够定位移动应用程序中具有移动配置文件的所有已知或匿名用户。此消息类型只能使用非个人和非敏感属性进行个性化，不需要在Mobile SDK和Adobe Campaign的应用程序内消息服务之间进行安全握手。

   For more information on how to handle personal and sensitive data, refer to [Handling mobile profile fields with personal and sensitive data](../../channels/using/preparing-and-sending-an-in-app-message.md#handling-mobile-profile-fields-with-personal-and-sensitive-data).

## Handling mobile profile fields with personal and sensitive data {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

需要扩展此资源才能收集您希望从移动设备发送到Adobe Campaign的数据。To do so, refer to this [page](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) for the detailed steps.

为了更安全地实现应用程序内消息的个性化，需要相应地配置此资源中的移动配置文件字段。In your **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, when creating your new mobile profiles fields, check **[!UICONTROL Personal and Sensitive]** to make them unavailable during In-App messages personalization.

>[!NOTE]
>
>如果您有一个在此表上具有自定义资源扩展的现有实施，我们建议您在利用这些字段以实现应用程序内消息个性化之前对字段进行适当标记。

![](assets/in_app_personal_data_2.png)

Once your **[!UICONTROL Subscriptions to an application]** custom resource is configured and published, you can start preparing your In-App delivery using the **[!UICONTROL Target users based on their Mobile profile (inApp)]** template. Only non-personal and non-sensitive fields will be available from **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource for personalization.

If you require personalization with **Personal and Sensitive** fields, we recommend using the **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** template which has additional security mechanism to ensure that your users' PII data remains secure.

## Preparing your In-App message {#preparing-your-in-app-message}

使用Adobe Campaign创建单独应用程序内消息的步骤有：

1. From Adobe Campaign home page, click the **[!UICONTROL In-App messaging]** card.

   You can also create an In-App from the **Marketing activities** tab, by clicking the **[!UICONTROL Create]** button.

   请注意，还可以从营销活动或Adobe Campaign主页或工作流中创建应用程序内消息。

1. Select **In-App message**.

   ![](assets/inapp_creating.png)

1. 根据受众定位需求选择相应的模板。

   ![](assets/inapp_creating_2.png)

   默认情况下，您可以选择以下三个现成的模板之一：

   * **[!UICONTROL Target users based on their Campaign CRM profile (inAppProfile)]**
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**

1. Enter the In-App message properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   ![](assets/inapp_creating_3.png)

1. 选择要为应用程序内消息定位的受众。根据与此交付关联的移动应用程序，您的受众将被预先过滤。

   Note that this step is not needed with the **[!UICONTROL Broadcast an In-App message (inAppBroadcast)]** since it targets all users of a mobile application.

   ![](assets/inapp_creating_8.png)

1. **[!UICONTROL Triggers]** 在选项卡中，拖放将触发消息的事件。选择触发器可选择用户执行的操作，这会导致显示应用程序内消息。

   有四种活动类别：

   * **[!UICONTROL Mobile Application events]**：在移动应用程序中实现的自定义事件。

      For more on events creations, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

   * **[!UICONTROL Life Cycle events]**：Adobe Mobile SDK支持的现成生命周期事件。

      For more on life cycle events, refer to this [page](https://marketing.adobe.com/resources/help/en_US/mobile/android/metrics.html).

   * **[!UICONTROL Analytics Events]**：根据在移动应用程序中进行的检测，支持以下三种类别：Adobe Analytics、上下文数据或视图状态。

      请注意，这些活动仅在您拥有Adobe Analytics许可证时可用。

   * **[!UICONTROL Places]**：以下三个类别利用实时位置数据提供上下文相关的移动体验：放置上下文数据，放置自定义元数据或地点事件类型。

      For more information on Adobe Places, refer to the [Places documentation](https://placesdocs.com/).
   ![](assets/inapp_creating_4.png)

1. If you use an **[!UICONTROL Analytics Events]**, Adobe Analytics and View state events will be automatically populated based on the report suites configured in the Analytics extension in Adobe Experience Platform Launch whereas Context data events have to be manually added.

   请注意，这些活动仅在您拥有Adobe Analytics许可证时可用。

   ![](assets/inapp_creating_7.png)

1. If you use a **[!UICONTROL Places]** trigger, Places context data, Places custom metadata or Places event type will be automatically populated based on all the Libraries and their Points of Interest created in Adobe Places.

   请注意，此触发器只会应用于在Experience Platform Launch中的Place扩展中选择的库中的“目标点”设备。For more information on the Places extension and how to install it, refer to this [documentation](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/places-extension-1/places-extension).

1. **[!UICONTROL Frequency & duration]** 在选项卡中，选择触发器的频率、开始和结束日期、每周日期和应用程序内消息处于活动状态之日。

   ![](assets/inapp_creating_5.png)

1. 编辑消息的内容并定义高级选项。See [Customizing an In-App message](https://helpx.adobe.com/campaign/standard/channels/using/customizing-a-push-notification.html).

   ![](assets/inapp_creating_6.png)

1. Click **[!UICONTROL Create]**.

您的应用程序内消息现已准备好发送给目标受众。

**相关主题：**

* [自定义应用程序内消息](../../channels/using/customizing-an-in-app-message.md)
* [应用程序内报告](../../reporting/using/in-app-report.md)
* [在工作流中发送应用程序内消息](../../automating/using/in-app-delivery.md)

## Sending your In-App message {#sending-your-in-app-message}

完成交付准备工作并执行批准步骤后，您可以发送邮件。

1. Click **[!UICONTROL Prepare]** to compute the target and generate the messages.

   ![](assets/inapp_sending_4.png)

1. 成功完成准备工作后，**部署**&#x200B;窗口会显示以下 KPI：**目标**&#x200B;和&#x200B;**要交付的内容**。

   You can check the Deployment window by clicking the ![](assets/lp_link_properties.png) button for potential exclusions or errors in your delivery.

   ![](assets/inapp_sending_5.png)

1. Click **[!UICONTROL Confirm]** to start sending your In-App message.

   ![](assets/inapp_sending_6.png)

1. 通过消息仪表板和日志检查您的交付状态。For more on this, refer to this [section](../../sending/using/monitoring-a-delivery.md).

   **[!UICONTROL Delivered]** KPI **[!UICONTROL Sent]** 计数基于成功从Campaign到Message交付服务发出的内容。请注意，这些KPI并不表示通过邮件交付服务获得或下载消息的移动设备计数。

   ![](assets/inapp_sending_7.png)

1. 利用交付报告衡量应用程序内消息的影响。For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).

**相关主题：**

* [应用程序内报告](../../reporting/using/in-app-report.md)
* [在工作流中发送应用程序内消息](../../automating/using/in-app-delivery.md)

