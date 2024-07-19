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
source-wordcount: '154'
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

1. 从&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**，单击&#x200B;**[!UICONTROL Create]**&#x200B;按钮。
1. 选择要执行的操作：

   * **[!UICONTROL Create a new resource]**：输入&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL ID]**&#x200B;字段。 **[!UICONTROL ID]** 字段属于必填字段。如果您将Label字段留空，则将自动从ID中完成该字段。

     ![](assets/schema_extension_2.png)

     >[!NOTE]
     >
     >最多使用 30 个字符。

   * **[!UICONTROL Extend an existing resource]**：选择要扩展的资源。

     ![](assets/schema_extension_10.png)

1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;以创建资源，如果为新资源，则创建资源将采用&#x200B;**[!UICONTROL Draft]**&#x200B;状态，如果为扩展，则创建资源将采用&#x200B;**[!UICONTROL Editing]**&#x200B;状态。

新资源已创建，现在可以配置。 有关资源配置的更多信息，请参阅[配置资源的数据结构](../../developing/using/configuring-the-resource-s-data-structure.md)。
