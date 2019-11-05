---
title: 创建或扩展资源
description: 了解如何从头开始定义资源。
page-status-flag: 从未激活
uuid: 7c26b63d-9587-472b-804f-cde5c45dfb3c
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 开发
content-type: 参考
topic-tags: adding-or-extending-a-resource
discoiquuid: 8dc45c37-6908-407e-8e41-4a4188cba2b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 创建或扩展资源{#creating-or-extending-the-resource}

如果您需要处理不是现成数据模型一部分的数据，管理员可以从头开始创建新资源或创建现有资源的扩展。

只能扩展以下现成资源：

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

1. 从 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**&#x200B;中，单击按 **[!UICONTROL Create]** 钮。
1. 选择要执行的操作：

   * **[!UICONTROL Create a new resource]**:输入和 **[!UICONTROL Label]** 字 **[!UICONTROL ID]** 段。 该字 **[!UICONTROL ID]** 段是必填字段。 如果将“标签”字段留空，则该字段将自动从ID完成。

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >我们建议最多使用30个字符。

   * **[!UICONTROL Extend an existing resource]**:选择要扩展的资源。

      ![](assets/schema_extension_10.png)

1. 单 **[!UICONTROL Create]** 击以创建资源，新资源时，该资源将处 **[!UICONTROL Draft]** 于状态，扩展时 **[!UICONTROL Editing]** 将处于状态。

此时将创建新资源，并且现在可以配置新资源。 有关资源配置的详细信息，请 [参阅配置资源的数据结构](../../developing/using/configuring-the-resource-s-data-structure.md)。
