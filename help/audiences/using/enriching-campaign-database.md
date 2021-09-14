---
title: 扩充数据库
description: 了解扩充数据库的各种方法。
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: Profiles
role: User
level: Intermediate
exl-id: 9c55a8b3-034e-4319-8a88-7b59e83fa458
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 3%

---

# 扩充数据库{#enriching-the-database}

Campaign Standard提供了多种工具来帮助您扩展营销数据库。 本节详细介绍可将数据注入Campaign的不同方法，以及对专用文档的引用。

## 通过工作流导入数据 {#importing-data-through-workflows}

工作流允许您通过使用[[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md)活动收集数据并将其导入Campaign数据库。

[此部分](../../automating/using/about-data-import-and-export.md)中介绍了通过工作流导入数据时的一般信息和最佳实践。

此外，您还可以设置模板以导入数据。 如果需要定期导入具有相同结构的文件，则使用导入模板是最佳做法。

您可以设置两种类型的模板：

* **工作流模板**:这些是预配置的工作流，您可以根据需要设置一次，并在每次要导入数据和更新数据库时重复使用。

   [此部分](../../automating/using/creating-import-workflow-templates.md)中详细介绍了用于导入数据的工作流模板示例。

* **导入数据模板**:与工作流模板一样，这些模板基于工作流，用于上传文件以更新数据库。配置完毕后，用户即可通过&#x200B;**[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**&#x200B;菜单下的简化视图，访问这些配置文件。

   有关导入数据模板的更多信息，请参阅[专用文档](../../automating/using/importing-data-with-import-templates.md)。

## 从登陆页面收集数据 {#collecting-data-from-landing-pages}

登陆页是Web窗体，可用于收集数据并创建或更新数据库中的现有信息。

原则如下：

* 通过添加用于收集数据的输入字段（名字、姓氏、电子邮件等），创建和设计登陆页面。
* 将每个输入字段与数据库中的相应字段映射。
* 通过网站或消息的直接链接，使登陆页面在线可用。

有关登陆页面的更多信息，请参阅[专用文档](../../channels/using/getting-started-with-landing-pages.md)。

## 从Microsoft Dynamics 365同步用户档案

与Microsoft Dynamics 365的Campaign Standard集成允许您将联系数据从Microsoft Dynamics 365传递到Campaign数据库。
然后，这些联系人会显示在“用户档案”列表中，并可在营销活动中定位。

有关此集成的更多信息，请参阅[专用文档](../../integrating/using/d365-acs-get-started.md)。

>[!NOTE]
>
>请注意，Campaign Standard- Microsoft Dynamics 365连接器当前处于有限可用状态，并且受多项限制的约束，详见文档中的说明。

## 通过API调用导入数据

Campaign StandardAPI允许您执行操作来更新数据库，如用户档案或服务的创建、更新或删除。

有关如何使用API的更多信息，请参阅[专用文档](../../api/using/get-started-apis.md)。

>[!IMPORTANT]
>
>在通过API调用批量创建或更新用户档案之前，请检查与您的许可协议对应的比例限制。 有关详细信息，请参见[此页面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。
