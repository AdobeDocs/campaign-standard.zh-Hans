---
title: 为 Microsoft Dynamics 365 集成配置 Adobe IO
description: 了解如何为Microsoft Dynamics 365集成配置AdobeIO。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 2%

---


# Adobe Campaign Standard和Adobe I/OMicrosoft Dynamics 365集成配置

本文将说明如何配置Adobe Campaign Standard和Adobe I/O，使集成应用程序能够访问数据。

## 配置Adobe Campaign Standard{#campaign-standard}

### 用户档案扩展

请在Adobe Campaign Standard启用“用户档案扩展”。   这是从Microsoft Dynamics 365同步用户档案资源中的自定义字段所必需的。   启用它们的步骤有：

1. 转到“设置”->“管理”->“开发”->“发布”。
1. 单击“准备发布”以准备发布。
1. 准备完成后，选中“创建用户档案和服务Ext API”并单击“发布”。

## 配置 Adobe I/O {#adobe-io}

Adobe I/O允许您启用对Adobe Campaign Standard和其他Adobe产品的API访问。   本文将详细介绍如何配置Adobe I/O，以便让Adobe Campaign Standard与Microsoft Dynamics 365集成以同步数据。

### 概述

在执行本文中的预集成设置之前，假定您已设置并拥有对贵组织的Campaign Standard实例的管理员访问权限。  如果尚未发生这种情况，您需要与Adobe客户服务部门联系以完成活动配置。

>[!CAUTION]
>
>以下步骤需要由管理员执行。

### 配置

您需要创建新的AdobeIO项目并配置它进行集成。

#### 创建新项目

要实现此目的，请按照以下步骤操作：

1. 导航到[AdobeIO控制台](https://console.adobe.io/home#)并从屏幕右上方的下拉菜单中选择您的AdobeIMS组织ID。

1. 然后单击&#x200B;**[!UICONTROL Quick Start]**&#x200B;下的&#x200B;**[!UICONTROL Create new project]**。

   ![](assets/adobeIO1.png)

1. 在&#x200B;**[!UICONTROL Get started with your new project]**&#x200B;下，单击&#x200B;**[!UICONTROL Add API]**。

   ![](assets/adobeIO2.png)

1. 选择Adobe CampaignAPI（可能需要向底部滚动），然后单击&#x200B;**[!UICONTROL Next]**。

   ![](assets/adobeIO3.png)

1. 在下一个屏幕上，您可以选择上传您自己的公钥或让AdobeIO为您生成密钥对。 这些说明将遵循后一个选项。 如果决定让AdobeIO生成密钥对，请单击选项1;然后单击&#x200B;**[!UICONTROL Generate keypair]**&#x200B;按钮。

   ![](assets/adobeIO4.png)

1. 在下一个屏幕上，将提示您命名并选择密钥对zip文件的下载位置。

下载后，您可以解压缩文件以显示公钥和私钥。 AdobeIO已将公钥应用于AdobeIO项目。 你以后需要保留你的私钥；私钥将在集成工具的预集成设置过程中使用。

1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;继续

   ![](assets/adobeIO5.png)

1. 在下一个屏幕上，您将选择要与此项目关联的产品用户档案。 选择标题中包含的产品用户档案:活动实例的租户ID - [!UICONTROL Administrators]

   示例：Campaign Standard-您的活动租户ID —— 管理员

1. 单击 **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO6.png)

1. 在下一个屏幕上，您将看到新AdobeIO项目的详细信息。 单击屏幕左上角的&#x200B;**[!UICONTROL Add to Project]**&#x200B;并从下拉菜单中选择&#x200B;**API**。

   ![](assets/adobeIO7.png)

1. 在下一个屏幕上，您需要选择I/O事件API，然后单击&#x200B;**[!UICONTROL Next]**。

1. 在下一个屏幕上单击&#x200B;**[!UICONTROL Save the configured API]**。  您将返回到项目详细信息屏幕。

1. 现在，单击屏幕左上角的&#x200B;**[!UICONTROL Add to Project]**&#x200B;并从下拉列表中选择&#x200B;**API**，就像之前一样。

1. 在下一个屏幕上，您需要选择I/O管理API并单击&#x200B;**[!UICONTROL Next]**。

1. 在下一个屏幕上单击&#x200B;**[!UICONTROL Save the configured API]**。

活动中的预集成设置现已完成。

**相关主题**

* [为Microsoft Dynamics 365集成配](../../integrating/using/d365-acs-configure-adobe-io.md) 置AdobeIO是设置集成的下一步
* [集成自助应用程](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 序概述包含启动和运行集成的完整列表步骤。


* [AdobeIO —— 服务帐户集成](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard- API访问设置](../../api/using/setting-up-api-access.md)
* [Campaign Standard- Dynamics 365集成](../../integrating/using/d365-acs-configure-d365.md)
