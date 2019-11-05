---
title: 退回摘要
description: 通过“弹出摘要”现成报告，了解已发送营销活动的状态及其可能遇到的错误。
page-status-flag: 从未激活
uuid: 90087311-4236-4df9-ae7d-4a15c00c70ab
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 报告
content-type: 参考
topic-tags: 报告列表
discoiquuid: 5ae561b4-03cf-4541-87ff-47f1027d53b8
context-tags: bounceReport,main;campaignLecurationReport,main;programLecurationReport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 退回摘要{#bounce-summary}

此报告详细描述了在提交过程中遇到的总体硬错误和软错误以及弹回的自动处理。

![](assets/campaign_reports_bounces.png)

每个表由摘要编号和图表表示。 您可以更改详细信息在各自的可视化设置中的显示方式。

**第5次重新划分** ，列出了5次检疫最多的交付：

“弹 **回原因** ”(Bounce reasons)表包含导致每个交付发生弹回的错误类型的可用数据：

* **[!UICONTROL User unknown]**:发送到无效电子邮件地址时生成的错误类型。
* **[!UICONTROL Invalid domain]**:将分发发送到域错误或不再存在的电子邮件地址时生成的错误类型。
* **[!UICONTROL Unreachable]**:消息传送字符串中遇到的错误类型。 例如，SMTP中继事件、域暂时不可访问等。
* **[!UICONTROL Account disabled]**:将分发发送到不再存在的电子邮件地址时生成的错误类型。
* **[!UICONTROL Mailbox full]**:当收件人的收件箱已满时生成的错误类型。 在生成此错误之前，有五次尝试传送消息。
* **[!UICONTROL Not connected]**:当接收方的移动电话关闭或消息发送时未连接到网络时生成的错误类型。

   >[!NOTE]
   >
   >此类错误只涉及移动渠道上的分发。

* **[!UICONTROL Refused]**:当Internet服务提供商(ISP)拒绝地址时生成的错误类型。 例如，当反垃圾邮件软件应用了安全规则时。

“域 **重新分区** ”表根据接收方域显示在分发过程中遇到的总体问题。
