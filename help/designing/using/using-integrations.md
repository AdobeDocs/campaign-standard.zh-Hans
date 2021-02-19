---
solution: Campaign Standard
product: campaign
title: '通过Adobe Campaign集成设计电子邮件 '
description: 了解如何通过电子邮件设计器中的Adobe Campaign集成来设计电子邮件。
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 5758e5f0f6811a97f51e995fa3c378a7c7117ff5
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 6%

---


# 多解决方案电子邮件设计 {#multi-solution-email-design}

Adobe Campaign优惠了多个电子邮件创作选项。 您可以使用Dreamweaver等解决方案编辑电子邮件内容并在电子邮件设计器中创建响应式消息。 您还可以使用Adobe Experience Manager通过电子邮件发送内容，并在您在Adobe Campaign Standard的电子邮件中使用。

## 在Dreamweaver {#editing-content-in-dreamweaver}中编辑内容

Adobe Campaign Standard与Dreamweaver的集成允许您在Dreamweaver界面中编辑电子邮件内容。 您可以访问Dreamweaver的强大界面来设计和开发响应式电子邮件内容。

* **双向同步**

   只要在一个产品中进行编辑，就会在另一个产品中实时更新。 如果要更改Dreamweaver中文本的颜色，则在您进行该编辑后，文本的颜色将保持活动。 此外，当您在Dreamweaver或活动中选择代码时，由于行号相同，因此选择将保留在两个产品之间，这在查找代码中的特定内容时非常有用。

* **通过 Dreamweaver 将本地图像上传到 Adobe Campaign**

   在Dreamweaver中创建或编辑电子邮件时，您只需从桌面或本地计算机中选择图像即可。 虽然Dreamweaver始终允许您这样做，但连接Dreamweaver和活动后，本地文件会立即上传到Adobe Campaign服务器：无需随内容变化手动上传图像。 此外，它还可确保始终以活动形式显示最新图像。

* **在Dreamweaver中添加活动个性化**

   对于电子邮件开发人员，不再需要添加文本（如`[[FIRSTNAME_PLACEHOLDER]]`），也无需查找数据模型表的语法。 Dreamweaver中的活动工具栏直接连接到您的活动实例的数据模型。 这意味着您可以从名字到地址之类的数据中提取任何个性化数据。 如果您已在活动中创建了内容块，则还可以将这些内容块直接拉入Dreamweaver。

此功能详见可访问[此处](https://helpx.adobe.com/cn/dreamweaver/using/working-with-dreamweaver-and-campaign.html)的Dreamweaver文档。

![](assets/do-not-localize/how-to-video.png) [在视频中发现此功能](#video)

## 在Experience Manager {#editing-content-in-experience-manager}中编辑内容

可以在Experience Manager中编辑电子邮件内容，然后在Adobe Campaign Standard中用于一封或多封电子邮件。 请参阅[本文档](../../integrating/using/integrating-with-experience-manager.md)。

## 产品列表{#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="使用产品列表"
>abstract="产品列表允许您引用数据收集并在电子邮件内容中显示它。"

产品列表允许您在电子邮件内容中引用一个或多个数据集合。 这些列表可用于交易电子邮件。 [此处](../../designing/using/using-product-listings.md)提供了此功能的专用部分。

## 电子邮件设计选项比较{#email-design-options-comparison}

Adobe Campaign优惠了多个电子邮件创作选项。 下表显示了其中每一种服务的主要可能性、优势和限制。

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
   <td> 支持的<br /> </td> 
   <td> 支持的<br /> </td> 
   <td> 支持的<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>编写HTML</strong><br /> </td> 
   <td> 支持的<br /> </td> 
   <td> 不支持<br /> </td> 
   <td> 支持的<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>更新HTML</strong><br /> </td> 
   <td> 仅在HTML组件<br />内 </td> 
   <td> 不支持<br /> </td> 
   <td> 支持的<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>基本个性化</strong><br /> </td> 
   <td> 支持的<br /> </td> 
   <td> 支持的<br /> </td> 
   <td> 支持的<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>高级个性化</strong><br /> </td> 
   <td> 支持的<br /> </td> 
   <td> 不支持<br /> </td> 
   <td> 不支持<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>验证/预览</strong><br /> </td> 
   <td> 支持的<br /> </td> 
   <td> 预览在AEM<br />验证活动<br />中 </td> 
   <td> 预览和活动<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>产品列表</strong><br /> </td> 
   <td> 电子邮件事务性消息<br />中支持 </td> 
   <td> 不支持<br /> </td> 
   <td> 不支持<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>优势</strong><br /> </td> 
   <td> 
     <p> — 通过拖放体验轻松构建电子邮件</p>
     <p> — 类似于旧版内容编辑器的功能</p>
     <p> — 可重复使用的片段内容</p>
  </td> 
   <td> 
     <p> — 在电子邮件中重复使用来自网站的资源</p>
     <p> — 利用电子邮件内容中的Experience Manager功能</p>
    </td> 
   <td> 
    <p> — 开发人员能够直接对电子邮件进行编码</p>
    <p> — 双向同步</p>
    <p> — 在Dreamweaver中脱机编辑并稍后同步</p>
    <p> — 通过Dreamweaver将图像上传到Adobe Campaign</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>限制</strong><br /> </td> 
   <td> 
     <p> — 片段中没有条件内容</p>
     <p> — 无法使用Experience Manager片段</p>
  </td> 
   <td> 
     <p> — 难以实施的高级个性化</p>
     <p> — 需要以Adobe Campaign发送测试</p>
  </td> 
   <td> 不支持动态内容<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>受众</strong><br /> </td> 
   <td> 希望保持HTML组件与拖放功能结合使用的灵活性的营销人员<br /> </td> 
   <td> 营销人员已经在使用希望使用基本个性化的标准电子邮件模板的Experience Manager<br /> </td> 
   <td> 希望编码电子邮件内容并直接与Adobe Campaign<br />集成的开发人员 </td> 
  </tr> 
  <tr> 
   <td> <strong>了解更多信息</strong><br /> </td> 
   <td> 请参阅<a href="../../designing/using/designing-content-in-adobe-campaign.md">关于电子邮件设计器</a>。<br /> </td> 
   <td> 请参阅<a href="../../integrating/using/integrating-with-experience-manager.md">与Experience Manager集成</a>。<br /> </td> 
   <td> 请参阅<a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver和活动</a>并观看此<a href="#video">视频</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 教程视频{#video}

此视频演示如何使用Dreamweaver为Adobe Campaign Standard创建和编辑内容。

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

其他Campaign Standard操作视频[此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans)可用。
