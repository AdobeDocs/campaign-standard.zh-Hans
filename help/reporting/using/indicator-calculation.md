---
title: 指标计算
description: 通过每个指标公式的列表了解报告的结果。
page-status-flag: 从未激活
uuid: dfbc9d7e-62db-4e77-bb8e-0ac826ec733
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 报告
content-type: 参考
topic-tags: about-reporting
discoiquuid: 45b11631-6b32-4074-8c8d-affd06407810
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 指标计算{#indicator-calculation}

下表根据交付类型提供了不同报表中使用的指示器列表及其计算公式。

## 电子邮件投放 {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>标签</strong><br /> </th> 
   <th> <strong>字段名称</strong><br /> </th> 
   <th> <strong>指示器计算公式</strong><br /> </th> 
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
   <td> 列入黑名单<br /> </td> 
   <td> @列入黑名单<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 列入黑名单的比率<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> 速率计算的分母基于已发送计数（已交付+弹回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 弹回次数+错误<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 弹回率+错误率<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> @单击<br /> </td> 
   <td> count（@trackingUrlType=1或10或11）<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 点击率<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delivered<br /> </td> 
   <td> 速率计算的分母仅基于“已交付”。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 交付率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivered/@sent<br /> </td> 
   <td> 速率计算的分母基于已发送计数（已交付+弹回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬弹回<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2 AND @failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 硬弹回率<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> 速率计算的分母基于已发送计数（已交付+弹回）。<br /> </td> 
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
   <td> “镜像”页<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> 速率计算的分母仅基于“已交付”。<br /> </td> 
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
   <td> @opens<br /> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11)- unique(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 开放率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delivered<br /> </td> 
   <td> 速率计算的分母仅基于“已交付”。<br /> </td> 
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
   <td> 拒绝<br /> </td> 
   <td> @已拒绝<br /> </td> 
   <td> count(@failureReason=20)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 已拒绝<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 拒绝率<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> 速率计算的分母基于已发送计数（已交付+弹回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已处理／已发送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delived + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 软弹起<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 软弹出率<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> 速率计算的分母基于已发送计数（已交付+弹回）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一点击<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 使用ThetaSketch概念计算唯一点击量。<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开次数<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 无法访问 <br /> </td> 
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
   <td> 速率计算的分母仅基于“已交付”。<br /> </td> 
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
   <th> <strong>标签</strong><br /> </th> 
   <th> <strong>字段名称</strong><br /> </th> 
   <th> <strong>指示器计算公式</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已处理／已发送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 弹回率+错误率<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 打开<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> 开放率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delived)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一打开次数<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 唯一打开使用唯一RecipientId的ThetaSketch概念计算。<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> 独特印象<br /> </td> 
   <td> @uniqueidespaces<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> 单击<br /> </td> 
   <td> @单击<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一点击<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 使用ThetaSketch概念计算唯一点击量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 点击率<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@delivered)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 应用程序内投放 {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>标签</strong><br /> </th> 
   <th> <strong>字段名称</strong><br /> </th> 
   <th> <strong>指示器计算公式</strong><br /> </th> 
   <th> <strong>评论</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已处理／已发送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
   <td> sent=已交付<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
   <td> delivered=已发送<br /> </td> 
  </tr> 
  <tr> 
   <td> 展示次数<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view)或@count（status=button 1单击+按钮2单击+不再续）<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 独特印象<br /> </td> 
   <td> @uniqueidespaces<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> 对于 <span class="uicontrol">基于其营销活动配置文件(inAppProfile)模板的Target用户</span> ，用户=收件人Id。<br /> 对于 <span class="uicontrol">Target移动应用程序(inAppBroadcast)</span> 和 <span class="uicontrol">Target用户的所有用户(基于其移动配置文件(inApp)模板)</span> ，用户= MC id或表示用户、移动应用程序和设备的唯一组合的等效项。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内单击 <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count(status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 唯一的应用程序内点击<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count(status=clicks))<br /> </td> 
   <td> 对于 <span class="uicontrol">基于其营销活动配置文件(inAppProfile)模板的Target用户</span> ，用户=收件人Id。<br /> 对于 <span class="uicontrol">Target移动应用程序(inAppBroadcast)</span> 和 <span class="uicontrol">Target用户的所有用户(基于其移动配置文件(inApp)模板)</span> ，用户= MC id或表示用户、移动应用程序和设备的唯一组合的等效项。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内点击率<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> Button 1或Button 2的总点击量／总印象*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解聘<br /> </td> 
   <td> @censiblation<br /> </td> 
   <td> @count(status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 独特的应用程序内免职<br /> </td> 
   <td> @uniqueccensible<br /> </td> 
   <td> @unique(@count(status=close))<br /> </td> 
   <td> 对于 <span class="uicontrol">基于其营销活动配置文件(inAppProfile)模板的Target用户</span> ，用户=收件人Id。<br /> 对于 <span class="uicontrol">Target移动应用程序(inAppBroadcast)</span> 和 <span class="uicontrol">Target用户的所有用户(基于其移动配置文件(inApp)模板)</span> ，用户= MC id或表示用户、移动应用程序和设备的唯一组合的等效项。<br /> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内解雇率<br /> </td> 
   <td> @rensulate<br /> </td> 
   <td> 总结／总展示次数*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

