---
solution: Campaign Standard
product: campaign
title: Campaign Standard 管理快速入门
description: 发现用户和权限管理、监视指南、特定于渠道的配置和应用程序设置指南。
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
translation-type: tm+mt
source-git-commit: 72fd9693fa089a7246bbb87fc10e6fcc4276eddd
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 14%

---


# Campaign Standard 管理快速入门 {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">“管理”菜单</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">用户和安全性</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">渠道配置</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">应用程序设置</a></p></td></tr>
</table>

作为基于云的解决方案，Adobe Campaign优惠管理员会以不同的方式配置应用程序。 尽管基础架构配置由Adobe执行，但功能管理员可以执行下面详述的各种配置操作。

>[!NOTE]
>
>如果您对实施和配置问题有任何疑问或请求，请与Adobe客户经理联系。

请注意，如果您的实例托管在AWS上，管理员用户还可以利用活动控制面板管理设置并跟踪每个实例的使用情况。 有关更多信息，请参阅[专用文档](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html)。

## 管理菜单{#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

单击左上角的Adobe Campaign标志时，可通过可访问的&#x200B;**[!UICONTROL Administration]**&#x200B;菜单执行不同的Adobe Campaign管理操作。 此部分界面只能由平台的功能管理员访问。

可用的不同菜单有：

* [用户和安全](../../administration/using/about-access-management.md):此菜单允许您管理对平台（用户、角色、安全组、设备）的访问。
* [渠道](../../administration/using/about-channel-configuration.md):此菜单重新分组链接到不同平台渠道（电子邮件、移动设备）的技术参数，以及类型和隔离管理。
* [应用程序设置](../../administration/using/external-accounts.md):此菜单允许您配置不同的应用程序元素(外部帐户、选项、技术工作流)。
* [开发](../../developing/using/data-model-concepts.md):此菜单允许您管理自定义资源并访问诊断工具。
* [实例设置](../../administration/using/branding.md):此菜单用于定义不同品牌并配置其设置(徽标、管理跟踪、URL域以访问登陆页等)。
* [部署](../../automating/using/managing-packages.md):此菜单重新分组包导入和导出选项。
* [客户指标](../../audiences/using/active-profiles.md):Adobe Campaign提供一个报告，其中显示活动用户档案的数量。此报告仅提供信息，对计费没有直接影响。
* [隐私工具](../../start/using/privacy-management.md):此菜单允许您创建GDPR访问和删除请求并跟踪其演变。

## 用户和安全性 {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

邀请用户访问应用程序并管理&#x200B;**安全组**，这些组是在您的组织内共享相同角色和权限的一组用户。 默认情况下，Adobe Campaign优惠一组&#x200B;**角色**，它允许您定义分配给用户和用户组的统一授权。 角色与&#x200B;**组织单位**&#x200B;相结合，为用户提供已过滤的界面视图，并定义他们对不同功能的访问。

活动标准还允许您监视与安全相关的信息。 您可以通过&#x200B;**[!UICONTROL Export audits]**&#x200B;屏幕检索用户执行的活动导出信息，并利用&#x200B;**[!UICONTROL Licenses]**&#x200B;屏幕来监视组织内所有已安装的数据许可证，以及内部版本号、发行版本和协议条款等不同信息。

阅读更多:

* [用户管理](../../administration/using/users-management.md)
* [组织单位](../../administration/using/organizational-units.md)
* [角色列表](../../administration/using/list-of-roles.md)
* [管理组和用户](../../administration/using/managing-groups-and-users.md)
* [审核导出日志](../../administration/using/auditing-export-logs.md)
* [许可证](../../administration/using/licenses.md)

## 渠道配置{#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

必须正确配置Adobe Campaign中的所有通信渠道才能有效发送消息。**[!UICONTROL Channel]**&#x200B;菜单允许您管理链接到不同渠道的技术参数。

配置各种&#x200B;**email**&#x200B;参数：跳出、隔离、电子邮件属性和路由参数的处理规则、typoly规则。 定义&#x200B;**SMS**&#x200B;路由的渠道配置和属性，以及SMS编码和格式。

设置&#x200B;**移动应用程序**，以便能够使用Adobe Experience PlatformSDK发送应用程序内消息和推送通知，并通过创建和设置事件配置&#x200B;**事务消息**。

阅读更多:

* [关于渠道配置](../../administration/using/about-channel-configuration.md)
* [配置电子邮件渠道](../../administration/using/configuring-email-channel.md)
* [配置短信渠道](../../administration/using/configuring-sms-channel.md)
* [配置移动应用程序](../../administration/using/configuring-a-mobile-application.md)
* [配置事务型消息传递](../../administration/using/configuring-transactional-messaging.md)

## 应用程序设置 {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard附带不同的应用程序元素，这些元素可以配置为满足您的需求。

设置&#x200B;**外部帐户**，用于将Adobe Campaign连接到外部服务器。 访问Campaign Standard目标映射，并使用&#x200B;**技术工作流**&#x200B;监视您的平台。

为您的组织定义一个或多个&#x200B;**品牌**，并在发生重要系统活动时，在应用程序中配置发送&#x200B;**实时通知**。

阅读更多:

* [关于 Campaign Standard 设置](../../administration/using/about-campaign-standard-settings.md)
* [外部帐户](../../administration/using/external-accounts.md)
* [Campaign 中的目标映射](../../administration/using/target-mappings-in-campaign.md)
* [技术工作流](../../administration/using/technical-workflows.md)
* [品牌策略](../../administration/using/branding.md)
* [发送内部通知](../../administration/using/sending-internal-notifications.md)
