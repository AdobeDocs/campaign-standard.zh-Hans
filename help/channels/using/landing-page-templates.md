---
title: 登陆页面模板
seo-title: 登陆页面模板
description: 登陆页面模板
seo-description: 了解有关登录页面模板的更多信息。
page-status-flag: 从未激活
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: 勒梅特
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 登陆页面
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage，向导；landingPage，概述；landingPage，主页
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9cdfafad7a2ac2db59b037962a84aa03568a55e6

---


# 关于登陆页面模板 {#landing-page-templates}

Campaign附带一组内置登录页面模板：

* **[!UICONTROL Acquisition]**:这是登录页面的默认模板，它允许您捕获和更新Campaign数据库中的数据。
* **[!UICONTROL Subscription]**:此模板应用于为服务提供订阅。
* **[!UICONTROL Unsubscription]**:此模板可从发送给订阅者的电子邮件链接到服务，以允许他们取消订阅此服务。
* **[!UICONTROL Blacklist]**:当Campaign不再希望联系配置文件时，应使用此模板。 有关黑名单的更多信息， [请参阅Campaign中的“关于选择加入和选择退出”](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

默认情况下，创建新登录页面时会建议使用这些模板。

![](assets/lp_creation_1.png)

要访问登陆页面模板，请单击左上角的Adobe Campaign徽标，然后选择 **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Landing page templates]**。

>[!NOTE]
>
>Adobe建议通过复制内置模板来创建您自己的模板。 某些参数只能在登陆页面模板中设置，不能直接在登陆页面中修改。

在构建模板时，我们建议向标 **记添加“type** ”属性。 此信息将由编辑器处理，并帮助用户在配置Web应用程序时将数据库字段链接到表单字段。

模板中的HTML代码示例：

```
<input id="email" type="email" name="email"/>
```

“类型”属性的正式列表位于以下地址： [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)