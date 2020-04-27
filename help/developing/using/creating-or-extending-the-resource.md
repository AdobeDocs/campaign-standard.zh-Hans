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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

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

1. 从 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**&#x200B;中，单击按 **[!UICONTROL Create]** 钮。
1. 选择要执行的操作：

   * **[!UICONTROL Create a new resource]**:输入和 **[!UICONTROL Label]** 字 **[!UICONTROL ID]** 段。 该字 **[!UICONTROL ID]** 段是必填字段。 如果将“标签”字段留空，将从ID自动完成该字段。

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >最多使用30个字符。

   * **[!UICONTROL Extend an existing resource]**:选择要扩展的资源。

      ![](assets/schema_extension_10.png)

1. 单 **[!UICONTROL Create]** 击以创建资源，新资源时，该资源将处 **[!UICONTROL Draft]** 于状态，扩展时 **[!UICONTROL Editing]** 将处于状态。

此时将创建新资源，并且现在可以配置新资源。 有关资源配置的详细信息，请 [参阅配置资源的数据结构](../../developing/using/configuring-the-resource-s-data-structure.md)。
