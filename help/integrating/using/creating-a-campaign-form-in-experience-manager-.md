---
title: '在Experience Manager中创建营销活动表单 '
seo-title: '在Experience Manager中创建营销活动表单 '
description: '在Experience Manager中创建营销活动表单 '
seo-description: 通过Adobe Experience Manager集成，您可以直接在AEM中创建表单，以创建和更新配置文件或管理订阅。
page-status-flag: 从未激活
uuid: 43057f81d47d-4b96-b150-217c289 cd608
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: customing-with-campaign-and-experience-manager
discoiquuid: 4a8b5807-87dd-4db4-bd67-890f0 adae932
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: eed2e3597548c97345f51fe62dd2b56af5042e87

---


# Creating a Campaign form in Experience Manager {#creating-a-campaign-form-in-experience-manager}

您可以在AEM站点上创建“表单”，并将表单中的字段映射到Adobe Campaign数据库中的字段。这允许您创建和更新配置文件，或管理服务订阅。

要在AEM站点上创建Adobe Campaign表单，请执行以下操作：

1. In your AEM site, create a new page based on the **Adobe Campaign Profile** template.

   ![](assets/aem_content_forms.png)

1. In the page properties, select the **[!UICONTROL Cloud Service]** corresponding to your Adobe Campaign instance.

   ![](assets/aem_content_forms_2.png)

1. Select the form type from the **[!UICONTROL Form Start]** component:

   * **Adobe Campaign：保存配置文件**
   * **Adobe Campaign：订阅服务**
   * **Adobe Campaign：取消订阅服务**

1. 通过添加可映射到Adobe Campaign数据库字段的不同字段和组件，编辑表单内容。
1. 测试并发布表单，使其可在AEM站点上访问。

For more information, refer to the [detailed documentation](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/adobe-campaign-forms.html).
