---
title: 删除资源
seo-title: 删除资源
description: 删除资源
seo-description: '了解如何删除资源 '
page-status-flag: 从未激活
uuid: de27589-3fa5-412c-8e5a-a4976 de05715
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 0130733d-4e3f-40cd-b959-56381f2 c8 f44
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Deleting a resource{#deleting-a-resource}

To delete a resource, the resource in question must be a **[!UICONTROL Draft]**. The resource is in **[!UICONTROL Draft]** status if:

* 它刚刚创建并且尚未发布。
* 如果它已经发布，则必须重新起草资源。

>[!CAUTION]
>
>重新起草和删除自定义资源是会影响其他资源的敏感操作。这些操作只能由专家用户执行。

要重新起草和删除已发布的资源，请执行以下操作：

1. 选择要重新草稿的资源。
1. Click the **[!UICONTROL Re-draft]** button in the action bar.

   ![](assets/schema_extension_uc26.png)

1. Click **[!UICONTROL Ok]**.

   >[!CAUTION]
   >
   >此操作具有确定性：将在发布修改后永久删除资源的数据库表或列及其数据，这会导致来自其他自定义资源的断开链接。只有资源定义才可用。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >If you re-draft an extension of the out-of-the-box **Profiles (profile)** resource, you must also re-draft any **Test profile (seedMember)** extension you may have defined. For more on extending the profile resource, see [this section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. 发布资源。For more detailed steps, refer to [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   The resource then goes into **Draft** mode and its activation status is **[!UICONTROL Inactive]**.

1. **[!UICONTROL List]** 在模式中，选中要删除的资源，然后单击 ![](assets/delete_darkgrey-24px.png)**[!UICONTROL Delete element]** 图标。

   ![](assets/schema_extension_uc28.png)

您的资源将从数据模型中删除。

>[!NOTE]
>
>如果修改或删除在活动上使用的自定义资源字段，相应的活动将自动取消发布。See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

