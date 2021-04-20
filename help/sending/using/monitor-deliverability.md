---
solution: Campaign Standard
product: campaign
title: 监控Adobe Campaign Standard中的交付能力
description: 使用Adobe Campaign Standard提供的工具监控平台的可交付性。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 10%

---


# 监控投放能力{#monitor-deliverability}

在下面，您将找到&#x200B;**[!UICONTROL Delivery throughput]**&#x200B;报告的详细信息以及Adobe Campaign提供的不同监视工具。 以下是有关交付能力监测的一些附加准则：
* 定期检查整个平台的投放吞吐量，以验证它是否与原始设置一致。
* 检查是否在重试中正确设置了重试(重试时间为30分钟，投放模板超过20分钟)。
* 定期验证弹回邮箱是否可访问，以及帐户是否即将过期。
* 检查每个投放吞吐量，确保其与投放内容的有效性一致(例如，“flash sales”应在数分钟内交付，而非数天内交付)。
* 检查错误和新隔离的数量是否与其他投放一致。
* 仔细咨询投放日志，以检查高亮显示的错误类型(阻止列表、DNS问题、防垃圾邮件规则等……)。

## 投放吞吐量 {#delivery-throughput}

此报告包含有关给定时间段内整个平台的投放吞吐量的信息，以测量消息传送的速度。

有关详细信息，请参阅[投放吞吐量](../../reporting/using/delivery-throughput.md)。

![](assets/delivery_reports_1.png)

您可以通过更改时间刻度来配置显示的值。

其他报表可用，如&#x200B;**[!UICONTROL Delivery summary]**&#x200B;或&#x200B;**[!UICONTROL Non-deliverables and bounces]**。 有关详细信息，请参阅[动态报告](../../reporting/using/about-dynamic-reports.md)。

## 监控投放 {#monitoring-deliveries}

消息仪表板允许您访问以下投放日志:**[!UICONTROL Sending logs]**、**[!UICONTROL Exclusion logs]**、**[!UICONTROL Exclusion causes]**、**[!UICONTROL Tracking logs]**&#x200B;和&#x200B;**[!UICONTROL Tracked URLs]**。 日志中包含发送、已排除的目标及排除原因，以及打开和单击等跟踪信息的详情。

有关详细信息，请参阅[监视投放](../../sending/using/monitoring-a-delivery.md)。

![](assets/sending_delivery1.png)

## 接收警报{#receiving-alerts}

**[!UICONTROL Delivery alerting]**&#x200B;功能是警报管理系统，它使一组用户能够自动接收包含有关其投放执行信息的通知。

有关详细信息，请参阅[发生故障时接收警报](../../sending/using/receiving-alerts-when-failures-happen.md)。

<!--## External tools (#external-tools)

### Signal Spam {#signal-spam}

Signal Spam is a French service which offers anonymized feedback loop reporting for French ISPs (Orange, SFR).

This service allows you to follow the reputation of the French ISPs and track customers' activity evolution.

Signal Spam also provides direct complaints that end users log through a dedicated interface. Those complaints are then quarantined from the email address database.

### 250ok {#solution-250ok}

250ok is a monitoring solution which provides IP and domain denylists, as well as reputation indicators.

The information provided is real-time, which allows for a pro-active assistance. 250ok a complementary solution to the Adobe deliverability internal tools.-->
