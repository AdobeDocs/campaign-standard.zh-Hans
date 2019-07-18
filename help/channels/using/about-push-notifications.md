---
title: 关于推送通知
seo-title: 关于推送通知
description: 关于推送通知
seo-description: 发现Adobe Campaign推送通知渠道的主要特殊性。
page-status-flag: 从未激活
uuid: 961aaeb5-6948-4fd2-b8 d7-de4510 c10566
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 推送通知
discoiquuid: 23b4212e-e878-4922-be20-50fb7 fa88 ae8
context-tags: MobileApp，概述
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 80e65c3fedc5452105c296144a683948daa69150

---


# About push notifications{#about-push-notifications}

>[!CAUTION]
>
>专家用户必须执行推送通知。如果需要协助，请与您的Adobe客户经理或专业服务合作伙伴联系。推送通知是可选功能。请检查您的许可协议并联系您的帐户管理人员以激活它。

Adobe Campaign允许您向iOS和Android移动设备发送个性化、分段推送通知。

通过利用Experience Cloud Mobile SDK V或Experience Platform SDK，可以在您在Adobe Campaign中设置的移动应用程序上收到这些消息。For more information on this, refer to [Configuring a mobile application using SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) and [Configuring a mobile application using Adobe Experience Platform SDKs](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

需要扩展此资源才能收集您希望从移动设备发送到Adobe Campaign的数据。To do so, refer to this [page](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) for the detailed steps.

Adobe Campaign中提供了两种类型的推送通知：

* **[!UICONTROL Alert/Message/Badge]** type notifications使您能够发送包含其他内容(声音、徽章、取消链接等)的标准基于文本的消息。that you can define in the **[!UICONTROL Advanced options]** section.

   此通知类型允许您添加标题和可在其中使用个性化字段的消息。To be able to personalize your message, make sure you select the **[!UICONTROL Send push on profiles]** template.

* **[!UICONTROL Silent push]** 类型通知用于无提示通知应用程序，而无需任何消息或内容供最终用户使用。此类型消息的典型用例是使应用程序知道要下载的服务器上有可用内容。

可以设置一些特定配置来定义通知行为。For more on this, refer to [this section](../../channels/using/customizing-a-push-notification.md).

As an expert user, to define these specific configurations, refer to the mobile app [technotes](https://helpx.adobe.com/campaign/kb/acs-article-list.html).

>[!NOTE]
>
>关于隐私的法律因国家/地区而异。一些国家要求您告知用户移动应用程序收集的数据类型。请检查与您所在国家/地区相关的法律相关法律。确保发送到移动应用程序的推送通知符合Apple(Apple Push Notification Service)和Google(Google Cloud Messaging或Firebase Cloud Messaging)指定的先决条件和条件。

**相关内容：**

* [准备和发送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
* [创建多语言推送通知](../../channels/using/creating-a-multilingual-push-notification.md)
* [在工作流中发送推送通知](../../automating/using/push-notification-delivery.md)
* [推送和应用程序内常见问题解答](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)

## Prerequisites {#prerequisites}

>[!NOTE]
>要利用Campaign中的推送通知功能，您需要提供不带密码的有效推送证书。
如果您有有效的p12证书，可以使用在线资源将其轻松转换为. pem文件。

首先，要开始发送推送通知，您需要使用SDK V配置移动应用程序。您还可以使用Experience Platform SDK配置移动应用程序。For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

在发送推送通知之前，您应该：

1. Make sure you can access the **[!UICONTROL Mobile app]** channel in Adobe Campaign.
1. 在以下位置配置移动应用程序：

   * Adobe Campaign
   * Adobe Mobile Services界面

1. 执行移动应用程序的特定设置：

   * 使用移动应用程序打包从Adobe Mobile Services界面下载的配置文件。
   * 将Experience Cloud Mobile SDK集成到您的移动应用程序中。

1. 定义要从应用程序的订阅者收集的数据。根据您定义的标准协调在Adobe Campaign数据库中具有个人资料的移动应用程序的用户。

配置移动应用程序后，您现在可以开始准备和发送应用程序内消息。For more on this, refer to [Preparing and sending a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).
