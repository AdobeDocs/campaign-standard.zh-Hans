---
title: 第 2 步：发布扩展
description: 了解如何在Campaign Standard中发布扩展。 系列的第2部分。
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: e3bebded-764c-4d2e-9580-c413f1576a2c
TQID: 'https://experienceleague.adobe.com/BPvEkhFMAe2Xiwllo4RwTzGeXo-IPxYiEp-1sGUzK-A'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 27%
---
# 第 2 步：发布扩展{#step-publish-the-extension}

1. 从高级菜单中，通过 Adobe Campaign 徽标，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]**，然后选择 **[!UICONTROL Publication]**。
1. 单击 **[!UICONTROL Prepare Publication]** 按钮。
1. 选择 **[!UICONTROL Create the Profiles & Services Ext API]** 选项。

   ![](assets/create-profile-and-services-api.png)

   >[!NOTE]
   >
   >如果API已发布（即表示您已为此资源或其他资源选中一次此选项），则将强制进行API更新。

1. 单击&#x200B;**[!UICONTROL Profiles & Services API Preview]**&#x200B;选项卡。

   这将向您显示API发布将应用于profilesAndServicesExt API当前版本的更改。

   在此，“促销代码”字段(ID：cusBrand)将插入到API中。

   ![](assets/extendpandsapi_diff.png)

1. 单击 **[!UICONTROL Publish]** 按钮。
