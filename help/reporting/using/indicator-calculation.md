---
title: 指标计算
description: 使用每个量度公式的列表了解报表的结果。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 47cc11d7-89e8-4d1c-9638-5f66a53cef7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 1%

---

# 指标计算{#indicator-calculation}

>[!NOTE]
>
>为了更好地处理和管理高容量分析和实时分析，动态报告使用近似聚合进行不同计数估计。 近似聚合可提供有限内存使用，并且通常比精确计算更快。

下表列出了不同报表中使用的指标及其计算公式，具体取决于投放类型。

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
   <td> 在阻止列表<br /> </td> 
   <td> @blacklisted<br /> </td> 
   <td> count(@failureReason=8， @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 阻止列表率<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> 费率计算的分母基于发送计数（已投放+跳出次数）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 退回+错误<br /> </td> 
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
   <td> 费率计算的分母仅基于“已投放”。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已投放<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 投放率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivered/@sent<br /> </td> 
   <td> 费率计算的分母基于发送计数（已投放+跳出次数）。<br /> </td> 
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
   <td> 费率计算的分母基于发送计数（已投放+跳出次数）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 无效域<br /> </td> 
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
   <td> 费率计算的分母仅基于“已投放”。<br /> </td> 
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
   <td> count(@trackingUrlType=2 +唯一(@trackingUrlType=1,2，3,6，10,11) — 唯一(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 打开率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delivered<br /> </td> 
   <td> 费率计算的分母仅基于“已投放”。<br /> </td> 
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
   <td> 费率计算的分母基于发送计数（已投放+跳出次数）。<br /> </td> 
  </tr>
  <tr> 
   <td> 被拒绝<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20， @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 拒绝率<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> 费率计算的分母基于发送计数（已投放+跳出次数）。<br /> </td> 
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
   <td> 软退回率<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> 费率计算的分母基于发送计数（已投放+跳出次数）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特点击<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 唯一点击量使用ThetaSketch概念进行计算。 有关详细信息，请参阅此 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">示例</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 独特打开次数<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 唯一(@trackingUrlType=1,2，3,6，10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 不可到达 <br /> </td> 
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
   <td> 取消订阅率<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@delivered<br /> </td> 
   <td> 费率计算的分母仅基于“已投放”。<br /> </td> 
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
   <td> 已投放<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放率<br /> </td> 
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
   <td> @count（状态=打开）<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delivered)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特打开次数<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 唯一打开次数使用唯一RecipientId的ThetaSketch概念进行计算。 有关详细信息，请参阅此 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">示例</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特展示次数<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count（状态=视图）)<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特点击<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 唯一点击量使用ThetaSketch概念进行计算。 有关详细信息，请参阅此 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">示例</a>.<br /> </td> 
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
   <td> 已投放<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
   <td> delivered=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view)或@count（status=button 1单击+按钮2单击+解除）<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 独特展示次数<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count（状态=视图）)<br /> </td> 
   <td> 对象 <span class="uicontrol">基于Campaign用户档案的目标用户(inAppProfile)</span> 模板，用户=收件人ID。<br /> 对象 <span class="uicontrol">定位移动应用程序的所有用户(inAppBroadcast)</span> 和 <span class="uicontrol">根据用户的移动配置文件定位用户(inApp)</span> 模板，用户= MC ID或等效项，表示用户、移动应用程序和设备的独特组合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点击次数 <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count (status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内独特点击次数<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count （状态=点击数）)<br /> </td> 
   <td> 对象 <span class="uicontrol">基于Campaign用户档案的目标用户(inAppProfile)</span> 模板，用户=收件人ID。<br /> 对象 <span class="uicontrol">定位移动应用程序的所有用户(inAppBroadcast)</span> 和 <span class="uicontrol">根据用户的移动配置文件定位用户(inApp)</span> 模板，用户= MC ID或等效项，表示用户、移动应用程序和设备的独特组合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点进率<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> 按钮1或按钮2的总点击次数/总展示次数*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解除<br /> </td> 
   <td> @dismissal<br /> </td> 
   <td> @count （状态=关闭）<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 独特应用程序内解除<br /> </td> 
   <td> @uniquedismissal<br /> </td> 
   <td> @unique(@count (status=close))<br /> </td> 
   <td> 对象 <span class="uicontrol">基于Campaign用户档案的目标用户(inAppProfile)</span> 模板，用户=收件人ID。<br /> 对象 <span class="uicontrol">定位移动应用程序的所有用户(inAppBroadcast)</span> 和 <span class="uicontrol">根据用户的移动配置文件定位用户(inApp)</span> 模板，用户= MC ID或等效项，表示用户、移动应用程序和设备的独特组合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解雇率<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> 关闭次数总计/展示次数总计*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>
