---
title: 退回摘要
seo-title: 退回摘要
description: 退回摘要
seo-description: 通过跳出式摘要报告，了解已发送营销活动的状态和他们可能遇到的错误。
page-status-flag: 从未激活
uuid: 90087311-4236-4df9-ae7 d-4a15 c00 c70 ab
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 报告报告
content-type: reference
topic-tags: 报告列表
discoiquuid: 5ae561b4-03cf-4541-87ff-47f1027d53b8
context-tags: boundsePort，main；Campaign循环报告，主要；编程报表，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Bounce summary{#bounce-summary}

此报告详细介绍交付过程中遇到的整体硬错误以及自动处理问题。

![](assets/campaign_reports_bounces.png)

每个表由摘要编号和图表表示。您可以更改详细信息在其各自的可视化设置中的显示方式。

**Flop redition** 列出了五个具有最大域名的交付：

**“跳出原因** ”表包含针对每个传送造成弹回的类型的可用数据：

* **[!UICONTROL User unknown]**：发送到无效电子邮件地址时生成的错误类型。
* **[!UICONTROL Invalid domain]**：发送发送到域名错误或不再存在的电子邮件地址时生成的错误类型。
* **[!UICONTROL Unreachable]**：消息交付字符串中遇到的错误类型。例如，SMTP传输事件，域暂时无法恢复等。
* **[!UICONTROL Account disabled]**：发送发送到不再存在的电子邮件地址时生成的错误类型。
* **[!UICONTROL Mailbox full]**：收件人收件箱已满时生成的错误类型。在生成此错误之前，有五次尝试发送消息。
* **[!UICONTROL Not connected]**：接收方移动电话关闭或发送消息时未连接到网络的错误类型。

   >[!NOTE]
   >
   >此类型的错误仅关注移动渠道上的分发。

* **[!UICONTROL Refused]**：Internet服务提供商(ISP)拒绝地址时生成的错误类型。例如，当防垃圾邮件软件应用了安全规则时。

**域重新划分** 表格显示了根据收件人域交付过程中遇到的整体问题。
