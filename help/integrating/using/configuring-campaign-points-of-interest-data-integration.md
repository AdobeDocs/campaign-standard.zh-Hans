---
title: 配置营销活动点数据集成
seo-title: 配置营销活动点数据集成
description: 配置营销活动点数据集成
seo-description: 了解如何在Adobe Campaign中配置兴趣点数据功能，以根据用户的位置发送个性化消息。
page-status-flag: 从未激活
uuid: 0689a06c-cc1 a-442f-95b8-a07 fcec85 d79
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: 使用营销活动和分析-移动-移动
discoiquuid: a967c6cc-c53 b-41b4-866b-90860d78 f463
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: d857bee3e7cb54ec179a73d9c256a14771cbd474

---


# 配置营销活动点数据集成{#configuring-campaign-points-of-interest-data-integration}

## 配置与Adobe Experience Platform SDK的营销活动点数据集成 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>应使用Adobe Experience Platform SDK在Adobe Campaign Standard中配置您的移动应用程序。有关详细步骤，请参阅此 [页面](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

用于收集位置数据的移动应用程序必须由Adobe Campaign界面中的 **管理员** 配置。

要能够将Adobe Experience Platform Location Services与使用Adobe Experience Platform SDK配置的移动应用程序结合使用，您需要：

1. 在Adobe **[!UICONTROL Places]** Experience Platform Launch中为您的移动应用程序配置添加和 **[!UICONTROL Places Monitor]** 扩展。在Adobe Campaign中设置移动应用程序。请参阅 [安装Adobe Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-extension#install-the-places-extension-in-adobe-experience-platform-launch) 中的Place扩展并 [在Experience Platform Launch中安装Place Monitor扩展](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-monitor-extension/using-the-places-monitor-extension)。

1. 设置扩展后，在其中 **[!UICONTROL Adobe Experience Platform Launch]** 创建数据元素以从这些扩展检索数据。请参阅此 [页面](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) 以创建您的数据元素。

1. 然后，您 **[!UICONTROL Adobe Experience Platform Launch]**&#x200B;需要创建规则以支持兴趣点和Adobe Campaign之间的移动使用案例。\
   此规则将在用户进入地理围栏 **[!UICONTROL Point of Interest]**&#x200B;时触发。请参阅此 [页面](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) 以创建规则。

1. 在位置定义 **[!UICONTROL Points of Interest]** 您的位置。请参阅 [创建目标点](https://placesdocs.com/places-services-by-adobe-documentation/places-database-management-1/managing-pois-in-the-places-ui#create-a-poi)。

1. 确保在Adobe Campaign中访问移动应用程序和收集的位置数据。请参阅 [访问用于收集位置数据](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) 和 [访问收集的位置数据](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data)的移动应用程序。

## 使用SDK V配置营销活动点数据集成 {#configuring-campaign-poi-sdkv4}

用于收集位置数据的移动应用程序必须由Adobe Campaign界面中的 **管理员** 配置。

要将Point of Interest数据功能与使用SDK V配置的移动应用程序结合使用，您需要：

1. 有权访问适用于移动设备的Adobe Analytics。请查看您的许可协议或与您的Adobe客户经理联系以了解更多信息。
1. 在Adobe Campaign中设置移动应用程序。请参阅 [在Campaign中设置移动应用程序](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)。
1. 在Adobe Mobile Services界面中设置移动应用程序。这使您能够确保将由Adobe Mobile Services收集的数据发送到Adobe Campaign。请参阅 [在Adobe Mobile Services中配置移动应用程序](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services)。
1. 执行移动应用程序的特定设置：

   * 使用移动应用程序打包从Adobe Mobile Services界面下载的配置文件。
   * 将Experience Cloud Mobile SDK集成到您的移动应用程序中。请参阅 [将SDK集成到移动应用程序](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#integrating-the-sdk-into-a-mobile-application)中。

1. 在Adobe Mobile Services界面中定义兴趣点。请参阅 [定义Adobe Mobile Services中的兴趣点](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#defining-points-of-interest-in-adobe-mobile-services)。
1. 定义要从移动应用程序的订阅者收集的数据。请参阅 [收集订阅者的兴趣点数据](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#collecting-subscribers--points-of-interest-data)。
1. 确保在Adobe Campaign中访问移动应用程序和收集的位置数据。请参阅 [访问用于收集位置数据](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) 和 [访问收集的位置数据](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data)的移动应用程序。

### 使用SDK V在Adobe Campaign中设置移动应用程序 {#setting-up-a-mobile-app-in-campaign}

要能够通过Adobe Campaign收集兴趣点数据，您必须配置Adobe Campaign将从中接收数据的移动应用程序。

1. 单击左上角 **[!UICONTROL Adobe Campaign]** 的标志，然后选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**。
1. 单击 **[!UICONTROL Create]** 以设置应用程序。
1. 在 **[!UICONTROL Application name]** 字段中输入名称，然后单击 **[!UICONTROL Create]**。

   请勿填写 **[!UICONTROL Device-specific settings]** 章节。这仅适用于配置接收推送通知的应用程序。

**[!UICONTROL Mobile application properties]** 在该部分中，列出了两个URL： **[!UICONTROL Collect PII endpoint]****[!UICONTROL Location Services endpoint]**&#x200B;和.它们将在Adobe Mobile Services界面中使用。请参阅 [在Adobe Mobile Services中配置移动应用程序](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services)。

* **[!UICONTROL Collect PII endpoint]** 该URL用于在移动应用程序启动时从移动应用程序中收集用户的Experience Cloud ID和注册令牌。当用户使用电子邮件、名字、姓氏等凭据登录应用程序时，还会收集此数据，并使用Adobe Campaign配置文件调解用户的注册令牌。
* **[!UICONTROL Location Services endpoint]** 该URL用于收集位置数据，如用户的纬度、longitude和从目标点的半径。

您现在可以在Adobe Mobile Services中使用这些值完成配置，如 [在Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services) 部分配置移动应用程序中所述。

![](assets/poi_mobile_app_properties.png)

### 在Adobe Mobile Services中配置V移动应用程序 {#configuring-a-mobile-app-in-adobe-mobile-services}

要将Adobe Mobile Services收集的数据发送到Adobe Campaign，您必须在Mobile Services界面中配置回执。

您需要在Adobe Campaign中设置的移动应用程序参数中找到特定信息(请参阅 [在Campaign中设置移动应用程序](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign))：

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

您必须具有Adobe Analytics的访问权限才能进行以下配置。如果您不是Adobe Analytics用户，请与Adobe Campaign管理员联系。

1. 登录 [mobilemarketing.adobe.com](http://mobilemarketing.adobe.com/)。
1. 创建应用程序或选择现有应用程序。
1. 转到 **[!UICONTROL Manage App Settings]** 页面。
1. 在 **访客ID服务** 部分中，选中 **启用，** 然后从下拉列表中选择您的组织。单击 **“保存**”。

   >[!CAUTION]
   >
   >此组织必须与您在Adobe Campaign实例中使用的相同。

1. Click **[!UICONTROL Manage Postbacks]**.
1. 创建回帖。

   * 选择 **[!UICONTROL PII]****[!UICONTROL Postback Type]**&#x200B;为。
   * **[!UICONTROL URL]** 在字段中，复制您在Adobe Campaign界面中配置的移动应用程序中 **[!UICONTROL Collect PII Endpoint]** 的URL，后跟服务器名称。请参阅 [在Campaign中设置移动应用程序](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)。
   * 填写 **[!UICONTROL Post Body]** 字段如下所示：

      对于iOS：

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

      对于Android：

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

   * 将 **内容类型设置** 为 **[!UICONTROL application/json]**。
   * **哪些数据标签触发回头客？**&#x200B;通常选择任何事件 **[!UICONTROL Launched]** 。**[!UICONTROL exists]**
   * Click **[!UICONTROL Save & Activate]**.

1. 创建第二个帖子。

   * 选择 **[!UICONTROL Postback]****[!UICONTROL Postback Type]**&#x200B;为。
   * **[!UICONTROL URL]** 在字段中，复制您在Adobe Campaign界面中配置的移动应用程序中 **[!UICONTROL Location Services Endpoint]** 的URL，后跟服务器名称。请参阅 [在Campaign中设置移动应用程序](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)。
   * 填写 **[!UICONTROL Post Body]** 字段如下所示：

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

   * 将 **内容类型设置** 为 **[!UICONTROL application/json]**。
   * **哪些数据标签触发回头客？**&#x200B;选择 **[!UICONTROL campaign.test]****[!UICONTROL exists]**&#x200B;和.
   * Click **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>有关配置回车的详细信息，请参阅 [Adobe Mobile Services文档](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html)。

### 将SDK集成到移动应用程序中 {#integrating-the-sdk-into-a-mobile-application}

Mobile核心服务的软件开发工具包(SDK)便于将移动应用程序集成到Adobe Campaign中。

本 [页](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)介绍了此步骤。

### 在Adobe Mobile Services中定义兴趣点 {#defining-points-of-interest-in-adobe-mobile-services}

定义用于收集位置数据的兴趣点：

1. 转到Adobe Mobile Services界面。
1. 添加应用程序。

   有关在Mobile Services中管理应用程序的更多信息，请参阅 [Adobe Mobile Services文档](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html)。

1. 定义目标点。

   有关管理兴趣点的更多信息，请参阅 [Adobe Mobile Services文档](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html)。

### 收集订阅者的兴趣点数据 {#collecting-subscribers--points-of-interest-data}

特定的自定义资源允许您定义要从应用程序的订阅者收集的数据。

此步骤在 [使用SDK V](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) 页配置移动应用程序中介绍。


## 访问用于收集位置数据的移动应用程序 {#accessing-mobile-apps-used-to-collect-location-data}

要在Adobe Campaign中访问已成功创建的应用程序，请执行以下操作：

1. 单击左上角的 **[!UICONTROL Adobe Campaign]** 标志。
1. 选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app (SDK v4)]** 或 **[!UICONTROL Mobile app (AEP SDK)]** 取决于SDK。
1. 从列表中选择一个移动应用程序以显示其属性。

   ![](assets/poi_mobile_app_subscribers.png)

应用程序的订阅者列表也会显示在 **[!UICONTROL Mobile application subscribers]** 选项卡中。用户是在其移动设备上安装了应用程序的所有用户。Adobe Campaign数据库配置文件使用注册令牌进行标识。

## 访问收集的位置数据 {#accessing-collected-location-data}

完成设置后，收集的目标点数据会列在每个配置文件 **[!UICONTROL Places]** 的选项卡中。访问列表：

1. 选择配置文件。
1. 单击右侧的 **[!UICONTROL Edit profile properties]** 按钮。
1. 选择 **[!UICONTROL Places]** 选项卡。

   ![](assets/poi_profile_places.png)

此时会列出当前配置文件所收集的兴趣点数据。位置数据存储在Adobe Campaign数据库中六个月。

有关访问和编辑配置文件的更多信息，请参阅 [配置文件](../../audiences/using/about-profiles.md)。
