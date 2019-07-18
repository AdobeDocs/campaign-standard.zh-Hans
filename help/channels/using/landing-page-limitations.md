---
title: 登陆页面限制
seo-title: 登陆页面限制
description: 登陆页面限制
seo-description: 发现营销活动登陆页面及其生命周期。
page-status-flag: 从未激活
uuid: b316bf47-7d98-46fa-ab4 f-67ff50 de8095
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 登录页面
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152 e14286
context-tags: LandingPage，向导；LandingPage，概述；LandingPage，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0b2377a2bfdb8745ec9c3e418d8bed00e18447ff

---


# Landing page limitations{#landing-page-limitations}

**编写和更新数据**

* Landing pages are limited to **[!UICONTROL Profile]** and **[!UICONTROL Subscription]** resources only. Record can be saved and updated from **[!UICONTROL Profile]** and a subscription/unsubscription to a **[!UICONTROL Service]**.
To learn more on resources configuration, see [Configuring the resource's data structure](../../developing/using/configuring-the-resource-s-data-structure.md).

[!CAUTION]
> A landing page cannot display or update data from any other resource than **[!UICONTROL Profile]** and **[!UICONTROL Subscription]**.

**预先加载**

* 登陆页面无法自动显示记录的列表，它无法列出已订阅的服务。For more information on services, refer to this [page](../../audiences/using/creating-a-service.md).

* 具有预填表单的登录页面(数据预加载页面)只能从Adobe Campaign电子邮件中访问。无法从网站页面访问此类表单。

**Contract**

* 对帐行为如下：找到匹配项后，调解过程就停止了。这意味着，只有在有重复项时，才可以对一个配置文件记录进行排序，而不能在多个记录上进行排序。

例如，您要将以下赢取登陆页面发送到配置文件，以使用配置文件的移动号码更新您的营销活动数据库。

![](assets/landing_page_limitation_1.png)

如果您的某个配置文件使用新信息填充登陆页面，但已经存在重复的配置文件，则具有最早创建日期的匹配配置文件将会更新，因为配置文件优先取决于其创建日期。

此处仅更新了第一个配置文件，因为它是最旧的条目。

![](assets/landing_page_limitation_2.png)

**测试登陆页面**

* 登陆页面只能用于档案，而不能用于测试档案，这意味着登陆页面无法作为电子邮件证明的一部分进行测试。
