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
TQID: https://experienceleague.adobe.com/LROFX17EE6zvJRbH4P--NjtiJLwanqeudAKzwnQj0BI
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 3%

---

# 丰富数据库{#enriching-the-database}

Campaign Standard提供了多种工具来帮助您增长营销数据库。 本节详细介绍可用于将数据注入Campaign的不同方法，并参考专用文档。

## 通过工作流导入数据 {#importing-data-through-workflows}

工作流允许您收集数据，并通过使用[[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md)活动将其导入Campaign数据库。

[此部分](../../automating/using/about-data-import-and-export.md)介绍了通过工作流导入数据时的一般信息和最佳实践。

此外，您可以设置模板以导入数据。 如果需要定期导入具有相同结构的文件，则使用导入模板是一种最佳实践。

您可以设置两种类型的模板：

* **工作流模板**：它们是预配置的工作流，可以根据您的需要设置一次，每次要导入数据和更新数据库时都可以重复使用。

  [此部分](../../automating/using/creating-import-workflow-templates.md)中详细介绍了用于导入数据的工作流模板示例。

* **导入数据模板**：与工作流模板类似，这些模板是基于工作流设置的上传文件以更新数据库的模板。 配置完毕后，用户即可通过&#x200B;**[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**&#x200B;菜单中的简化视图访问它们。

  有关导入数据模板的更多信息，请参阅[专用文档](../../automating/using/importing-data-with-import-templates.md)。

## 从登陆页面收集数据 {#collecting-data-from-landing-pages}

登陆页面是一种Web窗体，可用于收集数据以及创建或更新数据库中的现有信息。

其原则是：

* 通过添加输入字段以收集数据（名字、姓氏、电子邮件等）来创建和设计登陆页面。
* 将每个输入字段映射到数据库中的相应字段。
* 通过网站或消息中的直接链接在线提供登陆页面。

有关登录页的详细信息，请参阅[专用文档](../../channels/using/getting-started-with-landing-pages.md)。

## 从Microsoft Dynamics 365同步用户档案

Campaign Standard与Microsoft Dynamics 365集成允许您将联系数据从Microsoft Dynamics 365传递到Campaign数据库。
然后，这些联系人会显示在用户档案列表中，并可在营销活动中定位。

有关此集成的详细信息，请参阅[专用文档](../../integrating/using/d365-acs-get-started.md)。

>[!NOTE]
>
>请注意，Campaign Standard-Microsoft Dynamics 365连接器当前处于“有限可用”状态，并且受若干限制，具体详情请参阅此文档。

## 通过API调用导入数据

Campaign Standard API允许您执行更新数据库的操作，如用户档案或服务的创建、更新或删除。

有关如何使用API的更多信息，请参阅[专用文档](../../api/using/get-started-apis.md)。

>[!IMPORTANT]
>
>在通过API调用执行用户档案批量创建或更新之前，请检查与您的许可协议对应的比例限制。 有关详细信息，请参见[此页面](https://helpx.adobe.com/cn/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。
