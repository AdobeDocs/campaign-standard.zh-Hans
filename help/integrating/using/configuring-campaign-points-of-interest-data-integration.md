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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fc9c6371732aa0eba9e675d2709cd62c25b27b96

---


# 配置 Campaign-兴趣点数据集成{#configuring-campaign-points-of-interest-data-integration}

## 配置与Adobe Experience Platform SDK的Campaign-Points数据集成 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>您的移动应用程序应已使用Adobe Experience Platform SDK在Adobe Campaign Standard中配置。 有关详细步骤，请参阅此 [页](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

用于收集位置数据的移动应用程序必须由管理员在 **Adobe** Campaign界面中配置。

要能够将Adobe Experience Platform Location services与使用Adobe Experience Platform SDK配置的移动应用程序一起使用，您需要：

1. 在Adobe Experience Platform **[!UICONTROL Places]** Launch中 **[!UICONTROL Places Monitor]** ，将这些和扩展添加到您的移动应用程序配置中。 在Adobe Campaign中设置移动应用程序。 请参 [阅在Adobe Experience Platform Launch中安装Places扩展](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch) , [在Experience Platform Launch中安装Places Monitor扩展](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch)。

1. 设置扩展后，在中创建数据元素，以从 **[!UICONTROL Adobe Experience Platform Launch]** 这些扩展中检索数据。 请参阅本 [页](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) ，创建数据元素。

1. 然后，您 **[!UICONTROL Adobe Experience Platform Launch]**&#x200B;需要创建规则，以支持兴趣点和Adobe Campaign之间的移动使用案例。\
   此规则将在用户进入地理围栏时触发 **[!UICONTROL Point of Interest]**。 请参阅此 [页](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) ，以创建规则。

1. 在地点 **[!UICONTROL Points of Interest]** 中定义。 请参 [阅创建兴趣点](https://docs.adobe.com/content/help/en/places/using/poi-mgmt-ui/create-a-poi-ui.html)。

1. 确保您在Adobe Campaign中访问移动应用程序和收集的位置数据。 请参 [阅访问用于收集位置数据的移动应用程序](#accessing-mobile-apps-used-to-collect-location-data) ，以 [及访问收集的位置数据](#accessing-collected-location-data)。

## 使用SDK V4配置Campaign-Points的数据集成 {#configuring-campaign-poi-sdkv4}

用于收集位置数据的移动应用程序必须由管理员在 **Adobe** Campaign界面中配置。

要将兴趣点数据功能用于配置了SDK V4的移动应用程序，您需要：

1. 有权访问Adobe Analytics for Mobile。 有关详细信息，请查看您的许可协议或与您的Adobe客户经理联系。
1. 在Adobe Campaign中设置移动应用程序。 请参 [阅在Campaign中设置移动应用程序](#setting-up-a-mobile-app-in-campaign)。
1. 在Adobe Mobile services界面中设置您的移动应用程序。 这使您能够确保由Adobe Mobile services收集的数据被发送到Adobe Campaign。 请参 [阅在Adobe Mobile services中配置移动应用程序](#configuring-a-mobile-app-in-adobe-mobile-services)。
1. 执行手机应用程序的特定设置：

   * 将从Adobe Mobile services界面下载的配置文件与移动应用程序打包。
   * 将Experience Cloud Mobile SDK集成到您的移动应用程序中。 请参 [阅将SDK集成到移动应用程序中](#integrating-the-sdk-into-a-mobile-application)。

1. 在Adobe Mobile services界面中定义目标点。 请参 [阅定义Adobe Mobile services中的兴趣点](#defining-points-of-interest-in-adobe-mobile-services)。
1. 定义要从移动应用程序的用户处收集的数据。 请参 [阅收集用户的兴趣点数据](#collecting-subscribers--points-of-interest-data)。
1. 确保您在Adobe Campaign中访问移动应用程序和收集的位置数据。 请参 [阅访问用于收集位置数据的移动应用程序](#accessing-mobile-apps-used-to-collect-location-data) ，以 [及访问收集的位置数据](#accessing-collected-location-data)。

### 使用SDK V4在Adobe Campaign中设置移动应用程序 {#setting-up-a-mobile-app-in-campaign}

要能够通过Adobe Campaign收集兴趣点数据，您必须配置Adobe Campaign将从中接收数据的移动应用程序。

1. 单击左 **[!UICONTROL Adobe Campaign]** 上角的标志，然后选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**。
1. 单击 **[!UICONTROL Create]** 以设置应用程序。
1. 在字段中输入名 **[!UICONTROL Application name]** 称并单击 **[!UICONTROL Create]**。

   不要填写该 **[!UICONTROL Device-specific settings]** 部分。 这仅适用于配置接收推送通知的应用程序。

在部 **[!UICONTROL Mobile application properties]** 分中，列出了两个URL: **[!UICONTROL Collect PII endpoint]** 和 **[!UICONTROL Location Services endpoint]**。 它们将用于Adobe Mobile services界面。 请参 [阅在Adobe Mobile services中配置移动应用程序](#configuring-a-mobile-app-in-adobe-mobile-services)。

* URL用 **[!UICONTROL Collect PII endpoint]** 于在移动应用程序启动时从其收集用户的Experience Cloud ID和注册令牌。 当用户使用电子邮件、名、姓等凭据登录应用程序时，也会收集这些数据，并使用这些数据将用户的注册令牌与Adobe Campaign配置文件进行协调。
* 该 **[!UICONTROL Location Services endpoint]** URL用于从目标点收集位置数据，如用户的纬度、经度和半径。

您现在可以在Adobe Mobile services中使用这些值来完成配置，如在Adobe Mobile services中配 [置移动应用程序一节中所述](#configuring-a-mobile-app-in-adobe-mobile-services) 。

![](assets/poi_mobile_app_properties.png)

### 在Adobe Mobile services中配置V4移动应用程序 {#configuring-a-mobile-app-in-adobe-mobile-services}

要将Adobe Mobile services收集的数据发送到Adobe Campaign，您必须在Mobile services界面中配置回发。

您需要在Adobe Campaign中设置的移动应用程序参数中找到的特定信息(请参阅在Campaign中 [设置移动应用程序](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

您必须具有访问Adobe Analytics的权限才能进行以下配置。 如果您不是Adobe Analytics用户，请与您的Adobe Campaign管理员联系。

1. 登录 [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/)。
1. 创建应用程序或选择现有应用程序。
1. 转到页 **[!UICONTROL Manage App Settings]** 面。
1. 在“访 **客ID服务** ”部分，选 **中“启用** ”并从下拉列表中选择您的组织。 单击“ **保存**”。

   >[!CAUTION]
   >
   >此组织必须与您在Adobe Campaign实例中使用的组织相同。

1. Click **[!UICONTROL Manage Postbacks]**.
1. 创建回发。

   * 选择 **[!UICONTROL PII]** 作为 **[!UICONTROL Postback Type]**。
   * 在该字 **[!UICONTROL URL]** 段中，从您在Adobe Campaign界面中配置的移动应用程序复制 **[!UICONTROL Collect PII Endpoint]** URL，前面加有服务器名。 请参 [阅在Campaign中设置移动应用程序](#setting-up-a-mobile-app-in-campaign)。
   * 填写以 **[!UICONTROL Post Body]** 下字段：

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

   * 将内 **容类型设置** 为 **[!UICONTROL application/json]**。
   * 在哪些数 **据标记中触发回发？**，请选择任何事件，通常 **[!UICONTROL Launched]** 为和 **[!UICONTROL exists]**。
   * Click **[!UICONTROL Save & Activate]**.

1. 创建第二个回发。

   * 选择 **[!UICONTROL Postback]** 作为 **[!UICONTROL Postback Type]**。
   * 在该字 **[!UICONTROL URL]** 段中，从您在Adobe Campaign界面中配置的移动应用程序复制 **[!UICONTROL Location Services Endpoint]** URL，前面加有服务器名。 请参 [阅在Campaign中设置移动应用程序](#setting-up-a-mobile-app-in-campaign)。
   * 填写以 **[!UICONTROL Post Body]** 下字段：

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

   * 将内 **容类型设置** 为 **[!UICONTROL application/json]**。
   * 在哪些数 **据标记中触发回发？**, select **[!UICONTROL campaign.test]** and **[!UICONTROL exists]**.
   * Click **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>有关配置回发的详细信息，请参阅 [Adobe Mobile services文档](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html)。

### 将SDK集成到移动应用程序 {#integrating-the-sdk-into-a-mobile-application}

移动核心服务的软件开发工具包(SDK)简化了移动应用程序与Adobe Campaign的集成。

本页介绍了此 [步骤](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

### 定义Adobe Mobile services的兴趣点 {#defining-points-of-interest-in-adobe-mobile-services}

要定义用于收集位置数据的目标点，请执行以下操作：

1. 转到Adobe Mobile services界面。
1. 添加应用程序。

   有关在Mobile services中管理应用程序的详细信息，请参阅 [Adobe Mobile services文档](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html)。

1. 定义目标点。

   有关管理目标点的更多信息，请参阅 [Adobe Mobile services文档](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html)。

### 收集用户兴趣点数据 {#collecting-subscribers--points-of-interest-data}

特定的自定义资源允许您定义要从应用程序订阅者收集的数据。

使用SDK V4配置移 [动应用程序页面中介绍了此步骤](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) 。


## 访问用于收集位置数据的移动应用程序 {#accessing-mobile-apps-used-to-collect-location-data}

要在Adobe Campaign中访问成功创建的应用程序，请执行以下操作：

1. 单击左 **[!UICONTROL Adobe Campaign]** 上角的徽标。
1. 选 **[!UICONTROL Administration]** 择&gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app (SDK v4)]** ，或根据 **[!UICONTROL Mobile app (AEP SDK)]** SDK进行选择。
1. 从列表中选择一个手机应用程序以显示其属性。

   ![](assets/poi_mobile_app_subscribers.png)

该应用程序的订阅者列表也显示在该选 **[!UICONTROL Mobile application subscribers]** 项卡中。 订阅者是在其移动设备上安装了应用程序的所有用户。 Adobe Campaign数据库配置文件使用注册令牌进行标识。

## 访问收集的位置数据 {#accessing-collected-location-data}

完成设置后，收集的“目标点”数据将列在每个配置文件 **[!UICONTROL Places]** 的选项卡中。 要访问列表，请执行以下操作：

1. 选择配置文件。
1. 单击右 **[!UICONTROL Edit profile properties]** 侧的按钮。
1. 选择选 **[!UICONTROL Places]** 项卡。

   ![](assets/poi_profile_places.png)

将列出收集的当前配置文件的兴趣点数据。 位置数据在Adobe Campaign数据库中存储6个月。

有关访问和编辑配置文件的详细信息，请参阅 [配置文件](../../audiences/using/about-profiles.md)。
