---
title: 定义可见性条件
seo-title: 定义可见性条件
description: 定义可见性条件
seo-description: 使网页元素仅在某个条件受到尊重时才可见。
page-status-flag: 从未激活
uuid: 22005ba-ef09-4790-b2 f0-30ed74 cfa32 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: 定义条件内容
discoiquuid: c12125a7-a1 cf-4bc1-a138-57ff74974024
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Defining a visibility condition{#defining-a-visibility-condition}

您可以在任何元素上指定可见性条件。只有在条件被尊重时，才可见。

To add a visibility condition, select a block and enter the condition to be respected in the **[!UICONTROL Visibility condition]** field of its settings.

![](assets/delivery_content_5.png)

此选项仅适用于以下元素：地址、BLOCTUCTION、CENTER、DIR、DIV、DL、FiIELDSet、FORM、H1、H2、H3、H4、H5、H6、NOSCRL、OL、P、PRE、UL、TR、TD。

The expression editor is presented in the [Advanced expression editing](../../automating/using/editing-queries.md#about-query-editor) section.

These conditions adopt the XTK expression syntax (e.g. **context.profile.email !=''** or **context.profile.status='0'**). 默认情况下，所有字段都可见。

>[!NOTE]
>
>不能为已经包含动态内容的子元素或已经构成动态内容的块定义条件。不可见的动态块(如下拉列表)无法进行编辑。

