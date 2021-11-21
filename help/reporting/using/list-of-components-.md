---
title: '组件列表 '
description: 在此处查找动态报告中可用的每个组件的列表及其定义。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: 8980bf05-60a8-4360-a354-445e1faeb5b2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 1%

---

# 组件列表 {#list-of-components}

要了解有关维度和量度之间兼容性的更多信息，请参阅此 [表](/help/reporting/using/assets/dynamic_report_compatibility.pdf). 如果两个组件不兼容，则单元格将显示值 **无**.

[![图像](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=en)

## Dimension {#dimensions}

下表提供了报表中使用的维度列表及其定义。

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
   <td> 营销活动的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 城市<br /> </td> 
   <td> 在收件人用户档案中注册的城市。<br /> </td> 
  </tr> 
  <tr> 
   <td> 国家/地区<br /> </td> 
   <td> 收件人用户档案中注册的国家/地区。<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放<br /> </td> 
   <td> 投放的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 设备<br /> </td> 
   <td> 打开/查看/单击电子邮件/短信/推送通知的设备。<br /> </td> 
  </tr> 
  <tr> 
   <td> 失败原因<br /> </td> 
   <td> 导致每次投放退回（例如用户未知、域无效或邮箱已满）的错误类型。<br /> </td> 
  </tr> 
  <tr> 
   <td> 性别<br /> </td> 
   <td> 接受者的性别，如男性或女性。 如果收件人用户档案中的性别字段为空，则值为“无”。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内消息操作<br /> </td> 
   <td> 对传递的应用程序内消息执行的操作，例如对按钮1或2的操作或被解除的操作。<br /> </td> 
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
   <td> 打开/查看/单击消息的设备的平台。<br /> </td> 
  </tr> 
  <tr> 
   <td> 用户档案<br /> </td> 
   <td> 重组在用户档案资源扩展期间创建的现成和自定义用户档案字段，有关更多信息，请参阅此内容 <a href="../../developing/using/key-steps-to-add-a-resource.md">页面</a> 或 <a href="../../reporting/using/creating-a-custom-profile-dimension.md">示例</a>.<br /> 请注意，一旦发布链接到用户档案字段的自定义资源，即会检索此维度的数据。<br /> </td> 
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
   <td> 州<br /> </td> 
   <td> 收件人用户档案中注册的州。<br /> </td> 
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
   <td> 为URL提供的标签（如镜像页面），请与我们联系或打开。<br /> </td> 
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

下表提供了报表中使用的量度列表及其定义，具体取决于投放类型。

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
   <td> 开阻止列表启<br /> </td> 
   <td> 声明电子邮件为垃圾邮件或垃圾邮件的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 阻止列表率<br /> </td> 
   <td> 在“”上标记的投放阻止列表百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跳出次数+错误<br /> </td> 
   <td> 在投放和自动回访处理过程中累积的与已发送消息总数有关的错误总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跳出+错误率<br /> </td> 
   <td> 退回的电子邮件与已发送电子邮件的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> 在投放中点击内容的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 点进率<br /> </td> 
   <td> 投放中的点击次数百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已交付<br /> </td> 
   <td> 已成功发送的消息数，与已发送消息的总数有关。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付率<br /> </td> 
   <td> 成功发送的消息的百分比。<br /> </td> 
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
   <td> 单击镜像页面链接的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 镜像页面速率<br /> </td> 
   <td> 在镜像页面链接上的点击次数与总投放消息数的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 选件点击量<br /> </td> 
   <td> 在投放中点击选件的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 选件点击率<br /> </td> 
   <td> 选件的点击百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开<br /> </td> 
   <td> 投放中消息打开的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开率<br /> </td> 
   <td> 已打开消息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理/已发送<br /> </td> 
   <td> 投放的发送总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔离<br /> </td> 
   <td> 退回并导致地址隔离的消息数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔离率<br /> </td> 
   <td> 与已发送消息相比的隔离百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 被拒绝<br /> </td> 
   <td> 被SMTP服务器分类为垃圾邮件的邮件数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 拒绝率<br /> </td> 
   <td> 标记为已拒绝的消息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 软退回<br /> </td> 
   <td> 临时错误（如完整收件箱）的总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 软跳出率<br /> </td> 
   <td> 因临时原因而失败的投放的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特点击<br /> </td> 
   <td> 点击投放内容的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开数<br /> </td> 
   <td> 打开投放的收件人数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特退订<br /> </td> 
   <td> 单击退订链接的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 退订率<br /> </td> 
   <td> 与已投放消息相比，独特退订的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已取消订阅<br /> </td> 
   <td> 退订链接的点击次数。<br /> </td> 
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
   <td> 跳出次数+错误<br /> </td> 
   <td> 在投放期间累积的与已发送消息总数有关的错误总数，例如来自MCPNS或提供商的错误。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跳出+错误率<br /> </td> 
   <td> 与发送的推送通知相比，已退回的推送通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> 将推送通知发送到设备并由用户单击的次数。 用户要么想要查看通知（该通知随后将被移至推送打开跟踪），要么就将其关闭。<br /> </td> 
  </tr> 
  <tr> 
   <td> 点进率<br /> </td> 
   <td> 与推送通知交互的用户百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已交付<br /> </td> 
   <td> 成功发送的推送通知数，与已发送的推送通知总数有关。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付率<br /> </td> 
   <td> 成功发送推送通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> 将推送通知发送到设备且未在通知中心受到影响的次数。 在大多数情况下，展示次数数应与已交付的数量相似。 这可确保设备收到消息并将该信息转发回服务器。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理/已发送<br /> </td> 
   <td> 发送的推送通知总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开<br /> </td> 
   <td> 用户交付到设备并点击的推送通知总数，从而打开应用程序。 这类似于推送点击，除非取消通知后不会触发推送打开。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开率<br /> </td> 
   <td> 打开的推送通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特点击<br /> </td> 
   <td> 独特用户与推送通知交互的次数，例如单击通知或按钮。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特展示次数<br /> </td> 
   <td> 收件人的展示次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开数<br /> </td> 
   <td> 打开投放的收件人数。<br /> </td> 
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
   <td> 已交付<br /> </td> 
   <td> 服务提供商交付到设备的应用程序内消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> 收件人查看的应用程序内消息总数，具体取决于是否满足触发器标准。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点击 <br /> </td> 
   <td> 单击按钮1或按钮2的收件人总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点进率<br /> </td> 
   <td> 单击按钮1或按钮2的用户与查看消息的用户的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解聘<br /> </td> 
   <td> 通过单击关闭按钮或自动关闭收件人已忽略的消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解雇率<br /> </td> 
   <td> 收件人取消的应用程序内消息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理/已发送<br /> </td> 
   <td> 在投放发送过程中从Adobe Campaign发送的应用程序内消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特展示次数<br /> </td> 
   <td> 独特收件人的展示次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内独特点击次数<br /> </td> 
   <td> 收件人单击按钮1或按钮2的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特的应用程序内解雇<br /> </td> 
   <td> 收件人取消应用程序内消息的次数。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 区段 {#segments}

下表提供了报表中使用的区段列表及其定义。

<table> 
 <thead> 
  <tr> 
   <th> 区段<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 年龄：婴儿潮一代<br /> </td> 
   <td> 1946年至1954年出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：婴儿潮2岁<br /> </td> 
   <td> 1955年至1965年生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从18到25<br /> </td> 
   <td> 18至25岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从26到30<br /> </td> 
   <td> 26至30岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从31到40<br /> </td> 
   <td> 31至40岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从41到50<br /> </td> 
   <td> 41至50岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：第X代<br /> </td> 
   <td> 1966年至1976年出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：Y代（千禧一代）<br /> </td> 
   <td> 1977年至1994年生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：Z代<br /> </td> 
   <td> 1995年至今的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：大于50<br /> </td> 
   <td> 年龄大于50岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：少于25<br /> </td> 
   <td> 年龄小于25岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：少于30<br /> </td> 
   <td> 年龄小于30岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：少于40<br /> </td> 
   <td> 年龄小于40岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：少于50<br /> </td> 
   <td> 年龄小于50岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：沉默的一代<br /> </td> 
   <td> 1945年或之前出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 所有访问<br /> </td> 
   <td> 每个收件人<br /> </td> 
  </tr>
 </tbody> 
</table>
