---
title: 设置图像属性
seo-title: 设置图像属性
description: 设置图像属性
seo-description: 了解如何管理内容中包含的图像属性。
page-status-flag: 从未激活
uuid: 1a439105-d9 aa-4b30-a00 d-bcf731 a04 e08
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: 使用图像
discoiquuid: 80c9c1a5-6050-443d-810a-6bb755d39dca
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Setting up image properties{#setting-up-image-properties}

当您选择包含图像的块时，调色板中会提供以下属性：

* **启用个性化** 功能可使您自定义图像源。See [Personalizing an image source](../../designing/using/personalizing-an-image-source.md).
* **“图像标题** ”允许您定义图像标题。
* **替换文本** (电子邮件)或 **题注** (登陆页面)允许您定义链接到图像的题注(与 **alt** HTML属性对应)。
* When editing an email, **Style** lets you specify the image size, background, and border.
* When editing a landing page, **Dimensions** lets you specify the image size in pixels.

The editor allows you to work with **all image types** whose formats are compatible with browsers. To be compatible with the editor, the **"Flash" type animations** have to be inserted in an HTML page as follows:

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

