---
title: 在 Adobe Campaign Standard 中监控投放
description: 了解在 Adobe Campaign Standard 中监控投放的方法
audience: sending
content-type: reference
topic-tags: monitoring-messages
context-tags: delivery,main
feature: Performance Monitoring
role: User
level: Beginner
exl-id: ddc92077-df73-411d-a161-3263581e6945
source-git-commit: ed60bde4785da9a8cc5a6cc0efcdb24e2c1f65e3
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 79%

---

# 监测投放{#monitoring-a-delivery}

有多种方法可用于监控投放并衡量其影响。 功能管理员可访问消息日志和投放日志。

>[!IMPORTANT]
>
>仅功能 [管理员](../../administration/using/users-management.md#functional-administrators)，替换为 **[!UICONTROL Administration]** 角色和访问权限 **全部** 单位可访问发送日志、消息日志、跟踪日志、排除或订阅日志。 非管理员用户可以定位这些日志，但从链接表（用户档案、投放）开始。

* **消息日志**：可直接从消息仪表板访问这些日志。日志中包含发送、已排除的目标及排除原因，以及打开和单击等跟踪信息的详情。

  要查看消息日志，请单击 **[!UICONTROL Deployment]** 块右下方的图标。

  多个选项卡包含与 **[!UICONTROL Sending logs]**、**[!UICONTROL Exclusion logs]**、**[!UICONTROL Exclusion causes]**、**[!UICONTROL Tracking logs]** 和 **[!UICONTROL Tracked URLs]** 有关的信息（如存在）。请参阅[投放日志](#delivery-logs)。

  ![](assets/sending_delivery1.png)

  日志包含与投放和校样有关的所有消息。利用特定的图标，可识别错误或警告。有关更多信息，请参阅[批准消息](../../sending/using/previewing-messages.md)。

  您可以通过单击 **[!UICONTROL Export list]** 按钮导出日志。

  ![](assets/sending_delivery2.png)

* **作业日志**：可以通过选择，从消息仪表板访问由投放触发的批量作业列表 **[!UICONTROL Job history]** 从 **[!UICONTROL Summary]** 下拉列表。

  从列表中选择任意作业以查看所选作业的详细信息 **[!UICONTROL Batch job]**.

  ![](assets/sending_delivery8.png)

* **投放警报**：为长期跟踪投放是成功还是失败，Adobe Campaign 提供了电子邮件警报系统，用于发送通知以告知用户重要的系统活动。
* **报告**：在消息仪表板中，您可以访问此特定消息的多个报告。系统还提供了 **[!UICONTROL Reports]** 菜单，用于访问内置或自定义报告的完整列表，您可将其用于概览与消息或营销策划有关的特定指标。
* 管理员还可以将日志导出为单独的文件，以便在您自己的报告或 BI 工具中处理该文件。有关更多信息，请参阅[导出日志](../../automating/using/exporting-logs.md)。

**相关主题：**

* [在失败时接收提醒](../../sending/using/receiving-alerts-when-failures-happen.md)
* [报告](../../reporting/using/about-dynamic-reports.md)

## 投放日志 {#delivery-logs}

### 正在发送日志 {#sending-logs}

**[!UICONTROL Sending logs]** 选项卡提供了每次进行此投放的历史记录。此处保存了已发送消息的列表及其状态。您可通过该处查看每个收件人的投放状态。

对于具有 **[!UICONTROL Sent]** 状态的每个用户档案，**[!UICONTROL Date]** 列都显示了消息的发送时间。

![](assets/sending_delivery3.png)

要访问特定发送日志的详细信息，请单击对应行右侧的铅笔图标。

![](assets/sending_access-sending-log.png)

所有发送日志详细信息均为只读状态。您还可以查看镜像页面的预览。

![](assets/sending_sending-log.png)

>[!NOTE]
>
>要在 Campaign 用户界面中显示镜像页面的表达，镜像页面服务器 URL 必须是安全的。在本例中，[配置品牌](../../administration/using/branding.md#configuring-and-using-brands)时，请使用 https:// 而不是 http:// 设置此 URL。

### 排除日志 {#exclusion-logs}

**[!UICONTROL Exclusion logs]** 选项卡列出了从定向发送中排除的所有消息，并说明了发送失败的原因。

![](assets/sending_delivery4.png)

### 排除原因 {#exclusion-causes}

**[!UICONTROL Exclusion causes]** 选项卡显示从定向发送中排除的消息量（消息的数量）。

![](assets/sending_delivery5.png)
