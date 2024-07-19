---
title: 退回摘要
description: 使用弹回摘要现成报告，了解已发送营销活动的状态以及他们可能遇到的错误。
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
source-wordcount: '278'
ht-degree: 1%

---

# 退回摘要{#bounce-summary}

此报表详细说明在投放期间遇到的整体硬错误和软错误，以及退回的自动处理（请参阅[了解投放失败](../../sending/using/understanding-delivery-failures.md)）。

![](assets/campaign_reports_bounces.png)

每个表格都由摘要数字和图表表示。 您可以更改详细信息在其各自可视化图表设置中的显示方式。

**失败5重新分区**&#x200B;列出了隔离数量最多的五个投放：

**退回原因**&#x200B;表包含导致每次投放退回的错误类型的可用数据：

* **[!UICONTROL User unknown]**：将投放发送到无效电子邮件地址时生成的错误类型。
* **[!UICONTROL Invalid domain]**：将投放发送到域错误或不再存在的电子邮件地址时生成的错误类型。
* **[!UICONTROL Unreachable]**：在邮件投放字符串中遇到的错误类型，如暂时无法访问域。
* **[!UICONTROL Account disabled]**：将投放发送到不再存在的电子邮件地址时生成的错误类型。
* **[!UICONTROL Mailbox full]**：收件人的收件箱已满时生成的错误类型。 在生成此错误之前，会尝试五次传递消息。
* **[!UICONTROL Not connected]**：收件人的手机已关闭或在发送消息时未连接到网络时生成的错误类型。

  >[!NOTE]
  >
  >此类错误仅与移动渠道中的投放有关。

* **[!UICONTROL Refused]**：当Internet服务提供商(ISP)拒绝地址时生成的错误类型。 例如，当反垃圾邮件软件应用了安全规则时。

**域重新分区**&#x200B;表根据收件人域显示投放期间遇到的整体问题。
