---
solution: Campaign Standard
product: campaign
title: 丰富数据库
description: 了解丰富数据库的各种方法。
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: 用户档案
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 3%

---


# 丰富数据库{#enriching-the-database}

Campaign Standard优惠了多种工具来帮助您扩展营销数据库。 本节详细介绍了将数据注入活动时可使用的不同方法，以及对专用文档的引用。

## 通过工作流{#importing-data-through-workflows}导入数据

工作流允许您通过使用[[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md)活动收集数据并将其导入活动数据库。

[本节](../../automating/using/about-data-import-and-export.md)介绍了通过工作流导入数据时的一般信息和最佳实践。

此外，您还可以设置模板以导入数据。 如果您需要定期导入具有相同结构的文件，则使用导入模板是最佳做法。

您可以设置两种类型的模板：

* **工作流模板**:这些是预先配置的工作流，您可以根据需要设置一次，每次导入数据和更新数据库时都可以重复使用。

   [本节](../../automating/using/creating-import-workflow-templates.md)中详细介绍了用于导入数据的工作流模板的示例。

* **导入数据模板**:与工作流模板一样，这些模板基于工作流，设置为上传文件以更新数据库。配置后，用户可在&#x200B;**[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**&#x200B;菜单下使用简化的视图。

   有关导入数据模板的详细信息，请参阅[专用文档](../../automating/using/importing-data-with-import-templates.md)。

## 从登陆页{#collecting-data-from-landing-pages}收集数据

登陆页是Web表单，可用于收集数据并创建或更新数据库中的现有信息。

原则如下：

* 通过添加输入字段来收集数据（名、姓、电子邮件等），创建和设计登陆页。
* 将每个输入字段与数据库中的相应字段进行映射。
* 通过网站或消息中的直接链接在线提供登陆页。

有关登陆页的详细信息，请参阅[专用文档](../../channels/using/getting-started-with-landing-pages.md)。

## 从Microsoft Dynamics 365同步用户档案

Campaign Standard与Microsoft Dynamics 365的集成允许您将联系数据从Microsoft Dynamics 365传递到活动数据库。
然后，这些联系人会显示在用户档案列表中，并且可以定位在营销活动中。

有关此集成的详细信息，请参阅[专用文档](../../integrating/using/d365-acs-get-started.md)。

>[!NOTE]
>
>请注意，Campaign Standard-Microsoft Dynamics 365连接器当前处于有限可用性状态，并且受多项限制的约束，详见文档。

## 通过API调用导入数据

Campaign Standard API允许您执行操作来更新用户档案库，如创建、更新或删除数据库。

有关如何使用API的详细信息，请参阅[专用文档](../../api/using/get-started-apis.md)。

>[!IMPORTANT]
>
>在通过API调用执行用户档案批量创建或更新之前，请检查与您的许可协议对应的比例限制。 有关详细信息，请参见[此页面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。
