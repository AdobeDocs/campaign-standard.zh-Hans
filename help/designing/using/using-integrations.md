---
title: '通过Adobe Campaign集成设计电子邮件 '
seo-title: '通过Adobe Campaign集成设计电子邮件  '
description: '通过Adobe Campaign集成设计电子邮件 '
seo-description: 了解如何通过电子邮件设计器中的Adobe Campaign集成来设计电子邮件。
page-status-flag: 从未激活
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 设计
content-type: 参考
topic-tags: 编辑——电子邮件——内容
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 195e8db45609b8f92f0ec60c987cf6eadfd463eb

---

# 多解决方案电子邮件设计 {#multi-solution-email-design}

## 在Dreamweaver中编辑内容 {#editing-content-in-dreamweaver}

Adobe Campaign standard与Dreamweaver集成，使您能在Dreamweaver界面中编辑电子邮件内容。 您可以访问Dreamweaver的强大界面来设计和开发响应式电子邮件内容。

* **双向同步**

   只要在一个产品中进行编辑，就会在另一个产品中实时更新。 如果要在Dreamweaver中更改文本的颜色，一旦您进行了该编辑，文本的颜色就会在Campaign中实时显示。 此外，当您在Dreamweaver或Campaign中选择代码时，由于行号相同，因此选择将保留在两个产品之间，这在查找代码中的特定内容时非常有用。

* **通过Dreamweaver将本地图像上传到Adobe Campaign**

   在Dreamweaver中创建或编辑电子邮件时，您只需从桌面或本地计算机中选择图像。 虽然Dreamweaver始终允许您这样做，但是当Dreamweaver和Campaign连接后，本地文件会立即上传到Adobe Campaign服务器：无需随内容变化手动上传图像。 此外，它还可确保最新图像始终处于营销活动中。

* **在Dreamweaver中添加Campaign个性化**

   对于电子邮件开发人员，不再需要添加类似文本， `[[FIRSTNAME_PLACEHOLDER]]` 也无需查找数据模型表的语法。 Dreamweaver中的Campaign工具栏直接连接到Campaign实例的数据模型。 这意味着您可以从名字到地址等数据中抽取任何想要实现个性化的数据。 如果您已在Campaign中创建了内容块，则还可以直接将这些内容块拖入Dreamweaver。

此功能在此处可访问的Dreamweaver文档中有详细 [说明](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html)。 还提供 [演示视](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) 频。

## 在Experience manager中编辑内容 {#editing-content-in-experience-manager}

可以在Experience manager中编辑电子邮件内容，然后在Adobe Campaign standard中将其用于一条或多条电子邮件。 请参阅 [本文档](../../integrating/using/integrating-with-experience-manager.md)。

## 电子邮件设计选项比较 {#email-design-options-comparison}

Adobe Campaign提供多个电子邮件创作选项。 下表显示了每种解决方案的主要可能性、优势和限制。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> 电子邮件设计人员<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>开始空白电子邮件</strong><br /> </td> 
   <td> 支持<br /> </td> 
   <td> 支持<br /> </td> 
   <td> 支持<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>编写HTML</strong><br /> </td> 
   <td> 支持<br /> </td> 
   <td> 不支持<br /> </td> 
   <td> 支持<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>更新HTML</strong><br /> </td> 
   <td> 仅在HTML组件内<br /> </td> 
   <td> 不支持<br /> </td> 
   <td> 支持<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>基本个性化</strong><br /> </td> 
   <td> 支持<br /> </td> 
   <td> 支持<br /> </td> 
   <td> 支持<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>高级个性化</strong><br /> </td> 
   <td> 支持<br /> </td> 
   <td> 不支持<br /> </td> 
   <td> 不支持<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>校样／预览</strong><br /> </td> 
   <td> 支持<br /> </td> 
   <td> 在Campaign的AEM<br /> Proof中预览<br /> </td> 
   <td> 在Campaign中预览和校样<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>产品列表</strong><br /> </td> 
   <td> 电子邮件交易消息中支持<br /> </td> 
   <td> 不支持<br /> </td> 
   <td> 不支持<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>优势</strong><br /> </td> 
   <td> 
     -通过拖放体验轻松构建电子邮件<br/>-类似于旧版内容编辑器的功能<br/>-包含片段的可重用内容
  </td> 
   <td> 
     -在电子邮件中重用网站中的资产<br/>-在电子邮件内容中利用Experience manager的强大功能
    </td> 
   <td> 
    -开发人员可以直接编写电子邮件代码<br/>-双向同步<br/>-在Dreamweaver中脱机编辑并稍后同步<br/>-通过Dreamweaver将图像上传到Adobe Campaign
  </td> 
  </tr> 
  <tr> 
   <td> <strong>限制</strong><br /> </td> 
   <td> 
     -片段内没有条件内容<br/>-无法使用Experience manager片段
  </td> 
   <td> 
     -难以实施的高级个性化<br/>-需要在Adobe Campaign中发送测试
  </td> 
   <td> 不支持动态内容<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>受众</strong><br /> </td> 
   <td> 希望保持HTML组件与拖放功能结合使用的灵活性的营销人员<br /> </td> 
   <td> 营销人员已经使用Experience Manager，他们希望使用标准电子邮件模板，但很少个性化<br /> </td> 
   <td> 希望编码电子邮件内容并直接与Adobe Campaign集成的开发人员<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>了解更多信息</strong><br /> </td> 
   <td> 了解 <a href="../../designing/using/overview.md">电子邮件设计人员</a><br /> </td> 
   <td> 请参 <a href="../../integrating/using/integrating-with-experience-manager.md">阅与Experience Manager集成</a><br /> </td> 
   <td> 查看 <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver和Campaign</a> 并观看此视 <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">频</a><br /> </td> 
  </tr> 
 </tbody> 
</table>
