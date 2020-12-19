---
solution: Campaign Standard
product: campaign
title: 创建或扩展资源
description: 了解如何从头开始定义资源。
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
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

要创建或扩展资源，请执行以下操作：

1. 从&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**&#x200B;单击&#x200B;**[!UICONTROL Create]**&#x200B;按钮。
1. 选择要执行的操作：

   * **[!UICONTROL Create a new resource]**:输入 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 字段。**[!UICONTROL ID]** 字段属于必填字段。如果将“标签”字段留空，则该字段将自动从ID完成。

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >最多使用 30 个字符。

   * **[!UICONTROL Extend an existing resource]**:选择要扩展的资源。

      ![](assets/schema_extension_10.png)

1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;可创建资源，在出现新资源时，该资源将处于&#x200B;**[!UICONTROL Draft]**&#x200B;状态，在出现扩展时，将处于&#x200B;**[!UICONTROL Editing]**&#x200B;状态。

新资源已创建，现在可以进行配置。 有关资源配置的详细信息，请参阅[配置资源的数据结构](../../developing/using/configuring-the-resource-s-data-structure.md)。
