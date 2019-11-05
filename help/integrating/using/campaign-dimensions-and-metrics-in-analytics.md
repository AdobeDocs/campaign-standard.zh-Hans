---
title: Analytics 中的 Campaign 维度和指标
description: 了解您在Adobe Analytics中可以找到的不同维度，以开始跟踪Adobe Campaign中的电子邮件发送。
page-status-flag: 从未激活
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用活动和分析
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Analytics 中的 Campaign 维度和指标{#campaign-dimensions-and-metrics-in-analytics}

Adobe Campaign和Adobe Analytics集成允许您直接在Adobe Analytics中跟踪电子邮件发送的成功情况。

在Analytics中 **[!UICONTROL dimensions]** 找到的营销活动列在下面：

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 系列活动ID<br /> </td> 
   <td> 营销活动的内部名称，如营销活动中所示<br /> </td> 
  </tr> 
  <tr> 
   <td> 营销活动标签<br /> </td> 
   <td> 营销活动中显示的营销活动标签<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付ID<br /> </td> 
   <td> 营销活动中显示的交付的内部名称。<br /> 例如，DM1是计划每周发送子交付的重复交付。 DM2、DM3和DM4在前三周发送。 然后，“交付ID”维度将显示每个交付的结果，即DM1到DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 传送标签<br /> </td> 
   <td> 营销活动中显示的交付标签<br /> </td> 
  </tr> 
  <tr> 
   <td> 执行的交付ID<br /> </td> 
   <td> 营销活动中显示的交付的内部名称。 这只涉及在Campaign中执行时的交付。<br /> 例如，DM1是计划每周发送子交付的重复交付。 DM2、DM3和DM4在前三周发送。 然后，执行的交付ID维度将显示执行的交付的结果，即子交付DM2、DM3和DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 执行的交付标签<br /> </td> 
   <td> 营销活动中显示的交付标签。 这只涉及在Campaign中执行时的交付。<br /> </td> 
  </tr> 
 </tbody> 
</table>

在Analytics中 **[!UICONTROL metrics]** 找到的营销活动列在下面：

<table> 
 <thead> 
  <tr> 
   <th> 量度<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已单击<br /> </td> 
   <td> 内容在分发中的点击次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> 成功发送的消息数，与已发送消息的总数有关。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已打开<br /> </td> 
   <td> 邮件在分发中打开的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已发送<br /> </td> 
   <td> 传送的发送总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 总弹回次数<br /> </td> 
   <td> 在发送和自动返回处理过程中累积的与已发送消息总数有关的错误总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开<br /> </td> 
   <td> 打开分发的收件人数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一单击<br /> </td> 
   <td> 单击分发中内容的收件人数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消订阅<br /> </td> 
   <td> 取消订阅链接的点击次数。<br /> </td> 
  </tr> 
 </tbody> 
</table>

