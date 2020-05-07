---
title: 自定义列表
description: “了解如何在Adobe Campaign标准中自定义显示屏并在列表屏幕上操作：排序、筛选、删除或复制元素。 列表屏幕显示一个或多个给定资源的元素。”
page-status-flag: never-activated
uuid: 3350583c-91ca-4ea5-ac14-6b6f11c4a64a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 4ba4f766-fdee-4ff0-8fe4-0612ed2b69a4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 7%

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
<td>客户用户档案</td>
<td>丰富数据库</td>
<td>组织受众</td>
<td>隐私管理</td>
</tr>
</table>

## 客户用户档案 {#customer-profiles}

<img width="60px" alt="条件" src="assets/icon_profile.svg"/>

Adobe Campaign用户档案表示存储在数据库中的所有联系人。 每个用户档案对应于用户档案库中的一个条目，该条目包含该被定向、限定和单独跟踪的必要信息。 这意味着用户档案可以： 客户、潜在客户、订阅新闻稿的个人、收件人、用户或任何其他面额，具体取决于组织。

**阅读更多**

* [关于用户档案](../../audiences/using/about-profiles.md)
* [访问组织中的活动用户档案数](../../audiences/using/active-profiles.md)

## 丰富数据库 {#populating-database}

<img width="60px" alt="条件" src="assets/icon_populate.svg"/>

Campaign Standard优惠多种工具，帮助您扩展营销数据库。 本节详细介绍了将数据注入活动时可使用的不同方法以及对专用文档的引用。

### 通过工作流导入数据 {#importing-data-through-workflows}

工作流允许您收集数据，并通过使用活动将其导入活动数 [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) 据库。 本节介绍通过工作流导入数据时的一般信息和最 [佳做法](../../automating/using/importing-data.md)。

此外，您还可以设置模板以导入数据。 如果需要定期导入结构相同的文件，则使用导入模板是最佳做法。 您可以设置两种类型的模板：

* **工作流模板**: 这些是预配置工作流，您可以根据需要设置一次，并在每次要导入数据和更新数据库时重复使用。 本节详细介绍了用于导入数据的工作流 [模板示例](../../automating/using/importing-data.md#example--import-workflow-template)。

* **导入数据模板**: 与工作流模板一样，这些模板基于工作流，设置为上传文件以更新数据库。 配置后，用户可在／菜单下以简化的视图使 **[!UICONTROL Profile & audiences]** 用 **[!UICONTROL Imports]** 它们。 有关导入数据模板的详细信息，请参阅专 [用文档](../../automating/using/importing-data-with-import-templates.md)。

### 从登陆页收集数据 {#collecting-data-from-landing-pages}

登陆页是Web表单，可用于收集数据并创建或更新数据库中的现有信息。 原则如下：

* 通过添加输入字段来收集数据（名字、姓氏、电子邮件等），创建和设计登陆页。
* 将每个输入字段与数据库中的相应字段进行映射。
* 通过网站或消息的直接链接在线提供登陆页。

有关登陆页的更多信息，请参阅专 [用文档](../../channels/using/getting-started-with-landing-pages.md)。

**阅读更多**

* xxxx
* xxxx

### 同步来自Microsoft Dynamics 365的用户档案

Campaign Standard与Microsoft Dynamics 365集成后，您可以将联系人数据从Microsoft Dynamics 365传递给活动数据库。
这些联系人随后会显示在用户档案列表中，并可以定位在营销活动中。 有关此集成的详细信息，请参阅专 [用文档](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)。

>[!NOTE]
>
>请注意，Campaign Standard-Microsoft Dynamics 365连接器当前处于有限可用性状态，并且受多项限制，详见文档。

**阅读更多**

* xxxx
* xxxx

### 通过API调用导入数据

Campaign StandardAPI允许您执行操作来更新用户档案库，如创建、更新或删除数据库。 有关如何使用API的详细信息，请参阅专 [用文档](../../api/using/get-started-apis.md)。

>[!CAUTION]
>
>在通过API调用进行用户档案批量创建或更新之前，请检查与您的许可协议对应的比例限制。 有关详细信息，请参见[此页面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。

**阅读更多**

* xxxx
* xxxx

## 组织受众 {#organizing-audiences}

<img width="60px" alt="条件" src="assets/icon_audience.svg"/>

Adobe Campaign集成了高级分析和定位功能，使您能够投递相关、有效的消息并有效吸引客户。

借助工作流和查询编辑器，您可以根据您对不同活动的信息、活动、语言、偏好或营销历史，构建目标客户。 这允许您筛选订阅用户档案，或根据不限数量的条件创建目标受众。

**阅读更多**

* [关于受众](../../audiences/using/about-audiences.md)
* [创建受众](../../audiences/using/creating-audiences.md)

## 隐私管理 {#privacy-management}

<img width="60px" alt="条件" src="assets/icon_privacy.svg"/>

GDPR 是欧盟最新制定的一项隐私法规，用于协调和顺应时代更新数据保护需求。GDPR 适用于所持有数据的数据主体位于欧盟的 Adobe Campaign 客户。除了Adobe Campaign中已具备的隐私功能（包括同意管理、数据保留设置和用户角色），我们还将利用此机会作为数据处理者加入其他功能，以帮助您为某些GDPR请求做好数据管理者的准备。

请参阅本指 [南](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) ，进一步了解Adobe Campaign为帮助您符合GDPR而提供的工具和功能。

**阅读更多**

* xxxx
* xxxx