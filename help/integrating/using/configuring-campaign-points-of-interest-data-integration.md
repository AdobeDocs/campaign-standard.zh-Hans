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
source-git-commit: 60365021e10d3d0e3197f57c6e410af3b8ec0c1d

---


# Configuring Campaign-Points of Interest data integration{#configuring-campaign-points-of-interest-data-integration}

## Configuring Campaign-Points of Interest data integration with Adobe Experience Platform SDKs {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>应使用Adobe Experience Platform SDK在Adobe Campaign Standard中配置您的移动应用程序。For the detailed steps, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

The mobile applications used to collect location data must be configured by an **administrator** in the Adobe Campaign interface.

要能够将Adobe Experience Platform Location Services与使用Adobe Experience Platform SDK配置的移动应用程序结合使用，您需要：

1. Add the **[!UICONTROL Places]** and **[!UICONTROL Places Monitor]** extensions to your mobile app configuration in Adobe Experience Platform Launch. 在Adobe Campaign中设置移动应用程序。See [Install the Places extension in Adobe Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-extension#install-the-places-extension-in-adobe-experience-platform-launch) and [Install the Places Monitor extension in Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-monitor-extension/using-the-places-monitor-extension).

1. Once your extensions are set up, create data elements within **[!UICONTROL Adobe Experience Platform Launch]** to retrieve data from these extensions. Refer to this [page](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) to create your data elements.

1. Then, in **[!UICONTROL Adobe Experience Platform Launch]**, you need to create rules to support mobile use cases between Point of Interests and Adobe Campaign.\
   This rule will be triggered when a user enters a geo-fenced **[!UICONTROL Point of Interest]**. Refer to this [page](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) to create your rule.

1. Define your **[!UICONTROL Points of Interest]** in Places. See [Create a Point of Interest](https://placesdocs.com/places-services-by-adobe-documentation/places-database-management-1/managing-pois-in-the-places-ui#create-a-poi).

1. 确保在Adobe Campaign中访问移动应用程序和收集的位置数据。See [Accessing mobile apps used to collect location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) and [Accessing collected location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

## Configuring Campaign-Points of Interest data integration using SDK V4 {#configuring-campaign-poi-sdkv4}

The mobile applications used to collect location data must be configured by an **administrator** in the Adobe Campaign interface.

要将Point of Interest数据功能与使用SDK V配置的移动应用程序结合使用，您需要：

1. 有权访问适用于移动设备的Adobe Analytics。请查看您的许可协议或与您的Adobe客户经理联系以了解更多信息。
1. 在Adobe Campaign中设置移动应用程序。See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
1. 在Adobe Mobile Services界面中设置移动应用程序。这使您能够确保将由Adobe Mobile Services收集的数据发送到Adobe Campaign。See [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).
1. 执行移动应用程序的特定设置：

   * 使用移动应用程序打包从Adobe Mobile Services界面下载的配置文件。
   * 将Experience Cloud Mobile SDK集成到您的移动应用程序中。See [Integrating the SDK into a mobile application](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#integrating-the-sdk-into-a-mobile-application).

1. 在Adobe Mobile Services界面中定义兴趣点。See [Defining Points of Interest in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#defining-points-of-interest-in-adobe-mobile-services).
1. 定义要从移动应用程序的订阅者收集的数据。See [Collecting subscribers' Points of interest data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#collecting-subscribers--points-of-interest-data).
1. 确保在Adobe Campaign中访问移动应用程序和收集的位置数据。See [Accessing mobile apps used to collect location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) and [Accessing collected location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

### Setting up a mobile app in Adobe Campaign using SDK V4 {#setting-up-a-mobile-app-in-campaign}

要能够通过Adobe Campaign收集兴趣点数据，您必须配置Adobe Campaign将从中接收数据的移动应用程序。

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Click **[!UICONTROL Create]** to set up an application.
1. Enter a name in the **[!UICONTROL Application name]** field and click **[!UICONTROL Create]**.

   Do not fill in the **[!UICONTROL Device-specific settings]** section. 这仅适用于配置接收推送通知的应用程序。

**[!UICONTROL Mobile application properties]** 在该部分中，列出了两个URL： **[!UICONTROL Collect PII endpoint]****[!UICONTROL Location Services endpoint]**&#x200B;和.它们将在Adobe Mobile Services界面中使用。See [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).

* **[!UICONTROL Collect PII endpoint]** 该URL用于在移动应用程序启动时从移动应用程序中收集用户的Experience Cloud ID和注册令牌。当用户使用电子邮件、名字、姓氏等凭据登录应用程序时，还会收集此数据，并使用Adobe Campaign配置文件调解用户的注册令牌。
* **[!UICONTROL Location Services endpoint]** 该URL用于收集位置数据，如用户的纬度、longitude和从目标点的半径。

You can now use these values in Adobe Mobile Services to finish the configuration, as explained in the [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services) section.

![](assets/poi_mobile_app_properties.png)

### Configuring a V4 mobile app in Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

要将Adobe Mobile Services收集的数据发送到Adobe Campaign，您必须在Mobile Services界面中配置回执。

You will need specific information that you can find in the mobile application parameters set in Adobe Campaign (see [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

您必须具有Adobe Analytics的访问权限才能进行以下配置。如果您不是Adobe Analytics用户，请与Adobe Campaign管理员联系。

1. Log into [mobilemarketing.adobe.com](http://mobilemarketing.adobe.com/).
1. 创建应用程序或选择现有应用程序。
1. Go to the **[!UICONTROL Manage App Settings]** page.
1. In the **Visitor ID Service ** section, check **Enable** and select your organization from the drop-down list. Click **Save**.

   >[!CAUTION]
   >
   >此组织必须与您在Adobe Campaign实例中使用的相同。

1. Click **[!UICONTROL Manage Postbacks]**.
1. 创建回帖。

   * Select **[!UICONTROL PII]** as the **[!UICONTROL Postback Type]**.
   * **[!UICONTROL URL]** 在字段中，复制您在Adobe Campaign界面中配置的移动应用程序中 **[!UICONTROL Collect PII Endpoint]** 的URL，后跟服务器名称。See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Fill in the **[!UICONTROL Post Body]** field as follows:

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

   * Set **Content Type** as **[!UICONTROL application/json]**.
   * **哪些数据标签触发回头客？**&#x200B;通常选择任何事件 **[!UICONTROL Launched]** 。**[!UICONTROL exists]**
   * Click **[!UICONTROL Save & Activate]**.

1. 创建第二个帖子。

   * Select **[!UICONTROL Postback]** as the **[!UICONTROL Postback Type]**.
   * **[!UICONTROL URL]** 在字段中，复制您在Adobe Campaign界面中配置的移动应用程序中 **[!UICONTROL Location Services Endpoint]** 的URL，后跟服务器名称。See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Fill in the **[!UICONTROL Post Body]** field as follows:

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

   * Set **Content Type** as **[!UICONTROL application/json]**.
   * **哪些数据标签触发回头客？**&#x200B;选择 **[!UICONTROL campaign.test]****[!UICONTROL exists]**&#x200B;和.
   * Click **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>For detailed information on configuring postbacks, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html).

### Integrating the SDK into a mobile application {#integrating-the-sdk-into-a-mobile-application}

Mobile核心服务的软件开发工具包(SDK)便于将移动应用程序集成到Adobe Campaign中。

This step is described in this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

### Defining Points of Interest in Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

定义用于收集位置数据的兴趣点：

1. 转到Adobe Mobile Services界面。
1. 添加应用程序。

   For more information on managing applications in Mobile Services, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html).

1. 定义目标点。

   For more information on managing Points of Interest, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html).

### Collecting subscribers' Points of interest data {#collecting-subscribers--points-of-interest-data}

特定的自定义资源允许您定义要从应用程序的订阅者收集的数据。

This step is described in the [Configuring a mobile application using SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) page.


## Accessing mobile apps used to collect location data {#accessing-mobile-apps-used-to-collect-location-data}

要在Adobe Campaign中访问已成功创建的应用程序，请执行以下操作：

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app (SDK v4)]** or **[!UICONTROL Mobile app (AEP SDK)]** depending on the SDK.
1. 从列表中选择一个移动应用程序以显示其属性。

   ![](assets/poi_mobile_app_subscribers.png)

A list of the application's subscribers is also displayed in the **[!UICONTROL Mobile application subscribers]** tab. 用户是在其移动设备上安装了应用程序的所有用户。Adobe Campaign数据库配置文件使用注册令牌进行标识。

## Accessing collected location data {#accessing-collected-location-data}

Once the setup is done, the collected Points of Interest data is listed in the **[!UICONTROL Places]** tab of each profile. 访问列表：

1. 选择配置文件。
1. Click the **[!UICONTROL Edit profile properties]** button on the right.
1. Select the **[!UICONTROL Places]** tab.

   ![](assets/poi_profile_places.png)

此时会列出当前配置文件所收集的兴趣点数据。位置数据存储在Adobe Campaign数据库中六个月。

For more information on accessing and editing profiles, see [Profiles](../../audiences/using/about-profiles.md).
