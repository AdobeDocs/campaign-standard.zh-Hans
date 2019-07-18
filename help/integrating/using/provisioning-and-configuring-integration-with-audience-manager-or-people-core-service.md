---
title: 配置和配置与Audience Manager或People核心服务的集成
seo-title: 配置和配置与Audience Manager或People核心服务的集成
description: 配置和配置与Audience Manager或People核心服务的集成
seo-description: '了解如何配置Audience Manager/People核心服务集成以开始与不同的Adobe Experience Cloud解决方案共享受众或细分。 '
page-status-flag: 从未激活
uuid: e7329644-0033-4729-b4 a7-61bef137 f4 b5
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: publishing-with-campaign-and-operators-manager-or-ople-core-service
discoiquuid: eb24f4ea-325f-433a-91a0-c45906320 bcb
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Provisioning and configuring integration with Audience Manager or People core service{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

The provisioning and configuring of Audience Manager and People core in Adobe Campaign take two steps: [Submitting request to Adobe](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#submitting-request-to-adobe) then [Configuring the integration in Adobe Campaign](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#configuring-the-integration-in-adobe-campaign).

## Submitting request to Adobe {#submitting-request-to-adobe}

Audience Manager(AAM)或人员核心服务集成允许您在Adobe Campaign中导入和导出受众或细分。

必须首先配置此集成。To request provisioning of this integration, write an email to [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) with the following information:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>请求类型：</strong><br /> </td> 
   <td> 配置AAM/People核心服务系列活动集成 </td> 
  </tr> 
  <tr> 
   <td> <strong>组织名称：</strong><br /> </td> 
   <td> 您的组织名称 </td> 
  </tr> 
  <tr> 
   <td> <strong>IMS组织ID</strong><br /> </td> 
   <td> 您的IMS组织ID* </td> 
  </tr> 
  <tr> 
   <td> <strong>环境：</strong><br /> </td> 
   <td> 示例：Production </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM或People Service</strong><br /> </td> 
   <td> 示例：Adobe Audience Manager </td> 
  </tr> 
  <tr> 
   <td> <strong>声明的ID或访问者ID</strong><br /> </td> 
   <td> 示例：声明ID </td> 
  </tr> 
  <tr> 
   <td> <strong>附加信息</strong><br /> </td> 
   <td> 任何有用的信息或评论 </td> 
  </tr> 
 </tbody> 
</table>

* You can find your IMS Org ID on the Experience Cloud, in the **Administration** menu. 第一次连接到Adobe Experience Cloud时也会提供此功能。

## Configuring the integration in Adobe Campaign {#configuring-the-integration-in-adobe-campaign}

提交此请求后，Adobe将继续为您提供集成，并与您联系以提供必须完成配置的详细信息和信息：

* [步骤1：在Adobe Campaign中配置或检查外部帐户](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [步骤2：配置数据源](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)
* [步骤3：配置系列活动跟踪服务器](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-3--configure-campaign-tracking-server)
* [第步：配置访客ID服务](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-4--configure-the-visitor-id-service)

### Step 1: Configure or check the external accounts in Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

我们首先需要在Adobe Campaign中配置或检查外部帐户。这些帐户应由Adobe配置，并且应向您传达必要信息。

要执行此操作，请执行以下操作：

1. From the advanced menu, select **Administration &gt; Application settings &gt; External accounts**.

   选择以下集成的可用外部帐户之一：

   ![](assets/integration_aam_1.png)

1. Enter **[!UICONTROL Receiver server]** in following format
1. Enter the **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** and **[!UICONTROL AWS Region]**.

您的外部帐户现已为此集成配置。

### Step 2: Configure the Data Sources {#step-2--configure-the-data-sources}

在Audience Manager中创建了以下两个数据源：Adobe Campaign(MID)和Adobe Campaign(声明ID)。同时，这两个数据源在Adobe Campaign中可用：

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**：这是默认为访客ID配置的现成数据源。通过Campaign创建的区段将成为此数据源的一部分。
* **声明的ID** 数据源：需要使用Audience Manager中 **[!UICONTROL DeclaredId]** 的数据源定义创建和映射此数据源。

请注意，对于具有不同域的多个网站，Adobe Campaign不支持基于EID的调解。

To configure the **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** data source:

1. In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, select **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Choose **[!UICONTROL Adobe Campaign]** in the **[!UICONTROL Data Source/ Alias]** drop-down.
1. Enter the **[!UICONTROL AAM Destination ID]** provided by Adobe.

   ![](assets/integration_aam_3.png)

1. **[!UICONTROL Reconciliation process]** 在该类别中，我们建议您不要更改核对条件 **[!UICONTROL Visitor ID]**，始终使用。
1. Click **[!UICONTROL Save]**.

To create the **[!UICONTROL Declared ID]** data source:

1. In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, click the **[!UICONTROL Create]** button.
1. Edit the **[!UICONTROL Label]** of your data source.
1. In the **[!UICONTROL Data Source/ Alias]** drop-down, choose the Data Source corresponding to the **[!UICONTROL DeclaredID]** data source from Audience Manager.
1. Configure your data source by entering the **[!UICONTROL Data Source / Alias]** and **[!UICONTROL AAM Destination ID]** provided by Adobe.
1. Set the **[!UICONTROL Reconciliation process]** as needed.
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>The **[!UICONTROL AAM Destination ID]** field is not required if you are configuring the shared data source for the [Campaign-Triggers integration](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL Priority]** 仅在配置触发器-营销活动集成时需要。优先级决定将首先配置哪些数据源。优先级可为任意数量，如或100。优先级越高，在进行调解时首选项越高。

### Step 3: Configure Campaign Tracking server {#step-3--configure-campaign-tracking-server}

为了配置与People核心服务或Audience Manager的集成，我们还需要配置系列活动跟踪服务器。

此处，您需要确保在域(CNAME)上注册系列活动跟踪服务器。You can find more information about domain name delegation in [this article](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/Technotes/AdobeCampaign_Deliverability_Sub_Domain_Delegation.pdf).

### Step 4: Configure the Visitor ID Service {#step-4--configure-the-visitor-id-service}

In the case that your Visitor ID service has never been configured on your web properties or websites, refer to the following [document](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-aam-analytics.html) to learn how to configure your service or the following [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

您的配置和供应已完成，集成现在可用于导入和导出受众或区段。
