---
solution: Campaign Standard
product: campaign
title: 配置 Campaign-兴趣点数据集成
description: 了解如何在Adobe Campaign中配置Points of Interest数据功能，以根据用户的位置发送个性化消息。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 3%

---


# 配置 Campaign-兴趣点数据集成{#configuring-campaign-points-of-interest-data-integration}

## 配置与Adobe Experience Platform SDK的活动点数据集成{#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>您的移动应用程序应已使用Adobe Experience Platform SDK在Adobe Campaign Standard中配置。 有关详细步骤，请参阅此[页面](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html)。

用于收集位置数据的移动应用程序必须由Adobe Campaign接口中的&#x200B;**administrator**&#x200B;配置。

要能够将Adobe Experience Platform Location Services与使用Adobe Experience Platform SDK配置的移动应用程序一起使用，您需要：

1. 将&#x200B;**[!UICONTROL Places]**&#x200B;和&#x200B;**[!UICONTROL Places Monitor]**&#x200B;扩展添加到Adobe Experience Platform Launch中的移动应用程序配置。 在Adobe Campaign中设置移动应用程序。 请参阅[在Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch)中安装Places扩展和在Experience Platform Launch](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch)中安装Places Monitor扩展。[

1. 设置扩展后，在&#x200B;**[!UICONTROL Adobe Experience Platform Launch]**&#x200B;中创建数据元素，从这些扩展中检索数据。 请参阅此[页](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)以创建数据元素。

1. 然后，在&#x200B;**[!UICONTROL Adobe Experience Platform Launch]**&#x200B;中，您需要创建规则以支持兴趣点和Adobe Campaign之间的移动使用案例。\
   此规则将在用户进入带有地理围栏的&#x200B;**[!UICONTROL Point of Interest]**&#x200B;时触发。 请参阅此[页](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback)以创建规则。

1. 在“地点”中定义&#x200B;**[!UICONTROL Points of Interest]**。 请参阅[创建目标点](https://docs.adobe.com/content/help/en/places/using/poi-mgmt-ui/create-a-poi-ui.html)。

1. 确保在Adobe Campaign中访问移动应用程序和收集的位置数据。 请参阅[访问用于收集位置数据的移动应用程序](#accessing-mobile-apps-used-to-collect-location-data)和[访问收集的位置数据](#accessing-collected-location-data)。

## 使用SDK V4 {#configuring-campaign-poi-sdkv4}配置活动点数据集成

用于收集位置数据的移动应用程序必须由Adobe Campaign接口中的&#x200B;**administrator**&#x200B;配置。

要将兴趣点数据功能用于配置了SDK V4的移动应用程序，您需要：

1. 访问Adobe Analytics for Mobile。 有关详细信息，请查看您的许可协议或与Adobe帐户主管联系。
1. 在Adobe Campaign中设置移动应用程序。 请参阅[在活动](#setting-up-a-mobile-app-in-campaign)中设置移动应用程序。
1. 在Adobe Mobile Services界面中设置您的移动应用程序。 这使您能够确保由Adobe Mobile Services收集的数据发送到Adobe Campaign。 请参阅[在Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services)中配置移动应用程序。
1. 执行移动应用程序的特定设置：

   * 将从Adobe Mobile Services界面下载的配置文件与移动应用程序打包。
   * 将Experience Cloud Mobile SDK集成到您的移动应用程序中。 请参阅[将SDK集成到移动应用程序](#integrating-the-sdk-into-a-mobile-application)。

1. 在Adobe Mobile Services界面中定义目标点。 请参阅[定义Adobe Mobile Services中的目标点](#defining-points-of-interest-in-adobe-mobile-services)。
1. 定义要从移动应用程序的用户处收集的数据。 请参阅[收集用户的兴趣点数据](#collecting-subscribers--points-of-interest-data)。
1. 确保在Adobe Campaign中访问移动应用程序和收集的位置数据。 请参阅[访问用于收集位置数据的移动应用程序](#accessing-mobile-apps-used-to-collect-location-data)和[访问收集的位置数据](#accessing-collected-location-data)。

### 使用SDK V4 {#setting-up-a-mobile-app-in-campaign}在Adobe Campaign中设置移动应用程序

要能够用Adobe Campaign收集兴趣点数据，您必须配置Adobe Campaign将从中接收数据的移动应用程序。

1. 单击左上角的 **[!UICONTROL Adobe Campaign]** 徽标，然后选择 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**。
1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;设置应用程序。
1. 在&#x200B;**[!UICONTROL Application name]**&#x200B;字段中输入名称，然后单击&#x200B;**[!UICONTROL Create]**。

   请勿填写&#x200B;**[!UICONTROL Device-specific settings]**&#x200B;部分。 这仅适用于配置接收推送通知的应用程序。

在&#x200B;**[!UICONTROL Mobile application properties]**&#x200B;部分中，列出了两个URL:**[!UICONTROL Collect PII endpoint]**&#x200B;和&#x200B;**[!UICONTROL Location Services endpoint]**。 它们将用于Adobe Mobile Services界面。 请参阅[在Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services)中配置移动应用程序。

* **[!UICONTROL Collect PII endpoint]** URL用于在移动应用程序启动时从其收集用户的Experience CloudID和注册令牌。 当用户使用电子邮件、名、姓等凭据登录应用程序时，还会收集此数据并使用这些数据协调用户的注册令牌与Adobe Campaign用户档案。
* **[!UICONTROL Location Services endpoint]** URL用于从目标点收集位置数据，如用户的纬度、经度和半径。

您现在可以在Adobe Mobile Services中使用这些值来完成配置，如[在Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services)中配置移动应用程序一节中所述。

![](assets/poi_mobile_app_properties.png)

### 在Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}中配置V4移动应用程序

要将Adobe Mobile Services收集的数据发送到Adobe Campaign，您必须在Mobile Services界面中配置回发。

您需要在Adobe Campaign中设置的移动应用程序参数中找到的特定信息(请参阅[在活动中设置移动应用程序](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

您必须具有访问Adobe Analytics的权限才能进行以下配置。 如果您不是Adobe Analytics用户，请与您的Adobe Campaign管理员联系。

1. 登录[mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/)。
1. 创建应用程序或选择现有应用程序。
1. 转到&#x200B;**[!UICONTROL Manage App Settings]**&#x200B;页。
1. 在&#x200B;**访客ID服务**&#x200B;部分，选中&#x200B;**启用**&#x200B;并从下拉列表中选择您的组织。 单击&#x200B;**保存**。

   >[!CAUTION]
   >
   >此组织必须与您在Adobe Campaign实例上使用的组织相同。

1. 单击 **[!UICONTROL Manage Postbacks]**.
1. 创建回发。

   * 选择&#x200B;**[!UICONTROL PII]**&#x200B;作为&#x200B;**[!UICONTROL Postback Type]**。
   * 在&#x200B;**[!UICONTROL URL]**&#x200B;字段中，从您在Adobe Campaign接口中配置的移动应用程序复制&#x200B;**[!UICONTROL Collect PII Endpoint]** URL，前面是服务器名称。 请参阅[在活动](#setting-up-a-mobile-app-in-campaign)中设置移动应用程序。
   * 按如下方式填写&#x200B;**[!UICONTROL Post Body]**&#x200B;字段：

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

   * 将&#x200B;**内容类型**&#x200B;设置为&#x200B;**[!UICONTROL application/json]**。
   * 在&#x200B;**中，哪些数据标记触发回发？**，选择任何事件，通常 **[!UICONTROL Launched]** 为和 **[!UICONTROL exists]**。
   * 单击 **[!UICONTROL Save & Activate]**.

1. 创建第二个回发。

   * 选择&#x200B;**[!UICONTROL Postback]**&#x200B;作为&#x200B;**[!UICONTROL Postback Type]**。
   * 在&#x200B;**[!UICONTROL URL]**&#x200B;字段中，从您在Adobe Campaign接口中配置的移动应用程序复制&#x200B;**[!UICONTROL Location Services Endpoint]** URL，前面是服务器名称。 请参阅[在活动](#setting-up-a-mobile-app-in-campaign)中设置移动应用程序。
   * 按如下方式填写&#x200B;**[!UICONTROL Post Body]**&#x200B;字段：

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

   * 将&#x200B;**内容类型**&#x200B;设置为&#x200B;**[!UICONTROL application/json]**。
   * 在&#x200B;**中，哪些数据标记触发回发？**, select  **[!UICONTROL campaign.test]** and **[!UICONTROL exists]**.
   * 单击 **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>有关配置回发的详细信息，请参阅[Adobe Mobile Services文档](https://docs.adobe.com/content/help/en/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html)。

### 将SDK集成到移动应用程序{#integrating-the-sdk-into-a-mobile-application}

移动核心服务的软件开发工具包(SDK)简化了移动应用程序与Adobe Campaign的集成。

此[页面](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdkv4.html)中介绍了此步骤。

### 定义Adobe Mobile Services中的兴趣点{#defining-points-of-interest-in-adobe-mobile-services}

要定义用于收集位置数据的目标点，请执行以下操作：

1. 转到Adobe Mobile Services界面。
1. 添加应用程序。

   有关在Mobile Services中管理应用程序的详细信息，请参阅[Adobe Mobile Services文档](https://docs.adobe.com/content/help/en/mobile-services/using/manage-apps-ug/t-new-app.html)。

1. 定义目标点。

   有关管理目标点的详细信息，请参阅[Adobe Mobile Services文档](https://docs.adobe.com/content/help/en/mobile-services/using/location-ug/t-manage-points.html)。

### 收集用户的兴趣点数据{#collecting-subscribers--points-of-interest-data}

特定的自定义资源允许您定义要从应用程序订阅者收集的数据。

此步骤在[使用SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)页中介绍。


## 访问用于收集位置数据{#accessing-mobile-apps-used-to-collect-location-data}的移动应用程序

要在Adobe Campaign中访问成功创建的应用程序：

1. 单击左上角的&#x200B;**[!UICONTROL Adobe Campaign]**&#x200B;徽标。
1. 根据SDK选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]**&#x200B;或&#x200B;**[!UICONTROL Mobile app (AEP SDK)]**。
1. 从列表中选择一个手机应用程序以显示其属性。

   ![](assets/poi_mobile_app_subscribers.png)

**[!UICONTROL Mobile application subscribers]**&#x200B;选项卡中还会显示应用程序用户的列表。 用户是在其移动设备上安装应用程序的所有用户。 Adobe Campaign数据库用户档案用注册令牌标识。

## 访问收集的位置数据{#accessing-collected-location-data}

完成设置后，收集的“Points of Interest”（兴趣点）数据将列在每个用户档案的&#x200B;**[!UICONTROL Places]**&#x200B;选项卡中。 要访问列表:

1. 选择用户档案。
1. 单击右侧的&#x200B;**[!UICONTROL Edit profile properties]**&#x200B;按钮。
1. 选择 **[!UICONTROL Places]** 选项卡。

   ![](assets/poi_profile_places.png)

将列出当前用户档案收集的兴趣点数据。 位置数据在Adobe Campaign数据库中存储了6个月。

有关访问和编辑用户档案的详细信息，请参阅[用户档案](../../audiences/using/about-profiles.md)。
