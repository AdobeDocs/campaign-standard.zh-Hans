---
title: Campaign 集成入门
description: 使用其他 Adobe 解决方案，并将其各种功能与 Campaign 相结合。
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ecf88c7d-6729-4b3a-85c4-60427bb57442
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 77%

---

# 关于 Campaign 集成{#get-started-campaign-integrations}

本部分详细介绍 Adobe Campaign 的当前版本与其他解决方案和服务之间可用的功能集成。

通过下面提供的不用集成，可以将 Adobe Campaign 的投放和高级活动管理功能与帮助对用户体验进行个性化的解决方案相结合。

>[!NOTE]
>
> 默认情况下，Adobe Campaign 已链接到 Adobe Experience Cloud 帐户。

根据您的环境，还可以将其他解决方案链接到 Adobe Experience Cloud。它们以组织（也称为租户）的形式链接。

组织是允许管理员配置组和用户以及控制 Experience Cloud 中的单点登录的实体。组织的功能类似于跨所有 Experience Cloud 产品和解决方案的登录公司。大多数情况下，组织是您的公司名称。但是，公司可以有许多组织。[Adobe Experience Cloud 帮助门户](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html)中详细介绍了用户和组织管理。

如果您希望将来自其他系统的数据流与 Adobe Campaign 集成，请查看我们的 [API 文档](../../api/using/get-started-apis.md)。

>[!NOTE]
>
>Adobe Campaign Standard 还可以连接到 Microsoft Dynamics 365：此集成支持同步 CRM 系统中所有可用联系人数据，从而使所有相关联系人数据都可用于 Campaign 活动。有关此集成的更多信息，请参阅[使用 Campaign 和 Dynamics 365](../../integrating/using/d365-acs-get-started.md)。


<table> 
 <thead> 
  <tr> 
   <th> 解决方案<br /> </th> 
   <th> 用例<br /> </th> 
   <th> 请参阅<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Adobe Experience Manager<br /> </td> 
   <td> 允许您在 Adobe Experience Manager 中直接创建映射到 Adobe Campaign 数据库的电子邮件内容或表单。<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">使用Campaign和Experience Manager</a>, <a href="https://helpx.adobe.com/cn/experience-manager/6-4/sites/administering/using/campaignstandard.html">集成Experience Manager和Campaign Standard</a>, <a href="https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html">使用Experience Manager和营销活动创建电子邮件</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Target<br /> </td> 
   <td> 允许在打开由 Adobe Campaign 创建和发送的电子邮件时插入由 Adobe Target 动态计算的图像。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">使用Campaign和Target</a>, <a href="https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html">集成Campaign和Target</a>, <a href="https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html">实时个性化电子邮件图像</a> 视频（步骤3）
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Analytics<br /> </td> 
   <td> 允许直接在 Adobe Analytics 中跟踪电子邮件投放是否成功。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">与 Analytics 共享 Campaign 数据</a>，<a href="https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html">共享 KPI 以实现集成 Campaign 报告</a>视频（步骤 1）
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager 和 People 核心服务（用户档案和受众）<br /> </td> 
   <td> 允许您与您使用的不同 Adobe Experience Cloud 应用程序交换受众。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">People 核心服务（用户档案和受众）</a><br /> </td> 
  </tr> 
   <tr> 
   <td> Adobe Real-time Customer Data Platform(RTCDP)<br /> </td> 
   <td> Adobe Campaign与Adobe Real-time Customer Data Platform(RTCDP)之间的集成允许您共享区段数据并将受众导入Adobe Campaign。</td>
   <td><a href="../../integrating/using/get-started-sources-destinations.md">Sources 与 Destinations 入门</a></td>
  </tr> 
  <tr> 
   <td> Adobe资产核心服务和Assets On Demand<br /> </td> 
   <td> 允许将来自 Adobe Experience Cloud 库的资源插入到在 Adobe Campaign 中创建的电子邮件和登陆页。<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assets 核心服务</a> 或 Assets On Demand<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest (Analytics for Mobile)<br /> </td> 
   <td> 允许从移动应用程序的订阅者收集 Points of Interest 数据，以使用 Adobe Campaign 发送个性化营销消息。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">使用 Campaign 和 Points of Interest 数据</a> (Analytics for Mobile) 发送基于位置的营销消息<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Experience Cloud 触发器<br /> </td> 
   <td> 允许在 Adobe Campaign 中向客户发送个性化电子邮件，以对 Adobe Analytics 在网站上跟踪的特定行为作出反应。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">在 Campaign Standard 中使用 Experience Cloud Triggers</a>，<a href="../../integrating/using/abandonment-triggers-use-cases.md">Abandonment Triggers-Campaign 用例</a>, <a href="https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html">根据站点活动触发再营销消息</a>视频（步骤 2）
    </td> 
  </tr> 
    <tr> 
   <td> AdobeJourney Orchestration<br /> </td> 
   <td> 允许在AdobeJourney Orchestration的上下文中使用Adobe Campaign Standard的事务性消息传送功能，通过即装即用的操作发送电子邮件、推送通知和短信。<br /> </td> 
   <td> <a href="https://experienceleague.adobe.com/docs/journeys/using/action-journeys/working-with-adobe-campaign.html?lang=en">使用AdobeJourney Orchestration和Adobe Campaign Standard</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Dreamweaver<br /> </td> 
   <td> 允许从 Dreamweaver 编辑电子邮件内容并将其与 Adobe Campaign 同步。<br /> </td> 
   <td> 
    <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=zh-Hans">使用Dreamweaver创建个性化电子邮件</a> 视频， <a href="https://helpx.adobe.com/cn/dreamweaver/using/working-with-dreamweaver-and-campaign.html">为Dreamweaver使用Campaign扩展</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Adobe Experience Platform SDK<br /> </td> 
   <td> 允许使用 Experience Platform SDK 在 Adobe Campaign 中自动执行移动应用程序属性激活过程。<br /> </td> 
   <td> <a href="https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html">使用 Experience Platform SDK 配置移动应用程序</a><br /> </td> 
  </tr> 
 </tbody> 
</table>
