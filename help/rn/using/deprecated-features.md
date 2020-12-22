---
solution: Campaign Standard
product: campaign
title: Campaign Standard 已弃用和已移除的功能
description: 本页列出 Adobe Campaign Standard 的已弃用和已移除的功能。
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
translation-type: tm+mt
source-git-commit: 32aba66dd8987414cf90df1e7bfb9c419c5f68ff
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 85%

---


# 已弃用和已删除的功能 {#deprecated-and-removed-features}

Adobe 不断评估产品功能，以确定应用更现代的功能替换的旧功能，从而提高客户获得的整体价值，并且我们始终不断仔细考量向后兼容性。

为传达有待移除/替换的 Campaign Standard 功能，以下规则适用：

* 首先宣布弃用。尽管已弃用的功能仍然适用于现有用户，但是它们不会得到进一步增强或记录。
* 至少将在以下版本中移除已弃用的功能。本页会宣布实际的目标移除日期。

此过程为客户提供了至少一个版本周期，以在实际移除之前，使其实施适应已弃用功能的新版本或后继版本。

>[!NOTE]
>Adobe Campaign Standard 版本和新功能列在[发行说明](../../rn/using/release-notes.md)中。


## 已弃用的功能 {#deprecated-features}

本部分列出最新 Campaign Standard 版本中标记为已弃用的特性和功能。

通常，首先将计划在未来版本中移除的功能设置为已弃用，并提供替代功能。这些特性和功能不再适用于新的 Campaign Standard 客户，也不应当用于任何新实施。它们也会从产品文档中移除。

建议客户复查他们是否在其当前部署中利用相应的特性/功能，并制定计划来更改其实施，从而使用提供的替代功能。请参阅目标移除版本，以相应地规划环境和项目更新。

<table> 
 <thead> 
 <tr> 
   <th> <strong>预测主题行</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 自2020年12月15日起，已弃用“预测主题行”功能。</p><br/>
   <p>我们建议您利用基于AI的电子邮件功能，根据历史互动指标分析和预测开放率、最佳发送时间和可能的客户流失。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html">了解详情</a></p></br>
     <p>
     <em>目标删除：2021年4月</em></p>
     </td> 
  </tr> 
  </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK v4 推送通知</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 从 20.1 版本开始，弃用 SDK v4。<a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">了解详情</a>。</p><br/>
   <p><a href="Https://aep-sdks.gitbook.io/docs/">Adobe Experience Platform Mobile SDK</a>（以前称为 v5）将专门支持即将推出的 Adobe Experience Cloud 特性和功能。</p></br>
     <p>
     <em>目标删除日期：2021年8月31日</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>隐私请求 - Campaign API 和接口</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>从 Campaign 19.4 版本开始，将 Campaign API 和接口用于访问和删除请求的方法已被弃用。两步用户档案删除将不可用。使用 <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe 隐私核心服务</a>。</p></br>
   <p>另请参阅<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=en">管理隐私请求</a>。</p>
  <p> 
  <em>目标删除日期：2021 年 4 月</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>电子邮件设计 - 旧版电子邮件编辑器</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>从 Campaign 19.0 版本开始，弃用旧版电子邮件编辑器。使用<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">活动电子邮件设计器</a>创建和个性化您的电子邮件内容。 </p></br>
   <p>阅读<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">此部分</a>以了解如何针对新编辑器调整电子邮件模板。</p></br>
  <p> 
  <em>目标删除日期：2021年底</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>用户和安全 - 地理单位</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>从 18.7 版本开始，弃用地理单位。组织单位和地理单位在 Campaign 中是完全相同的构造。用户应仅使用组织单位来构建其用户权限/数据访问层次结构。<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=zh-Hans#administrating">了解详情</a>。请注意，从 18.7 版本开始，新 Campaign Standard 实例以及未创建地理单位的现有实例无法实现此功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## 已移除的功能 {#removed-features}

本部分列出已从 Campaign Standard 中移除的特性和功能。

<table> 
 <thead> 
  <tr> 
   <th> <strong>Experience Cloud 触发器的倾向分数</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Cloud 触发器中已取消<b>倾向分数</b>。因此，已从 Adobe Campaign Standard 中移除此选项。为避免扩充模式中的任何倾向分数值过时，我们建议更新模式以检索最新更改并重新发布现有触发器。有关更多信息，请参阅<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html">在 Campaign 中发布触发器</a>。
</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>适用于 Campaign Standard 的 Creative SDK</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>[!DNL Adobe Creative SDK] 已停用。因此，从 Campaign 20.2 版本开始，Campaign Standard 电子邮件中由 [!DNL Creative SDK] 提供的图像编辑功能不再可用。</p></br>
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
   <td> <p>从 2019 年春季和 Campaign 19.2 版本开始，Adobe Campaign 和 Adobe Experience Cloud 已终止支持 Microsoft Internet Explorer 11。请切换到 Microsoft Edge 或其他受支持的浏览器。<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html">了解详情</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>
