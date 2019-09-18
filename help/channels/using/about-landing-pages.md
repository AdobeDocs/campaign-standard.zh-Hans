---
title: 关于登陆页面
seo-title: 关于登陆页面
description: 关于登陆页面
seo-description: 发现Campaign登陆页面及其生命周期。
page-status-flag: 从未激活
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 登陆页面
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage，向导；landingPage，概述；landingPage，主页
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# 关于登陆页面{#about-landing-pages}

Campaign附带登录页面，这些Web表单可用于捕获受众信息、提供服务订阅、显示数据和扩展数据库。 登录页面还可用于获取或更新现有配置文件。

>[!CAUTION]
>
>登录页面只能用于更新配置文件。

Campaign附带一组内置登录页面模板：

* **[!UICONTROL Acquisition]**:这是登录页面的默认模板，它允许您捕获和更新Campaign数据库中的数据。
* **[!UICONTROL Subscription]**:此模板应用于为服务提供订阅。
* **[!UICONTROL Unsubscription]**:此模板可从发送给订阅者的电子邮件链接到服务，以允许他们取消订阅此服务。
* **[!UICONTROL Blacklist]**:当Campaign不再希望联系配置文件时，应使用此模板。 有关黑名单的更多信息， [请参阅Campaign中的“关于选择加入和选择退出”](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

默认情况下，创建新登录页面时会建议使用这些模板。

![](assets/lp_creation_1.png)

Adobe建议通过复制内置模板来创建您自己的模板。 某些参数只能在登陆页面模板中设置，不能直接在登陆页面中修改。

>[!NOTE]
>
>要访问登陆页面模板，请单击左上角的Adobe Campaign徽标，然后选择 **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Landing page templates]**。

登录页面的完整生命周期如下：

1. 创建：设计和设置登录页面的内容。
1. 测试：在测试配置文件上模拟登陆页面执行。
1. 发布：发布登陆页面以将其实时推送。
1. 到期或取消发布：手动取消发布或等待登陆页面过期，则不再可用。

![](assets/lp_livecycle.png)

创建和发布后，您可以通过网站或将登陆页面的直 [接链接插入到电子邮件中，从而访问登陆页面](../../designing/using/links.md#inserting-a-link)。

**相关主题：**

* [创建登陆页面视频](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-edit-landing-page-feature-video-use.html)
* [使用登陆页面订阅服务](../../audiences/using/creating-a-service.md)