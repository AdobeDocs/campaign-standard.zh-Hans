---
title: '集成工具入门 '
description: 集成工具入门
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: e73e2069-e86d-4be2-bf73-22e6dc164340
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 2%

---

# 自助集成应用程序入门 {#gs-self-service-app}

通过Adobe Campaign Standard与Microsoft Dynamics 365自助服务集成应用程序的集成，您能够配置数据流、控制数据流是否在运行以及在哪个环境中运行。 但是，在开始使用自助服务集成应用程序之前，您必须先完成一些先决条件。

## 概念和限制 {#concepts-and-restrictions}

在开始使用集成工具之前，您需要了解与集成相关的概念和防护，并采取一些初始步骤以获取访问权限。

请通过以下章节了解更多信息：

* [Microsoft Dynamics 365 集成快速入门](../../integrating/using/d365-acs-get-started.md)
* [集成最佳实践和限制](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [了解实施此集成的关键步骤](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [使用 Microsoft Dynamics 365 集成](../../integrating/using/d365-acs-using-the-integration.md)

## 先决条件 {#self-service-app-prerequisites}

您需要配置Microsoft Dynamics 365和Adobe Campaign Standard，以便集成应用程序能够访问您的数据。 在Dynamics 365、Adobe Campaign Standard和Adobe I/O中配置这将需要一些时间；但是，配置完它们后，您将能够通过自助服务集成应用程序的用户界面来控制集成。

请通过以下章节了解更多信息：

* [为 Campaign 集成配置 Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
* [配置 Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)
* [映射Campaign自定义资源和Microsoft Dynamics 365自定义实体](../../integrating/using/d365-acs-notices-and-recommendations.md)

## 配置自助服务集成应用程序的关键步骤 {#self-service-app-configuration-steps}

然后，您可以从集成工具开始。 按照以下步骤操作：

1. [获取集成应用程序的访问权限](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [配置集成应用程序以供您使用](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [实施数据同步](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [配置同步工作流](../../integrating/using/d365-acs-self-service-app-workflows.md)

## 链接到集成应用程序 {#self-service-app-link}

打开浏览器并浏览到与您的区域关联的连接器：

* [亚太](https://d365-acs-ap.ea.adobe.com/)
* [欧洲、中东或非洲(EMEA)](https://d365-acs-em.ea.adobe.com/)
* [美洲](https://d365-acs-am.ea.adobe.com/)

## 隐私请求确认 {#self-service-app-acknowledgement}

首次浏览到自助服务UI时，您将收到隐私确认。 您需要确认您了解自己在单独在Campaign和Microsoft Dynamics 365中执行隐私请求时的角色，然后才能继续。
进一步了解您的隐私责任以及如何在 [此部分](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).

## 设置凭据 {#self-service-app-credentials}

首次浏览UI时，您应会看到一个页面，其标题如下所示：

![](assets/do-not-localize/d365-to-acs-ui-header.png)

>[!NOTE]
>
> 如果尚未配置应用程序设置，则通常会收到提到“无法连接”Adobe Campaign Standard或Microsoft Dynamics 365的警报。

请确认您计划配置的“ORG”和“INSTANCE”选项。  如果没有，请单击下拉列表，然后选择正确的组织和实例。

>[!IMPORTANT]
>
> 如果您是首次配置连接器，并且/或您是此过程的新用户，则我们 **强烈** 敦促您选择“stage”或“dev”实例。 在尝试在生产环境中设置之前，您需要确保验证配置是否工作正常。

如果您拥有正确的组织和实例，请单击“汉堡包”菜单以显示下拉菜单。 然后，单击 **[!UICONTROL Settings...]** 在下拉菜单中，访问您在其中输入Microsoft Dynamics 365和Campaign凭据的页面（请参阅下文）。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-menu-pointers.png)

在 **[!UICONTROL Settings]** 页面，请填写以下部分：

* Microsoft Dynamics 365凭据
* Adobe凭据

开始 [此处](../../integrating/using/d365-acs-self-service-app-settings.md) 以查找有关在何处查找每个输入信息的更多详细信息。 完成后，单击 **[!UICONTROL Save]** 按钮。

## 检查初始配置 {#self-service-app-initial-config}

假定您已完成上述先决条件并正确添加了所有凭据，接下来让我们导航到 **[!UICONTROL Workflows]** 页面。 在中了解有关集成应用程序工作流程的更多信息 [本页](../../integrating/using/d365-acs-self-service-app-workflows.md).

在  **[!UICONTROL Workflows]** ，请单击与 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流以编辑其配置。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

在 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 页面，则可以访问已配置的表映射列表。  默认情况下，您会使用现成的联系人/用户档案映射。 需要单独配置所有其他自定义实体。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top-pointers.png)

在 **[!UICONTROL Edit Table Mapping]** 页面，检查 **[!UICONTROL Mappings]** 部分，以确保将Microsoft Dynamics 365中的字段映射到Campaign中的正确字段。 如果需要添加任何其他映射，请立即添加，以及替换项或过滤器。 [了解详情](../../integrating/using/d365-acs-self-service-app-data-sync.md)。

如果要添加新映射，请参阅 [此部分](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) 以了解更多信息。

配置正确后，单击 **[!UICONTROL Play]** 按钮 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流，以启动集成和数据流。

>[!IMPORTANT]
>
>我们 **强烈** 建议您先在暂存或开发环境中运行该环境，然后再在生产环境中运行。 请检查是否在标头中选择了stage/dev实例。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

运行后，您应该能够通过在Microsoft Dynamics 365中添加或修改条目，并在几分钟内观察Adobe Campaign中的这些更改来进行测试。 如果您随时需要停止此过程，只需按相同的按钮即可停止。 [了解详情](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## 集成应用程序工作区 {#self-service-app-workspace}

### 应用程序标题 {#app-header}

自助应用程序中的标题允许您定义当前正在查看和/或配置的组织和实例。

选择 **组织** 和 **实例** 要查看/编辑。 这些字段显示为只读，但是，当您将鼠标光标放在其上时，它们便可编辑。

单击带有三条水平线的按钮时，将显示一个下拉菜单 ![](assets//do-not-localize/d365-to-acs-icon-hamburger.png) 在标题的右侧。

下拉菜单中的条目有：

* **设置**:选择此选项将会将您发送到一个屏幕，该屏幕允许您指定Microsoft Dynamics 365和Adobe Campaign的API凭据，以及应用程序的其他常规设置。

* **文档**:此选项是指向特定于此集成的Adobe Campaign文档的链接

* **客户关怀**:这是与打开客户关怀票证相关的Experience Cloud文档的链接

* **注销**:这将使您从应用程序中注销，并允许您以其他用户身份登录。

* **关于**:此时将显示一个对话框，其中包含有关应用程序的信息，包括版权信息。

### 痕迹导航 {#app-breadcrumbs}

在您导航应用程序时，痕迹导航会显示在某些屏幕的顶部。

**示例:**

以下是 **[!UICONTROL Edit Table Mapping]** 显示痕迹导航和页面标题的屏幕。 在这种情况下，您可以单击 **[!UICONTROL Workflows]** 或 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 文本，以转到之前的某个屏幕。 **[!UICONTROL Edit Table Mapping]** 在此例中，痕迹导航不可点击，因为它是当前屏幕。

![](assets/do-not-localize/d365-to-acs-breadcrumbs-ingress.png)

### 常用按钮 {#app-buttons}

自助服务应用程序的多个页面中使用了以下图标。

![](assets/do-not-localize/d365-to-acs-icon-add.png)  — 向列表中添加新项目。

![](assets/do-not-localize/d365-to-acs-icon-edit.png)  — 编辑已存在的内容

![](assets/do-not-localize/d365-to-acs-icon-delete.png)  — 从项目列表中删除项目
