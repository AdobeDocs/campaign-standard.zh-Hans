---
title: 在Adobe Campaign Standard中监控投放能力
description: 使用Adobe Campaign Standard提供的工具监控平台的可投放性。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 683341fb-fef5-4aa1-8606-9526d9ae6290
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 9%

---

# 监测可投放性{#monitor-deliverability}

在下方，您将找到有关 **[!UICONTROL Delivery throughput]** 以及Adobe Campaign提供的各种监控工具。 以下是有关可投放性监测的其他准则：
* 定期检查整个平台的投放吞吐量，验证其是否与原始设置一致。
* 检查投放模板中是否正确设置了重试（重试期间为30分钟，重试次数超过20次）。
* 定期验证退回邮箱是否可访问，以及帐户是否即将过期。
* 检查每个投放吞吐量，确保其与投放内容的有效性一致（例如，“闪购”应在几分钟内投放，而不是几天）。
* 检查错误和新隔离的数量是否与其他投放一致。
* 请仔细查阅投放日志，详细检查突出显示的错误类型(阻止列表、DNS问题、反垃圾邮件规则等)。

## 投放吞吐量 {#delivery-throughput}

此报表包含有关给定时段内整个平台的投放吞吐量以测量消息投放速度的信息。

有关此内容的更多信息，请参阅 [投放吞吐量](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

您可以通过更改时间刻度来配置显示的值。

还提供其他报表，例如 **[!UICONTROL Delivery summary]** 或 **[!UICONTROL Non-deliverables and bounces]**. 有关此内容的更多信息，请参阅 [动态报告](../../reporting/using/about-dynamic-reports.md).

## 监控投放 {#monitoring-deliveries}

通过消息仪表板，可访问投放日志： **[!UICONTROL Sending logs]**， **[!UICONTROL Exclusion logs]**， **[!UICONTROL Exclusion causes]**， **[!UICONTROL Tracking logs]** 和 **[!UICONTROL Tracked URLs]**. 日志中包含发送、已排除的目标及排除原因，以及打开和单击等跟踪信息的详情。

有关此内容的更多信息，请参阅 [监控投放](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## 接收警报 {#receiving-alerts}

此 **[!UICONTROL Delivery alerting]** 功能是一个警报管理系统，通过它，一组用户可自动接收包含其投放执行信息的通知。

有关此内容的更多信息，请参阅 [发生故障时接收警报](../../sending/using/receiving-alerts-when-failures-happen.md).

<!--## External tools (#external-tools)

### Signal Spam {#signal-spam}

Signal Spam is a French service which offers anonymized feedback loop reporting for French ISPs (Orange, SFR).

This service allows you to follow the reputation of the French ISPs and track customers' activity evolution.

Signal Spam also provides direct complaints that end users log through a dedicated interface. Those complaints are then quarantined from the email address database.

### 250ok {#solution-250ok}

250ok is a monitoring solution which provides IP and domain denylists, as well as reputation indicators.

The information provided is real-time, which allows for a pro-active assistance. 250ok a complementary solution to the Adobe deliverability internal tools.-->
