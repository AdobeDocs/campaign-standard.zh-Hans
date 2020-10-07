---
title: 删除资源
description: '了解如何删除资源 '
page-status-flag: never-activated
uuid: 5de27589-6fa5-412c-8e5a-a4976de05715
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 0130733d-4e3f-40cd-b959-56381f2c8f44
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 删除资源{#deleting-a-resource}

要删除资源，该资源必须是 **[!UICONTROL Draft]**。 在以下情况下，资 **[!UICONTROL Draft]** 源处于状态：

* 它刚刚创建，尚未发布。
* 如果已发布，则必须重新起草资源。

>[!IMPORTANT]
>
>重新起草和删除自定义资源是敏感操作，可能会影响其他资源。 这些操作只能由专家用户执行。

要重新草拟和删除已发布的资源，请执行以下操作：

1. 选择要重新草拟的资源。
1. 单击操作栏中的 **[!UICONTROL Re-draft]** 按钮。

   ![](assets/schema_extension_uc26.png)

1. 单击 **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >此操作是明确的：在发布修改时，资源的数据库表或列及其数据将被永久删除，这可能导致来自其他自定义资源的链接中断。 只有资源定义仍可用。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >如果您重新草拟现成用户档案( **用户档案)资源的扩展** ，则还必须重新草拟您可能已定 **义的任何测试用户档案(** seedMember)扩展。 有关扩展用户档案资源的详细信息，请 [参阅此部分](../../developing/using/extending-the-profile-resource-with-a-new-field.md)。

1. 发布资源。 有关更详细的步骤，请参 [阅发布自定义资源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   资源随后将进入“ **草稿** ”模式，其激活状态为 **[!UICONTROL Inactive]**。

1. 在模 **[!UICONTROL List]** 式中，检查要删除的资源，然后单击 ![](assets/delete_darkgrey-24px.png) 图 **[!UICONTROL Delete element]** 标。

   ![](assets/schema_extension_uc28.png)

您的资源将从数据模型中删除。

>[!NOTE]
>
>如果修改或删除了用于事件的自定义资源字段，将自动取消发布对应的事件。See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

