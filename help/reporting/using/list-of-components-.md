---
solution: Campaign Standard
product: campaign
title: '组件列表 '
description: 在此处查找     动态报表及其定义。
audience: reporting
content-type: reference
topic-tags: about-reporting
translation-type: tm+mt
source-git-commit: 6fffc6a3574c71c01f1e07ff4e6e6aa194479079
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 1%

---


# 组件列表 {#list-of-components}

要进一步了解维与度量之间的兼容性，请参阅此[表](/help/reporting/using/assets/dynamic_report_compatibility.pdf)。 如果两个组件不兼容，单元格将显示值&#x200B;**无**。

[![图像](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=en)

## Dimension{#dimensions}

下表提供了报表中使用的维的列表及其定义。

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 浏览器<br /> </td> 
   <td> 打开或单击消息的浏览器。<br /> </td> 
  </tr> 
  <tr> 
   <td> 营销活动<br /> </td> 
   <td> 活动的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 城市<br /> </td> 
   <td> 在收件人用户档案注册的城市。<br /> </td> 
  </tr> 
  <tr> 
   <td> 国家／地区<br /> </td> 
   <td> 在收件人用户档案注册的国家／地区。<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放<br /> </td> 
   <td> 投放的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 设备<br /> </td> 
   <td> 打开／查看／单击电子邮件/SMS/推送通知的设备。<br /> </td> 
  </tr> 
  <tr> 
   <td> 失败原因<br /> </td> 
   <td> 导致每个投放弹回的错误类型，例如用户未知、无效域或邮箱已满。<br /> </td> 
  </tr> 
  <tr> 
   <td> 性别<br /> </td> 
   <td> 收件人的性别，如男性或女性。 如果收件人用户档案中的性别字段为空，则该值将为无。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内消息操作<br /> </td> 
   <td> 已交付对应用程序内消息的操作，例如按钮1或2的操作或解除的操作。<br /> </td> 
  </tr> 
  <tr> 
   <td> 消息类型<br /> </td> 
   <td> 用于投放的渠道，如电子邮件、短信、推送通知或应用程序内。<br /> </td> 
  </tr> 
  <tr> 
   <td> 移动应用程序名称<br /> </td> 
   <td> 移动应用程序的名称<br /> </td> 
  </tr> 
  <tr> 
   <td> 平台<br /> </td> 
   <td> 打开／查看／单击消息的设备的平台。<br /> </td> 
  </tr> 
  <tr> 
   <td> 用户档案<br /> </td> 
   <td> 重新分组在用户档案资源扩展期间创建的现成和自定义用户档案字段，有关详细信息，请参阅此<a href="../../developing/using/key-steps-to-add-a-resource.md">页</a>或此<a href="../../reporting/using/creating-a-custom-profile-dimension.md">示例</a>。<br /> 请注意，一旦发布链接到用户档案字段的自定义资源，便会检索该维的数据。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送平台<br /> </td> 
   <td> 打开推送通知的设备的平台，如iOS或Android。<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件人域<br /> </td> 
   <td> 用于打开电子邮件的域。<br /> </td> 
  </tr> 
  <tr> 
   <td> 循环投放<br /> </td> 
   <td> 重复投放的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 发件人域<br /> </td> 
   <td> 用于发送电子邮件的域。<br /> </td> 
  </tr> 
  <tr> 
   <td> 发件人IP<br /> </td> 
   <td> 用于发送电子邮件的IP。<br /> </td> 
  </tr> 
  <tr> 
   <td> 状态<br /> </td> 
   <td> 在收件人用户档案中注册的状态。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跟踪URL<br /> </td> 
   <td> 用户从消息中单击的URL。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跟踪URL类别<br /> </td> 
   <td> 分配给跟踪URL的类别。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跟踪URL标签<br /> </td> 
   <td> 给URL的标签，如镜像页面、联系我们或打开。<br /> </td> 
  </tr> 
  <tr> 
   <td> 事务投放<br /> </td> 
   <td> 事务投放的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 变体<br /> </td> 
   <td> A/B测试时电子邮件的变体。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 指标{#metrics}

下表根据投放类型为您提供了报告中使用的度量的列表及其定义。

### 电子邮件和短信量度{#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 度量<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 在阻止列表<br /> </td> 
   <td> 已声明电子邮件为垃圾邮件或垃圾邮件的收件人数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 阻止列表率<br /> </td> 
   <td> 投放上标阻止列表记的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 弹回次数+错误<br /> </td> 
   <td> 在投放和自动返回处理期间累积的与已发送消息总数相关的错误总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 弹回率+错误率<br /> </td> 
   <td> 弹回的电子邮件与发送的电子邮件的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> 在投放中单击内容的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 点进率<br /> </td> 
   <td> 投放中的点击百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已交付<br /> </td> 
   <td> 与已发送邮件总数相关的已成功发送邮件数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交货率<br /> </td> 
   <td> 成功发送邮件的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬弹起<br /> </td> 
   <td> 永久错误的总数，如错误的电子邮件地址。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬弹起率<br /> </td> 
   <td> 因永久错误而失败的投放百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 镜像页面<br /> </td> 
   <td> 单击收件人链接的镜像页面数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 镜像页面率<br /> </td> 
   <td> 镜像页面链接与投放消息总数的点击率。<br /> </td> 
  </tr> 
  <tr> 
   <td> 优惠单击<br /> </td> 
   <td> 在优惠中单击投放的时间。<br /> </td> 
  </tr> 
  <tr> 
   <td> 优惠点击率<br /> </td> 
   <td> 优惠上的点击百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开<br /> </td> 
   <td> 在投放中打开消息的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开速率<br /> </td> 
   <td> 已打开邮件的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理／已发送<br /> </td> 
   <td> 投放的发送总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔离<br /> </td> 
   <td> 弹回并导致地址隔离的消息数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔离率<br /> </td> 
   <td> 隔离与已发送消息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 被拒绝<br /> </td> 
   <td> SMTP服务器归类为垃圾邮件的邮件数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 被拒绝速率<br /> </td> 
   <td> 标记为已拒绝的邮件百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 软弹起<br /> </td> 
   <td> 临时错误的总数，如完整收件箱。<br /> </td> 
  </tr> 
  <tr> 
   <td> 软弹跳率<br /> </td> 
   <td> 因临时原因失败的投放百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击次数唯一<br /> </td> 
   <td> 单击收件人中某个内容的投放数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开次数<br /> </td> 
   <td> 打开投放的收件人数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消订阅率<br /> </td> 
   <td> 按收件人划分的退订与已传送消息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消订阅<br /> </td> 
   <td> 单击退订链接的次数。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 推送通知量度{#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 度量<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 弹回次数+错误<br /> </td> 
   <td> 在投放期间累积的与已发送消息总数相关的错误总数，例如MCPNS或提供程序的错误。<br /> </td> 
  </tr> 
  <tr> 
   <td> 弹回率+错误率<br /> </td> 
   <td> 与发送的推送通知相比，退回的推送通知百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> 推送通知被交付到设备并被用户点击的次数。 用户要么希望视图通知，然后将其移至“推送打开”跟踪，要么将其关闭。<br /> </td> 
  </tr> 
  <tr> 
   <td> 点进率<br /> </td> 
   <td> 与推送通知交互的用户百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已交付<br /> </td> 
   <td> 成功发送的推送通知数，与已发送的推送通知总数相关。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交货率<br /> </td> 
   <td> 成功发送推送通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> 推送通知已发送到设备且未在通知中心更改的次数。 在大多数情况下，展示次数应与已交付数目相似。 这可确保设备收到消息并将该信息中继回服务器。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理／已发送<br /> </td> 
   <td> 发送的推送通知总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开<br /> </td> 
   <td> 用户点击的推送通知总数，从而打开应用程序。 这与推送单击类似，但如果通知消失，则不会触发推送打开。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开速率<br /> </td> 
   <td> 已打开的推送通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击次数唯一<br /> </td> 
   <td> 唯一用户与推送通知交互的次数，例如单击通知或按钮。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一印象<br /> </td> 
   <td> 按收件人列出的展示次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开次数<br /> </td> 
   <td> 打开投放的收件人数。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 应用程序内度量{#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 度量<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已交付<br /> </td> 
   <td> 服务提供商向设备传送的应用程序内消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> 收件人看到的应用程序内消息总数，具体取决于是否满足触发器标准。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内单击<br /> </td> 
   <td> 单击Button 1或Button 2的收件人总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点击率<br /> </td> 
   <td> 单击“按钮1”或“按钮2”的用户与看到该消息的用户的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解聘<br /> </td> 
   <td> 通过单击关闭按钮或自动关闭收件人消失的消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解雇率<br /> </td> 
   <td> 收件人消失的应用程序内消息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理／已发送<br /> </td> 
   <td> 作为Adobe Campaign发送流程的一部分，从投放发送的应用程序内消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一印象<br /> </td> 
   <td> 唯一收件人的展示次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内单击次数唯一<br /> </td> 
   <td> 收件人单击Button 1或Button 2的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一应用程序内解除<br /> </td> 
   <td> 收件人忽略应用程序内消息的时间数。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 区段{#segments}

>[!NOTE]
>
>默认情况下，**[!UICONTROL Exclude proof]**&#x200B;区段已选中，以过滤您的报告，但可以根据需要进行更改。

下表提供了报告中使用的区段的列表及其定义。

<table> 
 <thead> 
  <tr> 
   <th> 段<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 年龄：婴儿潮一代1<br /> </td> 
   <td> 收件人生于1946年至1954年。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：婴儿潮一代2<br /> </td> 
   <td> 收件人生于1955年至1965年。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从18到25<br /> </td> 
   <td> 收件人年龄在18至25岁之间。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从26到30<br /> </td> 
   <td> 收件人26岁至30岁。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从31到40<br /> </td> 
   <td> 收件人31岁至40岁。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从41到50<br /> </td> 
   <td> 收件人41岁至50岁。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：X<br />代 </td> 
   <td> 收件人生于1966年至1976年。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：Y代（千禧一代）<br /> </td> 
   <td> 收件人生于1977年至1994年。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：Z代<br /> </td> 
   <td> 收件人从1995年出生至今。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：大于50<br /> </td> 
   <td> 年龄大于50的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：小于25<br /> </td> 
   <td> 年龄低于25的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：小于30<br /> </td> 
   <td> 年龄小于30的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：小于40<br /> </td> 
   <td> 年龄小于40的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：小于50<br /> </td> 
   <td> 年龄小于50的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：静默生成<br /> </td> 
   <td> 收件人生于1945年或之前。<br /> </td> 
  </tr> 
  <tr> 
   <td> 所有访问<br /> </td> 
   <td> 每个收件人<br /> </td> 
  </tr> 
    <tr> 
   <td> 排除验证<br /> </td> 
   <td> 从报告中排除验证<br /> </td> 
  </tr> 
 </tbody> 
</table>

