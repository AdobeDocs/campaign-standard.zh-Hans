---
title: '在 Experience Manager 中创建 Campaign 表单 '
description: 通过Adobe Experience Manager集成，您可以直接在AEM中创建表单以创建和更新用户档案或管理订阅。
page-status-flag: never-activated
uuid: 43057f81-d47d-4b96-b150-217c289cd608
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 4a8b5807-87dd-4db4-bd67-890f0adae932
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 在 Experience Manager 中创建 Campaign 表单 {#creating-a-campaign-form-in-experience-manager}

您可以在AEM站点上创建“表单”，并将表单中的字段映射到Adobe Campaign库中的字段。 这允许您创建和更新用户档案或管理服务订阅。

要在AEM站点上创建Adobe Campaign表单，请执行以下操作：

1. 在AEM站点中，根据Adobe Campaign用户档案模板创建 **新页面** 。

   ![](assets/aem_content_forms.png)

1. 在页面属性中，选择与 **[!UICONTROL Cloud Service]** 您的Adobe Campaign实例对应的。

   ![](assets/aem_content_forms_2.png)

1. 从组件中选择表单 **[!UICONTROL Form Start]** 类型：

   * **Adobe Campaign:保存用户档案**
   * **Adobe Campaign:订阅服务**
   * **Adobe Campaign:取消订阅服务**

1. 通过添加可映射到Adobe Campaign库字段的不同字段和组件，编辑表单的内容。
1. 测试并发布表单，使其可在AEM站点上访问。

有关详细信息，请参阅[详细文档](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html)。
