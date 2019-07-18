---
title: 内容设计最佳实践
seo-title: 内容设计最佳实践
description: 内容设计最佳实践
seo-description: 阅读这些准则以确保编辑器的最佳操作。
page-status-flag: 从未激活
uuid: ad74f49d-999f-4140-89b0-d1 ead8642 d89
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: 关于内容设计
discoiquuid: d33f5f14-a4 e3-4327-bd16-eb3135 a32076
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Content design best practices{#content-design-best-practices}

为了确保编辑器的最佳操作，建议遵循以下准则：

* 不支持SCSS样式表。如果导入包含HTML内容的ZIP文件，请使用常规CSS。
* When editing **email content**:

   在发送消息之前预览消息。Adobe Campaign提供了一种使用Litmus测试电子邮件渲染的方法。For more on this, see [Email rendering](../../sending/using/email-rendering.md).

* When editing **landing page content**:

   * 在Adobe Campaign中导入HTML页面模板之前，请确保模板打开并在各种浏览器中正确显示。
   * 如果HTML页面包含JavaScript脚本，则需要执行这些脚本，而不会出现编辑器之外的错误。通常，避免使用消息内容中的脚本来确保电子邮件客户端正确处理它。
   * When building a template, we recommend adding a **'type'** attribute to  tags. 此信息将由编辑器处理，并帮助用户在配置Web应用程序时将数据库字段链接到表单字段。

      模板中HTML代码的示例：

      ```
      <input id="email" type="email" name="email"/>
      ```

      The official list of 'type' attributes is available at the following address: [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)

More design and general best practices regarding messages are presented in the following Adobe Campaign step-by-step guide: [Delivery best practices with Adobe Campaign](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).
