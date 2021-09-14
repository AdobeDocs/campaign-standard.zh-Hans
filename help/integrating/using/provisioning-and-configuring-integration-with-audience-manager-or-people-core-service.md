---
title: 预配和配置与 Audience Manager 或 People 核心服务的集成
description: '了解如何配置Audience Manager/人员核心服务集成，以便开始与不同的Adobe Experience Cloud解决方案共享受众或区段。 '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 9%

---

# 预配和配置与 Audience Manager 或 People 核心服务的集成{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

在Adobe Campaign中配置和配置Audience Manager和人员核心需执行以下两个步骤：[向Adobe提交请求](#submitting-request-to-adobe)，然后[在Adobe Campaign中配置集成](#configuring-the-integration-in-adobe-campaign)。

## 向 Adobe 提交请求 {#submitting-request-to-adobe}

Audience Manager(AAM)或人员核心服务集成允许您在Adobe Campaign中导入和导出受众或区段。

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
   <td> <strong>IMS 组织 ID</strong><br /> </td> 
   <td> 您的IMS组织ID。 <br> 您可以在Experience Cloud的“管理”菜单中找到您的IMS组织ID。首次连接到Adobe Experience Cloud时，也会提供该服务。 </td> 
  </tr> 
  <tr> 
   <td> <strong>环境:</strong><br /> </td> 
   <td> 示例：生产 </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM或People Service</strong><br /> </td> 
   <td> 示例：Adobe Audience Manager。 请务必向配置团队提及您是否拥有Audience Manager许可证。</td> 
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

提交此请求后，Adobe将继续为您配置集成，并与您联系以提供完成配置所需的详细信息和信息：

* [步骤1:在Adobe Campaign中配置或检查外部帐户](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [步骤2:配置数据源](#step-2--configure-the-data-sources)
* [步骤3:配置促销活动跟踪服务器](#step-3--configure-campaign-tracking-server)
* [步骤4:配置访客ID服务](#step-4--configure-the-visitor-id-service)

### 步骤1:在Adobe Campaign中配置或检查外部帐户 {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

我们首先需要在Adobe Campaign中配置或检查外部帐户。 这些帐户应按Adobe进行配置，并且应将必要的信息通知您。

为实现此操作，请执行以下步骤：

1. 从高级菜单中，选择&#x200B;**管理>应用程序设置>外部帐户**。

   选择可用于此集成的以下外部帐户之一：

   ![](assets/integration_aam_1.png)

1. 按以下格式输入&#x200B;**[!UICONTROL Receiver server]**
1. 输入&#x200B;**[!UICONTROL AWS Access Key ID]**、**[!UICONTROL Secret Access Key]**&#x200B;和&#x200B;**[!UICONTROL AWS Region]**。

现在已为此集成配置了外部帐户。

### 步骤2:配置数据源 {#step-2--configure-the-data-sources}

在Audience Manager中创建以下两个数据源：Adobe Campaign(MID)和Adobe Campaign(DeclaredId)。 同时，以下两个数据源在Adobe Campaign中可用：

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:这是默认为访客ID配置的现成数据源。从Campaign创建的区段将包含在此数据源中。
* **声明** 的ID数据源：此数据源需要通过Audience Manager创建并映射 **[!UICONTROL DeclaredId]** 为数据源定义。

请注意，对于具有不同域的多个网站，Adobe Campaign不支持基于ECID进行协调。

要配置&#x200B;**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**&#x200B;数据源，请执行以下操作：

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;中，选择&#x200B;**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**。

   ![](assets/integration_aam_2.png)

1. 在&#x200B;**[!UICONTROL Data Source/ Alias]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Adobe Campaign]**。
1. 输入由Adobe提供的&#x200B;**[!UICONTROL AAM Destination ID]**。

   ![](assets/integration_aam_3.png)

1. 在&#x200B;**[!UICONTROL Reconciliation process]**&#x200B;类别中，我们建议您不要更改协调标准，并始终使用&#x200B;**[!UICONTROL Visitor ID]**。
1. 单击 **[!UICONTROL Save]**。

要创建&#x200B;**[!UICONTROL Declared ID]**&#x200B;数据源，请执行以下操作：

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;中，单击&#x200B;**[!UICONTROL Create]**&#x200B;按钮。
1. 编辑数据源的&#x200B;**[!UICONTROL Label]**。
1. 在&#x200B;**[!UICONTROL Data Source/ Alias]**&#x200B;下拉列表中，选择与来自Audience Manager的&#x200B;**[!UICONTROL DeclaredID]**&#x200B;数据源对应的数据源。
1. 通过输入由Adobe提供的&#x200B;**[!UICONTROL Data Source / Alias]**&#x200B;和&#x200B;**[!UICONTROL AAM Destination ID]**&#x200B;配置数据源。
1. 根据需要设置&#x200B;**[!UICONTROL Reconciliation process]**。
1. 单击 **[!UICONTROL Save]**。

>[!NOTE]
>
>如果要为[Campaign-Triggers集成](../../integrating/using/configuring-triggers-in-experience-cloud.md)配置共享数据源，则不需要&#x200B;**[!UICONTROL AAM Destination ID]**&#x200B;字段。 **[!UICONTROL Priority]** 仅在配置“触发器 — 促销活动”集成时才需要使用。优先级决定首先配置哪个数据源。 优先级可以是任意数字，如1或100。 优先级越高，在协调期间的优先级就越高。

### 步骤3:配置促销活动跟踪服务器 {#step-3--configure-campaign-tracking-server}

要配置与People Core服务或Audience Manager的集成，我们还需要配置促销活动跟踪服务器。

在此，您需要确保在域(CNAME)上注册了促销活动跟踪服务器。 您可以在[本文](https://helpx.adobe.com/cn/campaign/kb/domain-name-delegation.html)中找到有关域名配置的更多信息。

### 步骤4:配置访客ID服务 {#step-4--configure-the-visitor-id-service}

如果您的访客ID服务从未在您的Web属性或网站上配置，请参阅以下[文档](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html)以了解如何配置服务或以下[视频](https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html#step-two)。

您的配置和配置已完成，现在，该集成可用于导入和导出受众或区段。
