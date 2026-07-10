---
title: CNIL关于电子邮件跟踪像素的指南
description: 了解CNIL关于电子邮件跟踪像素的更新指南，以及可支持您的合规工作的Adobe Campaign Standard控件。
audience: administration
role: Admin
level: Experienced
hide: true
source-git-commit: 75f1f4ad8f7173f4601c9cff1ea93bf4092f274d
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 0%

---


# 了解CNIL关于电子邮件跟踪像素的更新指南 {#cnil-pixel-tracking}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解CNIL于2026年4月提出的关于电子邮件跟踪像素的建议，并发现可支持合规性工作的Adobe Campaign Standard控件，如跟踪激活、链接级别跟踪、同意数据模型、选择退出机制和报表。

>[!ENDSHADEBOX]

此帖子仅供参考。 这不是法律建议，也不保证您遵守适用法律。 下面描述的Adobe Campaign Standard产品功能是构建块，经过适当配置和操作后，可以支持合规的实施。 各客户有责任决定及遵守其于适用法律下之责任。

## 概述 {#overview}

2026年4月14日，法国数据保护机构，法国国家信息和自由委员会&#x200B;*发布了关于在电子邮件中使用跟踪像素的[建议](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf)。*&#x200B;该指南阐明何时需要获得同意，并强调针对电子邮件像素跟踪的适当同意实践的重要性。 此策略可能会影响向位于法国的订阅者发送电子邮件的任何实体的发送实践。

CNIL提供了自建议之日起三个月的时间，要求公司通知其电子邮件收件人（“用户”）跟踪像素的存在、其目的以及用户选择退出的权利。 在此过渡期间，客户应通知用户像素跟踪信息，并在必要时提供选择退出选项。 预计CNIL将在2026年7月14日之后开始执行活动。

随着CNIL和其他监管机构澄清有关跟踪像素和相关问题的指导，Adobe将继续监控更新，并告知客户支持电子邮件营销的Adobe产品（包括Adobe Campaign Standard）的技术功能。

Adobe电子邮件营销执行应用程序（包括Adobe Journey Optimizer、Journey Optimizer B2B、Adobe Campaign和Marketo Engage）提供了控件，可帮助客户在投放或电子邮件级别管理打开跟踪。 根据适用的CNIL指导和其他法律，客户有责任确定自己的合规义务，但这些功能可能会为客户合规工作提供支持。

### 什么是电子邮件跟踪像素 {#tracking-pixel}

电子邮件跟踪像素是嵌入到电子邮件HTML中的1x1透明图像。 收件人的电子邮件客户端加载该图像时，像素会向服务器发出ping信号，该信号记录时间戳、设备类型、电子邮件客户端等数据，有时还会记录IP地址以大致了解位置。 然后，该日志将绑定到收件人的记录，以允许营销人员查看电子邮件是否已打开。

### 客户支持 {#support}

为实施上述更改寻求帮助的客户可以与其现有的Adobe生态系统合作。 有关所引用Adobe功能的技术问题，请联系您的客户成功经理或技术客户经理。

## 与电子邮件跟踪相关的Adobe Campaign Standard功能 {#acs-functionality}

客户在配置架构时，可以使用Adobe Campaign Standard的本机跟踪、架构和个性化机制处理某些元素。

### 电子邮件分类 {#email-classification}

使用自定义字段扩展投放模板，这些字段指示电子邮件的类型（身份验证、仅可投放性、事务性、经同意营销、B2B潜在客户）。 在Campaign Standard中，投放模板可以包含流入报表和工作流逻辑的自定义字段。 此分类可确定每个发送适合哪个跟踪。

[了解如何创建和使用投放模板](../../channels/using/creating-an-email.md)

### 同意数据模型 {#consent-data-model}

通过Campaign Standard自定义资源机制（**管理>开发>自定义资源**）扩展配置文件资源，以包含每个用途的同意标记、同意时间戳和最近打开的日期（仅限日期，无时间组件）。 链接到用户档案的单独自定义资源会捕获仅支持个人同意证明的附加同意事件日志。 由于Campaign Standard登陆页面可以直接写入配置文件字段，因此当前的同意状态在本机上是可管理的；提交首选项后，同意日志将通过Adobe Campaign Standard REST API (`/profileAndServicesExt`)写入。

[了解如何创建或扩展资源](../../developing/using/creating-or-extending-the-resource.md)

[了解如何通过API与自定义资源交互](../../api/using/interacting-with-custom-resources.md)

### 像素发光 {#pixel-emission}

Adobe Campaign Standard通过投放或模板属性中的&#x200B;**[!UICONTROL Activate tracking]**&#x200B;切换控制投放级别的跟踪。 对于打开跟踪不合法的投放（仅身份验证，重新请求电子邮件），此切换处于禁用状态。 对于适合使用按用途像素发送的投放，一种方法是禁用标准自动插入像素，并使用包含条件1×1跟踪图像元素（每个用途一个）的内容块，其中为每个图像分配一个URL类别(`PIX_DELIV`、`PIX_PERF`、`PIX_PROFILE`、`PIX_FRAUD`)，并且仅在收件人的相应同意标志为true时显示。

[了解如何配置电子邮件跟踪参数](configuring-email-channel.md#tracking-parameters)

[了解如何在电子邮件Designer中管理跟踪的URL](../../designing/using/links.md#about-tracked-urls)

[了解如何添加内容块](../../designing/using/personalization.md#adding-a-content-block)

### 退出 {#withdrawal}

向每个电子邮件页脚添加一个&#x200B;**管理跟踪器首选项**&#x200B;链接，该链接不同于取消订阅链接。 该链接指向通过`recipientId`或`urlSubscription`机制验证的Campaign Standard登陆页面；收件人切换其按用途的同意标记并提交。 确认后，对Campaign Standard REST API的少量调用会将撤销事件写入同意日志。 建议表明，此链接本身安全不受跟踪要求约束。

[了解如何设置选择启用和选择禁用登陆页面](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)

[了解如何开始使用登陆页面](../../channels/using/getting-started-with-landing-pages.md)

### 同意证明 {#consent-proof}

每个同意更改（注册时捕获，从首选项页面更新，到期）在同意日志自定义资源中创建一行，其中带有措辞的版本代码、捕获时间戳、捕获源和范围。 此日志可通过Campaign Standard Explorer查询、通过REST API公开，并可通过计划工作流导出以供DPO审查。

[了解如何通过API与自定义资源交互](../../api/using/interacting-with-custom-resources.md)

### 重新招标治理 {#re-solicitation}

用户档案中的自定义`cusLastPixelRefusalDate`字段与排除该字段在选定时间段内的用户档案的类型过滤规则相结合，可阻止重新招徕在此期间拒绝的收件人。 计划的工作流通过标记过时记录并将到期事件写入同意日志来管理客户的同意到期时间范围。

[了解如何使用分类规则](../../sending/using/about-typology-rules.md)

[了解如何管理分类规则](../../sending/using/managing-typology-rules.md)

### 报告 {#reporting}

Campaign Standard动态报告基于URL类别和配置文件维度构建。 上述基于用途的URL类别在动态报告中以新维度的形式出现，允许操作员按用途对打开的数据进行切片并单击。 一旦URL类别设置就位，则同意跟踪和非同意跟踪之间的区别就在本机可见了。

[了解如何开始使用动态报告](../../reporting/using/about-dynamic-reports.md)

[了解跟踪指标](../../reporting/using/tracking-indicators.md)
