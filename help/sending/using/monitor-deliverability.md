---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standard监测可交付性
description: 使用Adobe Campaign Standard提供的工具监控平台的可交付性。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 7%

---


# 监控投放能力{#monitor-deliverability}

在下面，您将找到报告的 **[!UICONTROL Delivery throughput]** 详细信息以及Adobe Campaign提供的不同监视工具。 以下是有关交付性监控的一些附加准则：
* 定期检查整个平台的投放吞吐量，以验证其是否与原始设置一致。
* 检查重试是否设置正确(重试时间为30分钟，投放模板中的重试超过20分钟)。
* 定期验证弹回邮箱是否可访问，以及帐户是否即将过期。
* 检查每个投放吞吐量，确保其与投放内容的有效性(例如，“flash sales”应在几分钟内交付，而不是几天内交付)。
* 使用批次时，请验证在触发下一个波形之前，每个波形是否有足够的时间完成。
* 检查错误和新隔离的数量是否与其他投放一致。
* 仔细咨询投放日志，检查突出显示的错误类型(阻止列表、DNS问题、防垃圾邮件规则等……)。

## 投放吞吐量 {#delivery-throughput}

此报告包含有关给定时间段内整个平台的投放吞吐量的信息，以测量消息传送速度。

有关详细信息，请参阅 [投放吞吐量](../../reporting/using/delivery-throughput.md)。

![](assets/delivery_reports_1.png)

您可以通过更改时间刻度来配置显示的值。

还提供其他报告， **[!UICONTROL Delivery summary]** 如 **[!UICONTROL Non-deliverables and bounces]**&#x200B;或。 有关此方面的详细信息，请参 [阅动态报表](../../reporting/using/about-dynamic-reports.md)。

## 监控投放 {#monitoring-deliveries}

消息仪表板允许您访问投放日志: **[!UICONTROL Sending logs]**、 **[!UICONTROL Exclusion logs]**、 **[!UICONTROL Exclusion causes]**&#x200B;以 **[!UICONTROL Tracking logs]** 及 **[!UICONTROL Tracked URLs]**。 日志中包含发送、已排除的目标及排除原因，以及打开和单击等跟踪信息的详情。

有关此方面的详细信息，请 [参阅监视投放](../../sending/using/monitoring-a-delivery.md)。

![](assets/sending_delivery1.png)

## 接收警报 {#receiving-alerts}

The **[!UICONTROL Delivery alerting]** feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries.

有关详细信息，请参 [阅在失败时接收警报](../../sending/using/receiving-alerts-when-failures-happen.md)。

## 信号垃圾邮件 {#signal-spam}

Signal Spam是一种法国服务，它为法国ISP(Orange, SFR)优惠匿名反馈循环报告。

此服务允许您关注法国ISP的声誉并跟踪客户的活动发展。

Signal Spam还直接抱怨最终用户通过专用界面登录。 然后，这些投诉将被隔离在电子邮件地址数据库中。

## 250ok {#solution-250ok}

250ok是一种监控解决方案，提供IP和域阻止列表以及信誉指标。

提供的信息是实时的，它允许主动提供帮助。 250ok是Adobe交付能力内部工具的补充解决方案。
