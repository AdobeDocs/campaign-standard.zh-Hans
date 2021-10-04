---
title: 为 Microsoft Dynamics 365 集成配置 Adobe IO
description: 了解如何为Microsoft Dynamics 365集成配置AdobeIO。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: 7c34df594d4f649f259fb7edd946477f7b8d92d7
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 2%

---

# Adobe Campaign Standard和Microsoft Dynamics 365集成的Adobe I/O配置

本文将介绍如何配置Adobe Campaign Standard和Adobe I/O，以授予集成应用程序访问数据的权限。

## 配置Adobe Campaign Standard {#campaign-standard}

### 配置文件扩展

请在Adobe Campaign Standard中启用“配置文件扩展”。   要从Microsoft Dynamics 365同步配置文件资源中的自定义字段，需要此字段。   启用这些功能的步骤包括：

1. 转到“设置” — >“管理” — >“开发” — >“发布”。
1. 单击“准备发布”以准备发布。
1. 准备完成后，选中“创建Profiles &amp; Services Ext API”并单击“发布”。

## 配置 Adobe I/O {#adobe-io}

Adobe I/O允许您启用对Adobe Campaign Standard和其他Adobe产品的API访问。   本文将详细介绍如何配置Adobe I/O，以便授予Adobe Campaign Standard与Microsoft Dynamics 365集成的同步数据访问权限。

### 概述

在执行本文中的集成前设置之前，我们假定您已进行配置，并且拥有对贵组织Campaign Standard实例的管理员访问权限。  如果未发生这种情况，则需要联系Adobe客户关怀团队以完成Campaign配置。

>[!CAUTION]
>
>管理员需要执行下述步骤。

### 配置

您需要创建新的AdobeIO项目并为该集成配置它。

#### 创建新项目

要实现此目的，请按照以下步骤操作：

1. 导航到[AdobeIO控制台](https://console.adobe.io/home#)，然后从屏幕右上方的下拉菜单中选择您的Adobe IMS组织ID。

1. 然后，单击&#x200B;**[!UICONTROL Quick Start]**&#x200B;下的&#x200B;**[!UICONTROL Create new project]**。

   ![](assets/adobeIO1.png)

1. 在&#x200B;**[!UICONTROL Get started with your new project]**&#x200B;下，单击&#x200B;**[!UICONTROL Add API]**。

   ![](assets/adobeIO2.png)

1. 选择Adobe Campaign API（您可能需要向底部滚动），然后单击&#x200B;**[!UICONTROL Next]**。

   ![](assets/adobeIO3.png)

1. 在下一个屏幕上，您将可以选择上传您自己的公钥，或让AdobeIO为您生成密钥对。 这些说明将遵循后一选项。 如果决定让AdobeIO生成密钥对，请单击选项1;然后单击&#x200B;**[!UICONTROL Generate keypair]**&#x200B;按钮。

   ![](assets/adobeIO4.png)

1. 在下一个屏幕上，系统将提示您命名并选择密钥对zip文件的下载位置。

下载后，您可以解压缩文件以显示公钥和私钥。 AdobeIO已将公共密钥应用于您的AdobeIO项目。 您以后需要保留私钥；私钥将在集成工具的预集成设置期间使用。

1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;继续

   ![](assets/adobeIO5.png)

1. 在下一个屏幕中，您将选择要与此项目关联的产品配置文件。 选择标题中包含的产品配置文件：Campaign实例的租户ID - [!UICONTROL Administrators]

   示例：Campaign Standard- your-campaign-tenantID — 管理员

1. 单击 **[!UICONTROL Save configured API]**。

   ![](assets/adobeIO6.png)

1. 在下一个屏幕中，您将看到新AdobeIO项目的详细信息。 单击屏幕左上角的&#x200B;**[!UICONTROL Add to Project]** ，然后从下拉菜单中选择&#x200B;**API**。

   ![](assets/adobeIO7.png)

1. 在下一个屏幕上，您需要选择I/O事件API，然后单击&#x200B;**[!UICONTROL Next]**。

1. 在下一个屏幕上，单击&#x200B;**[!UICONTROL Save the configured API]**。  您将返回到项目详细信息屏幕。

1. 现在，单击屏幕左上角的&#x200B;**[!UICONTROL Add to Project]**，然后像之前一样从下拉菜单中选择&#x200B;**API**。

1. 在下一个屏幕上，您需要选择I/O管理API并单击&#x200B;**[!UICONTROL Next]**。

1. 在下一个屏幕上，单击&#x200B;**[!UICONTROL Save the configured API]**。

Campaign中的预集成设置现已完成。

**相关主题**

* [为Microsoft Dynamics 365集成配置Adobe](../../integrating/using/d365-acs-configure-adobe-io.md) IO是设置集成的下一步
* [集成自助服务应用](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 程序概述包含启动和运行集成的完整步骤列表。


* [AdobeIO — 服务帐户集成](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard- API访问设置](../../api/using/setting-up-api-access.md)
* [Campaign Standard- Dynamics 365集成](../../integrating/using/d365-acs-configure-d365.md)
