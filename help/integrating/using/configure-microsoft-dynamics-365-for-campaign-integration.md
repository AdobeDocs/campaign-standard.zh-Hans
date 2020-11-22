---
solution: Campaign Standard
product: campaign
title: 为 Campaign 集成配置 Microsoft Dynamics 365
description: 了解如何配置Microsoft Dynamics 365以实现活动集成。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 2%

---


# 为 Campaign 集成配置 Microsoft Dynamics 365

了解如何配置Microsoft Dynamics 365集成并激活与Adobe Campaign Standard的跨渠道通信的CRM数据。

## 概述

Adobe Campaign Standard-本页介绍了Microsoft Dynamics 365 [集成](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。

需要为此集成配置三个系统：

1. Adobe Campaign Standard-了 [解更多](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
1. Microsoft Dynamics 365 for Sales —— 描述如下
1. 集成工具——由Adobe咨询团队拥有

配置后，这些系统需要由管理员进行配置。

本文重点介绍在Microsoft Dynamics 365端，在预集成设置过程中需要的步骤，以使客户能够使用Adobe Campaign Standard- Microsoft Dynamics 365集成。

>[!NOTE]
>
>在今年晚些时候提供自助服务工具的UI之前，入职团队将帮助您配置集成。

## 先决条件

在此文档中执行集成前设置之前，假定您已配置并拥有对贵组织的Microsoft Dynamics 365实例的管理员访问权限。  如果尚未发生这种情况，您需要联系Microsoft客户支持以完成Dynamics 365配置。

如果要为登台和生产环境配置集成，您需要为登台和生产Dynamics 365实例执行以下步骤。 以下几条说明根据您是配置舞台还是生产Dynamics 365实例而略有不同(例如，对于生产实例，选择“prod” `<stage or prod>`)

## 设置应用程序和权限

OAuth访问令牌允许集成工具通过Web API与Microsoft Dynamics 365实例进行身份验证，以便将Campaign Standard体验事件发布到Microsoft Dynamics 365界面的时间轴视图。

以下视频概述了主要步骤：

>[!VIDEO](https://video.tv.adobe.com/v/27637)

要生成OAuth访问令牌，请按照以下步骤操作。

### 注册新应用程序

1. 在管理员登录下，登录portal.azure.com。

1. 单击左 **[!UICONTROL Azure Active Directory]** 侧菜单中的；然后，单 **[!UICONTROL App registrations]** 击出现的子菜单。

1. 单 **[!UICONTROL New registration]** 击屏幕顶部。

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. 填写应用程序注册屏幕：

   * 名称：adobe活动 `<stage or prod>`
   * 支持的帐户类型： **[!UICONTROL Accounts in this organizational directory only]** （默认值）

有关创建新应用程序的详细信息，请参 [阅本节](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。

>[!NOTE]
>
>Azure AD为您的应用程序分配一个唯一的应用程序（客户端）ID。 您以后在配置Dynamics 365时以及在为集成工具执行预集成设置时需要此ID。

### 生成客户端机密

1. 在应用程序概述屏幕左侧的子菜单中，单击 **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. 输入描述，设置持续时间，然后单击 **[!UICONTROL OK]**。

您的客户机密已创建。 在完成集成工具的预集成设置时暂时保留该值。

>[!CAUTION]
>
>根据需要保留此值以完成集成工具的预集成设置。 之后无法检索它。


### 设置权限

1. 在此屏幕或应用程序概述屏幕中， **[!UICONTROL API permissions]** 单击左侧子菜单中的。  单击 **[!UICONTROL Add a permission]**&#x200B;后，您需要在菜 **[!UICONTROL Dynamics CRM]** 单中进行选择。

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. 然后，选中该框 **[!UICONTROL user_impersonation]**&#x200B;并单击该 **[!UICONTROL Add permissions]** 按钮。

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

有关权限设置的详细信息，请参 [阅此部分](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis)。

### 创建应用程序用户

此新用户是通用用户。 它将由应用程序使用：此用户将使用API对Microsoft Dynamics 365进行任何更改。 要创建它，请按照以下步骤操作：

1. 导航到Dynamics 365实例，以管理员身份登录。

1. 单击右上角的齿轮图标，然后单击 **[!UICONTROL Advanced Settings]**。 在顶部横幅中，单击旁边的下 **[!UICONTROL Settings]**&#x200B;拉框，单 **[!UICONTROL Security > Users]**&#x200B;击。

1. 单击下拉菜单转到 **[!UICONTROL Application Users]**。 单击 **[!UICONTROL New]**.

1. 确保下拉菜单（位于用户图标旁边） **[!UICONTROL USER:APPLICATION USER]**。

   为新用户填写屏幕。  参数建议：

   * **[!UICONTROL User Name]** （电子邮件）:adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot;(例如，adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**:您在Azure AD中注册的应用程序的ID（此为必需）
   * 您可以留空 **[!UICONTROL Application ID URI]** , **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**:AdobeAPI `<stage or prod>`
   * **[!UICONTROL Email]**:与(或 **[!UICONTROL User Name]** 管理员的电子邮件（如果您愿意）相同

   有关应用程序用户创建的详细信息，请参 [阅此部分](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user)。

1. 单击用户图标并上传Adobe Campaign图标；这是当Dynamics 365中出现新视图事件时，将在时间轴Adobe中显示的图标。

<!-- ***getfile*** adobe campaign logo-->

1. 单击顶部功能区，打开用 **[!UICONTROL MANAGE ROLES]** 户角色列表。

1. 向下滚动并选 **[!UICONTROL System administrator]** 择此用户的访问权限。

1. 单击 **[!UICONTROL OK]**.

### 获取租户ID

按照本页 [中的说明](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) ，查找您的租户ID。  在集成工具中的预集成设置过程中，您将需要此ID。

## 安装Microsoft Dynamics 365的Campaign Standard

要将Dynamics 365应用程序集成到您的Campaign Standard环境，请按照以下步骤操作：

1. 导航到以下链接： [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) 并在搜索 _栏中搜索_ Dynamics 365的Adobe Campaign。
或者，您也可以导航到此 [链接](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)。
1. 按照说明为Dynamics 365实例安装应用程序。
1. 安装后，导航到Dynamics 365实例并以管理员身份登录。
1. 单击右上角的齿轮图标，然后单击 **[!UICONTROL Advanced Settings]**。 在顶部横幅中，单击旁边的下 **[!UICONTROL Settings]**&#x200B;拉框，单 **[!UICONTROL Processes]** 击下 **[!UICONTROL Process Center]**。
1. 搜索 **[!UICONTROL Adobe Campaign Email Bounce]** 任务并单击它。
1. 在选项 **[!UICONTROL Administration]** 卡上，将所有者更改为之前创建的AdobeAPI应用程序用户，方法是从顶部功能区 **[!UICONTROL Actions]** 中单击，然后选择 **[!UICONTROL Assign to another User]** 选项，从下 **[!UICONTROL Adobe API application user]** 拉列表中选择以分配。
1. 重新激活该过程。
1. 为任务做同样的 **[!UICONTROL Adobe Campaign Email Click]** 事。

>[!NOTE]
>
>如果您希望随时取消激活这些进程，可以在此屏幕中取消激 **[!UICONTROL Processes]** 活。

**相关主题**

* [Campaign Standard- Microsoft Dynamics 365集成](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [为 Microsoft Dynamics 365 集成配置 Adobe IO](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
