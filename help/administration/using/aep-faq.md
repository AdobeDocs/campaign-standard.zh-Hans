---
title: Adobe Experience PlatformSDK和Adobe Campaign集成常见问题解答
description: Adobe Experience PlatformSDK和Adobe Campaign集成常见问题解答
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d0a0c59763af8babc9701206cc39fe41b98e0cd4
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---


# Adobe Experience PlatformSDK和Adobe Campaign集成常见问题解答 {#aep-faq}

## Adobe Experience PlatformSDK集成是否可用于Adobe Campaign Standard和Adobe Campaign经典？ {#aep-validity}

是的， [!DNL Adobe Experience Platform SDK] 集成适用于Adobe Campaign Standard和Adobe Campaign经典。 您需要通过安装相 **[!UICONTROL Extension]** 应的 [!DNL Adobe Launch] 方式来启用集成。

有关此内容的详细信息，请参 [阅本页](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic) ,Campaign Classic [请参阅](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) 本页。

## Adobe Experience PlatformSDK集成在Adobe Campaign方面有哪些功能？ {#aep-capabilities}

请参阅下表，进一步了解这些功能。

![](assets/faq.png)

>[!Note]
>
>[!DNL Places] 集成包括将事件作为应用程序内消息的触发器（推送通知为N/A），通过数据和本地通知支持丰 [!DNL Places] 富用户档案。 Refer to this [page](../../channels/using/preparing-and-sending-an-in-app-message.md) for more information. <br>[!DNL Places] 有限集成包括用数据丰富 [!DNL Places] 用户档案。

## Adobe Experience PlatformSDK集成在Adobe Campaign Standard下有哪些用例？ {#aep-use-cases}

支持以下用例：

* 获取 **[!UICONTROL Mobile Profile]** 活动(在> > >选项卡 **[!UICONTROL Administration]** 中由 **[!UICONTROL Channels]** ECID标 **[!UICONTROL Mobile app (AEP SDK)]** 识 **[!UICONTROL Mobile Application subscribers]** )
* 丰富 **[!UICONTROL Mobile Profile]** Adobe Campaign(需 **[!UICONTROL Custom resource Extension]** 要appSubscriberRcp表)
* 获取用于发送推送消息的推送令牌（需要用户选择加入以接收推送消息）
* 发送推送和应用程序内消息
* 跟踪用户与推送和应用程序内消息的交互情况，并提供有关此情况的报告

## 要获得活动的移动用户档案，我必须做什么？ {#mobile-profile-campaign}

为此，请按照以下步骤操作：

1. 在中配 **[!UICONTROL Mobile property]** 置 [!DNL Launch]。
1. 安装Adobe Campaign Standard扩展。 请注意，Adobe Campaign Standard扩展还 **[!UICONTROL Mobile Core]**&#x200B;需要 **[!UICONTROL Profile]** 安装 **[!UICONTROL Lifecycle]** 的扩展，默认安装在中 [!DNL Launch]。
   * 用户应配置会话超时( **[!UICONTROL Mobile Core]** 扩展)，这会影响生命周期事件的频率。
   * 配置扩展后，用户应使用适用于iOS的Cocoapod和适用于Android的Gradle在移动应用程序中添加适当的依赖关系。 按照这里的 [指示](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。
   * 始终使用最新版本的库。
   * 在移动应用程序中，注 **[!UICONTROL Campaign]**&#x200B;册、 **[!UICONTROL UserProfile]**&#x200B;扩 **[!UICONTROL Identity]**&#x200B;展和 **[!UICONTROL Lifecycle]** 扩展 **[!UICONTROL Signal]** 功能。 按照这里的 [指示](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core)。
   * 注册扩展后，开始ACPCore。 对于Android，请确保设置Application onCreate()。 按照Launch中针对您的移动属性的移动安装说明中提供的确切说明进行操作。
   * 还需要以下SDK API。 按照此处为Android和iOS介绍 [的](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) ，实施生命周期开始和暂停API。
1. 在Adobe Campaign Standard **[!UICONTROL Mobile Property]** 中配置。 按照此处的 [步骤](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

## 要丰富活动中的移动用户档案，我必须做什么？ {#enrich-mobile-profile}

您需要配置CollectPII回传(请参 [阅本页](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback))并从SDK实施CollectPII API(请参阅本 [页](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii))。

## CollectPII调用的发射频率是多少？ {#collect-pii}

CollectPII呼叫的目的是丰富活动中的移动用户档案。 当有新的有意义信息时，应根据用户档案的使用案例和业务需要将其添加到客户中时，会触发该信息。

## 是否可以响应多个触发事件来触发CollectPII调用？ {#collect-pii-calls}

是的。 根据您的业务需要，您可以根据用户登录应用程序或购买某些内容或生命周期事件或用户输入地理序列等来触发CollectPII调用。 总而言之，用户与应用程序的交互，它生成您要用于用户档案扩充的信息。

## 我是否可以响应所有移动事件而触发CollectPII呼叫？ {#collect-pii-events}

CollectPII调用的频率和设计应根据业务需求而定，不应因为给数据库造成额外负载而盲目触发。

### 当我尝试在活动或启动中访问Adobe Experience Platform应用程序时，有时会收到一个属性不可用的错误。 {#aep-error}

这是已知问题，由于令牌过期而发生。 您应尝试登录。

## 一些有用的资源建议是什么，以进一步了解在Adobe Experience Platform启动中设置的移动属性？ {#resource-mobile-property}

查看以下资源：

* 启动／移动概 [述视频](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* 启动／移动 [提示与技巧指南](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## 要进一步了解Adobe Experience PlatformSDK（以前称为SDK V5），有哪些有用的资源建议？{#resource-aep}

查看以下资源：

* Experience PlatformSDK文 [档](https://aep-sdks.gitbook.io/docs/)
* Launch &amp;Experience PlatformSDK文档入 [门](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* 升级到Experience PlatformSDK文 [档](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* GithubExperience PlatformSDK文 [档](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)
