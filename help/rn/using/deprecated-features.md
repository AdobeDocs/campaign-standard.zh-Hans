---
title: Campaign standard已弃用和已删除的功能
description: 本页列出了Adobe Campaign standard的已弃用和已删除功能。
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
source-git-commit: 6ffbf03a7eb4fc1b5bfbd523c0c5342d41cfd211

---


# Campaign standard已弃用和已删除的功能 {#deprecated-and-removed-features}

Adobe不断评估产品功能，以确定应用更现代的替代方案取代的旧功能，以提高整体客户价值，并始终注意向后兼容性。

要传达即将拆除／替换Campaign standard功能，请遵循以下规则：

* 首先宣布弃用。 虽然已弃用的功能仍可用于现有用户，但不会进一步增强，也不会记录这些功能。
* 在以下版本中，将最早删除已弃用的功能。 此页面会宣布删除的实际目标日期。

此过程为客户提供了至少一个发布周期，以在实际删除之前将其实施调整为已弃用功能的新版本或后继版本。

>[!NOTE]
>Adobe Campaign standard版本和新功能列在发行说 [明中](../../rn/using/release-notes.md)。


## 已弃用功能 {#deprecated-features}

本节列出了最新Campaign standard版本中标记为已弃用的特性和功能。 通常，计划在未来版本中删除的功能会首先设置为已弃用，并提供替代功能。 这些功能和特性不再适用于新的Campaign standard客户，也不应用于任何新的实施。 它们也会从产品文档中删除。

建议客户检查是否在当前部署中使用了功能／功能，并制定计划更改其实施以使用提供的替代方案。 请参阅目标删除日期以相应地规划您的环境和项目更新。

<table> 
 <thead> 
  <tr> 
   <th> 版本<br /> </th> 
   <th> 功能<br /> </th> 
   <th> 替换<br /> </th> 
    <th> 目标删除日期<br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 20.1<br /> </td> 
   <td> Push Notifications<br /> </td> 
    <td> Adobe <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Experience Platform Mobile SDK</a> （以前称为v5）将独家支持即将推出的Adobe Experience cloud功能。 <br /> </td> 
    <td> 2020年9月30日<br /> </td> 
  </tr> 
  <tr> 
   <td> 20.1<br /> </td> 
   <td> Creative SDK for Campaign Standard<br /> </td> 
  <td> Adobe Creative SDK已停用。 因此，Campaign standard电子邮件中由Creative SDK提供支持的图像版本现已弃用。<br /> </td>
  <td> 2020年3月- Campaign 20.2版本<br /> </td> 
  </tr> 
  <tr> 
   <td> 19.4<br /> </td> 
   <td> 隐私请求- Campaign API和界面<br /> </td>
    <td> 不建议使用Campaign API和界面访问和删除请求。 使用隐私核心服务。 <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">了解更多信息</a>。 另请参阅 <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">Campaign standard中的隐私管理</a>。<br /> </td>
    <td> 2020年7月- Campaign 20.5版本<br /> </td> 
  </tr>
  <tr> 
   <td> 19.0<br /> </td> 
   <td> 电子邮件设计——旧版电子邮件编辑器<br /> </td>
    <td> 旧版电子邮件编辑器现已弃用。 使用新的电子邮件设计器创建和个性化您的电子邮件内容。 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">了解更多信息</a>。 阅读本 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">节</a> ，了解如何为新编辑者调整电子邮件模板。<br /> </td>
    <td> 2020年10月- Campaign 20.6版本<br /> </td> 
  </tr>
  <tr> 
   <td> 18.7<br /> </td> 
   <td> 用户和安全性——地理单位<br /> </td>
    <td> 组织和地理单位在Campaign中是相同的构造。 用户应仅使用组织单元来构建其用户权限／数据访问层次结构。 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">了解更多信息</a>。 请注意，新的Campaign standard实例以及没有创建地理单位的现有实例无法从18.7版本开始实现此功能。<br /> </td>
    <td> N/A<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 兼容性终止 {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> 版本<br /> </th> 
   <th> 功能<br /> </th> 
   <th> 替换<br /> </th> 
 </tr> 
 </thead> 
 <tbody>
<tr> 
   <td> 19.2<br /> </td> 
   <td> 隐私请求- Campaign API和界面<br /> </td>
    <td> 从2019年春季开始，Adobe Campaign和Adobe Experience cloud不再支持Microsoft Internet Explorer 11和Campaign 19.2版本。 请切换到Microsoft edge或其他支持的浏览器。  <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">了解更多信息</a>。<br /> </td>
    <td><br /> </td> 
  </tr>
  </tbody> 
</table>
