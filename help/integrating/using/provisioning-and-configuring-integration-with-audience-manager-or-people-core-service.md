---
solution: Campaign Standard
product: campaign
title: 预配和配置与 Audience Manager 或 People 核心服务的集成
description: '了解如何使用不同的Adobe Experience Cloud解决方案将Audience Manager/人员核心服务集成配置为开始共享受众或细分。 '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 9%

---


# 预配和配置与 Audience Manager 或 People 核心服务的集成{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

在Adobe Campaign中设置和配置Audience Manager和People核心需要执行两个步骤：[将请求提交到Adobe](#submitting-request-to-adobe)，然后[配置Adobe Campaign](#configuring-the-integration-in-adobe-campaign)中的集成。

## 向 Adobe 提交请求 {#submitting-request-to-adobe}

Audience Manager(AAM)或People核心服务集成允许您在Adobe Campaign中导入和导出受众或区段。

必须首先配置此集成。要请求配置此集成，请向 [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) 发送一封电子邮件，其中包含以下信息：

<table> 
 <tbody> 
  <tr> 
   <td> <strong>请求类型：</strong><br /> </td> 
   <td> 配置AAM/People核心服务 — 活动集成 </td> 
  </tr> 
  <tr> 
   <td> <strong>组织名称：</strong><br /> </td> 
   <td> 您的组织名称 </td> 
  </tr> 
  <tr> 
   <td> <strong>IMS 组织 ID</strong><br /> </td> 
   <td> 您的IMS组织ID。 <br> 您可以在“管理”菜单的Experience Cloud上找到您的IMS组织ID。在您首次连接到Adobe Experience Cloud时也会提供此组件。 </td> 
  </tr> 
  <tr> 
   <td> <strong>环境:</strong><br /> </td> 
   <td> 示例：制作 </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM或People Service</strong><br /> </td> 
   <td> 示例：Adobe Audience Manager。 请务必向供应团队提及您是否拥有Audience Manager许可证。</td> 
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

## 在Adobe Campaign {#configuring-the-integration-in-adobe-campaign}中配置集成

提交此请求后，Adobe将继续为您提供集成，并与您联系以提供您必须完成配置的详细信息和信息：

* [第1步：在Adobe Campaign中配置或检查外部帐户](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [第2步：配置数据源](#step-2--configure-the-data-sources)
* [第3步：配置活动跟踪服务器](#step-3--configure-campaign-tracking-server)
* [第4步：配置访客ID服务](#step-4--configure-the-visitor-id-service)

### 第1步：在Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}中配置或检查外部帐户

我们首先需要在Adobe Campaign中配置或检查外部帐户。 这些帐户应已由Adobe配置，并应已向您发送必要的信息。

为实现此操作，请执行以下步骤：

1. 从高级菜单中，选择&#x200B;**“管理”>“应用程序设置”>“外部帐户”**。

   选择以下可用于此集成的外部帐户之一：

   ![](assets/integration_aam_1.png)

1. 按以下格式输入&#x200B;**[!UICONTROL Receiver server]**
1. 输入&#x200B;**[!UICONTROL AWS Access Key ID]**、**[!UICONTROL Secret Access Key]**&#x200B;和&#x200B;**[!UICONTROL AWS Region]**。

您的外部帐户现在已配置用于此集成。

### 第2步：配置数据源{#step-2--configure-the-data-sources}

以下两个数据源是在受众管理器中创建的：Adobe Campaign(MID)和Adobe Campaign(DeclaredId)。 同时，这两个数据源在Adobe Campaign中可用：

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:这是默认为访客ID配置的现成数据源。从活动创建的区段将是此数据源的一部分。
* **声明** 的ID数据源：需要创建此数据源并将其与来自Audience Manager **[!UICONTROL DeclaredId]** 的数据源定义映射。

请注意，对于具有不同域的多个网站，Adobe Campaign不支持基于ECID的协调。

配置&#x200B;**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**&#x200B;数据源：

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;中，选择&#x200B;**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**。

   ![](assets/integration_aam_2.png)

1. 在&#x200B;**[!UICONTROL Data Source/ Alias]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Adobe Campaign]**。
1. 输入由Adobe提供的&#x200B;**[!UICONTROL AAM Destination ID]**。

   ![](assets/integration_aam_3.png)

1. 在&#x200B;**[!UICONTROL Reconciliation process]**&#x200B;类别中，我们建议您不要更改对帐标准并始终使用&#x200B;**[!UICONTROL Visitor ID]**。
1. 单击 **[!UICONTROL Save]**.

要创建&#x200B;**[!UICONTROL Declared ID]**&#x200B;数据源：

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;中，单击&#x200B;**[!UICONTROL Create]**&#x200B;按钮。
1. 编辑数据源的&#x200B;**[!UICONTROL Label]**。
1. 在&#x200B;**[!UICONTROL Data Source/ Alias]**&#x200B;下拉列表中，选择与来自Audience Manager的&#x200B;**[!UICONTROL DeclaredID]**&#x200B;数据源对应的数据源。
1. 输入Adobe提供的&#x200B;**[!UICONTROL Data Source / Alias]**&#x200B;和&#x200B;**[!UICONTROL AAM Destination ID]**，配置数据源。
1. 根据需要设置&#x200B;**[!UICONTROL Reconciliation process]**。
1. 单击 **[!UICONTROL Save]**.

>[!NOTE]
>
>如果要为[活动-Triggers集成](../../integrating/using/configuring-triggers-in-experience-cloud.md)配置共享数据源，则不需要&#x200B;**[!UICONTROL AAM Destination ID]**&#x200B;字段。 **[!UICONTROL Priority]** 仅当配置触发器时才需要 — 活动集成。优先级决定首先配置哪个数据源。 优先级可以是任意数字，如1或100。 优先级越高，在协调期间的偏好越高。

### 第3步：配置活动跟踪服务器{#step-3--configure-campaign-tracking-server}

要配置与People Core服务或受众管理器的集成，我们还需要配置活动跟踪服务器。

在此，您需要确保活动跟踪服务器已在域(CNAME)上注册。 可在[本文](https://helpx.adobe.com/cn/campaign/kb/domain-name-delegation.html)中找到有关域名配置的更多信息。

### 第4步：配置访客ID服务{#step-4--configure-the-visitor-id-service}

如果您的访客ID服务从未在您的Web属性或网站上配置过，请参阅以下[文档](https://docs.adobe.com/content/help/en/id-service/using/implementation/setup-aam-analytics.html)，了解如何配置您的服务或以下[视频](https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html#step-two)。

您的配置和设置已完成，集成现在可用于导入和导出受众或区段。
