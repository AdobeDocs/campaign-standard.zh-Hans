---
title: Adobe Experience Platform SDK与Adobe Campaign集成常见问题解答
description: Adobe Experience Platform SDK与Adobe Campaign集成常见问题解答
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 4%

---

# Experience Platform SDK 集成常见问题解答 {#aep-faq}

要使用Experience PlatformSDK应用程序发送推送通知和应用程序内消息，必须在Adobe Experience Platform SDK中设置并在Adobe Campaign中配置移动应用程序。

以下部分列出了有关此同步的常见问题。

有关推送或应用程序内的更多信息，请参阅以下常见问题解答：

* [推送通知常见问题解答](../../channels/using/about-push-notifications.md#push-faq)
* [应用程序内常见问题解答](../../channels/using/in-app-faq.md)
* [Adobe Experience Platform同步中的标记常见问题解答](../../administration/using/syncwithlaunch-faq.md)

## 开始前的有用资源 {#resource-mobile-property}

有关Adobe Experience Platform SDK和Campaign Standard集成的更多信息，请参阅以下资源：

* Launch/Mobile [概述视频](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Launch/Mobile [提示和技巧指南](https://www.adobe.com/content/dam/dx/us/en/products/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Adobe Experience Platform SDK集成是否适用于Adobe Campaign Standard和Adobe Campaign Classic? {#aep-validity}

是的， [!DNL Adobe Experience Platform SDK] 集成适用于Adobe Campaign Standard和Adobe Campaign Classic。 您必须安装相应的 **[!UICONTROL Extension]** 通过 [!DNL Data Collection UI] 以启用集成。

有关详细信息，请参见此 [ 页面](Https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。

## Adobe Experience Platform SDK集成在Adobe Campaign中可促进哪些功能？ {#aep-capabilities}

请参阅下表，了解有关这些功能的更多信息。

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] 集成包含作为应用程序内消息触发器的places事件（对于推送通知不适用），通过丰富用户档案 [!DNL Places] 数据和本地通知支持。 请参阅 [页面](../../channels/using/preparing-and-sending-an-in-app-message.md) 以了解更多信息。 <br>[!DNL Places] 有限集成包括通过 [!DNL Places] 数据。

## Adobe Experience Platform SDK集成在Adobe Campaign Standard中可促进哪些用例？ {#aep-use-cases}

支持以下用例：

* 获取 **[!UICONTROL Mobile Profile]** (由 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** 选项卡)
* 丰富 **[!UICONTROL Mobile Profile]** 在Adobe Campaign( **[!UICONTROL Custom resource Extension]** appSubscriberRcp表)
* 获取用于发送推送消息的推送令牌（需要用户选择加入才能接收推送消息）
* 发送推送消息和应用程序内消息
* 跟踪用户与推送消息和应用程序内消息的交互情况，并提供有关该情况的报表

## 要在Campaign中获取移动用户档案，我必须执行哪些操作？ {#mobile-profile-campaign}

要实现此目的，请执行以下步骤：

1. 配置 **[!UICONTROL Mobile property]** in [!DNL Launch].
1. 安装Adobe Campaign Standard扩展。 请注意，Adobe Campaign Standard扩展还需要 **[!UICONTROL Mobile Core]**, **[!UICONTROL Profile]** 和 **[!UICONTROL Lifecycle]** 默认安装在 [!DNL Launch].
   * 用户应在 **[!UICONTROL Mobile Core]** 会影响生命周期事件频率的扩展。
   * 配置扩展后，用户应使用Cocoapods for iOS和Gradle for Android在移动设备应用程序中添加相应的依赖项。 按照指示 [此处](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).
   * 始终获取库的最新版本。
   * 在移动设备应用程序中，注册 **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]**, **[!UICONTROL Lifecycle]** 和 **[!UICONTROL Signal]** 扩展。 按照指示 [此处](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core).
   * 注册扩展后，启动ACPCore。 对于Android，请确保setApplication onCreate()。 按照Launch中移动资产的移动设备安装说明中提供的确切说明进行操作。
   * 还需要以下SDK API。 实施生命周期开始和暂停API，如所述 [此处](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) 在Android中，在iOS中。
1. 配置 **[!UICONTROL Mobile Property]** 在Adobe Campaign Standard。 按照程序操作 [此处](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## 要在Campaign中扩充移动用户档案，我必须执行哪些操作？ {#enrich-mobile-profile}

必须配置CollectPII回发(请参阅 [页面](../../administration/using/configuring-rules-launch.md#pii-postback))并从SDK实施COLLECTPII API(请参阅 [页面](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii))。

## CollectPII调用应该触发多久一次？ {#collect-pii}

CollectPII调用的目标是在Campaign中扩充移动用户档案。 当客户希望根据其用例和业务需求将有意义的新信息添加到用户档案时，应触发该事件。

## 是否可以为响应多个触发事件而触发CollectPII调用？ {#collect-pii-calls}

是. 根据您的业务需要，您可以触发CollectPII调用以响应用户在应用程序中的登录，或者购买某些内容或生命周期事件或用户进入地理围栏等。 综上所述，用户与应用程序之间的交互，该交互会生成您希望用于扩充用户档案的信息。

## 我是否只能为响应所有移动设备事件而触发CollectPII调用？ {#collect-pii-events}

CollectPII调用的频率和设计应根据业务需求而定，且不应因为给数据库造成额外负载而盲目触发。

### 当我尝试在Campaign或Launch中访问Adobe Experience Platform应用程序时，有时会收到不可用的属性错误。 {#aep-error}

这是已知问题，由于令牌过期而发生。 您应尝试登录和登录。

## 要了解有关Adobe Experience Platform SDK（以前称为SDK V5）的更多信息，有哪些有用的资源建议？{#resource-aep}

请查看以下资源：

* Experience PlatformSDK [文档](Https://aep-sdks.gitbook.io/docs/)
* Launch和Experience PlatformSDK快速入门 [文档](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* 升级到Experience PlatformSDK [文档](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* GithubExperience PlatformSDK [文档](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## 创建推送通知投放时，我收到错误“您在投放时没有写入权限”。 {#write-access-error}

您应检查以下内容：

* 移动设备应用程序应该映射到需要创建和发送推送投放的用户的组织单位。 子组织单位的用户无法使用映射到父组织单位的应用程序创建推送投放。

* 应将创建推送投放的营销策划或项目映射到需要创建和发送推送投放的用户组织单位。 子组织单位的用户无法在映射到父组织单位的营销策划或项目中创建推送投放。
