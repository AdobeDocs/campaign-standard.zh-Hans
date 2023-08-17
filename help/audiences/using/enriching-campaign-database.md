---
title: 丰富数据库
description: 了解丰富数据库的各种方法。
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

# 丰富数据库{#enriching-the-database}

Campaign Standard提供了多种工具来帮助您扩大营销数据库。 本节详细介绍可用于将数据注入Campaign的不同方法，并参考专用文档。

## 通过工作流导入数据 {#importing-data-through-workflows}

利用工作流，可收集数据并通过使用将其导入Campaign数据库 [[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md) 活动。

有关通过工作流导入数据时的一般信息和最佳实践，请参阅 [本节](../../automating/using/about-data-import-and-export.md).

此外，您可以设置模板以导入数据。 如果需要定期导入具有相同结构的文件，则使用导入模板是一种最佳实践。

您可以设置两种类型的模板：

* **工作流模板**：它们是预配置的工作流，您可以根据需要设置一次，并在每次要导入数据和更新数据库时重复使用。

  有关用于导入数据的工作流模板的示例，请参见 [本节](../../automating/using/creating-import-workflow-templates.md).

* **导入数据模板**：与工作流模板类似，这些模板是基于工作流的模板，工作流设置为上传文件以更新数据库。 配置完毕后，即可通过下的简化视图向用户提供 **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** 菜单。

  有关导入数据模板的更多信息，请参阅 [专用文档](../../automating/using/importing-data-with-import-templates.md).

## 从登陆页面收集数据 {#collecting-data-from-landing-pages}

登陆页面是一种Web窗体，可用于收集数据以及创建或更新数据库中的现有信息。

其原则是：

* 通过添加输入字段以收集数据（名字、姓氏、电子邮件等）来创建和设计登陆页面。
* 将每个输入字段映射到数据库中的相应字段。
* 通过网站或消息中的直接链接在线提供登陆页面。

有关登录页面的更多信息，请参阅 [专用文档](../../channels/using/getting-started-with-landing-pages.md).

## 从Microsoft Dynamics 365同步配置文件

与Microsoft Dynamics 365的Campaign Standard集成允许您将联系数据从Microsoft Dynamics 365传递到Campaign数据库。
然后，这些联系人会显示在用户档案列表中，并可在营销活动中定位。

有关此集成的更多信息，请参阅 [专用文档](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>请注意，Campaign Standard-Microsoft Dynamics 365连接器当前处于“有限可用”状态，并且受若干限制，具体详情请参阅此文档。

## 通过API调用导入数据

Campaign StandardAPI允许您执行更新数据库的操作，如用户档案或服务的创建、更新或删除。

有关如何使用API的更多信息，请参阅 [专用文档](../../api/using/get-started-apis.md).

>[!IMPORTANT]
>
>在通过API调用执行用户档案批量创建或更新之前，请检查与您的许可协议对应的比例限制。 有关详细信息，请参见[此页面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。
