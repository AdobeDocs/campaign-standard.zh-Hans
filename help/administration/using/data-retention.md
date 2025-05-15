---
title: 数据保留
description: 了解标准表的默认保留值
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 2bc6ce04d2580b561bfdaafe29985353fd116a42
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 5%

---

# 数据保留{#data-retention}

>[!NOTE]
>
>数据报表仅可用于最近两年。 有关数据保留期的更多信息，请联系Adobe顾问或您的技术管理员。

Campaign中的标准日志表具有预设的保留期，可限制其数据存储持续时间，以避免系统过载。

数据保留配置由Adobe技术管理员在实施期间设置，每项实施的值可能会因客户要求而异。

请联系Adobe顾问或技术管理员，详细了解适用于您的环境的保留期，或设置自定义保留期。

请注意，使用标准工作流功能，可以为任何自定义表设置保留期。

以下是标准表的默认保留期。 根据您的数据使用情况，Adobe建议您尽可能使用建议的保留期，以提高Campaign实例的性能。

* **合并跟踪**：6个月（建议：1个月）
* **投放日志**：6个月（建议：1个月）
* **跟踪日志**：6个月（建议：1个月）
* **事件**：1 个月
* **事件处理的统计信息**：6个月（建议：1个月）
* **存档事件**：6个月（建议：1个月）
* **临时实体**：7 天
* **忽略的管道事件**：1 个月
* **投放警报**：1 个月
* **导出审核**：6个月（建议：1个月）
* **投放**： 2年

## 投放的保留期 {#deliveries}

<!-- By default, the retention period for deliveries is unlimited.-->

自2025年6月1日起，系统中将仅保留过去两年的投放。 您将在下面找到更多详细信息：

* 超过两年的任何投放将被永久移除，不再可供访问。
* 此清理仅包含已发送和失败的投放；不影响定期投放、草稿投放和模板。
* 删除投放后，任何链接的跟踪或发送信息也将被永久删除。
* 不会删除营销或事务投放模板。
* 对于定期投放，不会删除聚合期间设置为月或年的子投放。

如果您希望加快&#x200B;**[!UICONTROL Copy headers from delivery templates]**&#x200B;工作流等进程，则可以缩短投放保留期。 为此，请联系您的Adobe代表。

<!--

However, if there is a high volume of deliveries on your instance, you can update the **NmsCleanup_DeliveryPurgeDelay** option available from the **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** menu.

Each time the **[!UICONTROL Database cleanup]** workflow is run, the deliveries meeting the conditions set for this option will be deleted.

-->

<!--

When updating the **NmsCleanup_DeliveryPurgeDelay** option, it is recommended to proceed gradually with multiple iterations. For example, you can start by setting the value to 300 days, then 180 days, then 120 days, and so on - making sure iterations are at least 2 days apart. Otherwise, the **[!UICONTROL Database cleanup]** workflow may take much longer because of a large number of deliveries to delete.

This action can help speeding up processes such as the **[!UICONTROL Copy headers from delivery templates]** workflow. Learn more on technical workflows in [this section](technical-workflows.md).

The default value for the **NmsCleanup_DeliveryPurgeDelay** option is `-1`. In this case, no delivery is deleted.

For example, if you set it to `180`, any non-template deliveries that have not been updated in the last 180 days will be deleted when the **[!UICONTROL Database cleanup]** workflow is run.

-->


