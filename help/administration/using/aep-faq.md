---
title: Adobe Experience Platform SDK与Adobe Campaign集成常见问题解答
description: Adobe Experience Platform SDK与Adobe Campaign集成常见问题解答
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 4%

---

# Experience Platform SDK 集成常见问题解答 {#aep-faq}

要使用Experience PlatformSDK应用程序发送推送通知和应用程序内消息，必须在Adobe Experience Platform SDK中设置并在Adobe Campaign中配置移动应用程序。

以下部分列出了有关此同步的常见问题。

有关推送或应用程序内的更多信息，请参阅以下常见问题解答：

* [推送通知常见问题解答](../../channels/using/about-push-notifications.md#push-faq)
* [应用程序内常见问题解答](../../channels/using/in-app-faq.md)
* [与Launch同步技术工作流常见问题解答](../../administration/using/syncwithlaunch-faq.md)

## 开始前的有用资源 {#resource-mobile-property}

有关Adobe Experience Platform SDK和Campaign Standard集成的更多信息，请参阅以下资源：

* Launch/Mobile [概述视频](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Launch/Mobile [提示与技巧指南](https://www.adobe.com/content/dam/dx/us/en/products/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Adobe Experience Platform SDK集成是否适用于Adobe Campaign Standard和Adobe Campaign Classic? {#aep-validity}

是，[!DNL Adobe Experience Platform SDK]集成适用于Adobe Campaign Standard和Adobe Campaign Classic。 必须通过[!DNL Adobe Launch]安装相应的&#x200B;**[!UICONTROL Extension]**&#x200B;才能启用集成。

有关详细信息，请参见此 [ 页面](Https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。

## Adobe Experience Platform SDK集成在Adobe Campaign中可促进哪些功能？ {#aep-capabilities}

请参阅下表，了解有关这些功能的更多信息。

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] 集成包含places事件作为应用程序内消息的触发器（对于推送通知为不适用），通过数据和本地通知支持对用 [!DNL Places] 户档案进行扩充。有关更多信息，请参阅此[页面](../../channels/using/preparing-and-sending-an-in-app-message.md)。 <br>[!DNL Places] 有限的集成包括使用数据扩充用 [!DNL Places] 户档案。

## Adobe Experience Platform SDK集成在Adobe Campaign Standard中可促进哪些用例？ {#aep-use-cases}

支持以下用例：

* 在Campaign中获取&#x200B;**[!UICONTROL Mobile Profile]**（由&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]**&#x200B;选项卡中的ECID标识）
* 在Adobe Campaign中扩充&#x200B;**[!UICONTROL Mobile Profile]**（需要appSubscriberRcp表的&#x200B;**[!UICONTROL Custom resource Extension]**）
* 获取用于发送推送消息的推送令牌（需要用户选择加入才能接收推送消息）
* 发送推送消息和应用程序内消息
* 跟踪用户与推送消息和应用程序内消息的交互情况，并提供有关该情况的报表

## 要在Campaign中获取移动用户档案，我必须执行哪些操作？ {#mobile-profile-campaign}

要实现此目的，请执行以下步骤：

1. 在[!DNL Launch]中配置&#x200B;**[!UICONTROL Mobile property]**。
1. 安装Adobe Campaign Standard扩展。 请注意，Adobe Campaign Standard扩展还需要&#x200B;**[!UICONTROL Mobile Core]**、**[!UICONTROL Profile]**&#x200B;和&#x200B;**[!UICONTROL Lifecycle]**&#x200B;扩展，这些扩展默认情况下会安装在[!DNL Launch]中。
   * 用户应在&#x200B;**[!UICONTROL Mobile Core]**&#x200B;扩展中配置会话超时，这会影响生命周期事件的频率。
   * 配置扩展后，用户应使用适用于iOS的Cocoapods和适用于Android的Gradle在移动设备应用程序中添加相应的依赖项。 按照[此处](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)的说明操作。
   * 始终获取库的最新版本。
   * 在移动设备应用程序中，注册&#x200B;**[!UICONTROL Campaign]**、**[!UICONTROL UserProfile]**、**[!UICONTROL Identity]**、**[!UICONTROL Lifecycle]**&#x200B;和&#x200B;**[!UICONTROL Signal]**&#x200B;扩展。 按照[此处](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core)的说明操作。
   * 注册扩展后，启动ACPCore。 对于Android，请确保setApplication onCreate()。 按照Launch中移动资产的移动设备安装说明中提供的确切说明进行操作。
   * 还需要以下SDK API。 按照[此处](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)（适用于Android）和此处（适用于iOS）所述，实施生命周期开始和暂停API。
1. 在Adobe Campaign Standard中配置&#x200B;**[!UICONTROL Mobile Property]**。 按照[此处](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)的步骤操作。

## 要在Campaign中扩充移动用户档案，我必须执行哪些操作？ {#enrich-mobile-profile}

您必须配置CollectPII回发（请参阅此[page](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)）并从SDK实施CollectPII API（请参阅此[page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)）。

## CollectPII调用应该触发多久一次？ {#collect-pii}

CollectPII调用的目标是在Campaign中扩充移动用户档案。 当客户希望根据其用例和业务需求将有意义的新信息添加到用户档案时，应触发该事件。

## 是否可以为响应多个触发事件而触发CollectPII调用？ {#collect-pii-calls}

是的。 根据您的业务需要，您可以触发CollectPII调用以响应用户在应用程序中的登录，或者购买某些内容或生命周期事件或用户进入地理围栏等。 综上所述，用户与应用程序之间的交互，该交互会生成您希望用于扩充用户档案的信息。

## 我是否只能为响应所有移动设备事件而触发CollectPII调用？ {#collect-pii-events}

CollectPII调用的频率和设计应根据业务需求而定，且不应因为给数据库造成额外负载而盲目触发。

### 当我尝试在Campaign或Launch中访问Adobe Experience Platform应用程序时，有时会收到不可用的属性错误。 {#aep-error}

这是已知问题，由于令牌过期而发生。 您应尝试登录和登录。

## 要了解有关Adobe Experience Platform SDK（以前称为SDK V5）的更多信息，有哪些有用的资源建议？{#resource-aep}

请查看以下资源：

* Experience PlatformSDK [文档](Https://aep-sdks.gitbook.io/docs/)
* Launch和Experience PlatformSDK [快速入门文档](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* 升级到Experience PlatformSDK [文档](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* GithubExperience PlatformSDK [文档](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## 创建推送通知投放时，我收到错误“您在投放时没有写入权限”。 {#write-access-error}

您应检查以下内容：

* 移动设备应用程序应该映射到需要创建和发送推送投放的用户的组织单位。 子组织单位的用户无法使用映射到父组织单位的应用程序创建推送投放。

* 应将创建推送投放的营销策划或项目映射到需要创建和发送推送投放的用户组织单位。 子组织单位的用户无法在映射到父组织单位的营销策划或项目中创建推送投放。
