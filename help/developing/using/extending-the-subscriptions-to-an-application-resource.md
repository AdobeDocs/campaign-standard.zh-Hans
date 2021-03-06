---
title: 将订阅扩展到应用程序资源
description: 了解如何扩展对应用程序资源的订阅
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ac9c556d-c0f6-4b33-8855-1f5f669c148f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 24%

---

# 将订阅扩展到应用程序资源{#extending-the-subscriptions-to-an-application-resource}

在 Adobe Campaign 中，由移动设备发出的移动配置文件属性数据存储在 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 资源中，利用该资源，您可定义要从应用程序的订阅者那里收集的数据。有关自定义资源的更多信息，请参阅 [本页](../../developing/using/key-steps-to-add-a-resource.md).

可扩展此资源以收集您打算从移动设备发送到Adobe Campaign的数据。

1. 从高级菜单中，通过 Adobe Campaign 徽标，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]**，然后选择 **[!UICONTROL Custom resources]**。
1. 单击 **[!UICONTROL Create]** 然后选择 **[!UICONTROL Extend an existing resource]** 选项。
1. 选择 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 资源，单击 **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. 在 **[!UICONTROL Fields]** 类别 **[!UICONTROL Data structure]** ，可通过单击 **[!UICONTROL Add field]** 按钮。

   >[!NOTE]
   >
   >如果您管理多个移动设备应用程序，则必须列出所有应用程序使用的所有字段。 iOS或Android收集PII调用定义每个应用程序捕获的字段。

   ![](assets/in_app_personal_data.png)

1. 添加 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 到您的新字段。 选择字段的 **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. 在 **[!UICONTROL Link to profiles]** 类别中，配置用于将用户档案从Adobe Campaign数据库链接到应用程序订阅者（如电子邮件）的协调键值。

   请注意，对于应用程序内消息，您只能为所有移动应用程序定义一个协调键值。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** 并发布自定义资源。 有关自定义资源发布的更多信息，请参阅 [页面](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
