---
title: Adobe Experience Platform SDK与Adobe Campaign集成常见问题解答
description: Adobe Experience Platform SDK与Adobe Campaign集成常见问题解答
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 2%

---

# Experience Platform SDK 集成常见问题解答 {#aep-faq}

要使用Experience PlatformSDK应用程序发送推送通知和应用程序内消息，必须在Adobe Experience Platform SDK中设置移动应用程序，并在Adobe Campaign中进行配置。

以下部分列出了有关此同步的常见问题。

有关推送或应用程序内消息的详细信息，请参阅以下常见问题解答：

* [推送通知常见问题解答](../../channels/using/about-push-notifications.md#push-faq)
* [应用程序内常见问题解答](../../channels/using/in-app-faq.md)
* [Adobe Experience Platform 同步中的标记常见问题解答](../../administration/using/syncwithlaunch-faq.md)

## 开始前有用的资源 {#resource-mobile-property}

查看以下资源，以了解有关Adobe Experience Platform SDK和Campaign Standard集成的更多信息：

* 启动/移动 [概述视频](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* 启动/移动 [提示和技巧指南](https://www.adobe.com/content/dam/dx/us/en/products/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Adobe Experience Platform SDK集成是否同时适用于Adobe Campaign Standard和Adobe Campaign Classic？ {#aep-validity}

是， [!DNL Adobe Experience Platform SDK] 集成可用于Adobe Campaign Standard和Adobe Campaign Classic。 您必须安装相应的 **[!UICONTROL Extension]** 通过 [!DNL Data Collection UI] 以启用集成。

有关详细信息，请参阅此 [页面]https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard)。

## Adobe Experience Platform SDK集成有助于在Adobe Campaign中实现哪些功能？ {#aep-capabilities}

请参阅下表了解有关这些功能的更多信息。

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] 集成包括将places事件作为应用程序内消息的触发器（推送通知不适用），以及通过丰富用户档案 [!DNL Places] 数据和本地通知支持。 请参阅此 [页面](../../channels/using/preparing-and-sending-an-in-app-message.md) 以了解更多信息。 <br>[!DNL Places] 有限的集成包括通过扩充用户档案 [!DNL Places] 数据。

## Adobe Experience Platform SDK集成在Adobe Campaign Standard中促进什么用例？ {#aep-use-cases}

支持以下用例：

* 获取 **[!UICONTROL Mobile Profile]** 在Campaign中（由ECID标识） **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** tab)
* 扩充 **[!UICONTROL Mobile Profile]** 在Adobe Campaign中(需要 **[!UICONTROL Custom resource Extension]** （属于appSubscriberRcp表）
* 获取用于发送推送消息的推送令牌（需要用户选择加入以接收推送消息）
* 发送推送和应用程序内消息
* 跟踪用户与推送消息和应用程序内消息的交互并提供相关报表

## 要在Campaign中获取移动用户档案需做什么？ {#mobile-profile-campaign}

要实现此目的，请执行以下步骤：

1. 配置 **[!UICONTROL Mobile property]** 在 [!DNL Launch].
1. 安装Adobe Campaign Standard扩展。 请注意，Adobe Campaign Standard扩展还需要 **[!UICONTROL Mobile Core]**， **[!UICONTROL Profile]** 和 **[!UICONTROL Lifecycle]** 默认安装在中的扩展 [!DNL Launch].
   * 用户应在中配置会话超时 **[!UICONTROL Mobile Core]** 影响生命周期事件频率的扩展。
   * 配置扩展后，用户应使用Cocoapods for iOS和Gradle for Android在移动设备应用程序中添加适当的依赖项。 按照说明操作 [此处](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard).
   * 始终采用最新版本的库。
   * 在移动应用程序中，注册 **[!UICONTROL Campaign]**， **[!UICONTROL UserProfile]**， **[!UICONTROL Identity]**， **[!UICONTROL Lifecycle]** 和 **[!UICONTROL Signal]** 扩展。 按照说明操作 [此处](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#register-the-campaign-standard-extension-with-mobile-core).
   * 注册扩展后，请启动ACPCore。 对于Android，请务必设置Application onCreate()。 按照Launch中适用于您的移动资产的移动安装说明中提供的确切说明进行操作。
   * 还需要以下SDK API。 实施生命周期开始和暂停API，如所述 [此处](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android) 适用于Android的，以及此处适用于iOS的。
1. 配置 **[!UICONTROL Mobile Property]** 在Adobe Campaign Standard中。 请按照以下步骤操作 [此处](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## 要在Campaign中扩充移动用户档案需做什么？ {#enrich-mobile-profile}

您必须配置CollectPII回发(请参阅此 [页面](../../administration/using/configuring-rules-launch.md#pii-postback))并从SDK实施CollectPII API(请参阅此 [页面](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference))。

## 应多久触发CollectPII调用一次？ {#collect-pii}

CollectPII调用的目标是丰富Campaign中的移动用户档案。 每当有新的有意义的信息客户希望根据他们的用例和业务需求添加到用户档案时，都应触发该事件。

## 能否触发CollectPII调用以响应多个触发器事件？ {#collect-pii-calls}

是. 根据您的业务需求，您可以触发CollectPII调用以响应用户登录应用程序、购买某些内容或生命周期事件或用户进入地理围栏等。 总之，用户与应用程序之间的交互，该交互会生成要用于配置文件扩充的信息。

## 我是否可以只触发CollectPII调用以响应所有Mobile事件？ {#collect-pii-events}

CollectPII调用的频率和设计应该由业务需求决定，并且不应盲目触发，因为这会给数据库带来额外负载。

### 当我尝试在Campaign或Launch中访问Adobe Experience Platform应用程序时，有时会收到不可用属性错误。 {#aep-error}

这是一个已知问题，并且由于令牌过期而发生。 您应该尝试注销并登录。

## 要了解有关Adobe Experience Platform SDK（以前称为SDK V5）的更多信息，有哪些有用的资源建议？{#resource-aep}

查看以下资源：

* EXPERIENCE PLATFORMSDK [文档](https://developer.adobe.com/client-sdks/documentation/)
* Launch和Experience PlatformSDK快速入门 [文档](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/)
* 升级到Experience PlatformSDK [文档](https://developer.adobe.com/client-sdks/documentation/upgrade-platform-sdks)
* GithubExperience PlatformSDK [文档](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## 我在创建推送通知投放时收到错误“您没有投放写入权限”。 {#write-access-error}

您应该检查以下各项：

* 应将移动设备应用程序映射到需要创建和发送推送投放的用户的组织单位。 子组织单位的用户无法使用映射到父组织单位的应用程序创建推送投放。

* 在其中创建推送投放的活动或项目应映射到需要创建和发送推送投放的用户的组织单位。 子组织单位的用户无法在映射到父组织单位的活动或项目中创建推送投放。
