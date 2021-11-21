---
title: 指标计算
description: 通过每个量度公式的列表了解报表的结果。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 47cc11d7-89e8-4d1c-9638-5f66a53cef7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 2%

---

# 指标计算{#indicator-calculation}

>[!NOTE]
>
>为了更好地处理和管理大量数据和实时分析，动态报告使用大致汇总来做出不同的计数估计。 近似聚合提供有界的内存使用，并且通常比精确计算更快。

下表提供了不同报表中使用的指标列表及其计算公式，具体取决于投放类型。

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
   <td> count(@failureReason=4)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 开阻止列表启<br /> </td> 
   <td> @blacklisted<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 阻止列表率<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> 费率计算的分母基于已发送计数（已交付+退回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跳出次数+错误<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 跳出+错误率<br /> </td> 
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
   <td> 费率计算的分母仅基于“已交付”。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已交付<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 交付率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivered/@sent<br /> </td> 
   <td> 费率计算的分母基于已发送计数（已交付+退回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬退回<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2和@failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 硬退回率<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> 费率计算的分母基于已发送计数（已交付+退回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 域无效<br /> </td> 
   <td> @invalidDomain<br /> </td> 
   <td> count(@failureReason=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 邮箱已满<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failureReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 镜像页面<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> 费率计算的分母仅基于“已交付”。<br /> </td> 
  </tr> 
  <tr> 
   <td> 镜像页面速率<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivered<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 未连接<br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count(@failureReason=6)<br /> </td> 
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
   <td> 费率计算的分母仅基于“已交付”。<br /> </td> 
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
   <td> 费率计算的分母基于已发送计数（已交付+退回）。<br /> </td> 
  </tr>
  <tr> 
   <td> 被拒绝<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 拒绝率<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> 费率计算的分母基于已发送计数（已交付+退回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理/已发送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivered + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 软退回<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 软跳出率<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> 费率计算的分母基于已发送计数（已交付+退回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特点击<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 独特点击量使用ThetaSketch概念计算。 有关更多信息，请参阅此 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">示例</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开数<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 不可访问 <br /> </td> 
   <td> @unreachable<br /> </td> 
   <td> count(@failureReason=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 取消订阅<br /> </td> 
   <td> @unsubscribes<br /> </td> 
   <td> count(@trackingUrlType=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 退订率<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@delivered<br /> </td> 
   <td> 费率计算的分母仅基于“已交付”。<br /> </td> 
  </tr> 
  <tr> 
   <td> 用户未知<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failureReason=1)<br /> </td> 
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
   <td> 已交付<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 跳出+错误率<br /> </td> 
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
   <td> 唯一打开数<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 唯一打开数使用唯一RecipientId的ThetaSketch概念计算。 有关更多信息，请参阅此 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">示例</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特展示次数<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特点击<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 独特点击量使用ThetaSketch概念计算。 有关更多信息，请参阅此 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">示例</a>.<br /> </td> 
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
   <td> sent=delived<br /> </td> 
  </tr> 
  <tr> 
   <td> 已交付<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
   <td> delivery=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view)或@count(status=button 1 click + button 2 click + recomments)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 独特展示次数<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> 对于 <span class="uicontrol">根据用户的Campaign配置文件确定目标用户(inAppProfile)</span> 模板， user = Recipient Id。<br /> 对于 <span class="uicontrol">定位移动设备应用程序的所有用户(inAppBroadcast)</span> 和 <span class="uicontrol">根据用户的移动资料确定目标用户(inApp)</span> 模板、用户= MC ID或等效项，表示用户、移动设备应用程序和设备的唯一组合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点击 <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count(status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内独特点击次数<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count(status=clicks))<br /> </td> 
   <td> 对于 <span class="uicontrol">根据用户的Campaign配置文件确定目标用户(inAppProfile)</span> 模板， user = Recipient Id。<br /> 对于 <span class="uicontrol">定位移动设备应用程序的所有用户(inAppBroadcast)</span> 和 <span class="uicontrol">根据用户的移动资料确定目标用户(inApp)</span> 模板、用户= MC ID或等效项，表示用户、移动设备应用程序和设备的唯一组合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点进率<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> 按钮1或按钮2的总点击次数/总展示次数*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解聘<br /> </td> 
   <td> @dismissal<br /> </td> 
   <td> @count(status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 独特的应用程序内解雇<br /> </td> 
   <td> @uniquedismissal<br /> </td> 
   <td> @unique(@count(status=close)<br /> </td> 
   <td> 对于 <span class="uicontrol">根据用户的Campaign配置文件确定目标用户(inAppProfile)</span> 模板， user = Recipient Id。<br /> 对于 <span class="uicontrol">定位移动设备应用程序的所有用户(inAppBroadcast)</span> 和 <span class="uicontrol">根据用户的移动资料确定目标用户(inApp)</span> 模板、用户= MC ID或等效项，表示用户、移动设备应用程序和设备的唯一组合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解雇率<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> 总结/总展示次数*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>
