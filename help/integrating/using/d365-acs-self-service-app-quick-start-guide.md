---
title: '集成工具入门 '
description: 集成工具入门
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: efa30d7ed4a0caf929da6f485681078318849cda
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 2%

---


# 自助服务集成应用程序{#gs-self-service-app}入门

Adobe Campaign Standard与Microsoft Dynamics 365自助服务集成应用程序的集成使您能够配置数据流、控制数据流是否在运行以及在哪个环境。 但是，在开始使用自助服务集成应用程序之前，您必须完成一些先决条件。

## 概念和限制{#concepts-and-restrictions}

在开始使用集成工具之前，您需要了解与集成相关的概念和护栏，并采取一些初始步骤来访问。

请通过以下部分了解更多信息：

* [Microsoft Dynamics 365 集成快速入门](../../integrating/using/d365-acs-get-started.md)
* [集成最佳实践和限制](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [了解实施此集成的关键步骤](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [使用 Microsoft Dynamics 365 集成](../../integrating/using/d365-acs-using-the-integration.md)

## 先决条件{#self-service-app-prerequisites}

您需要配置Microsoft Dynamics 365和Adobe Campaign Standard，以便集成应用程序能够访问您的数据。 在Dynamics 365、Adobe Campaign Standard和Adobe I/O进行配置需要一些时间；但是，一旦配置了这些应用程序，您就可以通过自助服务集成应用程序的用户界面控制集成。

请通过以下部分了解更多信息：

* [为 Campaign 集成配置 Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
* [配置 Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)
* [映射活动自定义资源和Microsoft Dynamics 365自定义实体](../../integrating/using/d365-acs-notices-and-recommendations.md)

## 配置自助服务集成应用程序{#self-service-app-configuration-steps}的关键步骤

然后，您可以使用集成工具进行开始。 按照以下步骤操作：

1. [获取对集成应用程序的访问权限](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [配置集成应用程序以用于您的用途](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [实现数据同步](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [配置同步工作流](../../integrating/using/d365-acs-self-service-app-workflows.md)

## 链接到集成应用程序{#self-service-app-link}

打开浏览器并浏览到与您的区域关联的连接器：

* [亚太地区](http://d365-acs-ap.ea.adobe.com/)
* [欧洲、中东或非洲(EMEA)](http://d365-acs-em.ea.adobe.com/)
* [美洲](http://d365-acs-na.ea.adobe.com/)

## 隐私请求确认{#self-service-app-acknowledgement}

首次浏览自助服务UI时，将向您显示隐私确认。 在继续之前，您需要确认您了解自己在活动和Microsoft Dynamics 365中分别执行隐私请求时的角色。
在[本节](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)中进一步了解您的隐私责任以及如何管理隐私请求。

## 设置凭据{#self-service-app-credentials}

首次浏览到UI时，您应当看到一个标题如下：

![](assets/do-not-localize/d365-to-acs-ui-header.png)

>[!NOTE]
>
> 通常会收到警报，提到如果尚未配置应用程序设置，它“无法连接”到Adobe Campaign Standard或Microsoft Dynamics 365。

请验证“ORG”和“INSTANCE”选项是您计划配置的选项。  否则，请单击下拉列表，然后选择正确的组织和实例。

>[!IMPORTANT]
>
> 如果您是第一次配置连接器和／或您是此过程的新手，则我们&#x200B;**strongly**&#x200B;会建议您选择“stage”或“dev”实例。 在尝试在生产中设置之前，您需要确保验证配置是否工作正常。

如果您拥有正确的组织和实例，请单击“汉堡包”菜单以显示下拉菜单。 然后，在下拉菜单中单击&#x200B;**[!UICONTROL Settings...]**&#x200B;以访问输入Microsoft Dynamics 365和活动凭据的页面（请参阅下面的内容）。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-menu-pointers.png)

在&#x200B;**[!UICONTROL Settings]**&#x200B;页面中，填写以下部分：

* Microsoft Dynamics 365凭据
* Adobe凭据

转到[此处](../../integrating/using/d365-acs-self-service-app-settings.md)以查找有关在何处找到每个输入信息的更多详细信息。 完成后，单击底部的&#x200B;**[!UICONTROL Save]**&#x200B;按钮。

## 检查初始配置{#self-service-app-initial-config}

假定您已完成上述先决条件并正确添加了所有凭据，现在，让我们导航到&#x200B;**[!UICONTROL Workflows]**&#x200B;页面。 了解有关[此页](../../integrating/using/d365-acs-self-service-app-workflows.md)中集成应用程序工作流的更多信息。

在&#x200B;**[!UICONTROL Workflows]**&#x200B;页面中，单击与&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流关联的铅笔图标以编辑其配置。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

在&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;页中，可以访问已配置的表映射的列表。  它将默认设置为现成的联系人/用户档案映射。 所有其他自定义实体都需要单独配置。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top-pointers.png)

在&#x200B;**[!UICONTROL Edit Table Mapping]**&#x200B;页面中，检查&#x200B;**[!UICONTROL Mappings]**&#x200B;部分，确保将Microsoft Dynamics 365中的字段映射到活动中的正确字段。 如果需要添加任何其他映射，请立即添加，并添加任何替换项或过滤器。 [了解详情](../../integrating/using/d365-acs-self-service-app-data-sync.md)。

如果要添加新映射，请参阅[此部分](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping)以了解详细信息。

配置正确后，单击&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流旁的&#x200B;**[!UICONTROL Play]**&#x200B;按钮，以开始集成和数据流。

>[!IMPORTANT]
>
>我们&#x200B;**strongly**&#x200B;建议您先在Stage或Dev环境中运行此组件，然后再在Production中运行。 请检查是否在标题中选择了阶段／开发实例。


![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

运行后，您应能够通过在Microsoft Dynamics 365中添加或修改条目并在几分钟内观察Adobe Campaign中的这些更改来进行测试。 如果您需要随时停止此过程，只需按同一个按钮即可停止。 [了解详情](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## 集成应用程序工作区{#self-service-app-workspace}

### 应用程序标题{#app-header}

自助应用程序中的标题允许您定义当前查看和／或配置的组织和实例。

选择要视图/编辑的&#x200B;**ORG**&#x200B;和&#x200B;**INSTANCE**。 这些字段显示为只读，但是，当您将鼠标光标放在它上时，这些字段会变为可编辑的。

单击标题右侧有三行水平线![](assets//do-not-localize/d365-to-acs-icon-hamburger.png)的按钮时，将显示下拉菜单。

下拉菜单中的条目有：

* **设置**:选择此选项将发送到屏幕，通过屏幕可指定Microsoft Dynamics 365和Adobe Campaign的API凭据，以及应用程序的其他常规设置。

* **文档**:此选项是指向此集成特定的Adobe Campaign文档的链接

* **客户关怀**:这是指向与打开客户关怀票证相关的Experience Cloud文档的链接

* **注销**:这将使您退出应用程序，并允许您以其他用户身份登录。

* **关于**:此时将显示一个对话框，其中包含有关应用程序的信息，包括版权信息。

### 痕迹导航{#app-breadcrumbs}

导航应用程序时，痕迹导航会显示在某些屏幕的顶部。

**示例:**

下面是&#x200B;**[!UICONTROL Edit Table Mapping]**&#x200B;屏幕中显示痕迹导航和页面标题的示例。 在这种情况下，您可以单击&#x200B;**[!UICONTROL Workflows]**&#x200B;或&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;文本，转到以前的某个屏幕。 **[!UICONTROL Edit Table Mapping]** 在此例中，痕迹导航不可单击，因为它是当前屏幕。

![](assets/do-not-localize/d365-to-acs-breadcrumbs-ingress.png)

### 常用按钮{#app-buttons}

自助服务应用程序的多个页面中使用以下图标。

![](assets/do-not-localize/d365-to-acs-icon-add.png) -向列表添加新项目。

![](assets/do-not-localize/d365-to-acs-icon-edit.png) -编辑已存在的内容

![](assets/do-not-localize/d365-to-acs-icon-delete.png) -从项目列表中删除项目
