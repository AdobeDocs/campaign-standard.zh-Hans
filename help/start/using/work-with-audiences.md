---
title: 自定义列表
description: “了解如何在Adobe Campaign Standard中自定义列表屏幕的显示和操作：排序、筛选、删除或复制元素。 列表屏幕会显示一个或多个给定资源的元素。”
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 6%

---


# 使用用户档案和受众

<table>
<tr>
    <td valign="top">
        <a href="../../start/using/work-with-audiences.md"><img width="60px" alt="条件" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img width="60px" alt="条件" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="条件" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="条件" src="assets/icon_profile.svg"/></a>
    </td>
</tr>
<tr>
<td>客户配置文件</td>
<td>丰富数据库</td>
<td>组织受众</td>
<td>隐私管理</td>
</tr>
</table>

## 客户配置文件 {#customer-profiles}

<img width="60px" alt="条件" src="assets/icon_profile.svg"/>

Adobe Campaign用户档案表示存储在数据库中的所有联系人。 每个概要文件都对应于数据库中的一个条目，其中包含要定位并单独跟踪该概要文件的必要信息。 这意味着用户档案可以是：客户、潜在客户、订阅新闻通讯的个人、收件人、用户或任何其他对象，具体取决于组织。

**了解更多信息**

* [关于用户档案](../../audiences/using/about-profiles.md)
* [访问组织中的活动用户档案数](../../audiences/using/active-profiles.md)

## 丰富数据库 {#populating-database}

<img width="60px" alt="条件" src="assets/icon_populate.svg"/>

Campaign Standard提供了多种工具来帮助您扩大营销数据库。 本节详细介绍可用于将数据注入Campaign的不同方法，并参考专用文档。

### 通过工作流导入数据 {#importing-data-through-workflows}

工作流允许您收集数据，并通过使用[**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md)活动将其导入Campaign数据库。 [此部分](../../automating/using/about-data-import-and-export.md)介绍了通过工作流导入数据时的一般信息和最佳实践。

此外，您可以设置模板以导入数据。 使用导入模板是定期导入具有相同结构的文件的最佳实践。 您可以设置两种类型的模板：

* **工作流模板**：它们是预配置的工作流，可以根据您的需要设置一次，每次要导入数据和更新数据库时都可以重复使用。 [此部分](../../automating/using/creating-import-workflow-templates.md)中详细介绍了用于导入数据的工作流模板示例。

* **导入数据模板**：与工作流模板类似，这些模板是基于工作流设置的上传文件以更新数据库的模板。 配置完毕后，用户即可通过&#x200B;**[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**&#x200B;菜单中的简化视图访问它们。 有关导入数据模板的更多信息，请参阅[专用文档](../../automating/using/importing-data-with-import-templates.md)。

### 从登陆页面收集数据 {#collecting-data-from-landing-pages}

登陆页面是一种Web窗体，可用于收集数据以及创建或更新数据库中的现有信息。 其原则是：

* 通过添加输入字段以收集数据（名字、姓氏、电子邮件等）来创建和设计登陆页面。
* 将每个输入字段映射到数据库中的相应字段。
* 通过网站或消息中的直接链接在线提供登陆页面。

有关登录页的详细信息，请参阅[专用文档](../../channels/using/getting-started-with-landing-pages.md)。

**了解更多信息**

* xxxx
* xxxx

### 从Microsoft Dynamics 365同步配置文件

与Microsoft Dynamics 365的Campaign Standard集成允许您将联系数据从Microsoft Dynamics 365传递到Campaign数据库。
然后，这些联系人会显示在用户档案列表中，并可在营销活动中定位。 有关此集成的详细信息，请参阅[专用文档](../../integrating/using/d365-acs-get-started.md)。

>[!NOTE]
>
>请注意，Campaign Standard-Microsoft Dynamics 365连接器当前处于“有限可用”状态，并且受若干限制，具体详情请参阅此文档。

**了解更多信息**

* xxxx
* xxxx

### 通过API调用导入数据

Campaign StandardAPI允许您执行更新数据库的操作，如用户档案或服务的创建、更新或删除。 有关如何使用API的更多信息，请参阅[专用文档](../../api/using/get-started-apis.md)。

>[!CAUTION]
>
>在通过API调用执行用户档案批量创建或更新之前，请检查与您的许可协议对应的比例限制。 有关详细信息，请参见[此页面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。

**了解更多信息**

* xxxx
* xxxx

## 组织受众 {#organizing-audiences}

<img width="60px" alt="条件" src="assets/icon_audience.svg"/>

为了让您能够提供相关且有效的消息并有效地吸引客户，Adobe Campaign集成了高级分析和定位功能。

借助工作流和查询编辑器，您可以构建不同营销活动定位的受众，具体取决于您掌握的受众信息、其活动、语言、偏好或营销历史。 例如，这允许您过滤订阅的用户档案，或根据无限数量的标准创建目标受众。

**了解更多信息**

* [关于受众](../../audiences/using/about-audiences.md)
* [创建受众](../../audiences/using/creating-audiences.md)

## 隐私管理 {#privacy-management}

<img width="60px" alt="条件" src="assets/icon_privacy.svg"/>

GDPR是欧盟(EU)的新隐私法，旨在协调数据保护要求并使之现代化。 GDPR适用于所持有数据的数据主体位于欧盟的Adobe Campaign客户。 除了Adobe Campaign中已有的可用隐私功能（包括同意管理、数据保留设置和用户角色）之外，我们还将以数据处理方的角色利用此机会来包含其他功能，以帮助您作为数据控制方为特定GDPR请求做好准备。

请参阅[此部分](../../start/using/privacy.md)，了解有关Adobe Campaign为帮助您符合GDPR要求而提供的工具和功能的更多信息。

**了解更多信息**

* xxxx
* xxxx