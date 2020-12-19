---
solution: Campaign Standard
product: campaign
title: 将订阅扩展到应用程序资源
description: null
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 25%

---


# 将订阅扩展到应用程序资源{#extending-the-subscriptions-to-an-application-resource}

在 Adobe Campaign 中，由移动设备发出的移动配置文件属性数据存储在 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 资源中，利用该资源，您可定义要从应用程序的订阅者那里收集的数据。有关自定义资源的详细信息，请参阅[此页](../../developing/using/key-steps-to-add-a-resource.md)。

此资源可以扩展为收集您打算从移动设备发送到Adobe Campaign的数据。

1. 从高级菜单中，通过 Adobe Campaign 徽标，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]**，然后选择 **[!UICONTROL Custom resources]**。
1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;并选择&#x200B;**[!UICONTROL Extend an existing resource]**&#x200B;选项。
1. 选择&#x200B;**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**&#x200B;资源，然后单击&#x200B;**[!UICONTROL Create]**。

   ![](assets/in_app_personal_data_4.png)

1. 在&#x200B;**[!UICONTROL Data structure]**&#x200B;选项卡的&#x200B;**[!UICONTROL Fields]**&#x200B;类别中，通过单击&#x200B;**[!UICONTROL Add field]**&#x200B;按钮定义要从移动应用程序检索的客户数据。

   >[!NOTE]
   >
   >如果要管理多个移动应用程序，则必须列出所有应用程序使用的所有字段。 iOS或Android收集PII调用定义每个应用程序捕获的字段。

   ![](assets/in_app_personal_data.png)

1. 将&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL ID]**&#x200B;添加到新字段。 选择字段的&#x200B;**[!UICONTROL Type]**。

   ![](assets/schema_extension_uc9.png)

1. 在&#x200B;**[!UICONTROL Link to profiles]**&#x200B;类别中，配置用于将用户档案从Adobe Campaign库链接到应用程序订阅者（如电子邮件）的合并关键项。

   请注意，对于应用程序内消息，您只能为所有移动应用程序定义一个合并关键项。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** 并发布您的自定义资源。有关自定义资源发布的详细信息，请参阅此[页面](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

