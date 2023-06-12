---
title: 创建或扩展资源
description: 了解如何从头开始定义资源。
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: b8731088-a675-4070-9036-bf2b5254e4e8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 11%

---

# 创建或扩展资源{#creating-or-extending-the-resource}

如果您需要处理不属于内置数据模型的数据，管理员可以从头开始创建新资源或创建现有资源的扩展。

只能扩展以下内置资源：

* **[!UICONTROL Campaign (campaign)]**
* **[!UICONTROL Deliveries (delivery)]**
* **[!UICONTROL Landing page (Landingpage)]**
* **[!UICONTROL Profiles (profile)]**
* **[!UICONTROL Program (program)]**
* **[!UICONTROL Service (service)]**
* **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**
* **[!UICONTROL Test profiles (seedMember)]**
* **[!UICONTROL Workflow (workflow)]**

创建或扩展资源：

1. 起始日期 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**，单击 **[!UICONTROL Create]** 按钮。
1. 选择要执行的操作：

   * **[!UICONTROL Create a new resource]**：输入 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 字段。 **[!UICONTROL ID]** 字段属于必填字段。如果将Label字段留空，则将自动从ID中完成该字段。

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >最多使用 30 个字符。

   * **[!UICONTROL Extend an existing resource]**：选择要扩展的资源。

      ![](assets/schema_extension_10.png)

1. 单击 **[!UICONTROL Create]** 以创建资源，然后该资源将承受 **[!UICONTROL Draft]** 若是新资源或 **[!UICONTROL Editing]** 对于扩展，为状态。

已创建新资源，现在可以对其进行配置。 有关资源配置的更多信息，请参阅 [配置资源的数据结构](../../developing/using/configuring-the-resource-s-data-structure.md).
