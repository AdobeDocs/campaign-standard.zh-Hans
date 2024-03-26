---
title: 技术工作流
description: 了解有关技术工作流的更多信息
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: da3a3af5-207a-4289-bd07-00a8c5d1cf57
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 88%

---

# 技术工作流{#technical-workflows}

技术工作流是 Adobe Campaign 提供的现成工作流。技术工作流是计划在服务器上定期执行的操作或作业。

利用技术工作流，可对投放库执行维护操作、利用投放中的跟踪信息，并更新投放上的临时作业。

功能管理员可以通过 **[!UICONTROL Administration > Application settings > Workflows]** 菜单访问技术工作流。

>[!NOTE]
>
>功能管理员可以重新启动或暂停技术工作流，并修改其属性和结构。

![](assets/technical_workflows.png)

## 技术工作流列表 {#list-of-technical-workflows}

Adobe Campaign 中的技术工作流用于处理自触发的背景技术流程。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/B 测试</span> <br /> </td> 
   <td> <span class="uicontrol">abTesting</span> <br /> </td> 
   <td> 此工作流会分析每个变体的跟踪日志。在 A/B 测试期结束时，它会自动计算入选的变体。默认情况下，此工作流每日启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">付费</span> <br /> </td> 
   <td> <span class="uicontrol">billing</span> <br /> </td> 
   <td> 此工作流会通过电子邮件将系统活动报告发送给“billing”用户。默认情况下，此工作流于每日凌晨 1 点自动启动。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">数据库清理</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> 此工作流是数据库维护工作流：它可根据已定义的配置运行各种统计和进程，并从数据库中删除过时的数据。默认情况下，此工作流于每日凌晨 4 点自动启动。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">预测</span> <br /> </td> 
   <td> <span class="uicontrol">forecasting</span> <br /> </td> 
   <td> 此工作流用于对存储在临时预测中的投放执行分析（创建临时日志）。默认情况下，此工作流于每日凌晨 1 点启动。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">导入共享受众</span> <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span> <br /> </td> 
   <td> 此工作流可同步在 Adobe Campaign 中导入的 Adobe Experience Cloud 受众数据。默认情况下，每小时启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">即时报告共享</span> <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span> <br /> </td> 
   <td> 此工作流会在计划发送报告后立即启动。它会将您的报表转换为 pdf 文件，然后通过电子邮件将其发送给定向的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">与 Adobe Analytics 协调 KPI</span> <br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span> <br /> </td> 
   <td> 此工作流每天从报告服务中获取一次 KPI，并将其与来自 Adobe Analytics 的数据进行协调。随后，如果需要，它会推送数据的差异。默认情况下，此工作流于每日凌晨 4 点 20 分启动。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">消息中心本地存档</span> <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span> <br /> </td> 
   <td> 此工作流可将实时事件存档到历史表格中。默认情况下，每小时启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">报告聚合</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> 此工作流可更新报告中使用的聚合。默认情况下，此工作流于凌晨 2 点自动启动。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">与 Adobe Analytics 共享 KPI</span> <br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span> <br /> </td> 
   <td> 此工作流程可将 KPI 数据从 Adobe Campaign Standard 推送到 Adobe Analytics，每 15 分钟推送一次。<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">与 Launch 同步</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> 此工作流可同步在Adobe Campaign Standard中导入的标记移动属性。 每 15 分钟启动一次。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">跟踪日志恢复</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> 此工作流可同步在Adobe Campaign Standard中导入的标记移动属性。 每 15 分钟启动一次。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">恢复跟踪日志</span> <br /> </td> 
   <td> <span class="uicontrol">trackingLogRecover</span> <br /> </td> 
   <td> 此工作流可恢复丢失的跟踪日志。 请注意，此技术工作流用于特定上下文，并且仅限于Adobe内部使用。 <br> 默认情况下，每10分钟启动一次。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">更新投放执行</span> <br/> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span> <br/> </td> 
   <td> 此工作流可复制本地数据库中的broadlog和跟踪日志。 默认情况下，每 10 分钟启动一次。<br/> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">更新投放指标</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span> <br /> </td> 
   <td> 此工作流可更新投放的 KPI（关键绩效指标）。默认情况下，每小时启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新事件状态</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> 利用此工作流，可将状态归因到事件。可用事件状态如下所示：<br /><strong>待处理</strong>：事件处于队列中。尚未为其分配消息模板。<br /><span class="uicontrol">待处理投放</span>：事件处于队列中，已为其分配消息模板且投放正在处理该模板。<br /><strong>已发送</strong>：此状态复制于投放日志。这意味着投放已经发送。<br /><strong>被投放忽略</strong>：此状态复制于投放日志。这意味着该投放被忽略。<br /><strong>投放失败</strong>：此状态复制于投放日志。这意味着投放失败了。<br /><span class="uicontrol">事件未被考虑</span>：该事件无法链接到消息模板。将不会处理该事件。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">可投放性更新</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> 利用此工作流，可创建退件规则的鉴别规则列表，以及平台中域名和 MX 的列表。此工作流仅在打开 HTTPS 时起作用。默认情况下，此工作流于凌晨 2 点自动启动。<br /> </td> 
  </tr> 
 </tbody> 
</table>
