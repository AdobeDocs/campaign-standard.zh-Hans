---
title: 监测准则
description: 本页介绍了监视Campaign Standard的一般准则
audience: production
feature: Access Management
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 21%

---

# 监测准则 {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">监视系统</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">监控工作流</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">监控投放</a></p></td></tr>
</table>

Campaign Standard提供了多种监测实例的方法，以确保您的系统正常运行，并最终对设置工作流、发送投放等时可能发生的问题进行故障诊断。

## 监视系统 {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**系统通知**

Campaign Standard界面提供了一个通知窗格，允许您随时了解系统中发生的情况：事件状态、系统更新、需要执行操作等。 [了解更多信息](../../start/using/interface-description.md#top-bar)


**技术工作流**

技术工作流是计划在服务器上定期执行的操作或作业。要确保实例健康和正常运行，您需要确保它们始终启动并运行。 [了解更多信息](../../administration/using/technical-workflows.md)

**控制面板**

控制面板允许您管理实例的多个设置： URL权限，检查实例详细信息（如服务器的内部版本号），监控活动配置文件使用情况等。 它还允许您监视连接到实例的SFTP服务器上的可用空间。 [阅读更多](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans)。

>[!NOTE]
>
>所有管理员用户都可访问控制面板。[此页面](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=zh-Hans#discover-control-panel)详细介绍了授予用户管理员访问权限的步骤。

**技术对象**

此 **[!UICONTROL Diagnosis]** 菜单是监测和分析应用程序产生的各种技术对象的重要工具：数据模式、网页、批处理作业等。 [了解更多信息](../../developing/using/monitoring-data-model-changes.md)

**导出审核**

导出审核允许您监视对实例执行的导出：从工作流上传的文件、列表导出以及从直邮消息下载的文件。
[了解更多信息](../../administration/using/auditing-export-logs.md)

**许可证**

使用 **[!UICONTROL Licenses]** 菜单，监视有关实例的信息：已安装的许可证、内部版本和条款协议接受情况。
[了解更多信息](../../administration/using/licenses.md)

## 监控工作流 {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**最佳实践和故障排除**

在使用工作流时，遵循最佳实践和疑难解答指南有助于提高性能。
[了解更多信息](../../automating/using/best-practices-workflows.md)

**日志和任务**

工作流日志监控是分析工作流并确保其正常运行的关键步骤。
[了解更多信息](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**通知**

Campaign Standard允许您向主管发送通知，以监控工作流的执行情况，并查看是否存在需要您注意的错误。
[了解更多信息](../../automating/using/monitoring-workflow-execution.md#error-management)

## 监控投放 {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**可投放性**

Campaign Standard提供了多种可投放性工具来帮助您提高成功投放的邮件的数量：投放吞吐量报告、发送时间优化、邮件预览、电子邮件渲染、隔离管理等。
[了解更多信息](../../sending/using/about-deliverability.md)

**投放**

发送消息后，利用详细的日志，可监测投放并衡量活动是否成功，以及跟踪消息收件人的行为。
[了解更多信息](../../sending/using/monitoring-a-delivery.md)

**投放警报**

借助投放警报功能，您可以设置自动发送给一组用户的关于投放执行的警报：发送或准备失败、跳出率差、吞吐量低等。
[了解更多信息](../../sending/using/receiving-alerts-when-failures-happen.md)

**动态报告**

动态报告提供各种报告，帮助您随时了解投放的执行情况：跳出次数、收件人查看的投放次数最多、投放的吞吐量等。
[了解更多信息](../../reporting/using/about-dynamic-reports.md)
