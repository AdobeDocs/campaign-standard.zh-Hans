---
solution: Campaign Standard
product: campaign
title: 监控准则
description: 本节介绍监测Campaign Standard的一般准则。
audience: production
content-type: reference
topic-tags: introduction
index: y
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 9%

---


# 监控准则 {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">监视系统</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">监控工作流</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">监控投放</a></p></td></tr>
</table>

Campaign Standard提供了多种监视实例的方法，以确保系统正常，并最终解决在设置工作流、发送投放等时可能出现的问题。

## 监视系统 {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**系统通**&#x200B;知Campaign Standard界面提供通知窗格，通知窗格可让您始终获知系统中正在发生的情况：事件状态、系统更新、所需操作等。 [阅读更多](../../start/using/interface-description.md#top-bar)


**技术工作流**&#x200B;技术工作流是计划在服务器上定期执行的操作或作业。 要确保实例运行正常，您需要确保它们始终处于运行状态。 [阅读更多](../../administration/using/technical-workflows.md)

**控制面板**&#x200B;控制面板允许您管理实例的多个设置：URL权限、检查您的实例详细信息（如服务器的构建版本）、监视活动用户档案使用情况等。 它还允许您监视连接到实例的SFTP服务器上的可用空间。 [阅读更多](https://docs.adobe.com/content/help/zh-Hans/control-panel/using/control-panel-home.html)。

>[!NOTE]
>
>请注意，控制面板仅供管理员用户访问，并且适用于所有使用Adobe Managed Services的客户。

**技术对**&#x200B;象 **[!UICONTROL Diagnosis]** 菜单是监视和分析应用程序生成的不同技术对象的关键工具：数据模式、网页、批处理作业等。 [阅读更多](../../developing/using/monitoring-data-model-changes.md)

**导出审核**导出审核允许您监控对实例执行的导出：从工作流上传的文件、列表导出以及从直接邮件下载的文件。
[阅读更多](../../administration/using/auditing-export-logs.md)

**许可**&#x200B;通过菜 **[!UICONTROL Licenses]** 单监视实例的相关信息：已安装许可证、构建版本和条款协议接受。
[阅读更多](../../administration/using/licenses.md)

## 监控工作流 {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**最佳实践和疑难解答**在使用工作流时遵循最佳实践和疑难解答指南，可以帮助提高性能。
[阅读更多](../../automating/using/best-practices-workflows.md)

**日志和任务**工作流日志监视是分析工作流并确保其正常运行的关键步骤。
[阅读更多](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**通知**Campaign Standard允许您向主管发送通知，以监控工作流的执行情况，并查看是否存在需要您注意的错误。
[阅读更多](../../automating/using/monitoring-workflow-execution.md#error-management)

## 监控投放 {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**交付性**Campaign Standard提供了多种交付性工具，可帮助您提高成功发送邮件的数量：投放吞吐量报告、发送时间优化、消息预览、电子邮件渲染、隔离管理等。
[阅读更多](../../sending/using/about-deliverability.md)

**投放**发送消息后，详细日志允许您监视投放并衡量活动的成功程度，以及跟踪消息收件人的行为。
[阅读更多](../../sending/using/monitoring-a-delivery.md)

**投放警**报利用投放警报功能，您可以设置将自动发送给一组用户的有关投放执行的警报：发送或准备失败、跳出率不佳、吞吐量低等。
[阅读更多](../../sending/using/receiving-alerts-when-failures-happen.md)

**动态报告**动态报告提供各种报告，帮助您不断获知投放的表现：弹回次数、按收件人、投放吞吐量等查看次数最多的取消次数。
[阅读更多](../../reporting/using/about-dynamic-reports.md)
