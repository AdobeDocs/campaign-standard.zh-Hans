---
title: 为 Microsoft Dynamics 365 集成配置 Adobe IO
description: 了解如何为Microsoft Dynamics 365集成配置Adobe IO。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 2%

---


# Adobe Campaign Standard和Adobe I/O Configuration for Microsoft Dynamics 365 integration

本文将说明如何配置Adobe Campaign Standard和Adobe I/O，以便让集成应用程序访问数据。

## 配置Adobe Campaign Standard {#campaign-standard}

### 用户档案扩展

请在Adobe Campaign Standard中启用“用户档案扩展”。   这是从Microsoft Dynamics 365同步用户档案资源中的自定义字段所必需的。   启用这些功能的步骤有：

1. 转到“设置” — >“管理” — >“开发” — >“发布”。
1. 单击“准备发布”以准备发布。
1. 准备完成后，选中“创建用户档案和服务Ext API”并单击“发布”。

## 配置 Adobe I/O {#adobe-io}

Adobe I/O允许您启用对Adobe Campaign Standard和其他Adobe产品的API访问。   本文将详细介绍如何配置Adobe I/O，以便让Adobe Campaign Standard与Microsoft Dynamics 365集成访问以同步数据。

### 概述

在执行本文中的预集成设置之前，假定您已设置并有权访问贵组织的Campaign Standard实例。  如果尚未发生这种情况，您需要与Adobe客户服务部门联系以完成活动配置。

>[!CAUTION]
>
>以下描述的步骤需要由管理员执行。

### 配置

您需要创建新的Adobe IO项目并配置它以进行集成。

#### 创建新项目

为此，请按照以下步骤操作：

1. 导航到[Adobe IO控制台](https://console.adobe.io/home#)并从屏幕右上角的下拉菜单中选择您的AdobeIMS组织ID。

1. 然后单击&#x200B;**[!UICONTROL Quick Start]**&#x200B;下的&#x200B;**[!UICONTROL Create new project]**。

   ![](assets/adobeIO1.png)

1. 在&#x200B;**[!UICONTROL Get started with your new project]**&#x200B;下，单击&#x200B;**[!UICONTROL Add API]**。

   ![](assets/adobeIO2.png)

1. 选择Adobe CampaignAPI（您可能需要向底部滚动），然后单击&#x200B;**[!UICONTROL Next]**。

   ![](assets/adobeIO3.png)

1. 在下一个屏幕上，您可以选择上传您自己的公钥，或让Adobe IO为您生成密钥对。 这些说明将遵循后一个选项。 如果您决定让Adobe IO生成密钥对，请单击选项1;然后单击&#x200B;**[!UICONTROL Generate keypair]**&#x200B;按钮。

   ![](assets/adobeIO4.png)

1. 在下一个屏幕上，系统将提示您命名并选择密钥对zip文件的下载位置。

下载后，您可以解压缩文件以显示公共密钥和私钥。 Adobe IO已将公钥应用于您的Adobe IO项目。 您以后需要保留您的私钥；在集成工具的预集成设置期间，将使用私钥。

1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;继续

   ![](assets/adobeIO5.png)

1. 在下一个屏幕上，您将选择要与此项目关联的产品用户档案。 选择标题中包含的产品用户档案:您的活动实例的租户ID - [!UICONTROL Administrators]

   示例：Campaign Standard — 您的活动-tenantID — 管理员

1. 单击 **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO6.png)

1. 在下一个屏幕上，您将看到新Adobe IO项目的详细信息。 单击屏幕左上角的&#x200B;**[!UICONTROL Add to Project]**，然后从下拉菜单中选择&#x200B;**API**。

   ![](assets/adobeIO7.png)

1. 在下一个屏幕上，您需要选择I/O事件API，然后单击&#x200B;**[!UICONTROL Next]**。

1. 在下一个屏幕上，单击&#x200B;**[!UICONTROL Save the configured API]**。  您将返回到项目详细信息屏幕。

1. 现在，单击屏幕左上角的&#x200B;**[!UICONTROL Add to Project]**&#x200B;并从下拉菜单中选择&#x200B;**API**，就像之前一样。

1. 在下一个屏幕上，您需要选择I/O管理API并单击&#x200B;**[!UICONTROL Next]**。

1. 在下一个屏幕上，单击&#x200B;**[!UICONTROL Save the configured API]**。

活动中的预集成设置现已完成。

**相关主题**

* [为Microsoft Dynamics 365集成配](../../integrating/using/d365-acs-configure-adobe-io.md) 置Adobe IO是设置集成的下一步
* [集成自助服务应](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 用程序概述包含启动和运行集成的完整列表。


* [AdobeIO — 服务帐户集成](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard- API访问设置](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Dynamics 365集成](../../integrating/using/d365-acs-configure-d365.md)
