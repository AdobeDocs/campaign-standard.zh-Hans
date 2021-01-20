---
solution: Campaign Standard
product: campaign
title: 为 Campaign 集成配置 Microsoft Dynamics 365
description: 了解如何配置Microsoft Dynamics 365以实现活动集成。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 3ba3e0db816832ea57c124a9bea1fa82cf068859
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 1%

---


# 配置Microsoft Dynamics 365以与Adobe Campaign Standard集成

了解如何配置Microsoft Dynamics 365集成并激活与Adobe Campaign Standard的跨渠道通信的CRM数据。

## 概述

有关Adobe Campaign Standard与Microsoft Dynamics 365集成的一般说明，请参阅本页[。](../../integrating/using/d365-acs-get-started.md)

需要配置多个应用程序以启用集成，但本文将重点介绍Dynamics 365中所需的步骤。

## 先决条件

在此文档中执行集成前设置之前，假定您已配置并拥有对贵组织的Microsoft Dynamics 365实例的管理员访问权限。  如果尚未发生这种情况，您需要联系Microsoft客户支持以完成Dynamics 365配置。

如果要为登台和生产环境配置集成，您需要为登台和生产Dynamics 365实例执行以下步骤。 下面的一些说明根据您是配置舞台还是生产Dynamics 365实例而略有不同（例如，对于生产实例，选择`<stage or prod>`的“prod”）

## 设置应用程序和权限

OAuth访问令牌允许集成工具通过Web API与Microsoft Dynamics 365实例进行身份验证，以便将Campaign Standard体验事件发布到Microsoft Dynamics 365界面的时间轴视图。

以下视频概述了主要步骤：

>[!VIDEO](https://video.tv.adobe.com/v/27637)

要生成OAuth访问令牌，请按照以下步骤操作。

### 注册新应用程序{#register-a-new-app}

1. 在管理员登录下，登录portal.azure.com。

1. 单击左侧菜单中的&#x200B;**[!UICONTROL Azure Active Directory]**;然后，单击出现的子菜单上的&#x200B;**[!UICONTROL App registrations]**。

1. 单击屏幕顶部的&#x200B;**[!UICONTROL New registration]**。

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. 填写应用程序注册屏幕：

   * 名称：adobe活动`<stage or prod>`
   * 支持的帐户类型：**[!UICONTROL Accounts in this organizational directory only]**（默认值）

有关创建新应用程序的详细信息，请参阅[本节](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。

>[!NOTE]
>
>Microsoft Azure Directory为您的应用程序分配一个唯一的应用程序（客户端）ID。 以后配置Dynamics 365以及执行集成工具设置时，您需要此ID。

### 生成客户端密码{#generate-a-client-secret}

1. 在应用程序概述屏幕左侧的子菜单中，单击&#x200B;**[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. 输入说明，设置持续时间，然后单击&#x200B;**[!UICONTROL OK]**。

您的客户机密已创建。 在完成集成工具的预集成设置时暂时保留该值。

>[!CAUTION]
>
>根据需要保留此值以完成集成工具的预集成设置。 之后无法检索它。


### 设置权限

1. 在此屏幕或应用程序概述屏幕中，单击左侧子菜单中的&#x200B;**[!UICONTROL API permissions]**。  单击&#x200B;**[!UICONTROL Add a permission]**&#x200B;后，您需要在菜单中选择&#x200B;**[!UICONTROL Dynamics CRM]**。

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. 然后，选中&#x200B;**[!UICONTROL user_impersonation]**&#x200B;的复选框，并单击&#x200B;**[!UICONTROL Add permissions]**&#x200B;按钮。

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

有关权限设置的详细信息，请参阅[此部分](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis)。

### 创建应用程序用户

此新用户是通用用户。 它将由应用程序使用：此用户将使用API对Microsoft Dynamics 365进行任何更改。 要创建它，请按照以下步骤操作：

1. 导航到Dynamics 365实例，以管理员身份登录。

1. 单击右上角的齿轮图标，然后单击&#x200B;**[!UICONTROL Advanced Settings]**。 在顶部横幅中，单击&#x200B;**[!UICONTROL Settings]**&#x200B;旁边的下拉框，单击&#x200B;**[!UICONTROL Security > Users]**。

1. 单击下拉菜单，转到&#x200B;**[!UICONTROL Application Users]**。 单击 **[!UICONTROL New]**.

1. 确保用户图标旁边的下拉菜单显示&#x200B;**[!UICONTROL USER:APPLICATION USER]**。

   为新用户填写屏幕。  参数建议：

   * **[!UICONTROL User Name]** （电子邮件）:adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot;(例如，adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**:您在Azure AD中注册的应用程序的ID（此为必需）
   * 可以留空&#x200B;**[!UICONTROL Application ID URI]**&#x200B;和&#x200B;**[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**:AdobeAPI  `<stage or prod>`
   * **[!UICONTROL Email]**:与(或 **[!UICONTROL User Name]** 管理员的电子邮件（如果您愿意）相同

   有关应用程序用户创建的详细信息，请参阅[本节](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user)。

1. 单击用户图标并上传Adobe Campaign图标；这是当Dynamics 365中出现新视图事件时，将在时间轴Adobe中显示的图标。

1. 单击顶部功能区中的&#x200B;**[!UICONTROL MANAGE ROLES]**&#x200B;打开用户角色列表。

1. 向下滚动并选择此用户的&#x200B;**[!UICONTROL System administrator]**&#x200B;访问权限。

1. 单击 **[!UICONTROL OK]**.

### 获取租户ID {#get-the-tenant-id}

按照本页](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id)中的说明[查找您的租户ID。  在集成工具中的预集成设置过程中，您将需要此ID。

## 安装Microsoft Dynamics 365的Campaign Standard{#install-appsource-app}

要将Dynamics 365应用程序集成到您的Campaign Standard环境，请按照以下步骤操作：

1. 导航到以下链接：[https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps)并在搜索栏中搜索&#x200B;_对Dynamics 365_的Adobe Campaign。
或者，您也可以导航到此[链接](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)。
1. 按照说明为Dynamics 365实例安装应用程序。
1. 安装后，导航到Dynamics 365实例并以管理员身份登录。
1. 单击右上角的齿轮图标，然后单击&#x200B;**[!UICONTROL Advanced Settings]**。 在顶部横幅中，单击&#x200B;**[!UICONTROL Settings]**&#x200B;旁边的下拉框，单击&#x200B;**[!UICONTROL Process Center]**&#x200B;下的&#x200B;**[!UICONTROL Processes]**。
1. 搜索&#x200B;**[!UICONTROL Adobe Campaign Email Bounce]**&#x200B;任务并单击它。
1. 在&#x200B;**[!UICONTROL Administration]**&#x200B;选项卡上，将所有者更改为之前创建的AdobeAPI应用程序用户，方法是从顶部功能区中单击&#x200B;**[!UICONTROL Actions]**，然后选择&#x200B;**[!UICONTROL Assign to another User]**&#x200B;选项，从下拉菜单中选择&#x200B;**[!UICONTROL Adobe API application user]**&#x200B;进行分配。
1. 重新激活该过程。
1. 对&#x200B;**[!UICONTROL Adobe Campaign Email Click]**&#x200B;任务执行相同操作。

>[!NOTE]
>
>如果您希望随时取消激活这些进程，可以在此&#x200B;**[!UICONTROL Processes]**&#x200B;屏幕中取消激活。

**相关主题**

* [为Microsoft Dynamics 365集成配](../../integrating/using/d365-acs-configure-adobe-io.md) 置AdobeIO是设置集成的下一步
* [自助服务集成应用程序](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 入门包含启动和运行集成的完整列表。
