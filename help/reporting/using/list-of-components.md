---
title: 组件列表
description: 在此处查找动态报告中可用的每个组件的列表及其定义。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: 8980bf05-60a8-4360-a354-445e1faeb5b2
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 0%

---

# 组件列表 {#list-of-components}

要了解有关维度和量度之间兼容性的更多信息，请参阅此 [表](/help/reporting/using/assets/dynamic_report_compatibility.pdf). 如果两个组件不兼容，单元格将显示值 **无**.

[![图像](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf)

## 维度 {#dimensions}

下表列出了报表中使用的维度及其定义。

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
   <td> 从中打开或单击消息的浏览器。<br /> </td> 
  </tr> 
  <tr> 
   <td> 营销活动<br /> </td> 
   <td> 营销活动的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 城市<br /> </td> 
   <td> 在收件人信息配置文件中注册的城市。<br /> </td> 
  </tr> 
  <tr> 
   <td> 国家/地区<br /> </td> 
   <td> 在收件人信息配置文件中注册的国家/地区。<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放<br /> </td> 
   <td> 投放的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 设备<br /> </td> 
   <td> 从中打开/查看/单击电子邮件/短信/推送通知的设备。<br /> </td> 
  </tr> 
  <tr> 
   <td> 失败原因<br /> </td> 
   <td> 导致每次投放退回的错误类型，例如用户未知、无效域或邮箱已满。<br /> </td> 
  </tr> 
  <tr> 
   <td> 性别<br /> </td> 
   <td> 收件人的性别，例如男性或女性。 如果收件人配置文件中的gender字段为空，则该值将为none。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内消息操作<br /> </td> 
   <td> 对已投放应用程序内消息的操作，例如对按钮1或2的操作或解除。<br /> </td> 
  </tr> 
  <tr> 
   <td> 消息类型<br /> </td> 
   <td> 用于投放的渠道，如电子邮件、短信、推送通知或应用程序内消息。<br /> </td> 
  </tr> 
  <tr> 
   <td> 移动应用程序名称<br /> </td> 
   <td> 移动应用程序的名称<br /> </td> 
  </tr> 
  <tr> 
   <td> 平台<br /> </td> 
   <td> 从中打开/查看/单击消息的设备的平台。<br /> </td> 
  </tr> 
  <tr> 
   <td> 个人资料<br /> </td> 
   <td> 重组在用户档案资源扩展期间创建的现成和自定义用户档案字段，有关更多信息，请参阅此 <a href="../../developing/using/key-steps-to-add-a-resource.md">页面</a> 或此 <a href="../../reporting/using/creating-a-custom-profile-dimension.md">示例</a>.<br /> 请注意，一旦发布链接到用户档案字段的自定义资源，将立即检索此维度的数据。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送平台<br /> </td> 
   <td> 从中打开推送通知的设备的平台，如iOS或Android。<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件人域<br /> </td> 
   <td> 用于打开电子邮件的域。<br /> </td> 
  </tr> 
  <tr> 
   <td> 循环投放<br /> </td> 
   <td> 定期投放的标签和ID。<br /> </td> 
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
   <td> 在收件人配置文件中注册的州/省。<br /> </td> 
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
   <td> 为URL指定的标签，如镜像页面、联系我们或打开。<br /> </td> 
  </tr> 
  <tr> 
   <td> 事务性投放<br /> </td> 
   <td> 事务型投放的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 变量<br /> </td> 
   <td> A/B测试时电子邮件的变体。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 量度 {#metrics}

下表列出了报表中使用的量度及其定义，具体取决于投放类型。

### 电子邮件和短信量度 {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 量度<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 在阻止列表<br /> </td> 
   <td> 将电子邮件声明为垃圾邮件或垃圾邮件的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 阻止列表率<br /> </td> 
   <td> 在阻止列表上标记的投放百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 退回+错误<br /> </td> 
   <td> 投放和自动返回处理期间累计的错误总数与已发送消息的总数相关。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跳出+错误率<br /> </td> 
   <td> 退回的电子邮件与发送的电子邮件相比的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> 在投放中点击内容的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 点进率<br /> </td> 
   <td> 投放中的点击百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已投放<br /> </td> 
   <td> 成功发送的消息数，与已发送消息的总数相关。<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放率<br /> </td> 
   <td> 成功发送的消息百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬退回<br /> </td> 
   <td> 永久错误的总数，如错误的电子邮件地址。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬跳出率<br /> </td> 
   <td> 因永久错误而失败的投放百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 镜像页面<br /> </td> 
   <td> 点击镜像页面链接的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 镜像页面速率<br /> </td> 
   <td> 与投放消息总数相比，镜像页面链接的点击次数百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 优惠点击次数<br /> </td> 
   <td> 在投放中单击优惠的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 优惠点击率<br /> </td> 
   <td> 优惠的点击百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开<br /> </td> 
   <td> 在投放中打开消息的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开率<br /> </td> 
   <td> 打开邮件的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理/已发送<br /> </td> 
   <td> 投放的发送总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔离<br /> </td> 
   <td> 退回并导致地址隔离的邮件数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔离率<br /> </td> 
   <td> 与已发送消息相比的隔离百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 被拒绝<br /> </td> 
   <td> SMTP服务器分类为垃圾邮件的邮件数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 拒绝率<br /> </td> 
   <td> 标记为拒绝的邮件的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 软退回<br /> </td> 
   <td> 临时错误总数，如收件箱已满。<br /> </td> 
  </tr> 
  <tr> 
   <td> 软退回率<br /> </td> 
   <td> 因临时原因而失败的投放百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特点击<br /> </td> 
   <td> 点击投放中内容的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特打开次数<br /> </td> 
   <td> 打开投放的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一退订<br /> </td> 
   <td> 点击退订链接的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消订阅率<br /> </td> 
   <td> 与已投放消息相比的独特退订数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已取消订阅<br /> </td> 
   <td> 取消订阅链接的点击次数。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 推送通知量度 {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 量度<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 退回+错误<br /> </td> 
   <td> 投放期间累计的错误总数与已发送消息的总数相关，例如来自MCPNS或提供商的错误。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跳出+错误率<br /> </td> 
   <td> 退回的推送通知与已发送的推送通知相比的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> 推送通知送达设备并被用户单击的次数。 用户希望查看通知（通知随后将被移动到推送打开跟踪），或者关闭它。<br /> </td> 
  </tr> 
  <tr> 
   <td> 点进率<br /> </td> 
   <td> 与推送通知交互的用户百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已投放<br /> </td> 
   <td> 成功发送的推送通知数，与已发送推送通知的总数相关。<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放率<br /> </td> 
   <td> 已成功发送的推送通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> 将推送通知传递到设备并在通知中心保持未接触的次数。 在大多数情况下，展示次数应与交付次数相似。 这可确保设备收到消息并将该信息中继回服务器。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理/已发送<br /> </td> 
   <td> 发送的推送通知总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开<br /> </td> 
   <td> 发送到设备并由用户单击从而打开应用程序的推送通知总数。 这与推送点击类似，不同之处在于，如果取消通知，则不会触发推送打开。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开率<br /> </td> 
   <td> 已打开推送通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特点击<br /> </td> 
   <td> 独特用户与推送通知进行交互（例如单击通知或按钮）的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特展示次数<br /> </td> 
   <td> 收件人展示的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特打开次数<br /> </td> 
   <td> 打开投放的收件人数量。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 应用程序内量度 {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 量度<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已投放<br /> </td> 
   <td> 服务提供商发送到设备的应用程序内消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> 收件人查看的应用程序内消息总数，具体取决于是否满足触发器条件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点击次数 <br /> </td> 
   <td> 点击按钮1或按钮2的收件人总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点进率<br /> </td> 
   <td> 与看到消息的用户相比，点击按钮1或按钮2的用户百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解除<br /> </td> 
   <td> 收件人通过单击关闭按钮或自动关闭而关闭的消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解雇率<br /> </td> 
   <td> 收件人已解除的应用程序内消息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理/已发送<br /> </td> 
   <td> 作为投放发送过程的一部分从Adobe Campaign发送的应用程序内消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特展示次数<br /> </td> 
   <td> 独特收件人的展示次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内独特点击次数<br /> </td> 
   <td> 收件人点击按钮1或按钮2的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特应用程序内解除<br /> </td> 
   <td> 收件人解除应用程序内消息的次数。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 区段 {#segments}

下表列出了报表中使用的区段及其定义。

<table> 
 <thead> 
  <tr> 
   <th> 区段<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 年龄：婴儿潮一代1<br /> </td> 
   <td> 1946年至1954年出生的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：婴儿潮一代2<br /> </td> 
   <td> 1955年至1965年出生的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从18岁到25岁<br /> </td> 
   <td> 18至25岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从26到30<br /> </td> 
   <td> 26到30岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从31到40<br /> </td> 
   <td> 31至40岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从41岁到50岁<br /> </td> 
   <td> 41到50岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：第X代<br /> </td> 
   <td> 1966年至1976年出生的收件者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：Y代（千禧一代）<br /> </td> 
   <td> 1977年至1994年出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：Z代<br /> </td> 
   <td> 1995年至今天出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：大于50<br /> </td> 
   <td> 年龄超过50岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：小于25岁<br /> </td> 
   <td> 年龄小于25岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：小于30岁<br /> </td> 
   <td> 年龄小于30岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：40岁以下<br /> </td> 
   <td> 年龄小于40岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：小于50岁<br /> </td> 
   <td> 年龄小于50岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：静默世代<br /> </td> 
   <td> 1945年或之前出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 所有访问<br /> </td> 
   <td> 每个收件人<br /> </td> 
  </tr>
 </tbody> 
</table>
