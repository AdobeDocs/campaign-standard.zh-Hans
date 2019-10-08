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
source-git-commit: 0068746b0b90b85edfb2c93eb08a82e1adc2fca8

---


# 关于登陆页面{#about-landing-pages}

Campaign附带登录页面，这些Web表单可用于捕获受众信息、提供服务订阅、显示数据和扩展数据库。 登录页面还可用于获取或更新现有配置文件。

有关设置登陆页面所需步骤的详细信息，请参阅 [此部分](../../channels/using/main-steps-to-set-up-a-landing-page.md)

**相关主题：**

* [创建登陆页面教程视频](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-edit-landing-page-feature-video-use.html)
* [使用登陆页面订阅服务](../../audiences/using/creating-a-service.md)

## 登陆页面生命周期 {#landing-pages-life-cycle}

登录页面的完整生命周期如下：

1. 创建：设计和设置登录页面的内容。
1. 测试：在测试配置文件上模拟登陆页面执行。
1. 发布：发布登陆页面以将其实时推送。
1. 到期或取消发布：手动取消发布或等待登陆页面过期，则不再可用。

![](assets/lp_livecycle.png)

创建和发布后，您可以通过网站或将登陆页面的直 [接链接插入到电子邮件中，从而访问登陆页面](../../designing/using/links.md#inserting-a-link)。

## 登录页面限制{#landing-page-limitations}

以下部分列出了在开始设置登录页面之前您应了解的限制。

**编写和更新数据**

* 登录页面仅限于 **[!UICONTROL Profile]** 和 **[!UICONTROL Subscription]** 资源。 可以保存记录并从 **[!UICONTROL Profile]** 订阅／取消订阅更新到 **[!UICONTROL Service]**。
要了解有关资源配置的更多信息，请 [参阅配置资源的数据结构](../../developing/using/configuring-the-resource-s-data-structure.md)。

>[!CAUTION]
>
>登陆页面无法显示或更新除和之外的任何其他资源中的 **[!UICONTROL Profile]** 数据 **[!UICONTROL Subscription]**。

**预加载**

* 登陆页面无法自动显示记录列表，它无法列出已订阅配置文件的服务。 有关服务的详细信息，请参阅本 [页](../../audiences/using/creating-a-service.md)。

* 包含预填表单的登录页面（数据与页面预加载）只能从Adobe Campaign电子邮件中访问。 无法从网站页面访问此类表单。

**调解**

* 协调行为如下：一旦找到匹配项，协调进程就会停止。 这意味着，只能对一个配置文件记录进行协调，而不能对多个记录（如果有重复记录）进行协调。

例如，您希望将以下客户获取登录页发送到您的配置文件，以便使用配置文件的移动号码更新您的Campaign数据库。

![](assets/landing_page_limitation_1.png)

如果您的其中一个配置文件用新信息填充了登录页面，但已有重复的配置文件，则将更新具有最早创建日期的匹配配置文件，因为仅根据配置文件的创建日期对配置文件进行优先级排序。

此处仅更新了第一个配置文件，因为它是最旧的条目。

![](assets/landing_page_limitation_2.png)

**测试登陆页面**

* 登录页面仅对配置文件有效，而不对测试配置文件有效，这意味着登录页面不能作为电子邮件证明的一部分进行测试。
