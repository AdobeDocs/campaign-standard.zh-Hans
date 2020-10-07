---
title: 配置 Campaign-兴趣点数据集成
description: 了解如何在Adobe Campaign中配置兴趣点数据功能，以根据用户的位置发送个性化消息。
page-status-flag: never-activated
uuid: 0689a06c-cc1a-442f-95b8-a07fcec85d79
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: a967c6cc-c53b-41b4-866b-90860d78f463
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 3%

---


# 配置 Campaign-兴趣点数据集成{#configuring-campaign-points-of-interest-data-integration}

## 配置与Adobe Experience PlatformSDK的活动点数据集成 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>您的移动应用程序应已在Adobe Campaign Standard使用Adobe Experience PlatformSDK进行配置。 For the detailed steps, refer to this [page](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html).

用于收集位置数据的移动应用程序必须由Adobe Campaign **界面中** 的管理员进行配置。

要能够将Adobe Experience Platform位置服务与配置有Adobe Experience PlatformSDK的移动应用程序一起使用，您需要：

1. 将和扩 **[!UICONTROL Places]** 展添 **[!UICONTROL Places Monitor]** 加到您在Adobe Experience Platform Launch的移动应用程序配置。 在Adobe Campaign中设置移动应用程序。 请参 [阅在Adobe Experience Platform Launch安装Places扩展](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch)[和在Experience Platform Launch中安装Places Monitor扩展](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch)。

1. 设置扩展后，在中创建数据元素， **[!UICONTROL Adobe Experience Platform Launch]** 从这些扩展中检索数据。 请参阅本 [页](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) ，创建数据元素。

1. 然后，您需 **[!UICONTROL Adobe Experience Platform Launch]**&#x200B;要创建规则，以支持兴趣点和Adobe Campaign之间的移动使用案例。\
   当用户进入围栏时将触发此规则 **[!UICONTROL Point of Interest]**。 请参阅本 [页](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) ，以创建规则。

1. 在地点 **[!UICONTROL Points of Interest]** 中定义您。 请 [参阅创建兴趣点](https://docs.adobe.com/content/help/en/places/using/poi-mgmt-ui/create-a-poi-ui.html)。

1. 确保在Adobe Campaign中访问移动应用程序和收集的位置数据。 请参 [阅访问用于收集位置数据的移动应用程序](#accessing-mobile-apps-used-to-collect-location-data) , [以及访问收集的位置数据](#accessing-collected-location-data)。

## 使用SDK V4配置活动点数据集成 {#configuring-campaign-poi-sdkv4}

用于收集位置数据的移动应用程序必须由Adobe Campaign **界面中** 的管理员进行配置。

要将兴趣点数据功能用于配置了SDK V4的移动应用程序，您需要：

1. 可访问Adobe Analytics移动版。 有关详细信息，请查阅您的许可协议或与Adobe帐户主管联系。
1. 在Adobe Campaign中设置移动应用程序。 请参 [阅在活动中设置移动应用程序](#setting-up-a-mobile-app-in-campaign)。
1. 在AdobeMobile Services界面中设置您的移动应用程序。 这使您能够确保由AdobeMobile Services收集的数据被发送到Adobe Campaign。 请参 [阅在AdobeMobile Services中配置移动应用程序](#configuring-a-mobile-app-in-adobe-mobile-services)。
1. 执行手机应用程序的特定设置：

   * 将从AdobeMobile Services界面下载的配置文件与移动应用程序打包。
   * 将Experience CloudMobile SDK集成到您的移动应用程序中。 请参 [阅将SDK集成到移动应用程序](#integrating-the-sdk-into-a-mobile-application)。

1. 在AdobeMobile Services界面中定义兴趣点。 请参 [阅定义AdobeMobile Services中的兴趣点](#defining-points-of-interest-in-adobe-mobile-services)。
1. 定义要从移动应用程序的订户收集的数据。 请参 [阅收集用户兴趣点数据](#collecting-subscribers--points-of-interest-data)。
1. 确保在Adobe Campaign中访问移动应用程序和收集的位置数据。 请参 [阅访问用于收集位置数据的移动应用程序](#accessing-mobile-apps-used-to-collect-location-data) , [以及访问收集的位置数据](#accessing-collected-location-data)。

### 使用SDK V4在Adobe Campaign中设置移动应用程序 {#setting-up-a-mobile-app-in-campaign}

要能够通过Adobe Campaign收集兴趣点数据，您必须配置移动应用程序，Adobe Campaign将从其接收数据。

1. 单击左上角的 **[!UICONTROL Adobe Campaign]** 徽标，然后选择 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**。
1. 单击 **[!UICONTROL Create]** 以设置应用程序。
1. 在字段中输入名 **[!UICONTROL Application name]** 称，然后单击 **[!UICONTROL Create]**。

   不要填写该 **[!UICONTROL Device-specific settings]** 部分。 这仅适用于配置接收推送通知的应用程序。

在部 **[!UICONTROL Mobile application properties]** 分中，列出了两个URL: **[!UICONTROL Collect PII endpoint]** 和 **[!UICONTROL Location Services endpoint]**。 它们将用于AdobeMobile Services界面。 请参 [阅在AdobeMobile Services中配置移动应用程序](#configuring-a-mobile-app-in-adobe-mobile-services)。

* URL **[!UICONTROL Collect PII endpoint]** 用于在移动应用程序启动时从其收集用户的Experience CloudID和注册令牌。 当用户使用诸如电子邮件、名字、姓氏等凭据登录应用程序时，也会收集这些数据并用于协调用户的注册令牌与Adobe Campaign用户档案。
* 该 **[!UICONTROL Location Services endpoint]** URL用于从目标点收集位置数据，如用户的纬度、经度和半径。

您现在可以在AdobeMobile Services中使用这些值来完成配置，如在AdobeMobile Services中 [配置移动应用程序一节中所述](#configuring-a-mobile-app-in-adobe-mobile-services) 。

![](assets/poi_mobile_app_properties.png)

### 在AdobeMobile Services中配置V4移动应用程序 {#configuring-a-mobile-app-in-adobe-mobile-services}

要将AdobeMobile Services收集的数据发送给Adobe Campaign，必须在Mobile Services界面中配置回传。

您需要在Adobe Campaign中设置的移动应用程序参数中找到特定信息(请参 [阅在活动中设置移动应用程序](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

您必须具有访问Adobe Analytics的权限才能进行以下配置。 如果您不是Adobe Analytics用户，请与Adobe Campaign管理员联系。

1. 登录 [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/)。
1. 创建应用程序或选择现有应用程序。
1. Go to the **[!UICONTROL Manage App Settings]** page.
1. 在“ **访客ID服务** ”部分，选 **中“启用** ”并从下拉列表中选择您的组织。 单击&#x200B;**保存**。

   >[!CAUTION]
   >
   >此组织必须与您在Adobe Campaign实例上使用的组织相同。

1. 单击 **[!UICONTROL Manage Postbacks]**.
1. 创建回发。

   * 选择 **[!UICONTROL PII]** 作为 **[!UICONTROL Postback Type]**。
   * 在该字 **[!UICONTROL URL]** 段中，从您在Adobe Campaign **[!UICONTROL Collect PII Endpoint]** 界面中配置的移动应用程序复制URL，前面是服务器名称。 请参 [阅在活动中设置移动应用程序](#setting-up-a-mobile-app-in-campaign)。
   * 按如下方 **[!UICONTROL Post Body]** 式填写字段：

      对于iOS:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"apns",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

      对于Android:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"gcm",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

   * 将内 **容类型设** 置为 **[!UICONTROL application/json]**。
   * 在哪些 **数据标记中触发回传？**，选择任何事件，通常 **[!UICONTROL Launched]** 为和 **[!UICONTROL exists]**。
   * 单击 **[!UICONTROL Save & Activate]**.

1. 创建第二个回传。

   * 选择 **[!UICONTROL Postback]** 作为 **[!UICONTROL Postback Type]**。
   * 在该字 **[!UICONTROL URL]** 段中，从您在Adobe Campaign **[!UICONTROL Location Services Endpoint]** 界面中配置的移动应用程序复制URL，前面是服务器名称。 请参 [阅在活动中设置移动应用程序](#setting-up-a-mobile-app-in-campaign)。
   * 按如下方 **[!UICONTROL Post Body]** 式填写字段：

      ```
      {
      "locationData":{
      "distances":"{a.loc.dist}",
      "poiLabel":"{a.loc.poi}",
      "latitude.a":"{a.loc.lat.a}",
      "latitude.b":"{a.loc.lat.b}",
      "latitude.c":"{a.loc.lat.c}",
      "longitude.a":"{a.loc.lon.a}",
      "longitude.b":"{a.loc.lon.b}",
      "longitude.c":"{a.loc.lon.c}",
      "appId":"{a.appid}",
      "marketingCloudId":"{mid}"
      }
      }
      ```

   * 将内 **容类型设** 置为 **[!UICONTROL application/json]**。
   * 在哪些 **数据标记中触发回传？**, select **[!UICONTROL campaign.test]** and **[!UICONTROL exists]**.
   * 单击 **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>有关配置回发的详细信息，请参阅 [AdobeMobile Services文档](https://docs.adobe.com/content/help/en/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html)。

### 将SDK集成到移动应用程序 {#integrating-the-sdk-into-a-mobile-application}

移动核心服务的软件开发工具包(SDK)简化了移动应用程序与Adobe Campaign的集成。

本页介绍了此 [步骤](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdkv4.html)。

### 定义Adobe移动服务中的兴趣点 {#defining-points-of-interest-in-adobe-mobile-services}

要定义用于收集位置数据的兴趣点，请执行以下操作：

1. 转到AdobeMobile Services界面。
1. 添加应用程序。

   有关在Mobile Services中管理应用程序的详细信息，请参阅 [AdobeMobile Services文档](https://docs.adobe.com/content/help/en/mobile-services/using/manage-apps-ug/t-new-app.html)。

1. 定义兴趣点。

   有关管理兴趣点的更多信息，请参阅 [AdobeMobile Services文档](https://docs.adobe.com/content/help/en/mobile-services/using/location-ug/t-manage-points.html)。

### 收集用户兴趣点数据 {#collecting-subscribers--points-of-interest-data}

特定的自定义资源允许您定义要从应用程序的订阅者收集的数据。

使用SDK V4配置移 [动应用程序页面中介绍了此](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdkv4.html) 步骤。


## 访问用于收集位置数据的移动应用程序 {#accessing-mobile-apps-used-to-collect-location-data}

要在Adobe Campaign中访问成功创建的应用程序：

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. 选择 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** 或根 **[!UICONTROL Mobile app (AEP SDK)]** 据SDK进行选择。
1. 从列表中选择一个手机应用程序以显示其属性。

   ![](assets/poi_mobile_app_subscribers.png)

该应用程序的列表符也显示在选项卡 **[!UICONTROL Mobile application subscribers]** 中。 用户是在其移动设备上安装应用程序的所有用户。 Adobe Campaign库用户档案用注册令牌进行标识。

## 访问收集的位置数据 {#accessing-collected-location-data}

完成设置后，收集的“兴趣点”数据将列在每个用户档案 **[!UICONTROL Places]** 的选项卡中。 要访问列表:

1. 选择用户档案。
1. 单击右 **[!UICONTROL Edit profile properties]** 侧的按钮。
1. 选择 **[!UICONTROL Places]** 选项卡。

   ![](assets/poi_profile_places.png)

将列出当前用户档案收集的兴趣点数据。 位置数据在Adobe Campaign库中存储6个月。

有关访问和编辑用户档案的更多信息，请参阅 [用户档案](../../audiences/using/about-profiles.md)。
