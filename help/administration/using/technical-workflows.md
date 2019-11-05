---
title: 技术工作流
description: 技术工作流程是开箱即用的工作流程，旨在处理Adobe Campaign中的后台技术流程，从而确保平台的正确行为。
page-status-flag: 从未激活
uuid: 6e763dc1-e1d3-4d94-bc0b-ef5b1703d8e5
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参考
topic-tags: application-settings
discoiquuid: e9f147bd-6a5b-4b82-b9bb-311e38e22c62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 技术工作流{#technical-workflows}

Adobe Campaign提供了现成的技术工作流程。 技术工作流是计划在服务器上定期执行的操作或作业。

它们允许您对数据库执行维护操作，利用交付中的跟踪信息，并更新交付中的临时任务。

功能管理员可以访问菜单下的技术工 **[!UICONTROL Administration > Application settings > Workflows]** 作流。

>[!NOTE]
>
>作为功能管理员，您可以重新启动或暂停技术工作流，并修改其属性和结构。

![](assets/technical_workflows.png)

## 技术工作流程列表 {#list-of-technical-workflows}

技术工作流用于处理Adobe Campaign中自触发的后台和技术流程。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/B测试</span><br /> </td> 
   <td> <span class="uicontrol">abTesting</span><br /> </td> 
   <td> 此工作流会分析每个变体的跟踪日志。 在A/B测试周期结束时，它会自动计算入选变体。 默认情况下，它每天都启动。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">帐单</span><br /> </td> 
   <td> <span class="uicontrol">帐单</span><br /> </td> 
   <td> 此工作流通过电子邮件将系统活动报告发送给“付费”用户。 默认情况下，它每天凌晨1点自动开始。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">数据库清理</span><br /> </td> 
   <td> <span class="uicontrol">cleanup</span><br /> </td> 
   <td> 此工作流是数据库维护工作流：它运行不同的统计和进程，并根据已定义的配置从数据库中删除过时的数据。 默认情况下，它每天凌晨4点自动启动。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">预测</span><br /> </td> 
   <td> <span class="uicontrol">预测</span><br /> </td> 
   <td> 此工作流执行对存储在临时预测中的传送的分析（创建临时日志）。 默认情况下，它每天凌晨1点开始。 <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">导入共享的受众</span><br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span><br /> </td> 
   <td> 此工作流程可同步在Adobe Campaign中导入的Adobe Experience cloud受众数据。 默认情况下，每小时启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">即时报告共享</span><br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span><br /> </td> 
   <td> 计划发送报告后，此工作流即启动。 它将您的报表转换为pdf文件，然后通过电子邮件将其发送给目标收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI与Adobe Analytics协调</span><br /> </td> 
   <td> <span class="uicontrol">kpi调节</span><br /> </td> 
   <td> 此工作流每天从Reporting服务中获取一次KPI，并将它们与Adobe Analytics中的数据对帐。 然后，如果需要，它会推出差异。 默认情况下，它每天从凌晨4点20分开始。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">管理NMAC选择退出</span><br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMagt</span><br /> </td> 
   <td> 此工作流会更新移动设备上通知的取消订阅。 默认情况下，从凌晨1点到午夜，每隔6小时启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">消息中心本地存档</span><br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span><br /> </td> 
   <td> 此工作流会将实时事件存档到历史表中。 默认情况下，每小时启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">报告聚合</span><br /> </td> 
   <td> <span class="uicontrol">reportingAggroges</span><br /> </td> 
   <td> 此工作流会更新报告中使用的聚合。 默认情况下，它会在凌晨2点自动启动。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">与Adobe Analytics共享KPI</span><br /> </td> 
   <td> <span class="uicontrol">kpi共享</span><br /> </td> 
   <td> 此工作流程每15分钟将KPI数据从Adobe Campaign standard推送到Adobe Analytics。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新交付执行</span><br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span><br /> </td> 
   <td> 此工作流会更新交付的跟踪。 默认情况下，每10分钟启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新交付指标</span><br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span><br /> </td> 
   <td> 此工作流会更新交付的KPI（关键绩效指标）。 默认情况下，每小时启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新活动状态</span><br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span><br /> </td> 
   <td> 此工作流允许您将状态归因为事件。 <br /> 以下活动状态可用：待 <strong>定</strong>:该事件位于队列中。 尚未为其分配消息模板。<br /> 待 <span class="uicontrol">交付</span> :该事件在队列中，已为其分配消息模板，并且正在由分发处理该事件。<br /> 发 <strong>送</strong>:此状态将从交付日志中复制。 这意味着送货是送来的。<br /> 交 <strong>付忽略</strong>:此状态将从交付日志中复制。 这意味着交付被忽略。<br /> 交 <strong>付失败</strong>:此状态将从交付日志中复制。 这意味着交付失败。<br /> 未 <span class="uicontrol">考虑事件</span> :活动无法链接到消息模板。 不会处理该事件。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">可交付性更新</span><br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span><br /> </td> 
   <td> 此工作流允许您创建跳出规则资格规则列表以及平台中的域和MX列表。 此工作流仅在HTTPS打开时起作用。 默认情况下，它会在凌晨2点自动启动。<br /> </td> 
  </tr> 
 </tbody> 
</table>

