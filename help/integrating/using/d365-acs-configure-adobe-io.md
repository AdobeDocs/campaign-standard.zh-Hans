---
title: 为Microsoft Dynamics 365集成配置Adobe Developer
description: 了解如何为Microsoft Dynamics 365集成配置Adobe Developer
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: c701043cbba22711de1ea7ddc5266e193d771e14
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 1%

---

# 用于Microsoft Dynamics 365集成的Adobe Campaign Standard和Adobe Developer配置

本文介绍如何配置Adobe Campaign Standard和Adobe I/O，以便让集成应用程序能够访问数据。

## 配置Adobe Campaign Standard {#campaign-standard}

### 配置文件扩展

请在Adobe Campaign Standard中启用“配置文件扩展”。   要将配置文件资源中的自定义字段从Microsoft Dynamics 365同步，需要此字段。   启用这些功能的步骤包括：

1. 转到“设置” — >“管理” — >“开发” — >“发布”。
1. 单击“准备发布”以准备发布。
1. 准备完成后，选中“创建Profiles &amp; Services Ext API”，然后单击“发布”。

## 配置 Adobe I/O {#adobe-io}

Adobe I/O允许您启用对Adobe Campaign Standard及其他Adobe产品的API访问。   本文将详细介绍如何配置Adobe I/O，以便授予Adobe Campaign Standard与Microsoft Dynamics 365集成以同步数据的访问权限。

### 概述

在执行本文中的预集成设置之前，假定您已配置，并且拥有组织的Campaign Standard实例的管理员访问权限。  如果尚未发生这种情况，则需要联系Adobe客户关怀团队以完成Campaign配置。

>[!CAUTION]
>
>以下描述的步骤需要由管理员执行。

### 配置

您将需要创建一个新的Adobe Developer项目并为集成配置该项目。

#### 创建新项目

要实现此目的，请执行以下步骤：

1. 导航到 [Adobe Developer控制台](https://console.adobe.io/home#) 并从屏幕右上方的下拉菜单中选择您的Adobe组织ID 。

1. 然后单击 **[!UICONTROL Create new project]** 下 **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. 下 **[!UICONTROL Get started with your new project]**，单击 **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. 选择Adobe Campaign并单击 **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. 在下一个屏幕上，您可以选择身份验证类型。 您可以选择OAuth服务器到服务器或服务帐户(JWT)。 请注意，不再建议将服务帐户(JWT)凭据用于新项目，并且已弃用，支持更新的OAuth服务器到服务器凭据。 本指南中提供的说明仅适用于OAuth服务器到服务器身份验证。

   ![](assets/adobeIO4.png)

1. 在下一个屏幕上，您将选择要与此项目关联的产品配置文件。 选择标题中包含的产品配置文件：Campaign实例的租户ID - [!UICONTROL Administrators]

   示例：Campaign Standard- your-campaign-tenantID — 管理员

1. 单击 **[!UICONTROL Save configured API]**。

   ![](assets/adobeIO5.png)

1. 在下一个屏幕上，您将看到新的Adobe Developer项目的详细信息。 单击 **[!UICONTROL Add to Project]** ，然后选择 **API** 从下拉菜单中。

   ![](assets/adobeIO6.png)

1. 在下一个屏幕中，您需要选择I/O事件API ，然后单击 **[!UICONTROL Next]**.

1. 在下一个屏幕上，单击 **[!UICONTROL Save the configured API]**.  您将会返回到项目详细信息屏幕。

1. 现在，单击 **[!UICONTROL Add to Project]** ，然后选择 **API** 从下拉列表中删除，就像您之前所做的那样。

1. 在下一个屏幕中，您需要选择I/O管理API并单击 **[!UICONTROL Next]**.

1. 在下一个屏幕上，单击 **[!UICONTROL Save the configured API]**.

Campaign中的预集成设置现已完成。

**相关主题**

* [为Microsoft Dynamics 365集成配置Adobe Developer](../../integrating/using/d365-acs-configure-adobe-io.md) 是设置集成的下一步
* [集成自助服务应用程序概述](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 包含启动并运行集成的完整步骤列表。
* [Adobe Developer — 服务帐户集成](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard- API访问设置](../../api/using/setting-up-api-access.md)
* [Campaign Standard- Dynamics 365集成](../../integrating/using/d365-acs-configure-d365.md)
* [将凭据从JWT迁移到OAuth服务器到服务器](../../integrating/using/d365-acs-self-service-app-migrate-credentials.md) 包含将凭据从JWT迁移到OAuth服务器到服务器的步骤。
