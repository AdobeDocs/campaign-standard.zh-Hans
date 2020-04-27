---
title: 登陆页模板
description: 进一步了解登陆页模板。
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
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# 关于登陆页面模板 {#landing-page-templates}

活动附带一组内置的登陆页模板：

* **[!UICONTROL Acquisition]**:这是登陆页的默认模板，它允许您捕获和更新活动数据库中的数据。
* **[!UICONTROL Subscription]**:此模板应用于将订阅优惠到服务。
* **[!UICONTROL Unsubscription]**:此模板可从发送给订阅者的电子邮件链接到服务，以允许他们取消订阅此服务。
* **[!UICONTROL Blacklist]**:当用户档案不再希望通过活动联系时，应使用此模板。 有关黑名单的详细信 [息，请参阅关于选择加入和选择退出活动](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

默认情况下，创建新登陆页时会建议使用这些模板。

![](assets/lp_creation_1.png)

要访问登陆页模板，请单击左上角的Adobe Campaign标志，然后选择 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**。

>[!NOTE]
>
>Adobe建议通过复制内置模板来创建您自己的模板。 某些参数只能在登陆页模板中设置，不能直接在登陆页中修改。

在构建模板时，我们建议向标 **记添加“type** ”属性。 此信息将由编辑器处理，并帮助用户在配置Web应用程序时将数据库字段链接到表单字段。

模板中的HTML代码示例：

```
<input id="email" type="email" name="email"/>
```

“类型”属性的官方列表位于以下地址： [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)