---
title: 在登陆页面中定义动态内容
seo-title: 在登陆页面中定义动态内容
description: 在登陆页面中定义动态内容
seo-description: 按照以下步骤，根据通过Adobe Campaign表达式编辑器定义的条件在登录页面中动态显示不同的内容。
page-status-flag: 从未激活
uuid: 64a8ddd2-8bb0-44ef-bae9-b6b77a84ca8b
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 设计
content-type: 参考
topic-tags: 定义条件内容
discoiquuid: 00e5ed81-d3d1-4211-8352-71805a7042c9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# 在登陆页面中定义动态内容{#defining-dynamic-content-in-a-landing-page}

要在登陆页面中定义动态内容，请使用痕迹导航或直接单击元素来选择块。

![](assets/dynamic_content_lp_1.png)

某些块（如图像）无法直接选择。 在这种情况下，请使用痕迹导航选择父块。 然后，您可以修改此父元素中包含的所有元素，包括图像。 该条件将应用于父块中的所有子元素。

痕迹导航显示在“管理块 [”部分](../../channels/using/managing-landing-page-structure-and-style.md) 。

在登录页面中定义动态内容的后续步骤与电子邮件的后续步骤类似。 请参 [阅此部分](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

>[!NOTE]
>
>如果变体元素以红色列出，则表示尚未定义表达式。

## 在登陆页面中预览动态内容 {#previewing-dynamic-content-in-a-landing-page}

您可以在块的不同动态内容之间导航。 为此，请执行以下操作：

1. 选择块。

   箭头显示在图像的右侧和左侧。

1. 单击右箭头浏览可用的动态内容。

   ![](assets/dynamic_content_lp_2.png)

   每侧的箭头会根据您是否已到达最后一个或第一个可用的动态内容而变暗。

   ![](assets/dynamic_content_lp_3.png)

1. 要删除应用于某个块的所有条件，请选择该块，然后单击该 **[!UICONTROL Disable dynamic content]** 图标。
1. 选择要保留的动态内容。

   ![](assets/dynamic_content_lp_5.png)

在调色板中：

* 输入了表达式的内容不再以红色列出，而是以灰色显示。
* 当前选择的内容以蓝色显示。

![](assets/dynamic_content_lp_4.png)

