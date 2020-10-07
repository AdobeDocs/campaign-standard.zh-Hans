---
title: 创建或扩展资源
description: 了解如何从头开始定义资源。
page-status-flag: never-activated
uuid: 7c26b63d-9587-472b-804f-cde5c45dfb3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 8dc45c37-6908-407e-8e41-4a4188cba2b3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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

要创建或扩展资源，请执行以下操作：

1. 从 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**&#x200B;单击按 **[!UICONTROL Create]** 钮。
1. 选择要执行的操作：

   * **[!UICONTROL Create a new resource]**:输入 **[!UICONTROL Label]** 和字 **[!UICONTROL ID]** 段。 **[!UICONTROL ID]** 字段属于必填字段。如果将“标签”字段留空，则该字段将自动从ID完成。

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >最多使用 30 个字符。

   * **[!UICONTROL Extend an existing resource]**:选择要扩展的资源。

      ![](assets/schema_extension_10.png)

1. 单 **[!UICONTROL Create]** 击以创建资源，在有新资源时，该资 **[!UICONTROL Draft]** 源将处于状态，在有 **[!UICONTROL Editing]** 扩展时，将处于状态。

新资源已创建，现在可以进行配置。 有关资源配置的详细信息，请 [参阅配置资源的数据结构](../../developing/using/configuring-the-resource-s-data-structure.md)。
