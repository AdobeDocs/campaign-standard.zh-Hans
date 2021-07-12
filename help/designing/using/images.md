---
solution: Campaign Standard
product: campaign
title: 使用图像
description: 了解如何使用Email Designer管理电子邮件中的图像。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: 电子邮件设计
role: User
level: Intermediate
exl-id: b58a378d-18da-4c0f-b4e7-5d0a02aab4c2
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 3%

---

# 使用图像 {#images}

## 插入图像{#inserting-images}

您可以在电子邮件和登陆页面中插入图像。

根据您的配置，可以使用以下类型的图像：

* 本地图像
* 从Adobe Experience Cloud共享的图像 — 请参阅[使用Campaign和Assets核心服务](../../integrating/using/working-with-campaign-and-assets-core-service.md) / Assets On Demand
* 来自Adobe Target的动态图像 — 请参阅[使用Campaign和Target](../../integrating/using/about-campaign-target-integration.md)

>[!CAUTION]
>
>如果选择通过编辑HTML版本的电子邮件直接添加图像，则不得在HTML页面的&lt;script>标记&#x200B;**中调用**&#x200B;外部文件。 这些文件将不会导入到Adobe Campaign服务器中。

### 在电子邮件中插入图像 {#inserting-images-in-an-email}

1. 添加结构组件。 有关更多信息，请参阅[编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 在此结构组件中，添加&#x200B;**[!UICONTROL Image]**&#x200B;内容组件。

   ![](assets/des_insert_images_1.png)

1. 单击 **[!UICONTROL Browse]**。拖放图像或单击从计算机中选择文件。

   ![](assets/des_insert_images_2.png)

1. 选择之前添加的内容组件。
1. 检查图像属性，并根据需要进行调整。

   ![](assets/des_insert_images_3.png)

## 设置图像属性{#setting-up-image-properties}

选择包含图像的块时，面板中提供了以下属性：

* **启用** 个性化允许您自定义图像源。请参阅[个性化图像源](../../designing/using/personalization.md#personalizing-an-image-source)。
* **图像** 标题允许您为图像定义标题。
* **替换文本** （电子邮件）或 **标题** （登陆页面）允许您定义链接到图像的标题(与altHTML属 **** 性相对应)。
* 编辑电子邮件时，**Style**&#x200B;允许您指定图像大小、背景和边框。
* 编辑登陆页面时，**Dimension**&#x200B;允许您以像素为单位指定图像大小。

编辑器允许您使用&#x200B;**其格式与浏览器兼容的所有图像类型**。 要与编辑器兼容，**&quot;Flash&quot;类型的动画**&#x200B;必须按如下方式插入HTML页面：

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
