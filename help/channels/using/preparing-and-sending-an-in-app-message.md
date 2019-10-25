---
title: 准备和发送应用程序内消息
seo-title: 准备和发送应用程序内消息
description: 准备和发送应用程序内消息
seo-description: 创建应用程序内消息，以针对具有特定内容的应用程序订阅者。
page-status-flag: 从未激活
uuid: a79b0466-8641-46cc-a70f-e4e839587bb2
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 应用程序内消息传递
discoiquuid: 18bf5297-a688-4302-abe4-e2fbcafdb515
context-tags: 交付，触发器，返回；交付创建，向导
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 准备和发送应用程序内消息{#preparing-and-sending-an-in-app-message}

>[!NOTE]
>
>应用程序内个性化依赖于链接字段，该字段通常为CRM ID和／或移动应用程序登录ID。 在与Adobe Campaign一起使用时，您应自行负责保护此链接字段。 如果您无法保持链接字段的安全，则您的个性化信息可能会受到攻击。 如果您未遵循安全链接字段构成、管理和保护实践，则Adobe不承担因未经授权访问或使用任何配置文件数据而造成的损害的责任。

Adobe Campaign中提供三种类型的应用程序内消息：

* **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**:此消息类型允许您定位已订阅移动应用程序的Adobe Campaign配置文件（CRM配置文件）。 此消息类型可以使用Adobe Campaign中所有可用的配置文件属性进行个性化，但需要Mobile SDK与Campaign的应用程序内消息传递服务之间进行安全握手，以确保仅授权用户使用包含个人和敏感信息的消息。

   要在用户的设备上下载此消息类型，Mobile SDK必须发送链接字段，这些字段用于将移动配置文件连接到Adobe Campaign中的CRM配置文件。 有关支持应用程序内所需的SDK API的详细信息，请参阅本 [页](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference)。

* **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**:此消息类型允许您向移动应用程序的所有用户（当前或将来）发送消息，即使他们在Adobe Campaign中没有现有的配置文件也是如此。 因此，在自定义消息时无法个性化，因为Adobe Campaign中可能甚至不存在用户配置文件。
* **[!UICONTROL Target users based on their Mobile profile (inApp)]**:此消息类型允许您定位Adobe Campaign中具有移动配置文件的移动应用程序的所有已知或匿名用户。 此消息类型只能使用非个人属性和非敏感属性进行个性化，并且不需要Mobile SDK与Adobe Campaign的应用程序内消息传递服务之间的安全握手。

   有关如何处理个人和敏感数据的详细信息，请参阅处理 [包含个人和敏感数据的移动配置文件字段](#handling-mobile-profile-fields-with-personal-and-sensitive-data)。

![](assets/diagram_inapp.png)

## 使用个人和敏感数据处理移动配置文件字段 {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

需要扩展此资源以收集您打算从移动设备发送到Adobe Campaign的数据。 要执行此操作，请参阅本 [页](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) ，了解详细步骤。

为了更安全地实现应用程序内消息的个性化，需要相应地配置此资源中的移动配置文件字段。在您的 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**&#x200B;中，在创建新的移动配置文件字段时，请检查 **[!UICONTROL Personal and Sensitive]** 以使它们在应用程序内消息个性化期间不可用。

>[!NOTE]
>
>如果此表中有具有自定义资源扩展的现有实施，我们建议您在将字段用于个性化应用程序内消息之前相应地标记这些字段。

![](assets/in_app_personal_data_2.png)

配置和 **[!UICONTROL Subscriptions to an application]** 发布自定义资源后，您便可以开始使用模板准备应用程序内交 **[!UICONTROL Target users based on their Mobile profile (inApp)]** 付。 只有非个人和非敏感字段才可从资源中用于 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 个性化。

If you require personalization with **Personal and Sensitive** fields, we recommend using the **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** template which has additional security mechanism to ensure that your users' PII data remains secure.

## 准备应用程序内消息 {#preparing-your-in-app-message}

使用Adobe Campaign创建独立的应用程序内消息的步骤有：

1. 从Adobe Campaign主页，单击 **[!UICONTROL In-App messaging]** 卡。

   您还可以通过单击按钮从“营销活动”选 **项卡创建** “应用程序内 **[!UICONTROL Create]** ”。

   请注意，还可以从营销活动或Adobe Campaign主页或工作流中创建应用程序内消息。

1. 选择 **应用程序内消息**。

   ![](assets/inapp_creating.png)

1. 根据受众定位需求选择适当的模板。

   ![](assets/inapp_creating_2.png)

   默认情况下，您可以选择以下三个现成的模板之一：

   * **[!UICONTROL Target users based on their Campaign CRM profile (inAppProfile)]**
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**

1. 输入应用程序内消息属性，然后在字段中选择您的移动应用 **[!UICONTROL Associate a Mobile App to a delivery]** 程序。

   ![](assets/inapp_creating_3.png)

1. 选择要为应用程序内消息定位的受众。 根据与此分发关联的移动应用程序，预过滤您的受众。

   请注意，此步骤不是针对移动 **[!UICONTROL Broadcast an In-App message (inAppBroadcast)]** 应用程序的所有用户而需要的。

   ![](assets/inapp_creating_8.png)

1. 在选项卡 **[!UICONTROL Triggers]** 中，拖放将触发您的消息的事件。 通过选择触发器，您可以选择由用户完成的操作，以便显示应用程序内消息。

   有四类活动：

   * **[!UICONTROL Mobile Application events]**:在移动应用程序中实现的自定义事件。

      有关活动创建的更多信息，请参阅此 [页](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

   * **[!UICONTROL Life Cycle events]**:Adobe Mobile SDK支持的现成生命周期事件。

      有关生命周期事件的详细信息，请参阅本 [页](https://marketing.adobe.com/resources/help/en_US/mobile/android/metrics.html)。

   * **[!UICONTROL Analytics Events]**:根据移动应用程序中介绍的内容，支持以下三个类别：Adobe Analytics、Context数据或“查看”状态。

      请注意，这些活动仅在您拥有Adobe Analytics许可证时可用。

   * **[!UICONTROL Places]**:以下三个类别利用实时位置数据来提供上下文相关的移动体验：放置上下文数据、放置自定义元数据或放置事件类型。

      有关Adobe Places的详细信息，请参阅 [Places文档](https://placesdocs.com/)。
   ![](assets/inapp_creating_4.png)

1. 如果您使用 **[!UICONTROL Analytics Events]** Adobe Analytics和View状态事件，则将根据Adobe Experience Platform Launch中Analytics扩展中配置的报表包自动填充，而必须手动添加上下文数据事件。

   请注意，这些活动仅在您拥有Adobe Analytics许可证时可用。

   ![](assets/inapp_creating_7.png)

1. 如果您使用触发器， **[!UICONTROL Places]** 则将根据在Adobe Places中创建的所有库及其目标点自动填充“放置”上下文数据、“放置”自定义元数据或“放置”事件类型。

   请注意，此触发器将仅应用于Experience Platform Launch中“位置扩展”中选定库中的目标点。 有关Places扩展及其安装方法的详细信息，请参阅本 [文档](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/places-extension-1/places-extension)。

1. 在选 **[!UICONTROL Frequency & duration]** 项卡中，选择触发器的频率、开始和结束日期、一周中的某天以及应用程序内消息处于活动状态的一天中的时间。

   ![](assets/inapp_creating_5.png)

1. 编辑消息内容并定义高级选项。 请参 [阅自定义应用程序内消息](https://helpx.adobe.com/campaign/standard/channels/using/customizing-a-push-notification.html)。

   ![](assets/inapp_creating_6.png)

1. Click **[!UICONTROL Create]**.

您的应用程序内消息现已准备好发送给目标受众。

**相关主题：**

* [自定义应用程序内消息](../../channels/using/customizing-an-in-app-message.md)
* [应用程序内报告](../../reporting/using/in-app-report.md)
* [在工作流中发送应用程序内消息](../../automating/using/in-app-delivery.md)

## 发送应用程序内消息 {#sending-your-in-app-message}

完成交付准备并执行批准步骤后，即可发送消息。

1. 单击 **[!UICONTROL Prepare]** 以计算目标并生成消息。

   ![](assets/inapp_sending_4.png)

1. 成功完成准备工作后，**部署**&#x200B;窗口会显示以下 KPI：**目标**&#x200B;和&#x200B;**要交付的内容**。

   您可以通过单击交付中潜在排除或错 ![](assets/lp_link_properties.png) 误的按钮来检查“部署”窗口。

   ![](assets/inapp_sending_5.png)

1. 单 **[!UICONTROL Confirm]** 击以开始发送应用程序内消息。

   ![](assets/inapp_sending_6.png)

1. 通过消息仪表板和日志检查您的交付状态。 For more on this, refer to this [section](../../sending/using/monitoring-a-delivery.md).

   **[!UICONTROL Delivered]** KPI计数 **[!UICONTROL Sent]** 基于从营销活动成功发送到消息交付服务的内容。 请注意，这些KPI并不表示从消息交付服务成功接收或下载消息的移动设备的数量。

   ![](assets/inapp_sending_7.png)

1. 通过交付报告衡量应用程序内消息的影响。 For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).

**相关主题：**

* [应用程序内报告](../../reporting/using/in-app-report.md)
* [在工作流中发送应用程序内消息](../../automating/using/in-app-delivery.md)

