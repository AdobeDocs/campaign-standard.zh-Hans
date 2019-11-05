---
title: '在 Experience Manager 中创建 Campaign 表单 '
description: 通过Adobe Experience manager集成，您可以直接在AEM中创建表单以创建和更新配置文件或管理订阅。
page-status-flag: 从未激活
uuid: 43057f81-d47d-4b96-b150-217c289cd608
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用营销活动和体验管理器
discoiquuid: 4a8b5807-87dd-4db4-bd67-890f0adae932
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 在 Experience Manager 中创建 Campaign 表单 {#creating-a-campaign-form-in-experience-manager}

您可以在AEM站点上创建“表单”，并将表单中的字段映射到Adobe Campaign数据库中的字段。 这允许您创建和更新配置文件或管理服务的订阅。

要在AEM站点上创建Adobe Campaign表单，请执行以下操作：

1. 在您的AEM站点中，根据 **Adobe Campaign配置文件模板创建新页面** 。

   ![](assets/aem_content_forms.png)

1. 在页面属性中，选择与 **[!UICONTROL Cloud Service]** 您的Adobe Campaign实例相对应的。

   ![](assets/aem_content_forms_2.png)

1. 从组件中选择表单 **[!UICONTROL Form Start]** 类型：

   * **Adobe Campaign:保存配置文件**
   * **Adobe Campaign:订阅服务**
   * **Adobe Campaign:取消订阅服务**

1. 通过添加可映射到Adobe Campaign数据库字段的不同字段和组件，编辑表单的内容。
1. 测试并发布表单，以便在AEM站点上访问它。

有关详细信息，请参阅详 [细文档](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/adobe-campaign-forms.html)。
