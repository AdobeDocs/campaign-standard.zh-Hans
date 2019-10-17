---
title: 配置与Audience manager或People核心服务的集成
seo-title: 配置与Audience manager或People核心服务的集成
description: 配置与Audience manager或People核心服务的集成
seo-description: '了解如何配置Audience Manager/People核心服务集成，以开始使用不同的Adobe Experience cloud解决方案共享受众或细分。 '
page-status-flag: 从未激活
uuid: e7329644-0033-4729-b4a7-61bef137f4b5
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用Campaign和Audience manager或People核心服务
discoiquuid: eb24f4ea-325f-433a-91a0-c45906320bcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 90bb41ae78fe6fbcca0bd359c169adde4efd4b1b

---


# 配置与Audience manager或People核心服务的集成{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

在Adobe Campaign中设置和配置Audience manager和People核心需要执行两个步骤：向Adobe [提交请求](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#submitting-request-to-adobe) ，然 [后在Adobe Campaign中配置集成](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#configuring-the-integration-in-adobe-campaign)。

## 向Adobe提交请求 {#submitting-request-to-adobe}

Audience Manager(AAM)或People核心服务集成允许您在Adobe Campaign中导入和导出受众或区段。

必须首先配置此集成。 要请求提供此集成，请向Digital-Request@adobe.com发送一封电 [子邮件](mailto:Digital-Request@adobe.com) ，其中包含以下信息：

<table> 
 <tbody> 
  <tr> 
   <td> <strong>请求类型：</strong><br /> </td> 
   <td> 配置AAM/People核心服务- Campaign集成 </td> 
  </tr> 
  <tr> 
   <td> <strong>组织名称：</strong><br /> </td> 
   <td> 您的组织名称 </td> 
  </tr> 
  <tr> 
   <td> <strong>IMS组织ID</strong><br /> </td> 
   <td> 您的IMS组织ID。 <br> 您可以在Experience cloud的“管理”菜单中找到您的IMS组织ID。 首次连接到Adobe Experience cloud时也会提供该功能。 </td> 
  </tr> 
  <tr> 
   <td> <strong>环境：</strong><br /> </td> 
   <td> 示例：制作 </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM或People Service</strong><br /> </td> 
   <td> 示例：Adobe Audience Manager </td> 
  </tr> 
  <tr> 
   <td> <strong>声明的ID或访客ID</strong><br /> </td> 
   <td> 示例：声明的ID </td> 
  </tr> 
  <tr> 
   <td> <strong>其他信息</strong><br /> </td> 
   <td> 您可能拥有的任何有用信息或评论 </td> 
  </tr> 
 </tbody> 
</table>

*适 **[!UICONTROL Declared ID]** 用于所有共享受众集成。 请注意，如果您使用的是People核心服务，则使用的情况会 **[!UICONTROL Declared ID]** 因解决方案而异：

* 如果受众通过People核心服务从Adobe Campaign共享到Adobe Target，则可 **[!UICONTROL Declared ID]** 以进行配置。
* 如果受众是通过People核心服务从Adobe Campaign共享到Ad Cloud的，您将无法使用配置来对受 **[!UICONTROL Declared ID]** 众进行历史回填。 在构建受众时，还会出现一些延迟。
* 如果受众是通过People Core service从Adobe Analytics共享到Adobe Campaign的，则不会在Adobe Campaign中填充区段 **[!UICONTROL Declared ID]**。

如果您使用的是Adobe Audience Manager而不是People Core Service，则所有情 **[!UICONTROL Declared ID]** 况下都可正常使用。

您可以向以下地址提 **[!UICONTROL Declared ID]** 出供应请求： [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com)。

## 在Adobe Campaign中配置集成 {#configuring-the-integration-in-adobe-campaign}

提交此请求后，Adobe将继续为您提供集成，并与您联系以提供您必须完成配置的详细信息和信息：

* [第1步：在Adobe Campaign中配置或检查外部帐户](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [第2步：配置数据源](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)
* [第3步：配置系列活动跟踪服务器](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-3--configure-campaign-tracking-server)
* [第4步：配置访客ID服务](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-4--configure-the-visitor-id-service)

### 第1步：在Adobe Campaign中配置或检查外部帐户 {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

我们首先需要在Adobe Campaign中配置或检查外部帐户。 这些帐户应由Adobe配置，并且必要的信息应已通知您。

为此，请执行以下操作：

1. 从高级菜单中，选择“管 **理”&gt;“应用程序设置”&gt;“外部帐户**”。

   选择以下可用于此集成的外部帐户之一：

   ![](assets/integration_aam_1.png)

1. 按以 **[!UICONTROL Receiver server]** 下格式输入
1. 输入 **[!UICONTROL AWS Access Key ID]**&#x200B;和 **[!UICONTROL Secret Access Key]** 和 **[!UICONTROL AWS Region]**。

您的外部帐户现在已配置用于此集成。

### 第2步：配置数据源 {#step-2--configure-the-data-sources}

以下两个数据源是在Audience manager中创建的：Adobe Campaign(MID)和Adobe Campaign(DeclaredId)。 同时，Adobe Campaign中提供了以下两个数据源：

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:这是默认为访客ID配置的现成数据源。 从Campaign创建的区段将是此数据源的一部分。
* **声明的ID** 数据源：此数据源需要创建并映射到Audience Manager中 **[!UICONTROL DeclaredId]** 的数据源定义。

请注意，如果多个网站具有不同的域，则Adobe Campaign不支持基于ECID进行协调。

配置数 **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** 据源：

1. 在 **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**&#x200B;中，选择 **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**。

   ![](assets/integration_aam_2.png)

1. 在 **[!UICONTROL Adobe Campaign]** 下拉 **[!UICONTROL Data Source/ Alias]** 框中选择。
1. 输入Adobe **[!UICONTROL AAM Destination ID]** 提供的内容。

   ![](assets/integration_aam_3.png)

1. 在类 **[!UICONTROL Reconciliation process]** 别中，我们建议您不要更改协调标准并始终使用 **[!UICONTROL Visitor ID]**。
1. Click **[!UICONTROL Save]**.

要创建数据 **[!UICONTROL Declared ID]** 源，请执行以下操作：

1. 在 **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**&#x200B;中，单击按 **[!UICONTROL Create]** 钮。
1. 编辑 **[!UICONTROL Label]** 数据源。
1. 在下拉 **[!UICONTROL Data Source/ Alias]** 列表中，选择与Audience manager中的数据源相 **[!UICONTROL DeclaredID]** 应的数据源。
1. 通过输入Adobe提供的和配 **[!UICONTROL Data Source / Alias]** 置您 **[!UICONTROL AAM Destination ID]** 的数据源。
1. 根据需 **[!UICONTROL Reconciliation process]** 要设置。
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>如果 **[!UICONTROL AAM Destination ID]** 要配置共享数据源以进行 [Campaign-Triggers集成，则不需要此字段](../../integrating/using/configuring-triggers-in-experience-cloud.md)。 **[!UICONTROL Priority]** 仅在配置触发器——营销活动集成时需要。 优先级决定首先配置哪个数据源。 优先级可以是任意数字，如1或100。 优先级越高，协调期间的偏好越高。

### 第3步：配置系列活动跟踪服务器 {#step-3--configure-campaign-tracking-server}

要配置与People Core服务或Audience Manager的集成，我们还需要配置Campaign Tracking Server。

在此，您需要确保系列活动跟踪服务器已在域(CNAME)上注册。 您可以在本文中找到有关域名委托的更 [多信息](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/Technotes/AdobeCampaign_Deliverability_Sub_Domain_Delegation.pdf)。

### 第4步：配置访客ID服务 {#step-4--configure-the-visitor-id-service}

如果您的访客ID服务从未在您的Web属性或网站上配置过，请参阅以下文档 [](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-aam-analytics.html) ，了解如何配置服务或以下视 [频](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two)。

您的配置和配置已完成，该集成现在可用于导入和导出受众或区段。
