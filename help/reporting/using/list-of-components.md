---
title: 组件列表
description: 在此处查找中可用的每个组件的列表     动态报告及其定义。
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

要了解有关维度和量度之间兼容性的更多信息，请参阅此[表](/help/reporting/using/assets/dynamic_report_compatibility.pdf)。 如果两个组件不兼容，单元格将显示值&#x200B;**None**。

[![图像](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=zh-Hans)

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
   <td> 打开或单击邮件的浏览器。<br /> </td> 
  </tr> 
  <tr> 
   <td> 营销活动<br /> </td> 
   <td> 营销活动的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 城市<br /> </td> 
   <td> 在收件人配置文件中注册的城市。<br /> </td> 
  </tr> 
  <tr> 
   <td> 国家/地区<br /> </td> 
   <td> 在收件人的个人资料中注册的国家/地区。<br /> </td> 
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
   <td> 收件人的性别，例如男性或女性。 如果收件人配置文件中的gender字段为空，该值将为none。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内消息操作<br /> </td> 
   <td> 针对已传递的应用程序内消息的操作，例如针对按钮1或2的操作或解除。<br /> </td> 
  </tr> 
  <tr> 
   <td> 消息类型<br /> </td> 
   <td> 用于投放的渠道，如电子邮件、短信、推送通知或应用程序内消息。<br /> </td> 
  </tr> 
  <tr> 
   <td> 移动设备应用程序名称<br /> </td> 
   <td> 移动应用程序的名称<br /> </td> 
  </tr> 
  <tr> 
   <td> 平台<br /> </td> 
   <td> 从中打开/查看/单击消息的设备的平台。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配置文件<br /> </td> 
   <td> 重组在配置文件资源扩展期间创建的现成和自定义配置文件字段，有关更多信息，请参阅此<a href="../../developing/using/key-steps-to-add-a-resource.md">页面</a>或此<a href="../../reporting/using/creating-a-custom-profile-dimension.md">示例</a>。<br />请注意，一旦发布链接到用户档案字段的自定义资源，将立即检索此维度的数据。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送平台<br /> </td> 
   <td> 从中打开推送通知的设备平台，如iOS或Android。<br /> </td> 
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
   <td> 在收件人配置文件中注册的州。<br /> </td> 
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
   <td> 事务性投放的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 变体<br /> </td> 
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
   <td> 在阻止列表<br />上 </td> 
   <td> 将电子邮件声明为垃圾邮件或垃圾邮件的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 阻止列表率<br /> </td> 
   <td> 在阻止列表上标记的传递百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 退回+错误<br /> </td> 
   <td> 传递和自动返回处理期间累计的错误总数与已发送消息的总数之比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 退回+错误率<br /> </td> 
   <td> 与已发送的电子邮件相比退回的电子邮件百分比。<br /> </td> 
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
   <td> 成功发送的邮件数，与已发送的邮件总数相关。<br /> </td> 
  </tr> 
  <tr> 
   <td> 传递率<br /> </td> 
   <td> 成功发送的邮件百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬退回<br /> </td> 
   <td> 永久错误的总数，如错误的电子邮件地址。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬退回率<br /> </td> 
   <td> 因永久错误而失败的传递百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 镜像页面<br /> </td> 
   <td> 点击镜像页面链接的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 镜像页面速率<br /> </td> 
   <td> 与总投放消息相比镜像页面链接的点击次数百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 优惠点击次数<br /> </td> 
   <td> 在投放中点击优惠的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 优惠点击率<br /> </td> 
   <td> 对优惠的点击百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开<br /> </td> 
   <td> 在投放中打开邮件的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开率<br /> </td> 
   <td> 已打开邮件的百分比。<br /> </td> 
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
   <td> 已拒绝<br /> </td> 
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
   <td> 唯一打开次数<br /> </td> 
   <td> 打开投放的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一取消订阅<br /> </td> 
   <td> 点击取消订阅链接的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消订阅率<br /> </td> 
   <td> 与传递的邮件相比的唯一取消订阅数。<br /> </td> 
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
   <td> 与已发送消息总数相关的投放期间累计的错误总数，例如来自MCPNS或提供商的错误。<br /> </td> 
  </tr> 
  <tr> 
   <td> 退回+错误率<br /> </td> 
   <td> 退回的推送通知与已发送的推送通知相比的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> 推送通知送达设备并被用户单击的次数。 用户希望查看通知（该通知随后将被移动到推送打开跟踪），或者关闭它。<br /> </td> 
  </tr> 
  <tr> 
   <td> 点进率<br /> </td> 
   <td> 与推送通知交互的用户百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已投放<br /> </td> 
   <td> 成功发送的推送通知数，与已发送的推送通知总数相关。<br /> </td> 
  </tr> 
  <tr> 
   <td> 传递率<br /> </td> 
   <td> 已成功发送推送通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> 将推送通知传递到设备并在通知中心保持未接触的次数。 在大多数情况下，展示次数应与交付次数相似。 这可以确保设备收到消息并将该信息中继回服务器。<br /> </td> 
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
   <td> 收件人的展示次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开次数<br /> </td> 
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
   <td> 服务提供者传送到设备的应用程序内消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> 根据是否满足触发器条件，收件人查看的应用程序内消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点击<br /> </td> 
   <td> 点击按钮1或按钮2的收件人总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点击率<br /> </td> 
   <td> 与看到消息的用户相比，点击按钮1或按钮2的用户百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解除<br /> </td> 
   <td> 收件人通过单击“关闭”按钮或自动解除的邮件总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用内解雇率<br /> </td> 
   <td> 收件人已解除的应用程序内消息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理/已发送<br /> </td> 
   <td> 作为投放发送过程的一部分从Adobe Campaign发送的应用程序内消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特展示次数<br /> </td> 
   <td> 唯一收件人的展示次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内唯一点击次数<br /> </td> 
   <td> 收件人点击按钮1或按钮2的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一应用程序内解除<br /> </td> 
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
   <td> 1946年至1954年出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：婴儿潮一代2<br /> </td> 
   <td> 1955年至1965年出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从18到25<br /> </td> 
   <td> 18到25岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从26到30<br /> </td> 
   <td> 26到30岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从31到40<br /> </td> 
   <td> 31到40岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从41到50<br /> </td> 
   <td> 41到50岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：层代X<br /> </td> 
   <td> 1966年至1976年出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：第Y代（千禧一代）<br /> </td> 
   <td> 1977年至1994年出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：层代Z<br /> </td> 
   <td> 1995年至今天出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：大于50<br /> </td> 
   <td> 年龄大于50岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：小于25<br /> </td> 
   <td> 年龄小于25岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：小于30<br /> </td> 
   <td> 年龄小于30岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：小于40<br /> </td> 
   <td> 年龄小于40岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：小于50<br /> </td> 
   <td> 年龄小于50岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：静默生成<br /> </td> 
   <td> 1945年或之前出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 所有访问<br /> </td> 
   <td> 每个收件人<br /> </td> 
  </tr>
 </tbody> 
</table>
