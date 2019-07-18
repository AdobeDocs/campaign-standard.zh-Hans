---
title: 将订阅扩展到应用程序资源
seo-title: 将订阅扩展到应用程序资源
description: 将订阅扩展到应用程序资源
seo-description: null
page-status-flag: 从未激活
uuid: 8879b427-b31 b-4311-bf54-258a91 b1 fb78
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: 使用案例—扩展资源
discoiquuid: 59fa74e-86fc-42d3-90da-f48580 b5 ec13
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Extending the subscriptions to an application resource{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers. For more information on custom resources, refer to this [page](../../developing/using/key-steps-of-adding-a-resource.md).

此资源可扩展以收集您希望从移动设备发送到Adobe Campaign的数据。

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, then **[!UICONTROL Custom resources]**.
1. Click **[!UICONTROL Create]** and choose the **[!UICONTROL Extend an existing resource]** option.
1. Select the **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource and click **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. In the **[!UICONTROL Fields]** category of the **[!UICONTROL Data structure]** tab, define the customer data that you want to retrieve from your mobile application by clicking the **[!UICONTROL Add field]** button.

   >[!NOTE]
   >
   >如果您正在管理多个手机应用程序，则必须列出所有应用程序使用的字段。iOS或Android收集PII调用定义每个应用程序捕获的字段。

   ![](assets/in_app_personal_data.png)

1. Add a **[!UICONTROL Label]** and an **[!UICONTROL ID]** to your new field. Select your field's **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. In the **[!UICONTROL Link to profiles]** category, configure the reconciliation key used to link the profiles from the Adobe Campaign database to your applications' subscribers, such as the email.

   请注意，对于应用程序内消息，您只能为所有移动应用程序定义一个对帐密钥。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** 并发布自定义资源。For more information on custom resource publication, refer to this [page](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

