---
solution: Campaign Standard
product: campaign
title: 指标计算
description: 列表每个量度的公式，了解报表结果。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: 报告
role: 领导者
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 2%

---


# 指标计算{#indicator-calculation}

>[!NOTE]
>
>为了更好地处理和管理大容量和实时分析，动态报告使用近似聚合来进行不同的计数估计。 近似聚合优惠有界的内存使用，并且通常比精确计算快。

下表显示了不同报表中使用的指示器的列表，并根据投放类型给出了它们的计算公式。

## 电子邮件投放 {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>标签</strong> <br /> </th> 
   <th> <strong>字段名称</strong> <br /> </th> 
   <th> <strong>指标计算公式</strong> <br /> </th> 
   <th> <strong>评论</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 帐户已禁用<br /> </td> 
   <td> @disabled<br /> </td> 
   <td> count(@failureReason=4<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 在阻止列表<br /> </td> 
   <td> @blacklisted<br /> </td> 
   <td> count(@failureReason=8, @failureType=2<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 阻止列表率<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> 速率计算的分母基于已发送计数（已交付+弹回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 弹回次数+错误<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 跳出率+错误率<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count(@trackingUrlType=1或10或11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 点进率<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delivered<br /> </td> 
   <td> 速率计算的分母基于“仅交付”。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已传送<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 传递率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivered/@sent<br /> </td> 
   <td> 速率计算的分母基于已发送计数（已交付+弹回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬弹回<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2和@failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 硬弹回率<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> 速率计算的分母基于已发送计数（已交付+弹回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 无效域<br /> </td> 
   <td> @invalidDomain<br /> </td> 
   <td> count(@failureReason=2<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 邮箱已满<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failureReason=5<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 镜像页面<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6<br /> </td> 
   <td> 速率计算的分母基于“仅交付”。<br /> </td> 
  </tr> 
  <tr> 
   <td> 镜像页面率<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivered<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 未连接<br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count(@failureReason=6<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 打开<br /> </td> 
   <td> @uniqueOpens<br /> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11)- unique(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 打开率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delivered<br /> </td> 
   <td> 速率计算的分母基于“仅交付”。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔离<br /> </td> 
   <td> @quarantine<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 隔离率<br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @quarantine/@sent<br /> </td> 
   <td> 速率计算的分母基于已发送计数（已交付+弹回）。<br /> </td> 
  </tr>
  <tr> 
   <td> 被拒绝<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 被拒绝速率<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> 速率计算的分母基于已发送计数（已交付+弹回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理/已发送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivered + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 软跳<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 软跳出率<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> 速率计算的分母基于已发送计数（已交付+弹回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 单次单击<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 使用ThetaSketch概念计算唯一单击。 有关详细信息，请参阅此<a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">示例</a>。<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开次数<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 不可到达<br /> </td> 
   <td> @unreachable<br /> </td> 
   <td> count(@failureReason=3<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 取消订阅<br /> </td> 
   <td> @unsubscribes<br /> </td> 
   <td> count(@trackingUrlType=3<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 取消订阅率<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@delivered<br /> </td> 
   <td> 速率计算的分母基于“仅交付”。<br /> </td> 
  </tr> 
  <tr> 
   <td> 用户未知<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failureReason=1<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

## 推送通知投放 {#push-notification-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>标签</strong> <br /> </th> 
   <th> <strong>字段名称</strong> <br /> </th> 
   <th> <strong>指标计算公式</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已处理/已发送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
  </tr> 
  <tr> 
   <td> 已传送<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delived)<br /> </td> 
  </tr> 
  <tr> 
   <td> 传递率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 跳出率+错误率<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delivered)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开次数<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 唯一打开使用唯一RecipientId的ThetaSketch概念计算。 有关详细信息，请参阅此<a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">示例</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=delived)<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一印象<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=视图))<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> 单次单击<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 使用ThetaSketch概念计算唯一单击。 有关详细信息，请参阅此<a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">示例</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 点进率<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@delivered)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 应用程序内投放 {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>标签</strong> <br /> </th> 
   <th> <strong>字段名称</strong> <br /> </th> 
   <th> <strong>指标计算公式</strong> <br /> </th> 
   <th> <strong>评论</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已处理/已发送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
   <td> sent=delivered<br /> </td> 
  </tr> 
  <tr> 
   <td> 已传送<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delived)<br /> </td> 
   <td> delivered<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=视图)或@count(status=button 1 click + button 2 click + encrements)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 唯一印象<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=视图))<br /> </td> 
   <td> 对于<span class="uicontrol">基于其活动用户档案(inAppProfile)</span>模板的目标用户，用户=收件人ID。<br /> 对于 <span class="uicontrol">目标移动应用程序(inAppBroadcast)的所有用户</span> 和基于其 <span class="uicontrol">移动用户档案(inApp)模板的目标用</span> 户，用户= MC Id或表示用户、移动应用程序和设备的唯一组合的等效项。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内单击<br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count(status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 唯一应用程序内单击<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count(status=clicks))<br /> </td> 
   <td> 对于<span class="uicontrol">基于其活动用户档案(inAppProfile)</span>模板的目标用户，用户=收件人ID。<br /> 对于 <span class="uicontrol">目标移动应用程序(inAppBroadcast)的所有用户</span> 和基于其 <span class="uicontrol">移动用户档案(inApp)模板的目标用</span> 户，用户= MC Id或表示用户、移动应用程序和设备的唯一组合的等效项。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点击率<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> Button 1或Button 2的总点击量/总展示次数*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解聘<br /> </td> 
   <td> @dismissal<br /> </td> 
   <td> @count(status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 唯一应用程序内解除<br /> </td> 
   <td> @uniquedismissal<br /> </td> 
   <td> @unique(@count(status=close)<br /> </td> 
   <td> 对于<span class="uicontrol">基于其活动用户档案(inAppProfile)</span>模板的目标用户，用户=收件人ID。<br /> 对于 <span class="uicontrol">目标移动应用程序(inAppBroadcast)的所有用户</span> 和基于其 <span class="uicontrol">移动用户档案(inApp)模板的目标用</span> 户，用户= MC Id或表示用户、移动应用程序和设备的唯一组合的等效项。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解聘率<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> 总结/总展示次数*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

