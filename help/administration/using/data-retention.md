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

* **整合跟踪**：6个月（推荐：1个月）
* **投放日志**：6个月（推荐：1个月）
* **跟踪日志**：6个月（推荐：1个月）
* **事件**：1 个月
* **事件处理统计信息**：6个月（推荐：1个月）
* **已存档事件**：6个月（推荐：1个月）
* **临时实体**：7 天
* **忽略的管道事件**：1 个月
* **投放警报**：1 个月
* **导出审核**：6个月（推荐：1个月）

## 投放的保留期 {#deliveries}

默认情况下，投放的保留期不受限制。

但是，如果实例中的投放量很大，您可以更新 **NmsCleanup_DeliveryPurgeDelay** 选项可从以下网址获得： **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** 菜单。

每次 **[!UICONTROL Database cleanup]** 运行工作流，则将删除满足为此选项设置的条件的投放。

此操作有助于加快流程，例如 **[!UICONTROL Copy headers from delivery templates]** 工作流。

>[!NOTE]
>
>在中了解有关技术工作流的更多信息 [本节](technical-workflows.md).


的默认值 **NmsCleanup_DeliveryPurgeDelay** 选项为 `-1`. 在这种情况下，不会删除投放。

例如，如果将其设置为 `180`，则任何过去180天内未更新的非模板投放将被删除，当 **[!UICONTROL Database cleanup]** 运行工作流。

>[!NOTE]
>
>* 不会删除营销或事务投放模板。
>
>* 对于定期投放，不会删除聚合期间设置为月或年的子投放。

更新时 **NmsCleanup_DeliveryPurgeDelay** 选项，建议逐步进行多个迭代。 例如，您可以首先将该值设置为300天、180天、120天等 — 确保迭代之间至少间隔2天。 否则， **[!UICONTROL Database cleanup]** 由于要删除大量投放，工作流可能需要较长时间。

