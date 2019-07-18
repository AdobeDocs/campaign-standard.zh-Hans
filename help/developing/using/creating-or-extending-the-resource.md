---
title: 创建或扩展资源
seo-title: 创建或扩展资源
description: 创建或扩展资源
seo-description: 了解如何从头开始定义资源。
page-status-flag: 从未激活
uuid: 7c26b63d-9587-472b-804f-cde5 c45 dfb3 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: dc45c37-6908-407e-8e41-4a4188cba2b3
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Creating or extending the resource{#creating-or-extending-the-resource}

如果需要处理非现成数据模型的数据，管理员可以从头开始创建新资源或创建现有资源的扩展。

只能扩展以下现成的资源：

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

1. From **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**, click the **[!UICONTROL Create]** button.
1. 选择要执行的操作：

   * **[!UICONTROL Create a new resource]**：输入 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 字段。**[!UICONTROL ID]** 字段为必填字段。如果将“标签”字段留空，将从ID自动完成该字段。

      ![](assets/schema_extension_2.png)

   * **[!UICONTROL Extend an existing resource]**：选择要扩展的资源。

      ![](assets/schema_extension_10.png)

1. Click **[!UICONTROL Create]** to create the resource, which will then take on the **[!UICONTROL Draft]** status in case of new resource or the **[!UICONTROL Editing]** status in case of extension.

此时会创建新资源，现在可以配置该资源。For more on resource configuration, refer to [Configuring the resource's data structure](../../developing/using/configuring-the-resource-s-data-structure.md).
