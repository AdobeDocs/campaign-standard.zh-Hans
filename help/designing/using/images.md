---
title: 使用图像
description: 了解如何使用电子邮件设计器管理电子邮件中的图像。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 881c89272884c6340e170ab13e84612a5af19acd

---


# 使用图像 {#images}

## 插入图像{#inserting-images}

您可以在电子邮件和登陆页面中插入图像。

根据您的配置，可以使用以下类型的图像：

* 本地图像
* 从Adobe Experience cloud共享的图像——请参阅使 [用Campaign和Assets核心服务](../../integrating/using/working-with-campaign-and-assets-core-service.md) /资产（按需）
* Adobe Target中的动态图像——请参阅使 [用Campaign和Target](../../integrating/using/about-campaign-target-integration.md)

>[!CAUTION]
>
>如果选择通过编辑HTML版本的电子邮件直接添加图像，则不得在HTML页的&lt;script **>标签中调用外部文件** 。 这些文件不会导入到Adobe Campaign服务器上。

### 在电子邮件中插入图像 {#inserting-images-in-an-email}

1. 添加结构组件。 有关此内容的详细信息，请参 [阅编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 在此结构组件中，添加一个内 **[!UICONTROL Image]** 容组件。

   ![](assets/des_insert_images_1.png)

1. 单击 **[!UICONTROL Browse]**. 拖放图像或单击以从您的计算机中选择文件。

   ![](assets/des_insert_images_2.png)

1. 选择刚添加的内容组件。
1. 检查图像属性，并根据需要调整它们。

   ![](assets/des_insert_images_3.png)

## 设置图像属性{#setting-up-image-properties}

当您选择包含图像的块时，调色板中会提供以下属性：

* **启用个性化** ，您便可以自定义图像源。 请参 [阅个性化图像源](../../designing/using/personalization.md#personalizing-an-image-source)。
* **图像标题** ，允许您为图像定义标题。
* **替代文本** （电子邮件）或 **题注（登录页面）允许您定义链接到图像的题注(与** alt **** HTML属性相对应)。
* 编辑电子邮件时， **Style** 允许您指定图像大小、背景和边框。
* 编辑登陆页面时， **Dimensions** 允许您指定图像大小（以像素为单位）。

编辑器允许您处理其格式 **与浏览器兼容的** 所有图像类型。 要与编辑器兼容，必 **须按如下方式在HTML页面中插入** “Flash”类型的动画：

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

<!--
## Modifying images with the Adobe Creative SDK{#modifying-images-with-the-adobe-creative-sdk}

You can edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor when editing emails or landing pages.

The image editor offers a powerful, full-featured image editing UI component that allows you to edit images and apply effects and frames, original high-quality stickers, beautiful overlays, fun features like tilt shift and color splash, pro-level adjustments and more.

To modify an image with the Adobe Creative SDK:

1. Select the image.
1. In the toolbar, click the Creative Cloud icon.

   ![](assets/des_creative_sdk_icon.png)

1. Select the tool you want to use through the icons on the top of the window to modify the image.

   ![](assets/email_designer_ccsdktoolbar.png)

1. Click **[!UICONTROL Save]** when modifications are done. The updated image is saved on Adobe Campaign server and ready to be used.

>[!NOTE]
>
>Tools offered in the image editor cannot be customized.
-->