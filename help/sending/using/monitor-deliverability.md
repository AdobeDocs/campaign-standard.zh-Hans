---
title: 在Adobe Campaign standard中监控交付性
description: 使用Adobe Campaign standard提供的工具监控平台的可交付性。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1d5bb21ab16df87e268b9eabe92965be1b052556

---


# 监控交付性{#monitor-deliverability}

在下面，您将找到有关报告的 **[!UICONTROL Delivery throughput]** 详细信息以及Adobe Campaign提供的不同监视工具。 以下是有关交付性监控的一些附加准则：
* 定期检查整个平台的交付吞吐量，以验证其是否与原始设置一致。
* 检查在交付模板中是否正确设置了重试次数（30分钟，重试次数超过20次）。
* 定期验证弹回邮箱是否可访问，以及帐户是否即将过期。
* 检查每个交付吞吐量，确保其与交付内容的有效性一致(例如，“Flash销售”应在数分钟内交付，而不是数天内交付)。
* 使用波形时，在触发下一个波形之前，请验证每个波形是否有足够的时间完成。
* 检查错误数和新的隔离与其他发送的数量是否一致。
* 仔细查阅交付日志，以检查高亮显示的错误类型（灰色或黑名单、DNS问题、防垃圾邮件规则等）。

## 投放吞吐量 {#delivery-throughput}

此报告包含有关给定时间段内整个平台的交付吞吐量的信息，以测量消息的交付速度。

有关详细信息，请参阅 [交付吞吐量](../../reporting/using/delivery-throughput.md)。

![](assets/delivery_reports_1.png)

您可以通过更改时间刻度来配置显示的值。

其他报告可用，如 **[!UICONTROL Delivery summary]** 或 **[!UICONTROL Non-deliverables and bounces]**。 有关详细信息，请参阅 [动态报表](../../reporting/using/about-dynamic-reports.md)。

## 监控交付 {#monitoring-deliveries}

消息功能板允许您访问交付日志： **[!UICONTROL Sending logs]**、 **[!UICONTROL Exclusion logs]****[!UICONTROL Exclusion causes]**、 **[!UICONTROL Tracking logs]** 和 **[!UICONTROL Tracked URLs]**。 它们显示发送的详细信息、已排除的目标以及原因，以及打开和单击等跟踪信息。

有关此方面的详细信息，请参 [阅监视交付](../../sending/using/monitoring-a-delivery.md)。

![](assets/sending_delivery1.png)

## 接收警报 {#receiving-alerts}

该功 **[!UICONTROL Delivery alerting]** 能是警报管理系统，它使一组用户能够自动接收包含关于其发送的执行信息的通知。

有关详细信息，请参阅 [在失败时接收警报](../../sending/using/receiving-alerts-when-failures-happen.md)。

## Signal Spam {#signal-spam}

Signal Spam是一项法国服务，它为法国ISP(Orange, SFR)提供匿名反馈循环报告。

此服务允许您跟踪法国ISP的声誉并跟踪客户活动的演变。

Signal Spam还会直接投诉最终用户通过专用界面进行登录。 然后，这些投诉会被隔离到电子邮件地址数据库。

## 250ok {#solution-250ok}

250ok是一种提供IP、域黑名单和信誉指标的监控解决方案。

提供的信息是实时的，这允许主动协助。 250ok是Adobe可交付性内部工具的补充解决方案。
