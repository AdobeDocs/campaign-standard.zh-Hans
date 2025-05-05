---
title: 为Campaign集成配置Microsoft Dynamics 365
description: 了解如何为Campaign集成配置Microsoft Dynamics 365。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: 6947d163119dd6fc5966fdc723530b02bdd4a469
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 0%

---

# 配置Microsoft Dynamics 365以便与Adobe Campaign Standard集成

了解如何在与Adobe Campaign Standard的跨渠道通信中配置Microsoft Dynamics 365集成并激活您的CRM数据。

## 概述

[此页面](../../integrating/using/d365-acs-get-started.md)中介绍了Adobe Campaign Standard与Microsoft Dynamics 365集成的一般说明。

需要配置多个应用程序才能启用集成，但是，本文将重点介绍Dynamics 365中所需的步骤。

## 先决条件

在执行本文档中的预集成设置之前，假定您已配置并拥有组织的Microsoft Dynamics 365实例的管理员访问权限。  如果尚未发生这种情况，则需要联系Microsoft客户支持以完成Dynamics 365配置。

如果您要为暂存环境和生产环境配置集成，则需要为暂存环境和生产Dynamics 365实例执行以下步骤。 如果您正在配置暂存或生产Dynamics 365实例，以下一些说明略有不同（例如，对于生产实例，为`<stage or prod>`选择“prod”）

## 设置应用程序和权限

OAuth访问令牌允许集成工具通过Web API对您的Microsoft Dynamics 365实例进行身份验证，以便将Campaign Standard体验事件发布到Microsoft Dynamics 365界面的时间线视图。

以下视频概述了主要步骤：

>[!VIDEO](https://video.tv.adobe.com/v/34833?captions=chi_hans)

要生成OAuth访问令牌，请执行以下步骤。

### 注册新应用程序 {#register-a-new-app}

1. 在管理员登录下，登录到[portal.azure.com](https://portal.azure.com){target="_blank"}。

1. 单击左侧菜单中的&#x200B;**[!UICONTROL Azure Active Directory]**；然后在出现的子菜单中单击&#x200B;**[!UICONTROL App registrations]**。

1. 单击屏幕顶部的&#x200B;**[!UICONTROL New registration]**。

1. 填写应用程序注册屏幕：

   * 名称： adobe campaign `<stage or prod>`
   * 支持的帐户类型： **[!UICONTROL Accounts in this organizational directory only]** （默认值）

有关创建新应用程序的更多信息，请参阅[此章节](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}。

>[!NOTE]
>
>Microsoft Azure Directory为应用程序分配唯一的应用程序（客户端）ID。 稍后，在配置Dynamics 365时以及执行集成工具设置时，您将需要此ID。

### 生成客户端密码 {#generate-a-client-secret}

1. 在应用程序概述屏幕的左侧子菜单中，单击&#x200B;**[!UICONTROL Certificates and Secrets > New client secret]**

1. 输入描述，设置持续时间，然后单击&#x200B;**[!UICONTROL OK]**。

您的客户端密钥现已创建。 暂时保留该值，以完成集成工具的预集成设置。

>[!CAUTION]
>
>根据需要保留此值，以完成集成工具预集成设置。 之后无法检索它。


### 设置权限

1. 在此屏幕或应用程序概述屏幕中，单击左侧子菜单中的&#x200B;**[!UICONTROL API permissions]**。  单击&#x200B;**[!UICONTROL Add a permission]**&#x200B;后，您需要在菜单中选择&#x200B;**[!UICONTROL Dynamics CRM]**。

1. 然后选中&#x200B;**[!UICONTROL user_impersonation]**&#x200B;的框，并单击&#x200B;**[!UICONTROL Add permissions]**&#x200B;按钮。

有关权限设置的详细信息，请参阅[此部分](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}。

### 创建应用程序用户

此新用户是通用用户。 应用程序将使用此功能：此用户将会完成使用API对Microsoft Dynamics 365进行的任何更改。 要创建它，请执行以下步骤：

1. 导航到您的Dynamics 365实例，并以管理员身份登录。

1. 单击右上角的齿轮图标，然后单击&#x200B;**[!UICONTROL Advanced Settings]**。 在顶部横幅中，单击&#x200B;**[!UICONTROL Settings]**&#x200B;旁边的下拉菜单，然后单击&#x200B;**[!UICONTROL Security > Users]**。

1. 单击下拉菜单转到&#x200B;**[!UICONTROL Application Users]**。 单击 **[!UICONTROL New]**。

1. 确保用户图标旁边的下拉菜单显示&#x200B;**[!UICONTROL USER:APPLICATION USER]**。

   填写新用户的屏幕。  参数建议：

   * **[!UICONTROL User Name]** （电子邮件）： adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (例如，adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**：您在Azure AD中注册的应用程序的ID（这是必需的）
   * 您可以留空&#x200B;**[!UICONTROL Application ID URI]**&#x200B;和&#x200B;**[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**：AdobeAPI `<stage or prod>`
   * **[!UICONTROL Email]**：与&#x200B;**[!UICONTROL User Name]**&#x200B;相同（如果您愿意，也可以使用管理员的电子邮件）

   有关创建应用程序用户的详细信息，请参阅[此部分](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}。

1. 单击用户图标并上传Adobe Campaign图标；当Dynamics 365中出现新的Adobe事件时，此图标将显示在时间轴视图中。

1. 通过单击顶部功能区中的&#x200B;**[!UICONTROL MANAGE ROLES]**&#x200B;打开用户角色列表。

1. 向下滚动并选择此用户的&#x200B;**[!UICONTROL System administrator]**&#x200B;访问权限。

1. 单击 **[!UICONTROL OK]**。

### 获取租户ID {#get-the-tenant-id}

按照此页面[&#128279;](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id)中的说明查找您的租户ID。  在集成工具中设置预集成期间，您将需要此ID。

## 安装Microsoft Dynamics 365Campaign Standard {#install-appsource-app}

要将Dynamics 365应用程序集成到Campaign Standard环境，请执行以下步骤：

1. 浏览到[Microsoft业务应用程序](https://appsource.microsoft.com/en-us/marketplace/apps)，并在搜索栏中搜索_Adobe Campaign Standard_。
或者，您可以导航到此[链接](https://appsource.microsoft.com/en-us/product/dynamics-365/adobe.adobe_campaign_d365?tab=Overview){target="_blank"}。
1. 按照说明为Dynamics 365实例安装应用程序。
1. 安装后，导航到您的Dynamics 365实例并以管理员身份登录。
1. 单击右上角的齿轮图标，然后单击&#x200B;**[!UICONTROL Advanced Settings]**。 在顶部横幅中，单击&#x200B;**[!UICONTROL Settings]**&#x200B;旁边的下拉菜单，然后单击&#x200B;**[!UICONTROL Process Center]**&#x200B;下的&#x200B;**[!UICONTROL Processes]**。
1. 搜索&#x200B;**[!UICONTROL Adobe Campaign Email Bounce]**&#x200B;任务并单击它。
1. 在&#x200B;**[!UICONTROL Administration]**&#x200B;选项卡上，通过单击顶部功能区中的&#x200B;**[!UICONTROL Actions]**，将所有者更改为之前创建的AdobeAPI应用程序用户，然后选择&#x200B;**[!UICONTROL Assign to another User]**&#x200B;选项，从下拉列表中选择&#x200B;**[!UICONTROL Adobe API application user]**&#x200B;进行分配。
1. 重新激活进程。
1. 对&#x200B;**[!UICONTROL Adobe Campaign Email Click]**&#x200B;任务执行相同操作。

>[!NOTE]
>
>如果您希望随时停用这些进程，可以在此&#x200B;**[!UICONTROL Processes]**&#x200B;屏幕中停用。

**相关主题**

* [为Microsoft Dynamics 365集成配置Adobe Developer](../../integrating/using/d365-acs-configure-adobe-io.md)是设置集成的下一步
* [自助集成应用入门](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md)包含启动并运行集成的完整步骤列表。
