---
solution: Campaign Standard
product: campaign
title: 退回摘要
description: 通过现成的弹出摘要报告，了解已发送活动的状态以及他们可能遇到的错误。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 8%

---


# 退回摘要{#bounce-summary}

该报告会详细描述在投放期间遇到的整体硬错误和软错误，以及退回的自动处理。

![](assets/campaign_reports_bounces.png)

每个表由摘要编号和图表表示。 您可以更改详细信息在其各自的可视化设置中的显示方式。

**第5次重划** 列表的是5个投放的隔离数最多：

“弹 **出原因** ”表包含导致每个投放发生弹出的错误类型的可用数据：

* **[!UICONTROL User unknown]**:将投放发送到无效电子邮件地址时生成的错误类型。
* **[!UICONTROL Invalid domain]**:将投放发送到域错误或不再存在的电子邮件地址时生成的错误类型。
* **[!UICONTROL Unreachable]**:消息投放字符串中遇到的错误类型，如临时不可到达的域。
* **[!UICONTROL Account disabled]**:将投放发送到不再存在的电子邮件地址时生成的错误类型。
* **[!UICONTROL Mailbox full]**:收件人收件箱已满时生成的错误类型。 在生成此错误之前，有五次尝试传送消息。
* **[!UICONTROL Not connected]**:当收件人的移动电话关闭或消息发送时未连接到网络时生成的错误类型。

   >[!NOTE]
   >
   >此类错误只涉及移动渠道上的投放。

* **[!UICONTROL Refused]**:Internet服务提供商(ISP)拒绝地址时生成的错误类型。 例如，当防垃圾邮件软件应用了安全规则时。

“域 **重新分区** ”表根据收件人域显示在投放过程中遇到的所有问题。
