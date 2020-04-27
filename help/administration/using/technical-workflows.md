---
title: 技术工作流
description: 技术工作流是开箱即用的工作流，旨在处理Adobe Campaign中的后台技术流程，从而确保平台的正确行为。
page-status-flag: never-activated
uuid: 6e763dc1-e1d3-4d94-bc0b-ef5b1703d8e5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: e9f147bd-6a5b-4b82-b9bb-311e38e22c62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4cbc56973a57cde8af6cefa9ff89c7d29ab7b79

---


# 技术工作流{#technical-workflows}

技术工作流是开箱即用的，具有Adobe Campaign。 技术工作流是计划在服务器上定期执行的操作或作业。

它们允许您对数据库执行维护操作，利用投放中的跟踪信息，并更新投放上的临时作业。

功能管理员可以访问菜单下的 **[!UICONTROL Administration > Application settings > Workflows]** 技术工作流。

>[!NOTE]
>
>作为功能管理员，您可以重新启动或暂停技术工作流，并修改其属性和结构。

![](assets/technical_workflows.png)

## 列表技术工作流 {#list-of-technical-workflows}

技术工作流用于处理Adobe Campaign中自触发的背景和技术流程。

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
   <td> 此工作流执行对存储在临时预测中的投放的分析（创建临时日志）。 默认情况下，它每天凌晨1点开始。 <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">导入共享受众</span><br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span><br /> </td> 
   <td> 此工作流程可同步导入到Adobe Campaign中的Adobe Experience Cloud受众数据。 默认情况下，每小时启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">即时报告共享</span><br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span><br /> </td> 
   <td> 计划发送报告后，此工作流即启动。 它将您的报表转换为pdf文件，然后通过电子邮件将其发送到目标收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI与Adobe Analytics协调</span><br /> </td> 
   <td> <span class="uicontrol">kpi调节</span><br /> </td> 
   <td> 此工作流每天从报告服务中获取一次KPI，并将其与Adobe Analytics中的数据对帐。 然后，如果需要，它会推出差异。 默认情况下，它每天从凌晨4点20分开始。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">管理NMAC选择退出</span><br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMagt</span><br /> </td> 
   <td> 此工作流会更新移动设备上通知的退订。 默认情况下，从凌晨1点到午夜，每隔6小时启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">消息中心本地存档</span><br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span><br /> </td> 
   <td> 此工作流将实时事件存档到历史表中。 默认情况下，每小时启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">报告聚合</span><br /> </td> 
   <td> <span class="uicontrol">reportingAggroges</span><br /> </td> 
   <td> 此工作流会更新报告中使用的聚合。 默认情况下，它会在凌晨2点自动启动。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">与Adobe Analytics共享KPI</span><br /> </td> 
   <td> <span class="uicontrol">kpi共享</span><br /> </td> 
   <td> 此工作流程每15分钟将KPI数据从Adobe Campaign标准版推送到Adobe Analytics。<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">与Launch同步</span><br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span><br /> </td> 
   <td> 此工作流将同步在Adobe Campaign标准版中导入的Adobe Launch移动属性。 每15分钟启动一次。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">更新投放执行</span><br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span><br /> </td> 
   <td> 此工作流会更新投放的跟踪。 默认情况下，每10分钟启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新投放指示器</span><br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span><br /> </td> 
   <td> 此工作流会更新投放的KPI（关键绩效指标）。 默认情况下，每小时启动一次。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新事件状态</span><br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span><br /> </td> 
   <td> 此工作流允许您将状态归因到事件。 以下事件状态可用：<br /> 待 <strong>定</strong>:事件在队列中。 尚未为其分配消息模板。<br /> 待 <span class="uicontrol">处理投放</span> :事件在队列中，已为其分配消息模板，投放正在处理该模板。<br /> 发 <strong>送</strong>:此状态将从投放日志复制。 这意味着投放被送来了。<br /> 投放 <strong>忽略</strong>:此状态将从投放日志复制。 这意味着投放被忽略。<br /> <strong>投放失败</strong>:此状态将从投放日志复制。 这意味着投放失败了。<br /> <span class="uicontrol">事件未考虑</span> :无法将事件链接到消息模板。 不会处理事件。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">可交付性更新</span><br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span><br /> </td> 
   <td> 此工作流允许您创建跳出规则资格规则的列表，以及平台中域和MX的列表。 此工作流仅在HTTPS打开时起作用。 默认情况下，它会在凌晨2点自动启动。<br /> </td> 
  </tr> 
 </tbody> 
</table>

