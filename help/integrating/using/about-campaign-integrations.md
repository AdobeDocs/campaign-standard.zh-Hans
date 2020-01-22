---
title: 关于 Campaign 集成
description: Adobe Campaign允许您使用其他Adobe解决方案并结合其不同的功能。
page-status-flag: never-activated
uuid: 59d7cd99-a6f7-47f1-9b5c-c50e27a2bef8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: about-campaign-integrations
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# 关于 Campaign 集成{#about-campaign-integrations}

本节详细介绍了Adobe Campaign当前版本与其他解决方案和服务之间的功能集成。

下面介绍的不同集成功能允许您将Adobe Campaign的交付和高级营销活动管理功能与一组旨在帮助您个性化用户体验的解决方案相结合。

>[!NOTE]
>
> 默认情况下，Adobe Campaign已链接到Adobe Experience cloud帐户。

根据您的环境，其他解决方案也可以关联到Adobe Experience Cloud。 它们作为“组织”（也称为“租户”）链接。

组织是允许管理员配置组和用户以及控制Experience cloud中的单点登录的实体。 该组织的工作方式与跨所有Experience cloud产品和解决方案的登录公司类似。 大多数情况下，组织是您的公司名称。 但是，公司可以拥有许多组织。 用户和组织管理在 [Adobe Experience cloud帮助门户中有详细介绍](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)。

如果您希望将来自其他系统的数据流与Adobe Campaign集成，请查看我们的 [API文档](../../api/using/about-campaign-standard-apis.md)。

>[!NOTE]
>
>Adobe Campaign Standard还可以连接到Microsoft Dynamics 365:此集成可同步CRM系统中所有可用的联系人数据，使所有相关的联系人数据可用于营销活动活动。 有关此集成的详细信息，请参 [阅使用Campaign和Dynamics 365](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)。


<table> 
 <thead> 
  <tr> 
   <th> 解决方案<br /> </th> 
   <th> 用例<br /> </th> 
   <th> Refer to<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1、6.2、6.3、6.4<br /> </td> 
   <td> 允许您在Adobe Experience manager中直接创建映射到Adobe Campaign数据库的电子邮件内容或表单。<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">使用Campaign和Experience Manager</a><br/>, <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">集成Experience Manager和Campaign Standard</a> , <br/><a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">使用Experience Manager和Campaign创建电子邮件</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic, Standard<br /> </td> 
   <td> 允许您插入在打开由Adobe Campaign创建和发送的电子邮件时由Adobe Target动态计算的图像。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">使用Campaign和Target</a> ，集 <br/>成Campaign和Target <a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html">,</a><br/>实时视频个性化电子邮件图像 <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html"></a> （步骤3）
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> 允许您直接在Adobe Analytics中跟踪电子邮件发送的成功情况。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">与Analytics共享营销活动数据</a><br/>，共享 <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">KPI以实现集成的营销活动报告</a> （步骤1）
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience manager和人员核心服务（档案和受众）<br /> </td> 
   <td> 允许您使用您使用的不同Adobe Experience cloud应用程序交换受众。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">People Core Service(Profiles &amp; Audiences)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> 资产核心服务和资产（按需）<br /> </td> 
   <td> 允许您将Adobe Experience cloud库中的资产插入在Adobe Campaign中创建的电子邮件和登录页面中。<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assets Core Service</a> or Assets On Demand<br /> </td> 
  </tr> 
  <tr> 
   <td> 兴趣点（移动分析）<br /> </td> 
   <td> 允许您从移动应用程序的订阅者处收集兴趣点数据，以通过Adobe Campaign发送个性化的营销消息。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">发送包含营销活动和兴趣点数据的基于位置的营销消息</a> (Analytics for Mobile)<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud Triggers<br /> </td> 
   <td> 允许您在Adobe Campaign中向客户发送个性化电子邮件，以响应Adobe Analytics在您的网站上跟踪的特定行为。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">在Campaign Standard中使用Experience cloud触发器</a><br/>, <a href="../../integrating/using/abandonment-triggers-use-cases.md">Efilation Triggers-Campaign使用案例</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html"></a> 根据网站活动视频触发再营销消息（步骤2）
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> 允许您从Dreamweaver编辑电子邮件内容，并将其与Adobe Campaign同步。<br /> </td> 
   <td> 
    <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">使用Dreamweaver视频</a> 、使用Campaign extension for Dreamweaver <br/>创 <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">建个性化的电子邮件</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Creative SDK<br /> </td> 
   <td> 允许您编辑图像，并使用Adobe Creative SDK提供的一整套功能直接在内容编辑器中增强图像。<br /> </td> 
   <td> <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">使用Adobe Creative SDK修改图像</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Platform SDK<br /> </td> 
   <td> 允许使用Experience Platform SDK在Adobe Campaign中自动执行移动应用程序属性激活过程。<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">使用Experience Platform SDK配置移动应用程序</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

