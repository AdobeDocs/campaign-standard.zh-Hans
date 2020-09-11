---
title: 为 Microsoft Dynamics 365 集成配置 Adobe IO
description: 了解如何为Microsoft Dynamics 365集成配置AdobeIO。
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 801741bd605d11d1c9f88995286ef206dd46470f
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 3%

---


# 为 Microsoft Dynamics 365 集成配置 Adobe IO

在跨渠道通信中激活CRM数据：了解预集成设置过程中所需的步骤，以创建新的AdobeIO项目并为Microsoft Dynamics 365集成配置它。

## 概述

Adobe Campaign Standard-本页介绍了Microsoft Dynamics 365 [集成](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。

在执行本文中的预集成设置之前，假定您已设置并拥有对贵组织的Campaign Standard实例的管理员访问权限。  如果尚未发生这种情况，您需要与Adobe客户服务部门联系以完成活动配置。

>[!CAUTION]
>
>以下步骤需要由管理员执行。

## 配置

您需要创建新的AdobeIO项目并配置它进行集成。

### 创建新项目

要实现此目的，请按照以下步骤操作：

1. 导航到 [AdobeIO控制台](https://console.adobe.io/home#) ，然后从屏幕右上方的下拉菜单中选择您的AdobeIMS组织ID。

1. 然后单击下 **[!UICONTROL Create new project]** 面的 **[!UICONTROL Quick Start]**。

![](assets/adobeIO1.png)

1. 在 **[!UICONTROL Get started with your new project]**&#x200B;下，单击 **[!UICONTROL Add API]**。

![](assets/adobeIO2.png)

1. 选择Adobe CampaignAPI（可能需要向底部滚动），然后单击“下一步”。

![](assets/adobeIO3.png)

1. 在下一个屏幕上，您可以选择上传您自己的公钥或让AdobeIO为您生成密钥对。 这些说明将遵循后一个选项。 如果决定让AdobeIO生成密钥对，请单击选项1;然后单击“生成密钥对”按钮。

![](assets/adobeIO4.png)

1. 在下一个屏幕上，将提示您命名并选择密钥对zip文件的下载位置。

下载后，您可以解压缩文件以显示公钥和私钥。 AdobeIO已将公钥应用于AdobeIO项目。 你以后需要保留你的私钥；私钥将在集成工具的预集成设置过程中使用。

1. 单击“下一步”继续

![](assets/adobeIO5.png)

1. 在下一个屏幕上，您将选择要与此项目关联的产品用户档案。

1. 选择标题中包含的产品用户档案:活动实例的租户ID - [!UICONTROL Administrators] 示例：Campaign Standard-您的活动租户ID —— 管理员

1. 单击 [!UICONTROL Save configured API]。

![](assets/adobeIO6.png)

1. 在下一个屏幕上，您将看到新AdobeIO项目的详细信息。

1. 单击屏幕左上角的“添加到项目”，并从下拉菜单中选择“API”。

![](assets/adobeIO7.png)

1. 在下一个屏幕上，您需要选择I/O事件API，然后单击“下一步”。

1. 在下一个屏幕上，单击“保存已配置的API”。  您将返回到项目详细信息屏幕。

1. 现在，单击屏幕左上角的“添加到项目”，并从下拉菜单中选择“API”，就像之前一样。

1. 在下一个屏幕上，您需要选择I/O管理API并单击“下一步”。

1. 在下一个屏幕上，单击“保存已配置的API”。

活动中的预集成设置现已完成。  继续完 [成Microsoft Dynamics 365的预集成设置](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

**相关主题**

* [AdobeIO —— 服务帐户集成](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard- API访问设置](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#setting-up-api-access)
* [Campaign Standard- Dynamics 365集成](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)