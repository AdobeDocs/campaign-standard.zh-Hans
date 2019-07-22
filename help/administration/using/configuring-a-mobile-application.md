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
source-git-commit: b9799c40bd7b6422409456db2c4f694f486b42f8

---


# Configuring a mobile application{#configuring-a-mobile-application}

首先需要在Adobe Mobile Services中根据您要使用的渠道配置的移动应用程序上收到推送通知或应用程序内消息。

* 要发送应用程序内消息和推送通知，需要利用Adobe Experience Platform SDK在Adobe Campaign中设置您的移动应用程序。See [Using Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk).

* 要仅发送推送通知，您可以使用SDK V配置Adobe Campaign和Adobe Mobile Service之间的集成。See [Using SDK V4](#using-sdk-v4).

After your mobile applications are set up in Adobe Campaign by leveraging the Experience Cloud Mobile SDK V4 or Experience Platform SDK, they need to be configured by an administrator under the [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] menu.

>[!CAUTION]
>
>推送通知和应用程序内实施必须由专家用户执行。如果需要协助，请与您的Adobe客户经理或专业服务合作伙伴联系。

## Using Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

要使用Experience Platform SDK应用程序发送推送通知和应用程序内消息，必须在Adobe Experience Platform Experience Platform Experience Platform Launch中设置移动应用程序并在Adobe Campaign中配置。For the detailed steps to configure your mobile application using Experience Platform SDK, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

请按照以下步骤启动配置：

1. Make sure you can access the **[!UICONTROL Mobile]** channels: Push notification and In-App message in Adobe Campaign. 如果没有，请联系您的帐户团队。

   ![](assets/launch_1.png)

1. 通过创建移动类型的属性，在Experience Platform Launch中创建移动应用程序。For more info, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) documentation.
1. Install the **[!UICONTROL Adobe Campaign (Beta)]** extension for your mobile application in Experience Platform Launch:

   For more information on extensions, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard-beta) documentation.

1. Configure rules for your application in Adobe Launch, see [Configuring your application in Launch](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ConfiguringyourapplicationinLaunch)
1. Configure your Adobe Launch application in Adobe Campaign Standard, see [Setting up your Adobe Launch application in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Add channel specific configuration to your Mobile Application set-up, see [Channel-specific application configuration in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)

## Using SDK V4 {#using-sdk-v4}

不同于应用程序，SDK V和Adobe Experience Platform SDK支持推送通知。For the detailed steps to use push notifications with your mobile app, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

接收推送通知的移动应用程序必须由Adobe Campaign界面中的管理员配置。通过配置Adobe Campaign和Adobe Mobile Services，您可以将移动应用程序的数据用于您的营销活动。

要发送推送通知，您需要：

1. Make sure you can access the **[!UICONTROL Mobile app]** channel in Adobe Campaign.
1. 在以下位置配置移动应用程序：

   * [Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign)。
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices)。

1. 执行移动应用程序的特定设置：

   * 使用移动应用程序打包从Adobe Mobile Services界面下载的配置文件。
   * 将Experience Cloud Mobile SDK集成到您的移动应用程序中。

1. 定义要从应用程序的订阅者收集的数据。根据您定义的标准协调在Adobe Campaign数据库中具有个人资料的移动应用程序的用户。

   For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication).

1. 通过在设备上启动手机应用程序并登录，确保设置已成功完成。确保您选择接收通知。
1. Then, in Adobe Campaign's advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. 从列表中选择移动应用程序以显示其属性。订阅信息显示在订户列表下。

   ![](assets/push_notif_mobile_app.png)

1. To check the mobile applications a profile has subscribed to, in the **[!UICONTROL Profiles & Audiences > Profiles]** menu, select a profile and click the **[!UICONTROL Edit profile properties]** button on the right. The mobile applications are listed in the **[!UICONTROL Mobile App Subscriptions]** tab.

   ![](assets/push_notif_subscriptions.png)