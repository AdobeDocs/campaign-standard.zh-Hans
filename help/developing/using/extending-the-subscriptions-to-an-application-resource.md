---
title: 将订阅扩展到应用程序资源
description: null
page-status-flag: never-activated
uuid: 8879b427-b31b-4311-bf54-258a91b1fb78
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
discoiquuid: 59faa74e-86fc-42d3-90da-f48580b5ec13
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# 将订阅扩展到应用程序资源{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers. 有关自定义资源的详细信息，请参 [阅本页](../../developing/using/key-steps-to-add-a-resource.md)。

此资源可扩展以收集您打算从移动设备发送到Adobe Campaign的数据。

1. 从高级菜单中，通过Adobe Campaign徽标，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]**，然后 **[!UICONTROL Custom resources]**。
1. 单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Extend an existing resource]** 选项。
1. 选择资 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 源并单击 **[!UICONTROL Create]**。

   ![](assets/in_app_personal_data_4.png)

1. 在选项 **[!UICONTROL Fields]** 卡的类别中， **[!UICONTROL Data structure]** 通过单击按钮定义要从移动应用程序检索的客户数 **[!UICONTROL Add field]** 据。

   >[!NOTE]
   >
   >如果您管理多个移动应用程序，则必须列出所有应用程序使用的所有字段。 iOS或Android收集PII调用定义每个应用程序捕获的字段。

   ![](assets/in_app_personal_data.png)

1. 向新字 **[!UICONTROL Label]** 段添 **[!UICONTROL ID]** 加和。 选择字段的 **[!UICONTROL Type]**。

   ![](assets/schema_extension_uc9.png)

1. 在类别 **[!UICONTROL Link to profiles]** 中，配置用于将用户档案从Adobe Campaign数据库链接到应用程序订阅者（如电子邮件）的合并关键项。

   请注意，对于应用程序内消息，您只能为所有移动应用程序定义一个合并关键项。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** 并发布自定义资源。 有关自定义资源发布的详细信息，请参阅此 [页](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

