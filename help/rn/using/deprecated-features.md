---
title: Campaign Standard已弃用和已删除的功能
description: 本页列表已弃用并删除了Adobe Campaign Standard的功能。
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
source-git-commit: 5203f3b3c520f38d91627df2159a90ab5912e6b6
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 18%

---


# 已弃用和已删除的功能 {#deprecated-and-removed-features}

Adobe 不断评估产品功能，以确定应用更现代的功能替换的旧功能，从而提高客户获得的整体价值，并且我们始终不断仔细考量向后兼容性。

要传达即将拆除／替换Campaign Standard功能，请应用以下规则：

* 首先宣布弃用。尽管已弃用的功能仍可供现有用户使用，但不会进一步增强或记录这些功能。
* 至少将在以下版本中移除已弃用的功能。本页会宣布实际的目标移除日期。

此过程为客户提供了至少一个版本周期，以在实际移除之前，使其实施适应已弃用功能的新版本或后继版本。

>[!NOTE]
>Adobe Campaign Standard releases and new capabilities are listed in the [Release Notes](../../rn/using/release-notes.md).


## 已弃用的功能 {#deprecated-features}

本节介绍最新列表版本中标记为已弃用的Campaign Standard特性和功能。

通常，计划在未来版本中删除的功能会首先设置为已弃用，并提供替代功能。 这些特性和功能不再适用于新Campaign Standard客户，也不应用于任何新实施。 它们也会从产品文档中移除。

建议客户检查他们是否在当前部署中利用了功能／功能，并制定计划更改其实施以使用所提供的替代方案。 请参阅目标删除版本以相应地规划环境和项目更新。

<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK v4的推送通知</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 从20.1版本开始，SDK v4已弃用。 <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">了解详情</a>。</p><br/>
   <p>Adobe Experience Platform <a href="https://aep-sdks.gitbook.io/docs/">移动SDK</a> （以前称为v5）将独家支持即将推出的Adobe Experience Cloud特性和功能。</p></br>
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
   <td> <p>从活动19.4版本开始，已不再使用活动API和接口访问和删除请求。 删除2步用户档案不可用。 使用 <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe隐私核心服务</a>。</p></br>
   <p>另请参阅 <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">Campaign Standard中的隐私管理</a>。</p>
  <p> 
  <em>目标移除日期：2021 年</em></p>
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
   <td> <p>从活动19.0版本开始，已弃用传统电子邮件编辑器。 使用 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">新的电子邮件设计器</a> ，创建和个性化您的电子邮件内容。 </p></br>
   <p>阅读本 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">节</a> ，了解如何调整电子邮件模板以适应新编辑者。</p></br>
  <p> 
  <em>目标移除日期：2021 年</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>用户和安全——地理单位</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>从18.7版本开始，已弃用地理单元。 组织和地理单位是活动中的相同结构。 用户应仅使用组织单位来构建其用户权限／数据访问层次结构。 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">了解详情</a>。请注意，新Campaign Standard实例以及未创建地理单位的现有实例无法从18.7版本开始实现此功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Removed Features {#removed-features}

本节列表已从Campaign Standard中删除的特性和功能。

<table> 
 <thead> 
  <tr> 
   <th> <strong>Experience Cloud触发器的倾向得分</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>倾向 <b>得分已从Adobe Experience Cloud</b> “触发器”中取消。 因此，这一选项已从Adobe Campaign Standard删除。 为避免扩充模式中倾向得分的任何过时值，我们建议更新模式以检索最新更改并重新发布现有触发器。 有关详细信息，请参阅 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html#publishing-trigger-in-campaign"> 以活动发布触发器 </a>。
</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>适用于Campaign Standard的Creative SDK</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Creative SDK 已停用。因此，从活动20.2版开始，Campaign Standard电子邮件中不再提供以Creative SDK为后盾的图像版本。</p></br>
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
   <td> <p>Adobe Campaign和Adobe Experience Cloud已从2019年春季开始放弃对Microsoft Internet Explorer 11和活动19.2版本的支持。 请切换到Microsoft Edge或其他受支持的浏览器。 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/about-configuration-guidelines.html#compatible-browsers">了解详情</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>
