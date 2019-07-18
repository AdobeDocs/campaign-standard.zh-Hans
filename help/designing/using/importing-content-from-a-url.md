---
title: 从URL导入内容
seo-title: 从URL导入内容
description: 从URL导入内容
seo-description: 了解如何在创建电子邮件时从现有URL加载内容。
page-status-flag: 从未激活
uuid: db6c20f-7004-4fb8-add9-362eab3 d2795
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: 加载内容
discoiquuid: 738b7c8a-88eb-491c-a4 d0-078b0959 b973
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Importing content from a URL{#importing-content-from-a-url}

在从URL导入内容之前，请确保其遵循以下要求：

* 内容需要通过此URL公开提供。
* For security reasons, only URLs beginning with **[!UICONTROL https]** are allowed.
* 确保所有资源(图像、CSS)均在绝对链接和HTTPS中设置。否则，发送电子邮件后，将在没有资源的情况下显示镜像页面。以下是绝对链接定义的示例：

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>从URL加载内容仅可用于电子邮件渠道。

要检索现有内容表单URL，请按照以下步骤操作：

1. From the Email Designer home page, select the **[!UICONTROL Import from URL]** button.

   ![](assets/email_designer_importfromurl.png)

1. 定义要从中检索内容的URL。
1. Click **[!UICONTROL Confirm]**.

**相关主题：**

[从URL](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#Workingwithexistingcontent) 视频导入内容

## Retrieving content from a URL automatically at preparation time {#retrieving-content-from-a-url-automatically-at-preparation-time}

在消息准备过程中从URL导入内容允许您每次准备电子邮件时检索最新的HTML内容。这样，在发送时，重复电子邮件的内容始终是最新的。此功能还允许您创建在特定日期安排的消息，即使内容尚未准备就绪。

要在准备时检索内容，请按照以下步骤操作：

1. Select the **[!UICONTROL Content imported during preparation]** option.

   ![](assets/email_designer_importfromurl2.png)

1. URL内容在编辑器中显示为只读内容。

   >[!CAUTION]
   >
   >在此步骤中，不应考虑内容编辑器中的HTML显示。将在准备阶段检索它。

1. To preview the URL content that has been retrieved, open the message once it is created then click the **[!UICONTROL Preview]** button.

可以个性化从中检索内容的远程URL。要执行此操作，请执行以下步骤：

1. Click the email label on top of the screen to acces the Email Designer **[!UICONTROL Properties]** tab.
1. Find the **[!UICONTROL Remote URL]** field.

   ![](assets/email_designer_importfromurl4.png)

1. 插入所需的个性化字段、内容块或动态文本。

   **[!UICONTROL Current date - YYYYMMDD]** 例如，内容块使您能够插入日期。

   >[!NOTE]
   >
   >The available personalization fields are linked to **Delivery** attributes only (email creation date, status, campaign label...).

