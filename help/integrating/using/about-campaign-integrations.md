---
title: 关于Campaign集成
seo-title: 关于Campaign集成
description: 关于Campaign集成
seo-description: Adobe Campaign允许您使用其他Adobe解决方案并组合不同的功能。
page-status-flag: 从未激活
uuid: 59d7cd99-a6 f7-47f1-9b5 c-c50 e27 a2 bef8
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: 关于营销活动集成
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 337f2270f3f66d5172084a4e2a19d6185bf097ff

---


# About Campaign integrations{#about-campaign-integrations}

本节详细介绍了当前版本的Adobe Campaign和其他解决方案和服务之间提供的功能集成。

下面介绍的不同集成允许您将Adobe Campaign的交付和高级营销活动管理功能与创建的一系列解决方案结合起来，帮助您个性化用户体验。

>[!NOTE]
>
> 默认情况下，Adobe Campaign已链接到Adobe Experience Cloud帐户。

根据您的环境，其他解决方案也可以链接到Adobe Experience Cloud。它们链接为组织(也称为租户)。

组织是使管理员能够配置组和用户以及控制Experience Cloud中单点登录的实体。该组织的功能类似于一家登录公司，它横跨Experience Cloud产品和解决方案。大多数情况下，组织都是您的公司名称。但是，公司可以有许多组织。User and organization management is detailed in the [Adobe Experience Cloud help portal](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html).

If you would like to integrate data flows from other systems with Adobe Campaign, have a look at our [API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

>[!NOTE]
>
>Adobe Campaign Standard还可以连接到Microsoft Dynamics365：此集成可同步CRM系统中所有可用的联系人数据，从而使所有相关的联系人数据可用于活动活动。For more on this integration, refer to [Working with Campaign and Dynamics 365](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).


<table> 
 <thead> 
  <tr> 
   <th> Solution<br /> </th> 
   <th> Use Case<br /> </th> 
   <th> Refer to<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4<br /> </td> 
   <td> Allows you to create email contents or forms mapped to the Adobe Campaign database directly in Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">与Campaign和Experience Manager集成</a><br/>， <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">集成Experience Manager和Campaign Standard</a><br/>， <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">通过Experience Manager和Campaign创建电子邮件</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic, Standard<br /> </td> 
   <td> Allows you to insert images that are dynamically computed by Adobe Target when an email created and sent by Adobe Campaign is opened.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">使用Campaign和Target</a><br/><a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html">、集成Campaign和Target</a><br/>、 <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">个性化实时</a> 视频中的个性化电子邮件(第步)
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> Allows you to track the success of your email deliveries directly in Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">与Analytics共享Campaign数据</a><br/>， <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">为集成的Campaign报告</a> 视频共享KPI(步骤1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager and People core service (Profiles &amp; Audiences)<br /> </td> 
   <td> Allow you to exchange audiences with the different Adobe Experience Cloud applications that you use.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">People Core Service(档案和受众)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Asset core service and Assets On Demand<br /> </td> 
   <td> Allows you to insert assets from your Adobe Experience Cloud library into emails and landing pages created in Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assets核心服务</a> 或资产(按需)<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest (Analytics for Mobile)<br /> </td> 
   <td> Allows you to collect Points of Interest data from your mobile application's subscribers to send personalized marketing messages with Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">通过Campaign和Points of Interest数据发送基于位置的营销消息</a> (Analytics for Mobile)<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud Triggers<br /> </td> 
   <td> Allows you to send personalized emails to your customers in Adobe Campaign as a reaction to specific behaviors that are tracked on your website by Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">在Campaign Standard</a><br/>中使用Experience Cloud触发器， <a href="../../integrating/using/abandonment-triggers-use-cases.md">放弃触发器触发器系列活动用例</a><br/>， <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">触发基于站点活动</a> 视频的再营销消息(步骤2)
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Allows you to edit an email content from Dreamweaver and synchronize it with Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">使用Dreamweaver</a> 视频创建个性化电子邮件 <br/>， <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">使用Dreamweaver的Campaign扩展</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Creative SDK<br /> </td> 
   <td> Allows you to edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor.<br /> </td> 
   <td> <a href="../../designing/using/modifying-images-with-the-adobe-creative-sdk.md">使用Adobe Creative SDK修改图像</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Platform SDKs<br /> </td> 
   <td> Allows automation of the Mobile App Property activation process in Adobe Campaign using the Experience Platform SDKs.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">使用Experience Platform SDK配置移动应用程序</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

