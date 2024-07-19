---
title: 数据保留
description: 了解标准表的默认保留值
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 2e81a05b1b647991250d13d7d37f5da275a8db44
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 5%

---

# 数据保留{#data-retention}

Campaign中的标准日志表具有预设的保留期，可限制其数据存储持续时间，以避免系统过载。

数据保留配置由Adobe技术管理员在实施期间设置，每项实施的值可能会因客户要求而异。

请联系Adobe顾问或技术管理员，详细了解适用于您的环境的保留期，或设置自定义保留期。

请注意，使用标准工作流功能，可以为任何自定义表设置保留期。

以下是标准表的默认保留期。 根据您的数据使用情况，Adobe会尽可能建议您改用建议的保留期，以提高Campaign实例的性能。

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

## 投放的保留期 {#deliveries}

默认情况下，投放的保留期不受限制。

但是，如果您的实例上存在大量投放，则可以更新&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]**&#x200B;菜单中可用的&#x200B;**NmsCleanup_DeliveryPurgeDelay**&#x200B;选项。

每次运行&#x200B;**[!UICONTROL Database cleanup]**&#x200B;工作流时，将删除满足为此选项设置的条件的投放。

此操作有助于加快进程，如&#x200B;**[!UICONTROL Copy headers from delivery templates]**&#x200B;工作流。

>[!NOTE]
>
>在[本节](technical-workflows.md)中了解有关技术工作流的更多信息。


**NmsCleanup_DeliveryPurgeDelay**&#x200B;选项的默认值为`-1`。 在这种情况下，不会删除投放。

例如，如果您将其设置为`180`，则在运行&#x200B;**[!UICONTROL Database cleanup]**&#x200B;工作流时，将删除过去180天内未更新的任何非模板投放。

>[!NOTE]
>
>* 不会删除营销或事务投放模板。
>
>* 对于定期投放，不会删除聚合期间设置为月或年的子投放。

更新&#x200B;**NmsCleanup_DeliveryPurgeDelay**&#x200B;选项时，建议逐步执行多个迭代。 例如，您可以首先将该值设置为300天、180天、120天等 — 确保迭代之间至少间隔2天。 否则，由于要删除大量投放，**[!UICONTROL Database cleanup]**&#x200B;工作流可能需要更长的时间。

