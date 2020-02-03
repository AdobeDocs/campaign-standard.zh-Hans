---
title: 配置移动应用程序
description: 了解如何配置Adobe Campaign以使用SDK V4或Experience Platform SDK发送推送通知或应用程序内消息。
page-status-flag: never-activated
uuid: 63e1476a-7875-4f48-ba9e-97f1a0007e42
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 2a14500f-5ede-4131-8b1a-b7fd65b7e3aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aa1539a1fc5fd08e7cf4e081ae2517e39ddde121

---


# 配置移动应用程序{#configuring-a-mobile-application}

推送通知或应用程序内消息会在移动应用程序上接收，这些应用程序首先需要在Adobe Campaign standard中配置，具体取决于您要使用的渠道。

要发送应用程序内消息和推送通知，您的移动应用程序需要通过利用Adobe Experience Platform SDK在Adobe Campaign中设置。 请参 [阅使用Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk)。

在Adobe Campaign中通过利用Experience Cloud Mobile SDK V4或Experience Platform SDK设置移动应用程序后，需要由管理员在 [!UICONTROL Administration] > [!UICONTROL Channels] >菜单下配置这些应 [!UICONTROL Mobile app] 用程序。

>[!CAUTION]
>
>推送通知和应用程序内实施必须由专家用户执行。 如果需要协助，请与您的Adobe客户主管或专业服务合作伙伴联系。

设置手机应用程序后，您可以检索其收集的PII数据，以便从数据库创建或更新配置文件。 有关此内容的详细信息，请参阅此部分：根 [据移动应用程序数据创建和更新配置文件信息](../../channels/using/updating-profile-with-mobile-app-data.md)。

有关Adobe Campaign standard中移动交付的一般准则，请参阅本 [页](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## 使用Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

>[!Note]
>
>要通过使用Adobe Experience Platform SDK进一步了解Adobe Campaign Standard中支持的不同移动使用案例，请参阅本 [页](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)。

要使用Experience Platform SDK应用程序发送推送通知和应用程序内消息，必须在Adobe Experience Platform Experience Platform Launch中设置移动应用程序，并在Adobe Campaign中进行配置。 有关使用Experience Platform SDK配置移动应用程序的详细步骤，请参阅本 [页](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

请按照以下步骤启动配置：

1. 确保您可以访问渠 **[!UICONTROL Mobile]**道：Adobe Campaign中的推送通知和应用程序内消息。 如果没有，请与您的客户团队联系。

   ![](assets/launch_1.png)

1. 在Experience Platform Launch中通过创建移动类型的属性创建移动应用程序。 有关详细信息，请参阅 [Experience Platform Launch文档](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) 。
1. 在Experience Platform **[!UICONTROL Adobe Campaign Standard]**Launch中为移动应用程序安装扩展：

   有关扩展的详细信息，请参阅 [Experience Platform Launch文档](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) 。

1. 在Adobe Launch中配置应用程序规则，请参阅在 [Launch中配置应用程序](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. 在Adobe Campaign standard中配置Adobe Launch应用程序，请参阅 [在Adobe Campaign中设置Adobe Launch应用程序](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign)。
1. 将特定于渠道的配置添加到您的移动应用程序设置中，请参 [阅Adobe Campaign中特定于渠道的应用程序配置](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign)。

   ![](assets/launch_2.png)
