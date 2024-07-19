---
title: 删除资源
description: 了解如何删除资源
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: 4ddfdbcc-a154-4c10-a97e-73ad888d1f1f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 14%

---

# 删除资源{#deleting-a-resource}

要删除资源，相关资源必须是&#x200B;**[!UICONTROL Draft]**。 在以下情况下，资源处于&#x200B;**[!UICONTROL Draft]**&#x200B;状态：

* 它刚刚创建，尚未发布。
* 如果资源已经发布，则必须重新起草。

>[!IMPORTANT]
>
>重新起草和删除自定义资源是敏感操作，可能会影响其他资源。 这些操作只能由专家用户执行。

要重新草稿并删除已发布的资源，请执行以下操作：

1. 选择要重新起草的资源。
1. 单击操作栏中的 **[!UICONTROL Re-draft]** 按钮。

   ![](assets/schema_extension_uc26.png)

1. 单击 **[!UICONTROL Ok]**。

   >[!IMPORTANT]
   >
   >此操作是确定的：发布修改时，资源的数据库表或列及其数据将被永久删除，这可能会导致其他自定义资源的链接断开。 只有资源定义将保持可用。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >如果重新起草现成的&#x200B;**配置文件（配置文件）**&#x200B;资源的扩展，则还必须重新起草您可能已定义的任何&#x200B;**测试配置文件(seedMember)**&#x200B;扩展。 有关扩展用户档案资源的详细信息，请参阅[此部分](../../developing/using/extending-the-profile-resource-with-a-new-field.md)。

1. Publish资源。 有关更多详细步骤，请参阅[发布自定义资源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   然后，资源进入&#x200B;**草稿**&#x200B;模式，其激活状态为&#x200B;**[!UICONTROL Inactive]**。

1. 在&#x200B;**[!UICONTROL List]**&#x200B;模式下，检查要删除的资源，然后单击![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]**&#x200B;图标。

   ![](assets/schema_extension_uc28.png)

您的资源将从数据模型中删除。

>[!NOTE]
>
>如果修改或删除了用于事件的自定义资源字段，将自动取消发布对应的事件。请参阅[取消发布事务性事件](../../channels/using/publishing-transactional-event.md#unpublishing-an-event)。
