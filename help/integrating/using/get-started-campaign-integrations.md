---
title: Campaign 集成快速入门
description: 使用其他Adobe解决方案，并将其不同的功能与活动相结合。
page-status-flag: never-activated
uuid: 59d7cd99-a6f7-47f1-9b5c-c50e27a2bef8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d425e4b96604133fbdfc66fde38e4ca5c84baccd
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 7%

---


# 关于 Campaign 集成{#get-started-campaign-integrations}

本节详细介绍了当前版本的Adobe Campaign与其他解决方案和服务之间的功能集成。

下面介绍的不同集成功能允许您将Adobe Campaign的投放和高级活动管理功能与创建的一套解决方案相结合，帮助您个性化用户体验。

>[!NOTE]
>
> 默认情况下，Adobe Campaign已链接到Adobe Experience Cloud帐户。

根据您的环境，还可以将其他解决方案链接到Adobe Experience Cloud。 它们以组织（也称为租户）的形式链接。

组织是允许管理员配置组和用户以及控制Experience Cloud中的单点登录的实体。 组织的功能类似于跨所有Experience Cloud产品和解决方案的登录公司。 大多数情况下，组织是您的公司名称。 但是，公司可以有许多组织。 用户和组织管理在Adobe Experience Cloud帮 [助门户中详细介绍](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html)。

如果您希望将来自其他系统的数据流与Adobe Campaign集成，请查看我们的 [API文档](../../api/using/get-started-apis.md)。

>[!NOTE]
>
>Adobe Campaign Standard还可以连接到Microsoft Dynamics 365:此集成支持同步CRM系统中所有可用的联系人数据，使所有相关的联系人数据都可用于活动活动。 有关此集成的详细信息，请参 [阅使用活动和Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。


<table> 
 <thead> 
  <tr> 
   <th> 解决方案<br /> </th> 
   <th> Use Case<br /> </th> 
   <th> Refer to<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1、6.2、6.3、6.4、6.5<br /> </td> 
   <td> 允许您在Adobe Experience Manager直接创建映射到Adobe Campaign库的电子邮件内容或表单。<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">使用活动和Experience Manager</a>, <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">集成Experience Manager和Campaign Standard</a>, <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">创建包含Experience Manager和活动的电子邮件</a> 
    </td> 
  </tr> 
  <tr> 
   <td> 目标<br /> Classic, Standard<br /> </td> 
   <td> 允许您插入由Adobe Target在打开由Adobe Campaign创建和发送的电子邮件时动态计算的图像。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">使用活动和目标</a>, <a href="https://docs.adobe.com/content/help/en/target/using/integrate/campaign-and-target.html">集成活动和目标</a>, <a href="https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html">实时视频中个性化电子邮件图像</a> （步骤3）
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard、Premium <br /> </td> 
   <td> 允许您直接在Adobe Analytics跟踪电子邮件投放的成功。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">与Analytics共享活动</a>, <a href="https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html">共享KPI以实现集成活动报告</a> 视频（步骤1）
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager和人员核心服务(用户档案和受众)<br /> </td> 
   <td> 允许您与您使用的不同Adobe Experience Cloud应用程序交换受众。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">People Core Service(用户档案和受众)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> 资产核心服务和资产（按需）<br /> </td> 
   <td> 允许您将来自Adobe Experience Cloud图书馆的资源插入在Adobe Campaign中创建的电子邮件和登陆页中。<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">资产核心服务</a> 或资产（按需）<br /> </td> 
  </tr> 
  <tr> 
   <td> 兴趣点（移动分析）<br /> </td> 
   <td> 允许您从移动应用程序的订户收集兴趣点数据，以发送个性化的营销消息和Adobe Campaign。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">发送包含活动和兴趣点数据的基于位置的营销消息</a> (Analytics for Mobile)<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud Triggers<br /> </td> 
   <td> 允许您向Adobe Campaign客户发送个性化电子邮件，以响应Adobe Analytics在您的网站上跟踪的特定行为。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">在Experience Cloud、放弃触发器</a>- <a href="../../integrating/using/abandonment-triggers-use-cases.md">活动使用案例中使用Campaign Standard触发器</a>, <a href="https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html">根据站点活动视频触发再营销消息</a> （步骤2）
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> 允许您编辑来自Dreamweaver的电子邮件内容，并将其与Adobe Campaign同步。<br /> </td> 
   <td> 
    <a href="https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html">利用Dreamweaver视频创建个性化</a> 电子邮件， <a href="https://helpx.adobe.com/cn/dreamweaver/using/working-with-dreamweaver-and-campaign.html">使用Dreamweaver活动扩展</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Experience PlatformSDK<br /> </td> 
   <td> 允许使用激活SDK在Adobe Campaign中自动化移动应用程序属性Experience Platform流程。<br /> </td> 
   <td> <a href="https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html">使用Experience PlatformSDK配置移动应用程序</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

