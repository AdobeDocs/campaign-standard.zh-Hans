---
title: 预配和配置与 Audience Manager 或 People 核心服务的集成
description: 了解如何配置Audience Manager/人员核心服务集成，以便开始与其他Adobe Experience Cloud解决方案共享受众或区段。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: 26e37cea37b33924ac634c5e4ab7c60804a738f1
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 6%

---

# 预配和配置与 Audience Manager 或 People 核心服务的集成{#integration-with-audience-manager-or-people-core-service}

在Adobe Campaign中配置和配置Audience Manager与人员核心需要两个步骤： [向Adobe提交请求](#submitting-request-to-adobe) 则 [在Adobe Campaign中配置集成](#configuring-the-integration-in-adobe-campaign).

## 向Adobe提交请求 {#submitting-request-to-adobe}

通过Audience Manager (AAM)或People核心服务集成，您可以在Adobe Campaign中导入和导出受众或区段。

必须首先配置此集成。要请求配置此集成，请向 [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) 发送一封电子邮件，其中包含以下信息：

<table> 
 <tbody> 
  <tr> 
   <td> <strong>请求类型：</strong><br /> </td> 
   <td> 配置AAM/People核心服务 — Campaign集成 </td> 
  </tr> 
  <tr> 
   <td> <strong>组织名称：</strong><br /> </td> 
   <td> 您的组织名称 </td> 
  </tr> 
  <tr> 
   <td> <strong>IMS组织ID</strong><br /> </td> 
   <td> 您的组织ID。 <br> 要查找您的组织ID，请参阅 <a href="https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=zh-Hans">此页面</a></td> 
  </tr> 
  <tr> 
   <td> <strong>环境：</strong><br /> </td> 
   <td> 示例：生产 </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM或人员服务</strong><br /> </td> 
   <td> 示例：Adobe Audience Manager。 无论您是否拥有Audience Manager许可证，请务必向配置团队提及。</td> 
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

## 在Adobe Campaign中配置集成 {#configuring-the-integration-in-adobe-campaign}

提交此请求后，Adobe将继续为您预配集成，并联系您以提供完成配置所需的详细信息和信息：

* [步骤1：在Adobe Campaign中配置或检查外部帐户](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [步骤2：配置数据源](#step-2--configure-the-data-sources)
* [步骤3：配置Campaign跟踪服务器](#step-3--configure-campaign-tracking-server)
* [步骤4：配置访客ID服务](#step-4--configure-the-visitor-id-service)

### 步骤1：在Adobe Campaign中配置或检查外部帐户 {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

我们首先需要在Adobe Campaign中配置或检查外部帐户。 这些帐户应该已经过Adobe配置，并且应该已经向您传达了必要的信息。

为实现此操作，请执行以下步骤：

1. 从高级菜单中，选择 **管理>应用程序设置>外部帐户**.

   选择以下可用于此集成的外部帐户之一：

   ![](assets/integration_aam_1.png)

1. 输入 **[!UICONTROL Receiver server]** 以下列格式
1. 输入 **[!UICONTROL AWS Access Key ID]**， **[!UICONTROL Secret Access Key]** 和 **[!UICONTROL AWS Region]**.

您的外部帐户现在已为此集成进行了配置。

### 步骤2：配置数据源 {#step-2--configure-the-data-sources}

在Audience Manager中创建了以下两个数据源：Adobe Campaign (MID)和Adobe Campaign (DeclaredId)。 同时，这两个数据源在Adobe Campaign中可用：

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**：这是为访客ID默认配置的现成数据源。 从Campaign创建的区段将成为此数据源的一部分。
* **声明的ID** 数据源：此数据源需要创建并使用 **[!UICONTROL DeclaredId]** 数据源定义来自Audience Manager。

请注意，如果多个网站具有不同的域，则Adobe Campaign不支持基于ECID的协调。

配置 **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** 数据源：

1. 在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**，选择 **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. 选择 **[!UICONTROL Adobe Campaign]** 在 **[!UICONTROL Data Source/ Alias]** 下拉菜单。
1. 输入 **[!UICONTROL AAM Destination ID]** 由Adobe提供。

   ![](assets/integration_aam_3.png)

1. 在 **[!UICONTROL Reconciliation process]** 类别，我们建议您不要更改协调条件，并始终使用 **[!UICONTROL Visitor ID]**.
1. 单击 **[!UICONTROL Save]**。

要创建 **[!UICONTROL Declared ID]** 数据源：

1. 在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**，单击 **[!UICONTROL Create]** 按钮。
1. 编辑 **[!UICONTROL Label]** 数据源的。
1. 在 **[!UICONTROL Data Source/ Alias]** 从下拉列表中，选择与 **[!UICONTROL DeclaredID]** Audience Manager中的数据源。
1. 通过输入 **[!UICONTROL Data Source / Alias]** 和 **[!UICONTROL AAM Destination ID]** 由Adobe提供。
1. 设置 **[!UICONTROL Reconciliation process]** 根据需要。
1. 单击 **[!UICONTROL Save]**。

>[!NOTE]
>
>此 **[!UICONTROL AAM Destination ID]** 如果要为配置共享数据源，则不需要字段。 [Campaign-Triggers集成](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL Priority]** 仅在配置Triggers - Campaign集成时需要。 优先级决定先配置哪个数据源。 优先级可以是任意数字，如1或100。 优先级越高，协调期间的优先级越高。

### 步骤3：配置Campaign跟踪服务器 {#step-3--configure-campaign-tracking-server}

要配置与People核心服务或Audience Manager的集成，我们还需要配置Campaign跟踪服务器。

要使共享受众能够与访客ID配合使用，跟踪服务器域应该是已单击URL的子域或主网站。

>[!IMPORTANT]
>
> 您需要确保已在域(CNAME)上注册Campaign跟踪服务器。 有关域名配置的更多信息，请访问 [本文](https://helpx.adobe.com/cn/campaign/kb/domain-name-delegation.html).

### 步骤4：配置访客ID服务 {#step-4--configure-the-visitor-id-service}

如果从未在您的Web资产或网站上配置过访客ID服务，请参阅以下内容 [文档](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html) 了解如何配置服务或以下内容 [视频](https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html#step-two).

使用同步客户标识符与声明的ID `setCustomerID` 函数(位于包含集成代码的Experience CloudID服务中)： `AdobeCampaignID`. 此 `AdobeCampaignID` 应该与在中配置的收件人数据源中设置的协调键值匹配 [步骤2：配置数据源](#step-2--configure-the-data-sources).

您的配置和配置已完成，集成现在可用于导入和导出受众或区段。
