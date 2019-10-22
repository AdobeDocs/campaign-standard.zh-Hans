---
title: 管理电子邮件中的图像
seo-title: 管理电子邮件中的图像
description: 管理电子邮件中的图像
seo-description: 了解如何使用电子邮件设计器管理电子邮件中的图像。
page-status-flag: 从未激活
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 设计
content-type: 参考
topic-tags: 编辑——电子邮件——内容
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c43a258734f3344fad8c9cbd5bd5774d7f37b4f6

---


# 图像 {#images}

## 插入图像{#inserting-images}

您可以在电子邮件和登陆页面中插入图像。

根据您的配置，可以使用以下类型的图像：

* 本地图像
* 从Adobe Experience cloud共享的图像——请参阅使 [用Campaign和Assets核心服务](../../integrating/using/working-with-campaign-and-assets-core-service.md) /资产（按需）
* Adobe Target中的动态图像——请参阅使 [用Campaign和Target](../../integrating/using/about-campaign-target-integration.md)

如果启用，您可以使用Adobe Creative SDK修改图像。 请参 [阅使用Adobe Creative SDK修改图像](images.md#modifying-images-with-the-adobe-creative-sdk)。

>[!CAUTION]
>
>如果选择通过编辑HTML版本的电子邮件直接添加图像，则不得在HTML页的&lt;script **&gt;标签中调用外部文件** 。 这些文件不会导入到Adobe Campaign服务器上。

### 在电子邮件中插入图像 {#inserting-images-in-an-email}

1. 添加结构组件。 有关此内容的详细信息，请参 [阅编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 在此结构组件中，添加一个内 **[!UICONTROL Image]** 容组件。

   ![](assets/des_insert_images_1.png)

1. Click **[!UICONTROL Browse]**. 拖放图像或单击以从您的计算机中选择文件。

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

## 使用Adobe Creative SDK修改图像{#modifying-images-with-the-adobe-creative-sdk}

您可以编辑图像，并使用Adobe Creative SDK提供的一整套功能在编辑电子邮件或登录页面时直接在内容编辑器中增强图像。

图像编辑器提供功能强大、功能齐备的图像编辑UI组件，它允许您编辑图像并应用效果和帧、原始的高质量贴纸、美观的叠加、倾斜偏移和颜色初始化等有趣功能、专业级调整等。

要使用Adobe Creative SDK修改图像，请执行以下操作：

1. 选择图像。
1. 在工具栏中，单击Creative cloud图标。

   ![](assets/des_creative_sdk_icon.png)

1. 通过窗口顶部的图标选择要使用的工具以修改图像。

   ![](assets/email_designer_ccsdktoolbar.png)

1. 完成 **[!UICONTROL Save]** 修改后单击。 更新后的图像将保存在Adobe Campaign服务器上并可供使用。

>[!NOTE]
无法自定义图像编辑器中提供的工具。
