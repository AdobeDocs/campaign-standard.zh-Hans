---
title: 通过Adobe Campaign集成设计电子邮件
description: 在电子邮件Designer中了解如何通过Adobe Campaign集成设计电子邮件。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d5c72f69-68a2-4523-956f-f265ae79b470
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 5%

---

# 多解决方案电子邮件设计 {#multi-solution-email-design}

Adobe Campaign提供了多个电子邮件创作选项。 您可以在Email Designer中使用Dreamweaver等解决方案编辑电子邮件内容并创建响应式消息。 您还可以通过Adobe Experience Manager发送内容电子邮件，并在Adobe Campaign Standard的电子邮件中使用这些内容。

## 在Dreamweaver中编辑内容 {#editing-content-in-dreamweaver}

Adobe Campaign Standard与Dreamweaver集成允许您在Dreamweaver界面中编辑电子邮件的内容。 您可以访问Dreamweaver的强大界面，设计和开发响应式电子邮件内容。

* **双向同步**

  每当在一个产品中进行编辑时，就会在另一个产品中进行实时更新。 如果您要在Dreamweaver中更改文本的颜色，则一旦您进行了编辑，Campaign中文本的颜色即会变为实时颜色。 此外，当您在Dreamweaver或Campaign中选择代码时，由于行号相同，因此选择将保留在两个产品之间，这在查找代码中的特定内容时非常有用。

* **通过Dreamweaver将本地图像上传到Adobe Campaign**

  在Dreamweaver中创建或编辑电子邮件时，您只需从桌面或本地计算机中选择一个图像即可。 虽然Dreamweaver始终允许您执行此操作，但当Dreamweaver和Campaign连接时，本地文件会立即上传到Adobe Campaign服务器：无需在内容更改时手动上传图像。 此外，它还可确保在Campaign中始终实时显示最新图像。

* **在Dreamweaver中添加营销活动个性化设置**

  对于电子邮件开发人员而言，不再需要添加`[[FIRSTNAME_PLACEHOLDER]]`等文本，也不必查找数据模型表的语法。 Dreamweaver中的Campaign工具栏直接连接到Campaign实例的数据模型。 这意味着您可以从“名字”之类的“地址”中提取任何需要进行个性化的数据。 如果您已在Campaign中创建内容块，则还可以直接将这些内容块提取到Dreamweaver中。

此功能在[此处](https://helpx.adobe.com/cn/dreamweaver/using/working-with-dreamweaver-and-campaign.html)的Dreamweaver文档中进行了详细介绍。

![](assets/do-not-localize/how-to-video.png) [通过观看视频了解此功能](#video)

## 编辑Experience Manager中的内容 {#editing-content-in-experience-manager}

可以在Experience Manager中编辑电子邮件内容，然后在Adobe Campaign Standard中将其用于一封或多封电子邮件。 请参阅[本文档](../../integrating/using/integrating-with-experience-manager.md)。

## 产品列表 {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="使用产品列表"
>abstract="产品列表允许您参考数据集合并将其显示在电子邮件内容中。"

产品列表允许您在电子邮件内容中引用一个或多个数据集合。 这些列表可用于事务性电子邮件。 [此处](../../designing/using/using-product-listings.md)提供了此功能的专用部分。

## 电子邮件设计选项比较 {#email-design-options-comparison}

Adobe Campaign提供了多个电子邮件创作选项。 下表显示了每种方法的主要可能性、好处和限制。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> 电子邮件设计工具<br /> </th> 
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
   <td> <strong>写入HTML</strong><br /> </td> 
   <td> 支持<br /> </td> 
   <td> 不支持<br /> </td> 
   <td> 支持<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>更新HTML</strong><br /> </td> 
   <td> 仅在HTML组件<br />内 </td> 
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
   <td> <strong>校对/预览</strong><br /> </td> 
   <td> 支持<br /> </td> 
   <td> 在Campaign<br />的AEM<br />验证中预览 </td> 
   <td> 在Campaign<br />中预览和验证 </td> 
  </tr> 
  <tr> 
   <td> <strong>产品列表</strong><br /> </td> 
   <td> 在电子邮件事务型消息中受支持<br /> </td> 
   <td> 不支持<br /> </td> 
   <td> 不支持<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>福利</strong><br /> </td> 
   <td> 
     <p> — 通过拖放体验轻松构建电子邮件</p>
     <p> — 与旧版内容编辑器类似的功能</p>
     <p> — 带片段的可重用内容</p>
  </td> 
   <td> 
     <p> — 在电子邮件中重用网站中的资产</p>
     <p> — 利用电子邮件内容中的Experience Manager功能</p>
    </td> 
   <td> 
    <p> — 开发人员可直接为电子邮件编码</p>
    <p> — 双向同步</p>
    <p> — 在Dreamweaver中脱机编辑并稍后同步</p>
    <p> — 通过Dreamweaver将图像上传到Adobe Campaign</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>限制</strong><br /> </td> 
   <td> 
     <p> — 片段中无条件内容</p>
     <p> — 无法使用Experience Manager片段</p>
  </td> 
   <td> 
     <p> — 难以实施的高级个性化</p>
     <p> — 需要在Adobe Campaign中发送测试</p>
  </td> 
   <td> 不支持动态内容<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>受众</strong><br /> </td> 
   <td> 希望保持将HTML组件与拖放功能结合使用的灵活性的营销人员<br /> </td> 
   <td> 营销人员已在使用Experience Manager，他们希望使用很少进行个性化的标准电子邮件模板<br /> </td> 
   <td> 希望对电子邮件内容进行编码并直接与Adobe Campaign<br />集成的开发人员 </td> 
  </tr> 
  <tr> 
   <td> <strong>了解详情</strong><br /> </td> 
   <td> 查看<a href="../../designing/using/designing-content-in-adobe-campaign.md">关于电子邮件Designer</a>.<br /> </td> 
   <td> 请参阅<a href="../../integrating/using/integrating-with-experience-manager.md">与Experience Manager集成</a>.<br /> </td> 
   <td> 观看<a href="https://helpx.adobe.com/cn/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver和Campaign</a>并观看此<a href="#video">视频</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 教程视频 {#video}

本视频说明如何使用Dreamweaver创建和编辑Adobe Campaign Standard的内容。

>[!VIDEO](https://video.tv.adobe.com/v/37481?quality=12&captions=chi_hans)

[此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans)提供了其他Campaign Standard操作方法视频。
