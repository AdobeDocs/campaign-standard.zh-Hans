---
title: 集成工具入门
description: 集成工具入门
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e73e2069-e86d-4be2-bf73-22e6dc164340
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 1%

---

# 自助服务集成应用程序入门 {#gs-self-service-app}

Adobe Campaign Standard与Microsoft Dynamics 365自助式集成应用程序集成，使您能够配置数据流，控制数据流是否运行以及在哪个环境中运行。 但是，在开始使用自助集成应用程序之前，您必须先完成一些先决条件。

## 概念和限制 {#concepts-and-restrictions}

在开始使用集成工具之前，您需要了解与集成相关的概念和护栏，并采取一些初始步骤来获取访问权限。

请参阅以下部分以了解详情：

* [Microsoft Dynamics 365集成快速入门](../../integrating/using/d365-acs-get-started.md)
* [集成最佳实践和限制](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [了解实施此集成的关键步骤](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [使用 Microsoft Dynamics 365 集成](../../integrating/using/d365-acs-using-the-integration.md)

## 先决条件 {#self-service-app-prerequisites}

您需要配置Microsoft Dynamics 365和Adobe Campaign Standard，以便集成应用程序能够访问您的数据。 在Dynamics 365、Adobe Campaign Standard和Adobe I/O中配置此项需要一些时间；但是，配置完毕后，您就可以通过自助服务集成应用程序的用户界面控制集成。

请参阅以下部分以了解详情：

* [为Campaign集成配置Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
* [配置Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)
* [映射Campaign自定义资源和Microsoft Dynamics 365自定义实体](../../integrating/using/d365-acs-notices-and-recommendations.md)

## 配置自助服务集成应用程序的关键步骤 {#self-service-app-configuration-steps}

然后，您可以开始使用集成工具。 请按照以下步骤操作：

1. [获取对集成应用程序的访问权限](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [配置集成应用程序以供您使用](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [实施数据同步](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [配置同步工作流](../../integrating/using/d365-acs-self-service-app-workflows.md)

## 集成应用程序的链接 {#self-service-app-link}

打开浏览器并浏览到与您的地区关联的连接器：

* [亚太地区](https://d365-acs-ap.ea.adobe.com/)
* [欧洲、中东或非洲(EMEA)](https://d365-acs-em.ea.adobe.com/)
* [美洲](https://d365-acs-am.ea.adobe.com/)

## 隐私请求确认 {#self-service-app-acknowledgement}

首次浏览自助服务UI时，您将看到隐私确认。 您需要确认自己了解自己在分别在Campaign和Microsoft Dynamics 365中执行隐私请求时所扮演的角色，然后才能继续。
在[本节](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)中进一步了解您的隐私责任以及如何管理隐私请求。

## 设置您的凭据 {#self-service-app-credentials}

首次浏览UI时，您应该会看到一个页面，其标题如下所示：

![](assets/do-not-localize/d365-to-acs-ui-header.png)

>[!NOTE]
>
> 如果尚未配置应用程序设置，则通常会收到警报，指出其“无法连接”到Adobe Campaign Standard或Microsoft Dynamics 365。

请确认“ORG”和“INSTANCE”选项是您计划配置的选项。  如果没有，请单击下拉列表并选择正确的组织和实例。

>[!IMPORTANT]
>
> 如果您是第一次配置连接器和/或您是此进程的新手，我们&#x200B;**强烈**&#x200B;建议您选择“stage”或“dev”实例。 在尝试在生产环境中进行设置之前，您需要确保配置运行正常。

如果您有正确的组织和实例，请单击“汉堡包”菜单以显示下拉菜单。 然后，在下拉菜单中单击&#x200B;**[!UICONTROL Settings...]**&#x200B;以访问您输入Microsoft Dynamics 365和Campaign凭据的页面（请参阅下文）。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-menu-pointers.png)

在&#x200B;**[!UICONTROL Settings]**&#x200B;页中，填写以下部分：

* Microsoft Dynamics 365凭据
* Adobe凭据

转到[此处](../../integrating/using/d365-acs-self-service-app-settings.md)查找有关在何处查找每个输入信息的详细信息。 完成后，单击底部的&#x200B;**[!UICONTROL Save]**&#x200B;按钮。

## 检查初始配置 {#self-service-app-initial-config}

假定您已完成上述先决条件并已正确添加所有凭据，我们现在导航到&#x200B;**[!UICONTROL Workflows]**&#x200B;页面。 在[此页面](../../integrating/using/d365-acs-self-service-app-workflows.md)中了解有关集成应用工作流的更多信息。

在&#x200B;**[!UICONTROL Workflows]**&#x200B;页面中，单击与&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流关联的铅笔图标以编辑其配置。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

在&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;页中，您可以访问已配置的表映射列表。  这会将您默认使用现成的联系人/配置文件映射。 所有其他自定义实体将需要单独配置。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top-pointers.png)

在&#x200B;**[!UICONTROL Edit Table Mapping]**&#x200B;页面中，检查&#x200B;**[!UICONTROL Mappings]**&#x200B;部分，以确保Microsoft Dynamics 365中的字段被映射到Campaign中的正确字段。 如果需要添加任何其他映射，请立即添加，以及任何替换或过滤器。 [了解详情](../../integrating/using/d365-acs-self-service-app-data-sync.md)。

如果要添加新映射，请参阅[此部分](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping)以了解更多信息。

配置正确后，单击&#x200B;**[!UICONTROL Play]**&#x200B;工作流旁边的&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;按钮以启动集成和数据流。

>[!IMPORTANT]
>
>我们&#x200B;**强烈**&#x200B;建议您先在暂存或开发环境中运行它，然后再在生产中运行。 请检查在标题中是否选择了暂存/开发实例。
>

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

运行后，您应该能够通过在Microsoft Dynamics 365中添加或修改条目并在几分钟内观察Adobe Campaign中的这些更改来进行测试。 如果在任何时候您需要停止此进程，则只需按同一按钮即可将其停止。 [了解详情](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## 集成应用程序工作区 {#self-service-app-workspace}

### 应用程序标头 {#app-header}

自助应用程序中的标头允许您定义当前正在查看和/或配置的组织和实例。

选择要查看/编辑的&#x200B;**组织**&#x200B;和&#x200B;**实例**。 这些字段显示为只读，但是，当您将鼠标光标置于其上时，它们变为可编辑的。

单击标题右侧带有三条水平线![](assets//do-not-localize/d365-to-acs-icon-hamburger.png)的按钮时，将显示下拉菜单。

下拉菜单中的条目包括：

* **设置**：选择此选项会将您发送到一个屏幕，通过该屏幕可指定Microsoft Dynamics 365和Adobe Campaign的API凭据以及应用程序的其他常规设置。

* **文档**：此选项是特定于该集成的Adobe Campaign文档的链接

* **客户关怀**：这是与打开客户关怀票证相关的Experience Cloud文档的链接

* **注销**：这将使您从应用程序中注销，并允许您以其他用户身份重新登录。

* **关于**：这将显示一个对话框，其中包含有关该应用程序的信息，包括版权信息。

### 痕迹导航 {#app-breadcrumbs}

在导航应用程序时，某些屏幕顶部会显示痕迹导航。

**示例：**

以下是&#x200B;**[!UICONTROL Edit Table Mapping]**&#x200B;屏幕中显示痕迹导航和页面标题的示例。 在这种情况下，您可以单击&#x200B;**[!UICONTROL Workflows]**&#x200B;或&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;文本以转到上一个屏幕。 在这种情况下，痕迹导航中的&#x200B;**[!UICONTROL Edit Table Mapping]**&#x200B;不可点击，因为它是当前屏幕。

![](assets/do-not-localize/d365-to-acs-breadcrumbs-ingress.png)

### 常用按钮 {#app-buttons}

在自助应用程序的多个页面中使用以下图标。

![](assets/do-not-localize/d365-to-acs-icon-add.png) — 向列表添加新项。

![](assets/do-not-localize/d365-to-acs-icon-edit.png) — 编辑已存在的内容

![](assets/do-not-localize/d365-to-acs-icon-delete.png) — 从项列表中删除项
