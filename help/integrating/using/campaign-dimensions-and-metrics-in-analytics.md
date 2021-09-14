---
title: Analytics 中的 Campaign 维度和指标
description: 了解在Adobe Analytics中可找到的不同维度，以开始跟踪来自Adobe Campaign的电子邮件投放。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 3%

---

# Analytics 中的 Campaign 维度和指标{#campaign-dimensions-and-metrics-in-analytics}

Adobe Campaign和Adobe Analytics集成允许您直接在Adobe Analytics中跟踪电子邮件投放是否成功。

在Analytics中找到的Campaign **[!UICONTROL dimensions]**&#x200B;如下所示：

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 促销活动ID<br /> </td> 
   <td> Campaign<br />中显示的Campaign内部名称 </td> 
  </tr> 
  <tr> 
   <td> 营销活动标签<br /> </td> 
   <td> Campaign<br />中显示的Campaign标签 </td> 
  </tr> 
  <tr> 
   <td> 投放ID<br /> </td> 
   <td> Campaign中显示的投放内部名称。<br /> 例如，DM1是计划每周发送子投放的定期投放。DM2、DM3和DM4会在前三周发送。 然后，“投放ID”维度将显示每个投放的结果，即DM1到DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 投放标签<br /> </td> 
   <td> Campaign<br />中显示的投放标签 </td> 
  </tr> 
  <tr> 
   <td> 执行的投放ID<br /> </td> 
   <td> Campaign中显示的投放内部名称。 这仅涉及Campaign中执行时的投放。<br /> 例如，DM1是计划每周发送子投放的定期投放。DM2、DM3和DM4会在前三周发送。 然后，“已执行的投放ID”维度将显示已执行投放的结果，即子投放DM2、DM3和DM4。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 已执行的投放标签<br /> </td> 
   <td> Campaign中显示的投放标签。 这仅涉及在Campaign中执行时的投放。<br /> </td> 
  </tr> 
 </tbody> 
</table>

在Analytics中找到的Campaign **[!UICONTROL metrics]**&#x200B;如下所示：

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
   <td> 在投放中点击内容的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已传送<br /> </td> 
   <td> 已成功发送的消息数，与已发送消息的总数有关。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已打开<br /> </td> 
   <td> 投放中打开消息的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已发送<br /> </td> 
   <td> 投放的发送总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 退回总数<br /> </td> 
   <td> 在投放和自动回访处理过程中累积的与已发送消息总数有关的错误总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开<br /> </td> 
   <td> 打开投放的收件人数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一单击<br /> </td> 
   <td> 点击投放中内容的收件人数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已取消订阅<br /> </td> 
   <td> 退订链接的点击次数。<br /> </td> 
  </tr> 
 </tbody> 
</table>
