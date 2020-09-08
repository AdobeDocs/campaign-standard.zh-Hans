---
title: 登陆页面模板
description: 进一步了解登陆页面模板。
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 94%

---


# 关于登陆页面模板{#landing-page-templates}

Campaign 附带一系列内置登陆页面模板：

* **[!UICONTROL Acquisition]**：这是登陆页面的默认模板，用于在 Campaign 数据库中捕获和更新数据。
* **[!UICONTROL Subscription]**：此模板用于提供服务订阅。
* **[!UICONTROL Unsubscription]**：此模板可从发送给订阅者的电子邮件链接到服务，以便他们退订此服务。
* **[!UICONTROL Denylist]**：当某个用户档案不再希望 Campaign 与其联系时，应使用此模板。For more about denylist management, refer to [About opt-in and opt-out in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

默认情况下，创建新登陆页面时会提供这些模板。

![](assets/lp_creation_1.png)

要访问登陆页面模板，请单击左上角的 Adobe Campaign 徽标，然后选择 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**。

>[!NOTE]
>
>Adobe 建议通过复制内置模板来创建属于自己的模板。某些参数只能在登陆页面模板中设置，不能直接在登陆页面中修改。

在构建模板时，我们建议向标记添加 **&#39;type’** 属性。配置 Web 应用程序时，编辑器将处理此信息，并帮助用户将数据库字段链接到表单字段。

模板中的 HTML 代码示例：

```
<input id="email" type="email" name="email"/>
```

以下地址提供了“type”属性的官方列表：[https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)