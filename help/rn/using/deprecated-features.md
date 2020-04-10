---
title: Campaign Standard已弃用和已删除的功能
description: 本页列表已弃用并删除了Adobe Campaign标准版的功能。
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c35468d7c9a3177d755dad2a9ab2e09510d680fa

---


# 已弃用和已删除的功能 {#deprecated-and-removed-features}

Adobe不断评估产品功能，以确定应用更现代的替代方案取代的旧功能，以提高整体客户价值，并始终注意向后兼容性。

要传达即将移除／替换Campaign Standard功能，请遵循以下规则：

* 首先宣布弃用。 虽然已弃用的功能仍可用于现有用户，但不会进一步增强，也不会记录这些功能。
* 在以下版本中，将最早删除已弃用的功能。 此页中会宣布实际的目标删除日期。

此过程为客户提供了至少一个发布周期，以在实际删除之前将其实施调整为已弃用功能的新版本或后继版本。

>[!NOTE]
>Adobe Campaign标准版和新功能列在发行说 [明中](../../rn/using/release-notes.md)。


## 已弃用功能 {#deprecated-features}

本节列表了最新Campaign Standard版本中标记为已弃用的特性和功能。

通常，计划在未来版本中删除的功能会首先设置为已弃用，并提供替代功能。 这些特性和功能不再适用于新Campaign Standard客户，也不应用于任何新实施。 它们也会从产品文档中删除。

建议客户检查是否在当前部署中使用了功能／功能，并制定计划更改其实施以使用提供的替代方案。 请参阅目标删除日期以计划环境并相应更新项目。

<table> 
 <thead> 
  <tr> 
   <th> <strong>使用SDK v4推送通知</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 从20.1版本开始，已弃用SDK v4。 <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">了解更多信息</a>。</p><br/>
   <p>Adobe <a href="https://aep-sdks.gitbook.io/docs/">Experience Platform Mobile SDK</a> （以前称为v5）将独家支持即将推出的Adobe Experience Cloud功能。</p></br>
     <p>
     <em>目标删除日期：2020年9月30日</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>隐私请求-活动API和接口</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>从活动19.4版本开始，不再使用活动API和接口访问和删除请求。 将不能删除两步用户档案。 使用 <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe隐私核心服务</a>。</p></br>
   <p>另请参阅 <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">Campaign Standard中的隐私管理</a>。</p>
  <p> 
  <em>目标删除日期：2020年7月-活动20.5版 </em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>电子邮件设计——旧版电子邮件编辑器</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>从活动19.0版本开始，已弃用旧版电子邮件编辑器。 使用 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">新的电子邮件设计器</a> ，创建和个性化您的电子邮件内容。 </p></br>
   <p>阅读本 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">节</a> ，了解如何为新编辑者调整电子邮件模板。</p></br>
  <p> 
  <em>目标删除日期：2020年10月-活动20.6版 </em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>用户和安全性——地理单位</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>从18.7版本开始，已弃用地理单元。 组织和地理单元是活动中的相同结构。 用户应仅使用组织单元来构建其用户权限／数据访问层次结构。 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">了解更多信息</a>。 请注意，新Campaign Standard实例以及未创建地理单位的现有实例无法从18.7版本开始实现此功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## 删除的功能 {#removed-features}

本节列表了已从Campaign Standard中删除的特性和功能。

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK forCampaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Creative SDK已停用。 因此，从活动20.2版开始，Campaign Standard电子邮件中由Creative SDK提供支持的图像版本不再可用。</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

## 兼容性终止 {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Campaign和Adobe Experience Cloud已从2019年春季开始停止对Microsoft Internet Explorer 11和活动19.2版本的支持。 请切换到Microsoft Edge或其他支持的浏览器。 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">了解更多信息</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>
