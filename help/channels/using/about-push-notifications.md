---
solution: Campaign Standard
product: campaign
title: 关于推送通知
description: 了解 Adobe Campaign 中推送通知渠道的主要特性。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Push
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1284'
ht-degree: 50%

---


# 关于推送通知{#about-push-notifications}

>[!CAUTION]
>
>必须由专家用户执行推送通知的实施。如果需要协助，请与您的 Adobe 客户经理或专业服务合作伙伴联系。推送通知属于可选功能。请核实您的许可协议并联系您的帐户管理员以将其激活。

利用 Adobe Campaign，可向 iOS 和 Android 移动设备发送个性化的分段推送通知。

通过利用 Experience Platform SDK 在 Adobe Campaign 中设置的移动应用程序，可接收此类消息。有关此功能的详细信息，请参阅[使用 Adobe Experience Platform SDK 配置移动应用程序](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html)。

在 Adobe Campaign 中，由移动设备发出的移动配置文件属性数据存储在 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 资源中，利用该资源，您可定义要从应用程序的订阅者那里收集的数据。

需要扩展此资源，才能收集您打算从移动设备发送到 Adobe Campaign 的数据。要实现此目的，请参阅此[页面](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)以了解详细步骤。

Adobe Campaign 提供两种类型的推送通知：

* **[!UICONTROL Alert/Message/Badge]** 类型通知允许您发送基于文本的标准消息，其中可包含在 **[!UICONTROL Advanced options]** 部分中定义的附加内容（声音、徽章、深度连接等）。

   此通知类型允许您在个性化字段中添加标题和消息。要个性化您的消息，请确保选择 **[!UICONTROL Send push on profiles]** 模板。

* **[!UICONTROL Silent push]** 类型通知用于静默通知应用程序，不会向最终用户发送任何消息或内容。此类消息的典型用例，是让应用程序知道服务器上有可供下载的内容。

可以设置某些特定配置来定义通知行为。有关更多信息，请参阅[此章节](../../channels/using/customizing-a-push-notification.md)。

作为专家用户，要定义这些特定配置，请参阅移动应用[技术说明](https://helpx.adobe.com/cn/campaign/kb/acs-article-list.html)。

>[!NOTE]
>
>有关隐私的法律因国家/地区而异。有些国家/地区要求您向用户告知移动应用所收集的数据类型。请查看您所在国家/地区与移动应用相关的法律。确保发送到移动应用的推送通知符合 Apple（Apple 推送通知服务）和 Google（Google Cloud Messaging 或 Firebase Cloud Messaging）指定的先决条件和条件。

**相关内容：**

* [准备和发送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
* [创建多语言推送通知](../../channels/using/creating-a-multilingual-push-notification.md)
* [推送通知报告](../../reporting/using/push-notification-report.md)
* [Campaign Standard Mobile 指南](https://helpx.adobe.com/cn/campaign/kb/acs-mobile.html)

## 先决条件{#prerequisites}

>[!NOTE]
>要利用 Campaign 的推送通知功能，您需要提供没有密码的、.pem 格式的有效推送证书。

>
>如果您拥有有效的 p12 证书，则可以使用联机资源轻松将其转换为 .pem 文件。

在发送推送通知之前，您应：

1. 在 Adobe Campaign 中，确保可以访问 **[!UICONTROL Push notification]** 渠道。如果您无法访问这些渠道，请与帐户管理团队联系。

1. 验证您的用户是否拥有 Adobe Campaign Standard 和 Experience Platform Launch 的必要权限。

1. 在 Experience Platform Launch 中，创建移动属性。有关更多信息，请参阅[设置移动属性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)。

1. 在 Experience Platform Launch 中，安装 **[!UICONTROL Adobe Campaign Standard]** 扩展。

1. 在 Adobe Campaign Standard 中，配置您在 Experience Platform Launch 中创建的移动属性。有关更多信息，请参阅[在 Adobe Campaign 中设置 Experience Platform Launch 应用程序](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign)。

1. 将特定于渠道的配置添加到您的移动应用设置中。有关更多信息，请参阅 [Adobe Campaign 中特定于渠道的应用程序配置](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

1. 要支持移动使用案例实施，请参阅[在 Adobe Campaign Standard 中使用 Adobe Experience Platform SDK 支持的移动使用案例](https://helpx.adobe.com/cn/campaign/kb/configure-launch-rules-acs-use-cases.html)中关于扩展、Experience Platform Launch 规则和 SDK 实施的详细说明。

## 推送通知常见问题解答{#push-faq}

### 要进一步了解推送渠道，有哪些有用的资源建议？{#resource-push}

查看以下资源：

* [视频Tutorials](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [产品文档](../../channels/using/about-push-notifications.md)
* 使用AEP SDK [文档](../../administration/using/configuring-a-mobile-application.md)进行配置
* [社区页](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### 要获取活动中的推送令牌，我必须做什么？{#push-token-acquisition}

确保设置团队已在Adobe Campaign Standard中完成推送渠道的设置。 从SDK实施setPushIdentifier API。 有关详细信息，请参见此 [ 页面](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#set-up-push-messaging)。

### 在活动中包含推送令牌和ECID后，我还需要发送推送通知吗？{#sending-push}

客户需要提供.pem格式的有效推送证书才能发送推送通知。 您不需要此证书的密码。

### 如果我有.p12证书而不是.pem证书，该怎么办？{#certificates}

通过在终端中运行以下命令，可以将.p12证书转换为.pem证书。 还有几个在线资源可用于转换说明。

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### 如何知道证书上传是否成功？{#certificate-upload}

您将看到以下消息。

![](assets/faq_2.png)

### 我是否可以同时为iOS应用程序上传生产证书和沙箱证书（对于Android，为N/A）？{#prod-sandbox-certificate}

否，应用程序在沙箱或生产模式下工作，一旦设置，将无法更改为其他应用程序（即沙箱到生产应用程序）。 我们建议您首先在沙箱模式下测试应用程序，然后过渡到生产模式。

要更改到生产模式，您必须创建另一个应用程序。 另外，请务必不要选中沙箱复选框并上传生产证书。

### 我是否可以同时上传iOS和Android凭据？{#ios-android-credentials}

是的，活动同时支持两个平台，并允许您上传两个平台的凭据。

### 我已成功上载推送证书，但未发送推送消息。{#push-certificates-upload}

请通过在[此处](https://pushtry.com/)测试您的推送证书，确保它们有效。

### 我可以从pushtry.com成功发送推送通知，但不能通过活动。{#push-not-sending}

请确保您遵循[此处](../../administration/using/push-payload.md)提供的推送有效负荷说明。

请注意，对于Android，活动仅支持数据负载，不支持通知负载

### 我已在Adobe Campaign Standard的“管理”部分配置了应用程序，但移动应用程序在投放属性中不可用。{#mobile-app-unavailable}

应用程序还必须上传有效的推送证书，才能在投放属性中使用。

### 我已尝试了此页面上的所有说明，但无法从活动发送推送。{#push-troubleshoot}

请打开客户关怀票。

### 推送通知从活动传送，但媒体文件未显示。{#media-file-unavailable}

移动应用程序开发人员需要处理应用程序中媒体文件的支持。 有时，网络带宽也可能会阻止媒体文件呈现。 有关其他指针，请参阅此[页](../../administration/using/image-push-notification.md)。

### 要在活动中启用推送报告，我必须做什么？{#push-reporting-enable}

按照下面的步骤进行操作：

* 配置推送跟踪回发。 可以在[此处](../../administration/using/configuring-a-mobile-application.md)找到说明。
* 从Mobile Core实施trackAction API。 有关详细信息，请参阅此[页](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference)。

此[页面](../../administration/using/push-tracking.md)中提供了更多详细说明。

### 哪些报表可用于推送渠道?{#push-report-available}

现成报表在“推送”Adobe Campaign中提供。 请参阅此[文档](../../reporting/using/push-notification-report.md)。

请参阅此[页](../../reporting/using/indicator-calculation.md#push-notification-delivery)以了解如何计算每个推送量度。

### 推送和应用程序内消息中是否支持深层链接？{#deeplink-push}

是，推送消息中支持深层链接。 深层链接应包括：

* 声明需要禁用投放跟踪以使开发人员能够工作的语言。
* Appsflyer与Branch合作，可以进行开发跟踪。 有关分支和Adobe Campaign Standard集成的详细信息，请参阅此[页面](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1)。
