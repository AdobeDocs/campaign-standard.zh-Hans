---
solution: Campaign Standard
product: campaign
title: 退回摘要
description: 通过现成的“跳出摘要”报表，了解已发送活动的状态以及他们可能遇到的错误。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
translation-type: tm+mt
source-git-commit: 2bc5eae996dfa3ecdde3540f3a4f759c668e93ec
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---


# 退回摘要{#bounce-summary}

此报告详细说明了在投放过程中遇到的整体硬错误和软错误以及弹回的自动处理(请参阅[了解投放故障](../../sending/using/understanding-delivery-failures.md))。

![](assets/campaign_reports_bounces.png)

每个表都由摘要编号和图表表示。 您可以更改详细信息在各自的可视化设置中的显示方式。

**Flop 5重** 新划分列出了投放数最多的五个隔离:

**跳出原因**&#x200B;表包含导致每个投放跳出的错误类型的可用数据：

* **[!UICONTROL User unknown]**:将投放发送到无效电子邮件地址时生成的错误类型。
* **[!UICONTROL Invalid domain]**:将投放发送到域错误或不再存在的电子邮件地址时生成的错误类型。
* **[!UICONTROL Unreachable]**:消息投放字符串中遇到的错误类型，如域临时不可到达。
* **[!UICONTROL Account disabled]**:将投放发送到不再存在的电子邮件地址时生成的错误类型。
* **[!UICONTROL Mailbox full]**:当收件人的收件箱已满时生成的错误类型。在生成此错误之前，有五次尝试传送消息。
* **[!UICONTROL Not connected]**:当收件人的移动电话关闭或消息发送时未连接到网络时生成的错误类型。

   >[!NOTE]
   >
   >此类错误仅涉及移动渠道上的投放。

* **[!UICONTROL Refused]**:Internet服务提供商(ISP)拒绝地址时生成的错误类型。例如，当防垃圾邮件软件应用了安全规则时。

**域重新分区**&#x200B;表根据收件人域显示投放过程中遇到的总体问题。
