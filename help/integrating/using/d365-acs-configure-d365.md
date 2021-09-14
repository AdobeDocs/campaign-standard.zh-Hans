---
title: 为 Campaign 集成配置 Microsoft Dynamics 365
description: 了解如何为Campaign集成配置Microsoft Dynamics 365。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 1%

---

# 配置Microsoft Dynamics 365以与Adobe Campaign Standard集成

了解如何配置Microsoft Dynamics 365集成，并在与Adobe Campaign Standard的跨渠道通信中激活CRM数据。

## 概述

[此页面](../../integrating/using/d365-acs-get-started.md)中介绍了Adobe Campaign Standard与Microsoft Dynamics 365集成的一般说明。

需要配置多个应用程序才能启用集成，但是，本文将重点介绍Dynamics 365中所需的步骤。

## 先决条件

在本文档中执行集成前设置之前，我们假定您已配置并拥有对贵组织的Microsoft Dynamics 365实例的管理员访问权限。  如果尚未发生这种情况，则需要联系Microsoft客户支持以完成Dynamics 365配置。

如果要为暂存环境和生产环境配置集成，则需要为暂存和生产Dynamics 365实例执行以下步骤。 如果要配置舞台或生产Dynamics 365实例（例如，对于生产实例，选择“prod”表示`<stage or prod>`），下面的一些说明会略有不同

## 设置应用程序和权限

OAuth访问令牌允许集成工具通过Web API与Microsoft Dynamics 365实例进行身份验证，以便将Campaign Standard体验事件发布到Microsoft Dynamics 365界面的时间轴视图。

以下视频中概述了主要步骤：

>[!VIDEO](https://video.tv.adobe.com/v/27637)

要生成OAuth访问令牌，请执行下列步骤。

### 注册新应用程序 {#register-a-new-app}

1. 在您的管理员登录下，登录portal.azure.com。

1. 单击左侧菜单中的&#x200B;**[!UICONTROL Azure Active Directory]**;然后，在出现的子菜单上单击&#x200B;**[!UICONTROL App registrations]**。

1. 单击屏幕顶部的&#x200B;**[!UICONTROL New registration]**。

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. 填写应用程序注册屏幕：

   * 名称：adobe campaign `<stage or prod>`
   * 支持的帐户类型：**[!UICONTROL Accounts in this organizational directory only]**（默认值）

有关创建新应用程序的更多信息，请参阅[此部分](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。

>[!NOTE]
>
>Microsoft Azure Directory为您的应用程序分配一个唯一的应用程序（客户端）ID。 您以后在配置Dynamics 365时以及执行集成工具设置时，都将需要此ID。

### 生成客户端密钥 {#generate-a-client-secret}

1. 在应用程序概述屏幕的左侧子菜单中，单击&#x200B;**[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. 输入描述，设置持续时间并单击&#x200B;**[!UICONTROL OK]**。

您的客户端密钥现已创建完成。 暂时保留值，以完成集成工具的预集成设置。

>[!CAUTION]
>
>根据需要保留此值，以完成集成工具预集成设置。 之后将无法检索到。


### 设置权限

1. 在此屏幕或应用程序概述屏幕中，单击左侧子菜单中的&#x200B;**[!UICONTROL API permissions]**。  单击&#x200B;**[!UICONTROL Add a permission]**&#x200B;后，需要在菜单中选择&#x200B;**[!UICONTROL Dynamics CRM]**。

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. 然后选中&#x200B;**[!UICONTROL user_impersonation]**&#x200B;复选框，并单击&#x200B;**[!UICONTROL Add permissions]**&#x200B;按钮。

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

有关权限设置的更多信息，请参阅[此部分](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis)。

### 创建应用程序用户

此新用户是通用用户。 它将由应用程序使用：此用户将使用API对Microsoft Dynamics 365进行任何更改。 要创建它，请执行以下步骤：

1. 导航到Dynamics 365实例并以管理员身份登录。

1. 单击右上角的齿轮图标，然后单击&#x200B;**[!UICONTROL Advanced Settings]**。 在顶部横幅中，单击&#x200B;**[!UICONTROL Settings]**&#x200B;旁边的下拉菜单，然后单击&#x200B;**[!UICONTROL Security > Users]**。

1. 单击下拉菜单，转到&#x200B;**[!UICONTROL Application Users]**。 单击 **[!UICONTROL New]**。

1. “确保”下拉列表中用户图标旁边显示&#x200B;**[!UICONTROL USER:APPLICATION USER]**。

   为新用户填写屏幕。  参数建议：

   * **[!UICONTROL User Name]** （电子邮件）：adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`”(例如adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**:您在Azure AD中注册的应用程序的ID（必需）
   * 可将&#x200B;**[!UICONTROL Application ID URI]**&#x200B;和&#x200B;**[!UICONTROL Azure AD Object ID]**&#x200B;留空
   * **[!UICONTROL Full Name]**:AdobeAPI  `<stage or prod>`
   * **[!UICONTROL Email]**:与相同( **[!UICONTROL User Name]** 或管理员的电子邮件（如果您愿意）

   有关应用程序用户创建的更多信息，请参阅[此部分](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user)。

1. 单击用户图标并上传Adobe Campaign图标；当Dynamics 365中出现新的Adobe事件时，时间轴视图中将显示此图标。

1. 单击顶部功能区中的&#x200B;**[!UICONTROL MANAGE ROLES]**&#x200B;以打开用户角色列表。

1. 向下滚动并选择此用户的&#x200B;**[!UICONTROL System administrator]**&#x200B;访问权限。

1. 单击 **[!UICONTROL OK]**。

### 获取租户ID {#get-the-tenant-id}

按照本页](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id)中的说明[查找租户ID。  在集成工具的集成前设置过程中，您将需要此ID。

## 安装Microsoft Dynamics 365Campaign Standard {#install-appsource-app}

要将Dynamics 365应用程序集成到您的Campaign Standard环境，请执行以下步骤：

1. 导航到以下链接：[https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps)并在搜索栏中搜索&#x200B;_Adobe Campaign for Dynamics 365_。
或者，您也可以导航到此[链接](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)。
1. 按照说明为Dynamics 365实例安装应用程序。
1. 安装后，导航到Dynamics 365实例并以管理员身份登录。
1. 单击右上角的齿轮图标，然后单击&#x200B;**[!UICONTROL Advanced Settings]**。 在顶部横幅中，单击&#x200B;**[!UICONTROL Settings]**&#x200B;旁边的下拉菜单，然后单击&#x200B;**[!UICONTROL Process Center]**&#x200B;下的&#x200B;**[!UICONTROL Processes]**。
1. 搜索&#x200B;**[!UICONTROL Adobe Campaign Email Bounce]**&#x200B;任务并单击它。
1. 在&#x200B;**[!UICONTROL Administration]**&#x200B;选项卡上，将所有者更改为之前创建的AdobeAPI应用程序用户，方法是从顶部功能区中单击&#x200B;**[!UICONTROL Actions]**，然后选择&#x200B;**[!UICONTROL Assign to another User]**&#x200B;选项，从下拉菜单中选择&#x200B;**[!UICONTROL Adobe API application user]**&#x200B;以进行分配。
1. 重新激活该过程。
1. 对&#x200B;**[!UICONTROL Adobe Campaign Email Click]**&#x200B;任务执行相同的操作。

>[!NOTE]
>
>如果您想随时停用这些进程，可以在此&#x200B;**[!UICONTROL Processes]**&#x200B;屏幕中执行此操作。

**相关主题**

* [为Microsoft Dynamics 365集成配置Adobe](../../integrating/using/d365-acs-configure-adobe-io.md) IO是设置集成的下一步
* [自助集成应用程序入门](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 中包含启动和运行集成的完整步骤列表。
