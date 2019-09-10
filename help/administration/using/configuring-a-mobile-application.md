---
title: 配置移动应用程序
seo-title: 配置移动应用程序
description: 配置移动应用程序
seo-description: 了解如何配置Adobe Campaign以使用SDK V或Experience Platform SDK发送推送通知或应用程序内消息。
page-status-flag: 从未激活
uuid: 63e1476a-7875-4f48-ba9 e-97f1 a0007 e42
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: 配置渠道
discoiquuid: 2a14500f-5ee-4131-8b1a-b7 fd65 b7 e aa
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 3b7da7df5092476be4c6acc21b2ad2472a80da83

---


# 配置移动应用程序{#configuring-a-mobile-application}

首先需要在Adobe Mobile Services中根据您要使用的渠道配置的移动应用程序上收到推送通知或应用程序内消息。

* 要发送应用程序内消息和推送通知，需要利用Adobe Experience Platform SDK在Adobe Campaign中设置您的移动应用程序。请参阅 [使用Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk)。

* 要仅发送推送通知，您可以使用SDK V配置Adobe Campaign和Adobe Mobile Service之间的集成。请参阅 [使用SDK V4](#using-sdk-v4)。

通过利用Experience Cloud Mobile SDK V或Experience Platform SDK在Adobe Campaign中设置移动应用程序后，管理员需要在 [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] 菜单下配置这些应用程序。

>[!CAUTION]
>
>推送通知和应用程序内实施必须由专家用户执行。如果需要协助，请与您的Adobe客户经理或专业服务合作伙伴联系。

设置移动应用程序后，您可以检索其收集的PII数据，以便从数据库中创建或更新配置文件。有关此操作的详细信息，请参阅本节： [基于移动应用程序数据创建和更新配置文件信息](../../channels/using/updating-profile-with-mobile-app-data.md)。

## 使用Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

>[!Nte]
>
>要通过Adobe Experience Platform SDK进一步了解Adobe Campaign Standard支持的不同移动使用案例，请参阅此 [页](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)。

要使用Experience Platform SDK应用程序发送推送通知和应用程序内消息，必须在Adobe Experience Platform Experience Platform Experience Platform Launch中设置移动应用程序并在Adobe Campaign中配置。有关使用Experience Platform SDK配置移动应用程序的详细步骤，请参阅此 [页](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

请按照以下步骤启动配置：

1. 确保您可以访问 **[!UICONTROL Mobile]** 渠道：Adobe Campaign中的推送通知和应用程序内消息。如果没有，请联系您的帐户团队。

   ![](assets/launch_1.png)

1. 通过创建移动类型的属性，在Experience Platform Launch中创建移动应用程序。有关更多信息，请参阅 [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) 文档。
1. 在Experience **[!UICONTROL Adobe Campaign Standard]** Platform Launch中安装移动应用程序的扩展：

   有关扩展的更多信息，请参阅 [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) 文档。

1. 在Adobe Launch中配置应用程序规则，请参阅 [在Launch中配置应用程序](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. 在Adobe Campaign Standard中配置Adobe Launch应用程序，参阅 [在Adobe Campaign中设置您的Adobe Launch应用程序](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign)。
1. 将特定于渠道的配置添加到手机应用程序设置中，参阅 [Adobe Campaign中的特定于渠道的应用程序配置](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign)。

   ![](assets/launch_2.png)

## 使用SDK V4 {#using-sdk-v4}

不同于应用程序，SDK V和Adobe Experience Platform SDK支持推送通知。有关将推送通知与移动应用程序结合使用的详细步骤，请参阅此 [页](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

接收推送通知的移动应用程序必须由Adobe Campaign界面中的管理员配置。通过配置Adobe Campaign和Adobe Mobile Services，您可以将移动应用程序的数据用于您的营销活动。

要发送推送通知，您需要：

1. 确保您可以在Adobe Campaign中访问 **[!UICONTROL Mobile app]** 渠道。
1. 在以下位置配置移动应用程序：

   * [Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign)。
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices)。

1. 执行移动应用程序的特定设置：

   * 使用移动应用程序打包从Adobe Mobile Services界面下载的配置文件。
   * 将Experience Cloud Mobile SDK集成到您的移动应用程序中。

1. 定义要从应用程序的订阅者收集的数据。根据您定义的标准协调在Adobe Campaign数据库中具有个人资料的移动应用程序的用户。

   有关此操作的详细信息，请参阅此 [页面](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication)。

1. 通过在设备上启动手机应用程序并登录，确保设置已成功完成。确保您选择接收通知。
1. 然后，在Adobe Campaign的高级菜单中，选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**。
1. 从列表中选择移动应用程序以显示其属性。订阅信息显示在订户列表下。

   ![](assets/push_notif_mobile_app.png)

1. 要检查已订阅的移动应用程序，请在 **[!UICONTROL Profiles & Audiences > Profiles]** 菜单中选择配置文件，然后单击右侧的 **[!UICONTROL Edit profile properties]** 按钮。移动应用程序列在 **[!UICONTROL Mobile App Subscriptions]** 选项卡中。

   ![](assets/push_notif_subscriptions.png)