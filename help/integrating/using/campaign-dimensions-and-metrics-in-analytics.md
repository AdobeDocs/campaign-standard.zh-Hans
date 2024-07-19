---
title: Analytics 中的 Campaign 维度和指标
description: 了解可在Adobe Analytics中找到的各种维度，以开始从Adobe Campaign跟踪电子邮件投放。
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

通过Adobe Campaign和Adobe Analytics集成，您可以直接在Adobe Analytics中跟踪电子邮件投放的成功情况。

下面列出了在Analytics中找到的营销活动&#x200B;**[!UICONTROL dimensions]**：

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> 定义<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 营销活动ID<br /> </td> 
   <td> 营销活动的内部名称，如营销活动<br />中所示 </td> 
  </tr> 
  <tr> 
   <td> 营销活动标签<br /> </td> 
   <td> 营销活动中的营销活动标签，如营销活动<br />中所示 </td> 
  </tr> 
  <tr> 
   <td> 投放ID<br /> </td> 
   <td> 在Campaign中看到的投放的内部名称。<br />例如，DM1是计划每周发送子投放的循环投放。 DM2、DM3和DM4在前三周发送。 然后，投放ID维度将显示每次投放的结果，即DM1到DM4。<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放标签<br /> </td> 
   <td> 在Campaign<br />中看到的投放标签 </td> 
  </tr> 
  <tr> 
   <td> 执行的投放ID<br /> </td> 
   <td> 在Campaign中看到的投放的内部名称。 这仅涉及在Campaign中执行的投放。<br />例如，DM1是计划每周发送子投放的循环投放。 DM2、DM3和DM4在前三周发送。 然后，执行的投放ID维度将显示执行的投放的结果，即子投放DM2、DM3和DM4。<br /> </td> 
  </tr> 
  <tr> 
   <td> 执行的投放标签<br /> </td> 
   <td> 在Campaign中看到的投放标签。 这仅涉及在Campaign中执行的投放。<br /> </td> 
  </tr> 
 </tbody> 
</table>

下面列出了在Analytics中找到的营销活动&#x200B;**[!UICONTROL metrics]**：

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
   <td> 已投放<br /> </td> 
   <td> 成功发送的邮件数，与已发送的邮件总数相关。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已打开<br /> </td> 
   <td> 在投放中打开邮件的次数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已发送<br /> </td> 
   <td> 投放的发送总数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 退回总计<br /> </td> 
   <td> 传递和自动返回处理期间累计的错误总数与已发送消息的总数之比。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开<br /> </td> 
   <td> 打开投放的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特点击<br /> </td> 
   <td> 点击投放中内容的收件人数量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已取消订阅<br /> </td> 
   <td> 取消订阅链接的点击次数。<br /> </td> 
  </tr> 
 </tbody> 
</table>
