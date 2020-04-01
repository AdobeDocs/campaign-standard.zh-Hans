---
title: 为Microsoft Dynamics 365集成配置Unifi
description: 了解如何为Microsoft Dynamics 365集成配置Unifi
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---



# 为Microsoft Dynamics 365集成配置Unifi

配置Unifi以设置和激活Microsoft Dynamics 365 -Adobe Campaign集成。

## 先决条件

在执行本文中的置备后步骤之前，假定您已经成功地完成了活动和 [Dynamics 365的置备后](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)[步骤](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。  如果尚未发生这种情况，您需要按照这些步骤完成Campaign Standard和Dynamics 365后置备。

还假定您已联系Unifi，已为您创建了Unifi帐户，并已成功登录。  如果尚未发生这种情况，请按照本文中所述的 [步骤操作](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。

>[!CAUTION]
>
>在配置Unifi时，强烈建议您与Unifi和／或Adobe咨询（联系您的Adobe CSM）合作。

## 配置活动集成

在第一次连接时，单击 **[!UICONTROL Adobe Campaign Standard]** 以输入活动凭据。

这些凭据大多来自您在Campaign Standard配置步骤期间在Adobe I/O控制台中创建 [的集成](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)。

>[!NOTE]
>
>为确保安全性和隐私，在重新访问这些配置屏幕时，敏感凭据字段显示为空。

1. 对于Adobe身份验证URL，请输入 `https://ims-na1.adobelogin.com/ims/exchange/jwt`

1. 输入您 **[!UICONTROL Adobe IO Organization ID]** 和您的 **[!UICONTROL Adobe IO Integration ID]**。

要获取您的Adobe IO组织和集成ID，请导航到“通过Adobe I/O控制台集成”屏幕并记下Web URL。

它应该是这样的：, `https://console.adobe.io/integrations/<Org ID>/<Int ID>/overview`其中组织ID和整体ID是数字。

1. 输入 **[!UICONTROL Tenant ID]**

要获取您的租户ID，请执行以下步骤：

1. 导航到 [Adobe Admin Console](https://adminconsole.adobe.com/) ，然后从右上下拉菜单中选择您的IMS组织。
1. 选择您的Adobe Campaign标准产品，然后选择您的Campaign Standard实例（如果您有多个）。  这将带来一列表的产品用户档案。

   产品用户档案描述通常以下列格式之一显示，其中 `<tenantID>` 是实例的租户ID。

`Campaign Standard – https://<tenantID> - <ROLE>`

`Campaign Standard – <tenantID> - <ROLE>`

>[!NOTE]
>
>如果您在识别租户ID时遇到问题，请联系您> Adobe技术联系人或Adobe客户关怀。
>
>合作伙伴沙箱实例租户ID通常遵循 `https://<tenantId>`模式，其 `tenantId` 中为 `tbd.campaign-sandbox.adobe.com`。

1. 输入您的 **[!UICONTROL Campaign Instance ID]**。

要获取您的实例ID，请按照以下步骤操作：

    1. 在Web浏览器中输入“https://&lt;acs-instance-url>/r/test”，将“&lt;acs-instance-url>”替换为Campaign Standard实例的URL。
    1. 响应将包含“instance=”，后跟实例ID。

1. 选择活动实例的区域。

1. 您可以留空 **[!UICONTROL Base Directory]** 的。

1. 选择选 **[!UICONTROL Allow as Output Destination]** 项。

设置参数后，单击并检 **[!UICONTROL CONNECT]** 查连接是否成功。

否则，单击并 **[!UICONTROL CLOSE]** 检查参数。

>[!NOTE]
>
>如果您无法完成此步骤，请与 [Unifi客户服务联系](mailto:support@unifisoftware.atlassian.net)。

## 配置Dynamics 365集成

单击Microsoft Dynamics CRM以配置Dynamics 365凭据。 这些凭据大多来自您在Microsoft Dynamics 365配置步骤期间在Microsoft Dynamics 365中创建的集成。

>[!NOTE]
>
>为确保安全性和隐私，在重新访问这些配置屏幕时，敏感凭据字段显示为空。

1. 对 **[!UICONTROL URL]**&#x200B;于，输入Dynamics 365实例的URL，注意在“.crm”(例如， `https://mydynamicsinstance.api.crm.dynamics.com`)前插入“.api”

1. 对于 **[!UICONTROL clientid]**，您将使用在创建应用程序注册时生成的应用程序 ID配置 [Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

1. 对于 **[!UICONTROL clientsecret]**，您将使用在配置Dynamics 365时向应用程序注册添加客户端机密时生成 [的客户端机密](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

1. 对于 **[!UICONTROL callbackurl]**，添加 `http://localhost:33333`。

1. 对于 **[!UICONTROL refresh token]**，留空。

1. 对 **[!UICONTROL于租户ID]**，请使用您从portal.azure.com获得的租户ID配置 [Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

1. 最后，选中该框 **[!UICONTROL Allow as Output Destination]**。

输入参数后，单击并 **[!UICONTROL CONNECT]** 检查连接是否成功。

否则，单击并 **[!UICONTROL CLOSE]** 检查参数。

>[!NOTE]
>
>如果您无法完成此步骤，请与 [Unifi客户服务联系](mailto:support@unifisoftware.atlassian.net)。

## 完成唯一设置

设置凭据后，您需要通知Unifi，因为在完成集成设置之前需要执行一些其他步骤。  联系您收到的Unifi联系信息，以指示您已设置凭据。

您需要选择退出选项，并在完成后通知Unifi（指示Unifi正在选择哪个退出选项）。  有关退出选项的说明，请参阅《Unifi用户指 [南》](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn)。

Unifi完成其工作后，他们将通知您并提供进一步信息，以帮助您配置Unifi实例，运行一次数据入口，然后，成功完成后，您可以启用计划。

建议对于各种用例使用以下频率：

* 入口：每15分钟
* 进度：每15分钟
* 删除：每天
* 选择退出：每天

>[!NOTE]
>
>默认情况下，SEND营销事件会从出口作业中筛选出来。  如果您希望在Dynamics 365中看到“发送营销事件”，则需要在Unifi中修改出口作业的过滤器（步骤5）。

Unifi中有两个不同的角色，一个所有者用户和一个只读分析师用户。 所有者用户可以修改作业和计划，而只读分析师则不能。  给定客户实例只能有一个所有者用户。  如果客户需要更改分配为所有者用户的个人，他们可以向adobe-support@unifisoftware.com [](mailto:adobe-support@unifisoftware.com)。

以下视频中显示了统一配置、作业详细信息、设置和监视。

## Unifi Jobs

### Unifi作业概述

>[!VIDEO](https://video.tv.adobe.com/v/27392)

此视频介绍了与Microsoft Dynamics 365（02:10分钟）进行Adobe Campaign标准集成所需的不同Unifi作业

### Unifi作业详细信息：入口和出口

>[!VIDEO](https://video.tv.adobe.com/v/27396)

此视频介绍Unifi中的进入和出口作业（04:27分钟）

### 操作化和监控

>[!VIDEO](https://video.tv.adobe.com/v/27391)

此视频介绍工作流和计划（03:03分钟）

更像这样
* [使用Adobe Campaign标准版- Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [配置Microsoft Dynamics 365以实现活动集成](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
* [为Microsoft Dynamics 365配置Adobe IO -Campaign Standard集成](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Microsoft Dynamics 365集成功能页](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)