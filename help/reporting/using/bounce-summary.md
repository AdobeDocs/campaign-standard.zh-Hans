---
title: 退回摘要
description: 通过现成的“退回摘要”报表，了解已发送营销活动的状态以及他们可能遇到的错误。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 03ea2f20-959c-497e-bd71-4e77132d712e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---

# 退回摘要{#bounce-summary}

此报告详细介绍了在投放过程中遇到的整体硬错误和软错误以及退回的自动处理（请参阅[了解投放失败](../../sending/using/understanding-delivery-failures.md)）。

![](assets/campaign_reports_bounces.png)

每个表都由概要数字和图表表示。 您可以更改详细信息在各自的可视化设置中的显示方式。

**第5次重** 新划分会列出5个具有最高隔离次数的投放：

**退回原因**&#x200B;表包含导致每个投放出现退回的错误类型的可用数据：

* **[!UICONTROL User unknown]**:将投放发送到无效电子邮件地址时生成的错误类型。
* **[!UICONTROL Invalid domain]**:将投放发送到域错误或不再存在的电子邮件地址时生成的错误类型。
* **[!UICONTROL Unreachable]**:消息投放字符串中遇到的错误类型，如域名临时不可访问。
* **[!UICONTROL Account disabled]**:将投放发送到不再存在的电子邮件地址时生成的错误类型。
* **[!UICONTROL Mailbox full]**:收件人收件箱已满时生成的错误类型。在生成此错误之前，已尝试五次传送消息。
* **[!UICONTROL Not connected]**:当收件人的手机关闭或在发送消息时未连接到网络时生成的错误类型。

   >[!NOTE]
   >
   >此类错误仅涉及移动渠道上的投放。

* **[!UICONTROL Refused]**:Internet服务提供商(ISP)拒绝地址时生成的错误类型。例如，当防垃圾邮件软件应用了安全规则时。

**域重新分区**&#x200B;表根据收件人域显示投放过程中遇到的整体问题。
