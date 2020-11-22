---
solution: Campaign Standard
product: campaign
title: Adobe Experience PlatformSDK与Adobe Campaign集成常见问题解答
description: Adobe Experience PlatformSDK与Adobe Campaign集成常见问题解答
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 3%

---


# Experience Platform SDK 集成常见问题解答 {#aep-faq}

要使用Experience PlatformSDK应用程序发送推送通知和应用程序内消息，必须在Adobe Experience PlatformSDK中设置移动应用程序并在Adobe Campaign中进行配置。

以下部分列表了有关此同步的常见问题。

有关推送或应用程序内的更多信息，请参阅以下常见问题解答：

* [推送通知常见问题解答](../../channels/using/about-push-notifications.md#push-faq)
* [应用程序内常见问题解答](../../channels/using/about-in-app-messaging.md#in-app-faq)
* [与Launch技术工作流程同步常见问题解答](../../administration/using/syncwithlaunch-faq.md)

## 开始前的有用资源 {#resource-mobile-property}

有关Adobe Experience PlatformSDK和Campaign Standard集成的更多信息，请查看以下资源：

* 启动／移动概 [述视频](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* 启动／移动 [提示与技巧指南](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Adobe Experience PlatformSDK集成是否可用于Adobe Campaign Standard和Adobe Campaign Classic? {#aep-validity}

是的 [!DNL Adobe Experience Platform SDK] ,Adobe Campaign Standard和Adobe Campaign Classic均可集成。 您需要通过安装相 **[!UICONTROL Extension]** 应的 [!DNL Adobe Launch] 方式来启用集成。

有关详细信息，请参见此 [ 页面](Https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。

## Adobe Experience PlatformSDK集成在Adobe Campaign方面有哪些功能？ {#aep-capabilities}

请参阅下表，进一步了解这些功能。

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] 集成包括将事件作为应用程序内消息的触发器（推送通知为N/A），通过数据和本地通知支持丰 [!DNL Places] 富用户档案。 Refer to this [page](../../channels/using/preparing-and-sending-an-in-app-message.md) for more information. <br>[!DNL Places] 有限集成包括用数据丰富 [!DNL Places] 用户档案。

## Adobe Experience PlatformSDK集成在Adobe Campaign Standard有哪些用例？ {#aep-use-cases}

支持以下用例：

* 获取 **[!UICONTROL Mobile Profile]** 活动(在> > >选项卡 **[!UICONTROL Administration]** 中由 **[!UICONTROL Channels]** ECID标 **[!UICONTROL Mobile app (AEP SDK)]** 识 **[!UICONTROL Mobile Application subscribers]** )
* 丰富 **[!UICONTROL Mobile Profile]** Adobe Campaign(需 **[!UICONTROL Custom resource Extension]** 要appSubscriberRcp表)
* 获取用于发送推送消息的推送令牌（需要用户选择加入以接收推送消息）
* 发送推送和应用程序内消息
* 跟踪用户与推送和应用程序内消息的交互情况，并提供有关此情况的报告

## 要获得活动的移动用户档案，我必须做什么？ {#mobile-profile-campaign}

要实现此目的，请执行以下步骤：

1. 在中配 **[!UICONTROL Mobile property]** 置 [!DNL Launch]。
1. 安装Adobe Campaign Standard扩展。 请注意，Adobe Campaign Standard扩展 **[!UICONTROL Mobile Core]**&#x200B;还 **[!UICONTROL Profile]** 需要 **[!UICONTROL Lifecycle]** 默认安装的扩展 [!DNL Launch]。
   * 用户应配置会话超时( **[!UICONTROL Mobile Core]** 扩展)，这会影响生命周期事件的频率。
   * 配置扩展后，用户应使用适用于iOS的Cocoapod和适用于Android的Gradle在移动应用程序中添加适当的依赖关系。 按照这里的 [指示](Https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。
   * 始终使用最新版本的库。
   * 在移动应用程序中，注 **[!UICONTROL Campaign]**&#x200B;册、 **[!UICONTROL UserProfile]**&#x200B;扩 **[!UICONTROL Identity]**&#x200B;展和 **[!UICONTROL Lifecycle]** 扩展 **[!UICONTROL Signal]** 功能。 按照这里的 [指示](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core)。
   * 注册扩展后，开始ACPCore。 对于Android，请确保设置Application onCreate()。 按照Launch中针对您的移动属性的移动安装说明中提供的确切说明进行操作。
   * 还需要以下SDK API。 按照此处为Android和iOS介绍 [的](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) ，实施生命周期开始和暂停API。
1. 在Adobe Campaign Standard **[!UICONTROL Mobile Property]** 配置。 按照此处的 [步骤](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

## 要丰富活动中的移动用户档案，我必须做什么？ {#enrich-mobile-profile}

您需要配置CollectPII回传(请参 [阅本页](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback))并从SDK实施CollectPII API(请参阅本 [页](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii))。

## CollectPII调用的发射频率是多少？ {#collect-pii}

CollectPII呼叫的目的是丰富活动中的移动用户档案。 当有新的有意义信息时，应根据用户档案的使用案例和业务需求将其添加到客户中时，会触发该信息。

## 是否可以响应多个触发事件来触发CollectPII调用？ {#collect-pii-calls}

是的。 根据您的业务需要，您可以根据用户登录应用程序或购买某些内容或生命周期事件或用户输入地理序列等来触发CollectPII调用。 总而言之，用户与应用程序的交互，它生成您要用于用户档案扩充的信息。

## 我是否可以响应所有移动事件而触发CollectPII呼叫？ {#collect-pii-events}

CollectPII调用的频率和设计应根据业务需求而定，不应因为给数据库造成额外负载而盲目触发。

### 当我尝试在活动或启动中访问Adobe Experience Platform应用程序时，有时会出现属性不可用错误。 {#aep-error}

这是已知问题，由于令牌过期而发生。 您应尝试登录。

## 要进一步了解Adobe Experience PlatformSDK（以前称为SDK V5），有哪些有用的资源建议？{#resource-aep}

查看以下资源：

* Experience PlatformSDK文 [档](https://aep-sdks.gitbook.io/docs/)
* Launch &amp;Experience PlatformSDK文档入 [门](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* 升级到Experience PlatformSDK文 [档](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* GithubExperience PlatformSDK文 [档](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## 在创建推送通知投放时，我收到错误“您没有对投放的写入权限”。 {#write-access-error}

您应检查以下内容：

* 移动应用程序应映射到需要创建和发送推送投放的用户的组织单位。 子组织单元的用户无法使用映射到父组织单元的应用程序创建推送投放。

* 创建推送投放的活动或项目应映射到需要创建和发送推送投放的用户的组织单位。 子组织单元的用户不能在映射到父组织单元的活动或项目中创建推送投放。