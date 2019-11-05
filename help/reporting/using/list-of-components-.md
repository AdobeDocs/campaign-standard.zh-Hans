---
title: '组件列表 '
description: 在此处查找动态报表中可用的每个组件的列表及其定义。
page-status-flag: 从未激活
uuid: a2403806-8df4-4bb1-bac2-2689dc584ae0
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 报告
content-type: 参考
topic-tags: about-reporting
discoiquuid: 17cf126a-7ce1-4e11-bb5e-2bdce01cfded
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 组件列表 {#list-of-components}

要进一步了解维度与指标之间的兼容性，请参阅 [此表](https://docs.campaign.adobe.com/doc/standard/en/Technotes/dynamic_report_compatibility.pdf)。 如果两个组件不兼容，则单元格将显示值 **None**。

[![图像](/help/reporting/using/assets/dynamic_report_compatibility.png)](https://docs.campaign.adobe.com/doc/standard/en/Technotes/dynamic_report_compatibility.pdf)

## Dimensions {#dimensions}

下表提供了报表中使用的维列表及其定义。

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
   <td> City registered in the recipient's profile.<br /> </td> 
  </tr> 
  <tr> 
   <td> 国家／地区<br /> </td> 
   <td> 收件人个人资料中注册的国家／地区。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> 交付的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 设备<br /> </td> 
   <td> 打开／查看／单击电子邮件/SMS/推送通知的设备。<br /> </td> 
  </tr> 
  <tr> 
   <td> 失败原因<br /> </td> 
   <td> 导致每个交付发生弹回的错误类型，例如用户未知、无效域或邮箱已满。<br /> </td> 
  </tr> 
  <tr> 
   <td> 性别<br /> </td> 
   <td> 接受者的性别，如男性或女性。 如果收件人的个人资料中的性别字段为空，则该值将为“无”。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内消息操作<br /> </td> 
   <td> 对已交付的应用程序内消息执行的操作，例如对按钮1或2的操作或取消。<br /> </td> 
  </tr> 
  <tr> 
   <td> 消息类型<br /> </td> 
   <td> 用于交付的渠道，如电子邮件、短信、推送通知或应用程序内。<br /> </td> 
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
   <td> 配置文件<br /> </td> 
   <td> 重新分组在配置文件资源扩展期间创建的现成配置文件和自定义配置文件字段，有关详细信息，请参阅此页 <a href="../../developing/using/key-steps-to-add-a-resource.md">或</a> 本示 <a href="../../reporting/using/creating-a-custom-profile-dimension.md">例</a>。<br /> 请注意，一旦发布了链接到配置文件字段的自定义资源，即会检索此维的数据。<br /> </td> 
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
   <td> 重复交付<br /> </td> 
   <td> 重复交付的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 发送者域<br /> </td> 
   <td> 用于发送电子邮件的域。<br /> </td> 
  </tr> 
  <tr> 
   <td> 发送方IP<br /> </td> 
   <td> 用于发送电子邮件的IP。<br /> </td> 
  </tr> 
  <tr> 
   <td> 州<br /> </td> 
   <td> 在收件人配置文件中注册的状态。<br /> </td> 
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
   <td> 为URL提供的标签，如镜像页面，请与我们联系或打开。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易交付<br /> </td> 
   <td> 交易交付的标签和ID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 变体<br /> </td> 
   <td> A/B测试时电子邮件的变体。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 指标 {#metrics}

下表根据交付类型，提供了报告中使用的度量列表及其定义。

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
   <td> 列入黑名单<br /> </td> 
   <td> 宣布电子邮件为垃圾邮件或垃圾邮件的收件人数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 列入黑名单的比率<br /> </td> 
   <td> 标为黑名单的交货百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 弹回次数+错误<br /> </td> 
   <td> 在发送和自动返回处理过程中累积的与已发送消息总数有关的错误总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 弹回率+错误率<br /> </td> 
   <td> 弹回的电子邮件与发送的电子邮件的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> 内容在分发中的点击次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 点击率<br /> </td> 
   <td> 分发中的点击率。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> 成功发送的消息数，与已发送消息的总数有关。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付率<br /> </td> 
   <td> 成功发送的消息百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 强弹<br /> </td> 
   <td> 永久错误的总数，如错误的电子邮件地址。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬弹回率<br /> </td> 
   <td> 由于永久错误而失败的提交百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> “镜像”页<br /> </td> 
   <td> 单击镜像页面链接的收件人数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 镜像页面速率<br /> </td> 
   <td> 与总交付消息相比，镜像页面链接上的点击量百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 选件点击<br /> </td> 
   <td> 在分发中单击选件的时间。<br /> </td> 
  </tr> 
  <tr> 
   <td> 优惠点击率<br /> </td> 
   <td> 选件的点击率。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开<br /> </td> 
   <td> 邮件在分发中打开的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 开放率<br /> </td> 
   <td> 已打开消息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理／已发送<br /> </td> 
   <td> 传送的发送总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔离<br /> </td> 
   <td> 弹回并导致地址隔离的消息数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔离率<br /> </td> 
   <td> 与已发送邮件相比，隔离的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已拒绝<br /> </td> 
   <td> SMTP服务器分类为垃圾邮件的邮件数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 拒绝率<br /> </td> 
   <td> 标记为已拒绝的消息百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 软弹起<br /> </td> 
   <td> 临时错误的总数，如完整收件箱。<br /> </td> 
  </tr> 
  <tr> 
   <td> 软弹出率<br /> </td> 
   <td> 因临时原因而失败的交货百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一点击<br /> </td> 
   <td> 单击分发中内容的收件人数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开次数<br /> </td> 
   <td> 打开分发的收件人数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消订阅率<br /> </td> 
   <td> 与已交付消息相比，收件人取消订阅的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消订阅<br /> </td> 
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
   <td> 弹回次数+错误<br /> </td> 
   <td> 在发送过程中累积的与已发送消息总数相关的错误总数，例如MCPNS或提供商的错误。<br /> </td> 
  </tr> 
  <tr> 
   <td> 弹回率+错误率<br /> </td> 
   <td> 与发送的推送通知相比，弹回的推送通知百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> 推送通知被交付到设备并被用户点击的次数。 用户要么要查看通知，然后将其移至“推送打开”跟踪，要么将其关闭。<br /> </td> 
  </tr> 
  <tr> 
   <td> 点击率<br /> </td> 
   <td> 与推送通知交互的用户百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> 成功发送的推送通知数（与已发送的推送通知总数相关）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付率<br /> </td> 
   <td> 成功发送推送通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> 推送通知已发送到设备且未在通知中心更改的次数。 在大多数情况下，展示次数应与已交付的数字相似。 这确保设备获得消息并将该信息转发回服务器。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理／已发送<br /> </td> 
   <td> 发送的推送通知总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开<br /> </td> 
   <td> 交付到设备并由用户点击以打开应用程序的推送通知总数。 这与推送单击类似，但如果通知被取消，则不会触发推送打开。<br /> </td> 
  </tr> 
  <tr> 
   <td> 开放率<br /> </td> 
   <td> 已打开推送通知的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一单击<br /> </td> 
   <td> 唯一用户与推送通知交互的次数，例如单击通知或按钮。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特印象<br /> </td> 
   <td> 按收件人显示次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开次数<br /> </td> 
   <td> 打开分发的收件人数。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 应用程序内指标 {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 量度<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> 服务提供商交付到设备的应用程序内消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> 接收方查看的应用程序内消息总数，具体取决于是否满足触发器标准。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内单击 <br /> </td> 
   <td> 单击按钮1或按钮2的收件人总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点击率<br /> </td> 
   <td> 单击“按钮1”或“按钮2”的用户与查看消息的用户的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解聘<br /> </td> 
   <td> 收件人通过单击关闭按钮或自动关闭而忽略的消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解雇率<br /> </td> 
   <td> 收件人忽略的应用程序内消息的百分比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理／已发送<br /> </td> 
   <td> 作为发送流程的一部分从Adobe Campaign发送的应用程序内消息总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特印象<br /> </td> 
   <td> 唯一收件人的展示次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一的应用程序内点击<br /> </td> 
   <td> 收件人单击按钮1或按钮2的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特的应用程序内免职<br /> </td> 
   <td> 收件人忽略应用程序内消息的时间。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 细分 {#segments}

>[!NOTE]
>
>默认情况下，该区 **[!UICONTROL Exclude proof]** 段已被选中以过滤您的报表，但可以根据需要进行更改。

下表提供了报告中使用的区段列表及其定义。

<table> 
 <thead> 
  <tr> 
   <th> 细分<br /> </th> 
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
   <td> 18岁到25岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从26到30<br /> </td> 
   <td> 26岁到30岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从31到40<br /> </td> 
   <td> 31岁到40岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：从41到50<br /> </td> 
   <td> 41岁到50岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：X代<br /> </td> 
   <td> 1966年至1976年出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：Y代（千禧一代）<br /> </td> 
   <td> 1977年至1994年出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：Z代<br /> </td> 
   <td> 1995年至今的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：大于50<br /> </td> 
   <td> 年龄大于50的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：少于25<br /> </td> 
   <td> 年龄低于25岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：少于30<br /> </td> 
   <td> 年龄小于30的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：少于40<br /> </td> 
   <td> 年龄低于40岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：少于50<br /> </td> 
   <td> 年龄低于50岁的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年龄：静默生成<br /> </td> 
   <td> 1945年或之前出生的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 所有访问<br /> </td> 
   <td> 每个收件人<br /> </td> 
  </tr> 
    <tr> 
   <td> 排除证明<br /> </td> 
   <td> 从报告中排除校样（仅从Campaign 19.4版本开始）<br /> </td> 
  </tr> 
 </tbody> 
</table>

