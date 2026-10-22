---
title: 使用 Adobe Experience Platform 属性个性化营销活动
description: 了解如何使用Adobe Experience Platform属性个性化您的营销活动。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 6%
---
# 使用 Adobe Experience Platform 属性个性化营销活动 {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>Audience Destinations服务当前为测试版，可能会频繁更新，恕不另行通知。 客户需要在Azure上托管（目前为测试版，仅限北美地区使用）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀。
>
>使用Adobe Experience Platform中的上下文数据的&#x200B;**推送**&#x200B;和&#x200B;**应用程序内**&#x200B;渠道尚不可用于个性化。

为您的工作流配置了[Adobe Experience Platform受众](../../integrating/using/aep-about-audience-destinations-service.md)后，您可以使用专门存在于Experience Data Model (XDM)中的用户档案属性对消息进行个性化设置。

为此，您必须将这些属性添加到&#x200B;**[!UICONTROL Read audience]**&#x200B;活动中：

1. 打开&#x200B;**[!UICONTROL Read audience]**&#x200B;活动。 在&#x200B;**[!UICONTROL Additional data]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Create element]**&#x200B;按钮。

   请注意，**[!UICONTROL Additional data]**&#x200B;选项卡仅在选择Adobe Experience Platform受众后可用。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >此功能不支持数组和映射数据类型。 此外，选取器中只显示合并架构中的数据。

1. 从列表中选择所需的XDM字段，然后单击&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/aep_wkf_readaudience_perso1.png)

1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮以将其添加到其他数据列表。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. 对要添加到工作流中的每个XDM字段重复这些步骤。

   >[!NOTE]
   >
   >在&#x200B;**[!UICONTROL Read audience]**&#x200B;活动中最多可添加20个XDM字段。

1. 添加所有字段后，单击&#x200B;**[!UICONTROL Confirm]**&#x200B;按钮以保存更改。 现在即可使用这些功能对投放进行个性化。

有关如何创建和个性化投放的更多信息，请参阅Campaign Standard文档：

* [了解通信渠道](../../channels/using/get-started-communication-channels.md)
* [关于渠道活动](../../automating/using/about-channel-activities.md)
* [个性化投放](../../designing/using/personalization.md)
