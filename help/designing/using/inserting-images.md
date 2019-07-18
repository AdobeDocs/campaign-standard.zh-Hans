---
title: 插入图像
seo-title: 插入图像
description: 插入图像
seo-description: 了解如何向内容中添加图像。
page-status-flag: 从未激活
uuid: ac42b1d3-50ad-4323-b474-1e50 e468901 f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: 使用图像
discoiquuid: ee832ac-96e5-41e1-8390-6669ba30d4d8
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Inserting images{#inserting-images}

您可以在电子邮件和登录页面中插入图像。

根据您的配置，可以使用以下类型的图像：

* 本地图像
* Images shared from Adobe Experience Cloud - refer to [Working with Campaign and Assets Core Service](../../integrating/using/working-with-campaign-and-assets-core-service.md) / Assets On Demand
* Dynamic images from Adobe Target - refer to [Working with Campaign and Target](../../integrating/using/about-campaign-target-integration.md)

如果启用此功能，您可以使用Adobe Creative SDK修改图像。See [Modifying images with the Adobe Creative SDK](../../designing/using/modifying-images-with-the-adobe-creative-sdk.md).

>[!CAUTION]
>
>If you choose to add an image directly by editing the HTML version of the email, you must not call up **external files in a &lt;script&gt; tag** of the HTML page. 这些文件将不会导入到Adobe Campaign服务器上。

## Inserting images in an email {#inserting-images-in-an-email}

1. 添加结构组件。For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).
1. Inside this structure component, add an **[!UICONTROL Image]** content component.

   ![](assets/des_insert_images_1.png)

1. Click **[!UICONTROL Browse]**. 拖放图像或单击可从计算机中选择文件。

   ![](assets/des_insert_images_2.png)

1. 选择刚刚添加的内容组件。
1. 检查图像属性并根据需要调整图像属性。

   ![](assets/des_insert_images_3.png)

## Inserting images in a landing page {#inserting-images-in-a-landing-page}

1. 在登陆页面内容中，选择包含图像的块。
1. Select the **[!UICONTROL Insert]** button.

   ![](assets/des_insert_images_lp_1.png)

1. Choose **[!UICONTROL Local image]** from the contextual toolbar.

   ![](assets/des_insert_images_lp_2.png)

1. 选择一个文件。

   ![](assets/des_insert_images_lp_3.png)

1. 根据需要调整图像属性。

   ![](assets/des_insert_images_lp_4.png)

