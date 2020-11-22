---
solution: Campaign Standard
product: campaign
title: Analytics 中的 Campaign 维度和指标
description: 了解您在Adobe Analytics可以找到的不同维度，以开始跟踪您的电子邮件投放，从Adobe Campaign。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 3%

---


# Analytics 中的 Campaign 维度和指标{#campaign-dimensions-and-metrics-in-analytics}

Adobe Campaign和Adobe Analytics集成使您能够直接在Adobe Analytics跟踪电子邮件投放的成功。

在Analytics **[!UICONTROL dimensions]** 中找到的活动列在下面：

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 活动ID<br /> </td> 
   <td> 活动内部名称，如活动所示<br /> </td> 
  </tr> 
  <tr> 
   <td> 活动标签<br /> </td> 
   <td> 活动标签在活动<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放ID<br /> </td> 
   <td> 投放的内部名称，如活动所示。<br /> 例如，DM1是计划每周发送子投放的循环投放。 DM2 、 DM3和DM4在前三周发送。 投放ID维度随后将显示每个投放的结果，即DM1到DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 投放标签<br /> </td> 
   <td> 投放标签在活动<br /> </td> 
  </tr> 
  <tr> 
   <td> 已执行投放ID<br /> </td> 
   <td> 投放的内部名称，如活动所示。 这只涉及在活动中执行投放。<br /> 例如，DM1是计划每周发送子投放的循环投放。 DM2 、 DM3和DM4在前三周发送。 执行投放ID维度随后将显示执行投放的结果，即子投放DM2、DM3和DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 已执行的投放标签<br /> </td> 
   <td> 投放的标签，如活动。 这只涉及在活动中执行投放。<br /> </td> 
  </tr> 
 </tbody> 
</table>

在Analytics **[!UICONTROL metrics]** 中找到的活动列在下面：

<table> 
 <thead> 
  <tr> 
   <th> 度量<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已单击<br /> </td> 
   <td> 在投放中单击内容的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已交付<br /> </td> 
   <td> 与已发送邮件总数相关的已成功发送邮件数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已打开<br /> </td> 
   <td> 在投放中打开消息的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已发送<br /> </td> 
   <td> 投放的发送总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 总弹回数<br /> </td> 
   <td> 在投放和自动返回处理期间累积的与已发送消息总数相关的错误总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开<br /> </td> 
   <td> 打开收件人的投放数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一单击<br /> </td> 
   <td> 单击收件人中某个内容的投放数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取消订阅<br /> </td> 
   <td> 单击退订链接的次数。<br /> </td> 
  </tr> 
 </tbody> 
</table>

