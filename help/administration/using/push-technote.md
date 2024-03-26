---
title: 推送通知渠道即将发生的变化
description: 推送通知渠道即将发生的变化
audience: channels
feature: Push
role: Admin
level: Experienced
exl-id: e273b443-7c43-482b-8f86-60ada4b57cbf
source-git-commit: db035a41515e94836bdfbfc3d620586dc1f5ce31
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 1%

---

# 推送通知渠道更改 {#push-upgrade}

您可以使用Campaign在Android和iOS设备上发送推送通知。 要执行此操作，Campaign需要依赖特定的订阅服务。 2024年发布了Android Firebase Cloud Messaging (FCM)服务的一些重要更改，这些更改可能会影响Adobe Campaign实施。 您可能需要更新Android推送消息的订阅服务配置才能支持此更改。

此外，Adobe强烈建议迁移到基于令牌的连接而不是APN的基于证书的连接，这种连接更加安全和可扩展。

要确保服务不中断，您必须升级在Adobe Campaign中注册的移动应用程序，以纳入FCM (Android)和APN (iOS)的最新身份验证机制。


[详细了解如何在Adobe Campaign Standard中配置移动应用程序证书](configuring-a-mobile-application.md#channel-specific-config)


## Google Android Firebase Cloud Messaging (FCM)服务 {#fcm-push-upgrade}

### 更改了哪些内容？ {#fcm-changes}

作为Google持续努力改进其服务的一部分，旧版FCM API将在以下日期停用 **2024年6月20日**. 在中了解有关Firebase云消息HTTP协议的更多信息 [Google Firebase文档](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

正在启动 [24.1版本](../../rn/using/release-notes.md)，Adobe Campaign Standard支持使用HTTP v1 API发送Android推送通知消息。

### 您是否受影响？ {#fcm-impact}

如果您已使用Adobe Campaign Standard发送推送通知，则必须更新实施。

必须转换为最新的API才能避免任何服务中断。

<!--To check if you are impacted, you can filter your **Services and Subscriptions** as per the filter below

* If any of your active push notification service uses the **HTTP (legacy)** API, your setup will be directly impacted by this change. You must review your current configurations and move to the newer APIs as described below.

* If your setup exclusively uses the **HTTP v1** API for Android push notifications, then you are already in compliance and no further action will be required on your part.-->

### 如何更新？ {#fcm-transition-procedure}

#### 先决条件 {#fcm-transition-prerequisites}

* 支持 **HTTP v1 API** 模式已在24.1版本中添加。 如果您的环境运行在旧版本上，则此更改的先决条件是将您的环境升级到 [最新Campaign Standard版本](../../rn/using/release-notes.md).

* 需要Android Firebase Admin SDK服务的帐户JSON文件才能将移动应用程序移动到HTTP v1。 了解如何在中获取此文件 [Google Firebase文档](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* 如果您仍在使用此旧版SDK，则必须使用Adobe Experience Platform SDK更新您的实施。 了解如何在中迁移到AdobeExperience Platform SDK [本文](sdkv4-migration.md).

* 确保您拥有 **移动应用程序配置** Adobe Experience Platform权限。 [了解详情](https://experienceleague.adobe.com/docs/experience-platform/collection/permissions.html?lang=en#adobe-experience-platform-data-collection-permissions){target="_blank"}。


#### 过渡过程 {#fcm-transition-steps}

要将环境移动到HTTP v1，请执行以下步骤：

1. 浏览至 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/push_technote_1.png)

1. 选择需要更新证书的特定移动应用程序。

1. 查看 **[!UICONTROL Update app credentials]** 复选框。

   ![](assets/push_technote_5.png)

1. 从您的Android项目的 `build.gradle` 文件。 例如， `com.android.test.testApp`. 请确保为暂存环境和生产环境使用不同的ID。

1. 上传Android私钥JSON密钥文件。

   ![](assets/push_technote_3.png)

1. 单击 **保存** 按钮。

>[!NOTE]
>
>应用这些更改后，所有交付到Android设备的新推送通知都将使用HTTP v1 API。 正在重试、进行中和正在使用的现有推送投放仍使用HTTP（旧版）API。


## Apple iOS推送通知服务(APN) {#apns-push-upgrade}

### 更改了哪些内容？ {#ios-changes}

按照Apple的建议，您应使用无状态身份验证令牌保护与Apple推送通知服务(APN)的通信。

基于令牌的身份验证提供了与APN进行通信的无状态方式。 无状态通信比基于证书的通信速度更快，因为它不要求APN查找与您的提供商服务器相关的证书或其他信息。 使用基于令牌的身份验证还有其他优势：

* 您可以使用来自多个提供程序服务器的相同令牌。

* 您可以使用一个令牌为您的公司的所有应用程序分发通知。

要了解有关到APN的基于令牌的连接，请参阅 [Apple开发人员文档](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

Adobe Campaign Standard支持基于令牌和基于证书的连接。 如果您的实施依赖于基于证书的连接，Adobe强烈建议您将其更新为基于令牌的连接。

### 您是否受影响？ {#ios-impact}

如果您当前的实施依赖于基于证书的请求来连接到APN，则您会受到影响。 建议转换为基于令牌的连接。

<!--To check if you are impacted, you can filter your **Services and Subscriptions** as per the filter below:

![](assets/filter-services-ios.png)


* If any of your active push notification service uses the **Certificate-based authentication** mode (.p12), your current implementations should be reviewed and moved to a **Token-based authentication** mode (.p8) as described below.

* If your setup exclusively uses the **Token-based authentication** mode for iOS push notifications, then your implementation is already up-to-date and no further action will be required on your part.-->

### 如何更新？ {#ios-transition-procedure}

#### 先决条件 {#ios-transition-prerequisites}

* 支持 **基于令牌的身份验证** 已添加模式 [24.1版本](../../rn/using/release-notes.md). 如果您的环境运行在旧版本上，则此更改的先决条件是将您的环境升级到 [最新Campaign Standard版本](../../rn/using/release-notes.md).

* 您需要APN身份验证令牌签名密钥来生成您的服务器使用的令牌。 您从Apple开发人员帐户请求此密钥，如中所述 [Apple开发人员文档](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.


#### 过渡过程 {#ios-transition-steps}

要将iOS移动应用程序移动到基于令牌的身份验证模式，请执行以下步骤：

1. 浏览至 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/push_technote_1.png)

1. 选择需要更新证书的特定移动应用程序。

1. 查看 **[!UICONTROL Update app credentials]** 复选框。

   ![](assets/push_technote_2.png)

1. 提供 **应用程序ID** (iOS捆绑包ID)。 您可以在Xcode中的应用程序主目标中找到iOS捆绑包ID（应用程序ID）。

1. 上传您的 **iOS p8证书文件**.

1. 填写APN连接设置 **[!UICONTROL Key Id]** 和 **[!UICONTROL iOS Team Id]**.

   ![](assets/push_technote_4.png)

1. 单击 **[!UICONTROL Save]**。

您的iOS应用程序现在已移至基于令牌的身份验证模式。

## 常见问题解答{#push-upgrade-faq}

+++我们能否在暂存和生产实例上保留相同的appID？

对于iOS移动应用程序，您可以在暂存环境和生产环境中使用相同的应用程序ID，即您的iOS应用程序捆绑包ID。 但是，在Android上，每个环境的应用程序ID应该是唯一的。 因此，我们建议将“暂存”附加到在暂存环境中创建的应用程序ID

+++


+++我们是否只能迁移Android应用程序？

不需要，需要按照上述步骤迁移Android和iOS应用程序。

+++

+++迁移后需要执行哪种类型的验证？

我们建议对所有与推送相关的用例进行功能验证。

+++

+++保存移动应用程序时出现“未授权”错误时该怎么办？

这似乎是一个与Adobe Experience Platform数据收集相关的权限问题。 要解决此问题，必须在Adobe Admin Console中添加“移动设备”和“移动设备应用程序配置”权限，如本文的“先决条件”部分中所述。

+++

+++是否需要更改移动设备应用程序代码？

不需要，只需在Firebase和应用程序开发人员帐户中进行与配置相关的更改。 不需要更改客户移动设备应用程序。

+++

+++我们是否需要每年更新iOS证书？

不会，此迁移后，无需每年更新iOS证书。

+++

+++如果未完成此迁移，会发生什么情况？

根据Google的通知，Android推送消息将在2024年6月20日之后开始失败。 [了解更多信息](https://firebase.google.com/docs/cloud-messaging/migrate-v1){target="_blank"}。

+++

+++客户在完成FCMv1迁移后是否可以迁移回FCM？

是，在2024年6月20日之前，客户将能够迁移回FCM。 在此日期之后，迁移选项将不再可用。

+++

+++SDK V4移动应用程序是否支持HTTP v1 API迁移？

不能，客户需要先将其移动设备应用程序迁移到V5 SDK，然后继续上述迁移。 他们需要优先做到这一点，因为根据Google的通知，他们的推送服务将从2024年6月开始失败。

+++

+++暂存实例上的更改是否会对生产实例产生任何影响？

不会，暂存移动应用程序中的任何更改不会影响生产实例。

+++