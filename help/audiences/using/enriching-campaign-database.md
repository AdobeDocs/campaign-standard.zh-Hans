---
title: 丰富数据库
description: 了解丰富数据库的各种方法。
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 1%

---


# 丰富数据库{#enriching-the-database}

Campaign Standard优惠多种工具，帮助您扩展营销数据库。 本节详细介绍了将数据注入活动时可使用的不同方法以及对专用文档的引用。

## 通过工作流导入数据 {#importing-data-through-workflows}

工作流允许您收集数据，并通过使用活动将其导入活动数 [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) 据库。

本节介绍通过工作流导入数据时的一般信息和最 [佳做法](../../automating/using/importing-data.md)。

此外，您还可以设置模板以导入数据。 如果需要定期导入结构相同的文件，则使用导入模板是最佳做法。

您可以设置两种类型的模板：

* **工作流模板**: 这些是预配置的工作流，您可以根据需要设置一次，并在每次要导入数据和更新数据库时重复使用。

   本节详细介绍了用于导入数据的工作流 [模板示例](../../automating/using/importing-data.md#example--import-workflow-template)。

* **导入数据模板**: 与工作流模板一样，这些模板基于工作流，设置为上传文件以更新数据库。 配置后，用户可在／菜单下以简化的视图使 **[!UICONTROL Profile & audiences]** 用 **[!UICONTROL Imports]** 它们。

   有关导入数据模板的详细信息，请参阅专 [用文档](../../automating/using/importing-data-with-import-templates.md)。

## 从登陆页收集数据 {#collecting-data-from-landing-pages}

登陆页是Web表单，可用于收集数据并创建或更新数据库中的现有信息。

原则如下：

* 通过添加输入字段来收集数据（名字、姓氏、电子邮件等），创建和设计登陆页。
* 将每个输入字段与数据库中的相应字段进行映射。
* 通过网站或消息的直接链接在线提供登陆页。

有关登陆页的更多信息，请参阅专 [用文档](../../channels/using/getting-started-with-landing-pages.md)。

## 同步来自Microsoft Dynamics 365的用户档案

Campaign Standard与Microsoft Dynamics 365集成后，您可以将联系人数据从Microsoft Dynamics 365传递给活动数据库。
这些联系人随后会显示在用户档案列表中，并可以定位在营销活动中。

有关此集成的详细信息，请参阅专 [用文档](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。

>[!NOTE]
>
>请注意，Campaign Standard-Microsoft Dynamics 365连接器当前处于有限可用性状态，并且受多项限制，详见文档。

## 通过API调用导入数据

Campaign StandardAPI允许您执行操作来更新用户档案库，如创建、更新或删除数据库。

有关如何使用API的详细信息，请参阅专 [用文档](../../api/using/get-started-apis.md)。

>[!CAUTION]
>
>在通过API调用进行用户档案批量创建或更新之前，请检查与您的许可协议对应的比例限制。 有关详细信息，请参见[此页面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。
