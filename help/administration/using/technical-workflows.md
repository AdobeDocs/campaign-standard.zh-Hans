---
title: 技术工作流程
seo-title: 技术工作流程
description: 技术工作流程
seo-description: 技术工作流程是现成的工作流，旨在处理Adobe Campaign中的后台技术流程，从而确保平台的行为正确。
page-status-flag: 从未激活
uuid: e763dc1-e1 d3-4d94-bc0 b-ef5 b1703 d8 e5
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: 应用程序设置
discoiquuid: e9f147bd-6a5b-4b82-b9 bb-311e38 e22 c62
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 2541b6dadd005c74d6bb737a0e3692e63a5b85db

---


# Technical workflows{#technical-workflows}

Adobe Campaign提供技术工作流程。技术工作流程是计划在服务器上定期执行的操作或作业。

它们允许您对数据库执行维护操作，利用交付中的跟踪信息，并更新交付的临时作业。

Functional administrators can access technical workflows under the **[!UICONTROL Administration > Application settings > Workflows]** menu.

>[!NOTE]
>
>作为职能管理员，您可以重新启动或暂停技术工作流程，并修改其属性和结构。

![](assets/technical_workflows.png)

## List of technical workflows {#list-of-technical-workflows}

技术工作流程用于处理Adobe Campaign中的自触发背景和技术流程。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>描述</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/B测试</span><br /> </td> 
   <td> <span class="uicontrol">Abtesting</span><br /> </td> 
   <td> 此工作流分析每个变体的跟踪日志。在A/B测试期结束时，它会自动计算入选变体。By default, it is started every day.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">帐单</span><br /> </td> 
   <td> <span class="uicontrol">计费</span><br /> </td> 
   <td> 此工作流通过电子邮件向“计费”用户发送系统活动报告。By default, it is automatically started every day at 1am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">数据库清理</span><br /> </td> 
   <td> <span class="uicontrol">清理</span><br /> </td> 
   <td> 此工作流是数据库维护工作流：它运行不同的统计和进程，并根据定义的配置从数据库中删除废弃的数据。By default, it is automatically started every day 4am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">预测功能</span><br /> </td> 
   <td> <span class="uicontrol">预测</span><br /> </td> 
   <td> 此工作流执行临时预测中存储的分发(创建临时日志)。By default, it is started every day at 1am. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">导入共享受众</span><br /> </td> 
   <td> <span class="uicontrol">ImportSharedAudience</span><br /> </td> 
   <td> 此工作流同步在Adobe Campaign中导入的Adobe Experience Cloud受众数据。By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">即时报告共享</span><br /> </td> 
   <td> <span class="uicontrol">ReportSendingNow</span><br /> </td> 
   <td> 此工作流在计划发送报告后立即启动。It converts your report into a pdf file then sends it in an email to the targeted recipients.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI与Adobe Analytics的合作</span><br /> </td> 
   <td> <span class="uicontrol">KPiCondition</span><br /> </td> 
   <td> 此工作流每天从报表服务获取KPI，并将其与Adobe Analytics中的数据进行统一。然后根据需要推送差异。By default, it is started every day at 4.20am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">管理NMAC选择退出</span><br /> </td> 
   <td> <span class="uicontrol">MobileAPPopToMMgt</span><br /> </td> 
   <td> 此工作流更新了移动设备上通知的取消订阅。By default, it is started every 6 hours between 1am and midnight.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">消息中心本地存档</span><br /> </td> 
   <td> <span class="uicontrol">McSynch_ Local</span><br /> </td> 
   <td> 此工作流将实时活动归档到历史记录中。By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">报表汇总</span><br /> </td> 
   <td> <span class="uicontrol">ReportingLats</span><br /> </td> 
   <td> 此工作流更新报告中使用的集合。By default, it is automatically started at 2am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">使用Adobe Analytics共享KPI</span><br /> </td> 
   <td> <span class="uicontrol">KPiSharing</span><br /> </td> 
   <td> This workflow pushes KPI data every 15 minutes from Adobe Campaign Standard to Adobe Analytics.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新交付执行</span><br /> </td> 
   <td> <span class="uicontrol">updateLiveReferExInfo</span><br /> </td> 
   <td> 此工作流会更新交付的跟踪。By default, it is started every 10 minutes.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新交付指示器</span><br /> </td> 
   <td> <span class="uicontrol">updateLiveRevications</span><br /> </td> 
   <td> 此工作流更新交付的KPI(关键性能指标)。By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新活动状态</span><br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span><br /> </td> 
   <td> 此工作流允许您将状态属性归到活动。The following event statuses are available:<br /> <strong>Pending</strong>: The event is in a queue. 尚未将邮件模板分配给它。<br /><span class="uicontrol">待定交付</span> ：活动在队列中，已为该活动分配了一个消息模板，交付过程正在处理该模板。<br /><strong>发送</strong>日期：此状态将从交付日志中复制。这意味着发送已发送。<br /><strong>交付忽略</strong>：此状态将从交付日志中复制。这意味着分发被忽略。<br /><strong>交付失败</strong>：此状态将从交付日志中复制。这意味着分发失败。<br /><span class="uicontrol">未考虑事件</span> ：活动无法链接到消息模板。The event will not be processed.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">可交付的更新</span><br /> </td> 
   <td> <span class="uicontrol">交付过程更新</span><br /> </td> 
   <td> 此工作流允许您创建退回规则资格规则列表以及平台中的域和MX列表。此工作流仅在HTTPS处于打开状态时才起作用。By default, it is automatically started at 2am.<br /> </td> 
  </tr> 
 </tbody> 
</table>

