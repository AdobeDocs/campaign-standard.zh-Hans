---
title: 关于登陆页面内容设计
seo-title: 关于登陆页面内容设计
description: 关于登陆页面内容设计
seo-description: 了解登陆页面内容编辑器的特性。
page-status-flag: 从未激活
uuid: 8b230690-8a63-44da-b4ed-8e9d8fd84262
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 设计
content-type: 参考
topic-tags: 编辑——登陆——页面内容
discoiquuid: 212720d2-5d57-4e7a-bb72-10512050e78c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---

# 关于登陆页面内容设计{#about-landing-page-content-design}

使用标准内容编辑器在Adobe Campaign中创建和修改登陆页面的内容。

本节介绍登陆页面内容编辑器的特性：

* [登陆页面内容编辑器界面](../../channels/using/landing-page-content-editor-interface.md)
* [管理登陆页面结构和样式](../../channels/using/managing-landing-page-structure-and-style.md)
* [更改登陆页面表单数据属性](../../channels/using/changing-a-landing-page-form-data-properties.md)

要进一步了解一个或多个营销活动常见的操作，请参阅以下部分：

* 有关个性化登录页面内容的更多信息，请参 [阅插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)[和添加内容块](../../designing/using/personalization.md#adding-a-content-block)。
* 有关在登陆页面中定义动态内容的详细信息，请 [参阅在登陆页面中定义动态内容](../../channels/using/defining-dynamic-content-in-a-landing-page.md)。
* 有关在登录页面中插入链接的详细信息，请参 [阅插入链接](../../designing/using/links.md#inserting-a-link)。
* 有关在登录页面中插入图像的详细信息，请参阅 [插入图像](../../designing/using/images.md)。

另请查看内 [容设计的一般最佳实践](../../designing/using/overview.md#content-design-best-practices)。

>[!NOTE]
>
>如果您的实例是在Adobe Campaign Standard 19.0版本之前安装的，您仍可以访问旧版电子邮件内容编辑器。 界面、使用原则和配置基本上与登录页面的下面所述相同。 但是，在旧版电子邮件内容编辑器中可能不提供或维护所有功能，该编辑器从19.0版本开始已弃用。 要通过具有扩展功能的拖放界面快速编辑电子邮件内容，请使用电子邮 [件设计器](../../designing/using/overview.md)。

## 登录页面设计最佳实践 {#landing-pages-best-practices-design}

* 编辑登陆 **页面内容时**:

   * 在Adobe Campaign中导入HTML页面模板之前，请确保在各种浏览器中正确打开和显示该模板。
   * 如果HTML页包含JavaScript脚本，则需要在编辑器外执行这些脚本时不会出错。 通常，请避免在邮件内容中使用脚本，以确保电子邮件客户端正确处理该脚本。
   * 在构建模板时，我们建议向标 **记添加“type** ”属性。 此信息将由编辑器处理，并帮助用户在配置Web应用程序时将数据库字段链接到表单字段。
   模板中的HTML代码示例：

   ```
   <input id="email" type="email" name="email"/>
   ```

   “类型”属性的正式列表位于以下地址： [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)