---
title: 删除资源
description: '了解如何删除资源 '
page-status-flag: 从未激活
uuid: 5de27589-6fa5-412c-8e5a-a4976de05715
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 开发
content-type: 参考
topic-tags: adding-or-extending-a-resource
discoiquuid: 0130733d-4e3f-40cd-b959-56381f2c8f44
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 删除资源{#deleting-a-resource}

要删除资源，相关资源必须是 **[!UICONTROL Draft]**。 如果满足以下条件，则资 **[!UICONTROL Draft]** 源处于状态：

* 它刚刚创建，尚未发布。
* 如果已经发布，则必须重新起草资源。

>[!CAUTION]
>
>重新起草和删除自定义资源是可能影响其他资源的敏感操作。 这些操作只能由专家用户执行。

要重新草拟和删除已发布的资源，请执行以下操作：

1. 选择要重新草拟的资源。
1. 单击操 **[!UICONTROL Re-draft]** 作栏中的按钮。

   ![](assets/schema_extension_uc26.png)

1. Click **[!UICONTROL Ok]**.

   >[!CAUTION]
   >
   >这一行动是明确的：在发布修改时，资源的数据库表或列及其数据将被永久删除，这可能导致来自其他自定义资源的链接断开。 只有资源定义仍可用。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >如果您重新草拟了现成的配置文件（配置文件）资源的扩展，则还必须重新草拟您可能已定义的任何 **Test配置文件(seedMember)****** 扩展。 有关扩展配置文件资源的详细信息，请参 [阅此部分](../../developing/using/extending-the-profile-resource-with-a-new-field.md)。

1. 发布资源。 有关更详细的步骤，请参阅 [发布自定义资源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   然后，该资源进入“ **草稿** ”模式，其激活状态为 **[!UICONTROL Inactive]**。

1. 在模 **[!UICONTROL List]** 式中，检查要删除的资源，然后单击 ![](assets/delete_darkgrey-24px.png) 图 **[!UICONTROL Delete element]** 标。

   ![](assets/schema_extension_uc28.png)

您的资源将从数据模型中删除。

>[!NOTE]
>
>如果修改或删除了在事件上使用的自定义资源的字段，则相应的事件将自动取消发布。 See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

