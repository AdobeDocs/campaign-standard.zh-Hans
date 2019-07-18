---
title: 监控交付
seo-title: 监控交付
description: 监控交付
seo-description: 了解如何监控分发。
page-status-flag: 从未激活
uuid: 7772c607-debd-40fd-3322-4d49119979 b4
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: 监视消息
discoiquuid: eb9fa216-4568-423a-9396-1f7b82181ae9
context-tags: 交付，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Monitoring a delivery{#monitoring-a-delivery}

可以通过多种方式监控分发并衡量其影响：

* **消息日志**：这些日志可以直接从消息仪表板访问。它们显示发送的详细信息、目标被排除的原因、原因以及打开和单击等跟踪信息。

   To view the message logs, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   Several tabs contain information (if it exists) regarding the **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** and **[!UICONTROL Tracked URLs]**. See [Delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   ![](assets/sending_delivery1.png)

   日志包含与交付和校样相关的所有消息。特定图标允许您识别错误或警告。For more on this, see [Approving messages](../../sending/using/previewing-messages.md).

   You can export the log by clicking the **[!UICONTROL Export list]** button.

   ![](assets/sending_delivery2.png)

* **交付通知**：为了跟踪交付成功或失败，Adobe Campaign提供电子邮件警报系统，用于发送通知以告知用户重要系统活动。
* **报告**：在消息仪表板中，您可以访问此特定消息的多个报告。You also have a **[!UICONTROL Reports]** menu that allows you to access a complete list of built-in or custom reports that you can use to outline specific metrics related to your message or campaign.
* 管理员还可以将日志导出到单独的文件中，该文件可以在您自己的报表或BI工具中进行处理。For more on this, see [Exporting logs](../../automating/using/exporting-logs.md).

**相关主题：**

* [在发生故障时接收通知](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Reports](../../reporting/using/about-dynamic-reports.md)

## Delivery logs {#delivery-logs}

### Sending logs {#sending-logs}

**[!UICONTROL Sending logs]** 此选项卡提供此交付的每个实例的历史记录。此处存储已发送消息及其状态的列表。它允许您查看每个收件人的交付状态。

For each profile with a **[!UICONTROL Sent]** status, the **[!UICONTROL Date]** column shows when the message was sent.

![](assets/sending_delivery3.png)

### Exclusion logs {#exclusion-logs}

**[!UICONTROL Exclusion logs]** 选项卡列出了已从目标发送的所有消息，并指定发送失败的原因。

![](assets/sending_delivery4.png)

### Exclusion causes {#exclusion-causes}

**[!UICONTROL Exclusion causes]** 选项卡显示目标发送中排除的消息的音量(以消息数量为单位)。

![](assets/sending_delivery5.png)

