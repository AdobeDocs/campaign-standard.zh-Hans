---
title: Campaign Standard 管理快速入门
description: 探索用户和权限管理、监控指南、特定于渠道的配置以及应用程序设置指南
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
feature: Access Management
role: Admin
level: Experienced
exl-id: 9676b5e8-4c34-4848-8616-235e0bac5d6b
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 15%

---

# Campaign Standard 管理快速入门 {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">“管理”菜单</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">用户和安全性</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">渠道配置</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">应用程序设置</a></p></td></tr>
</table>

作为基于云的解决方案，Adobe Campaign为管理员提供了不同的应用程序配置方式。 尽管基础架构配置由Adobe执行，但功能管理员可以执行下面详述的各种配置操作。

>[!NOTE]
>
>如果您对实施和配置问题有任何疑问或请求，请联系您的Adobe客户经理。

请注意，管理员用户还可以利用Campaign控制面板来管理设置并跟踪每个实例的使用情况。 有关更多信息，请参阅[专用文档](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans)。

## “管理”菜单 {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

通过单击左上角的Adobe Campaign徽标时可访问的&#x200B;**[!UICONTROL Administration]**&#x200B;菜单执行不同的Adobe Campaign管理操作。 该界面的这一部分只能由平台的功能管理员访问。

可用的不同菜单包括：

* [用户和安全](../../administration/using/about-access-management.md):利用此菜单，可管理对平台（用户、角色、安全组、设备）的访问。
* [渠道](../../administration/using/about-channel-configuration.md):此菜单可重组链接到不同平台渠道（电子邮件、移动设备）的技术参数，以及分类和隔离管理。
* [应用程序设置](../../administration/using/external-accounts.md):利用此菜单，可配置不同的应用程序元素（外部帐户、选项、技术工作流）。
* [开发](../../developing/using/data-model-concepts.md):利用此菜单，可管理自定义资源并访问诊断工具。
* [实例设置](../../administration/using/branding.md):在此菜单中，您可以定义不同的品牌并配置其设置（徽标、管理跟踪、用于访问登陆页面的URL域等）。
* [部署](../../automating/using/managing-packages.md):此菜单可重组资源包导入和导出选项。
* [客户量度](../../audiences/using/active-profiles.md):Adobe Campaign会提供一个报表，其中显示活动用户档案的数量。此报表仅提供信息，对账单没有直接影响。
* [隐私工具](../../start/using/privacy-management.md):利用此菜单，可创建GDPR访问和删除请求，并跟踪其演变。

## 用户和安全性 {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

邀请用户访问应用程序并管理&#x200B;**安全组**，这些组是在您的组织内共享相同角色和权限的一组用户。 默认情况下，Adobe Campaign提供一组&#x200B;**角色**，用于定义分配给用户和用户组的统一授权。 角色与&#x200B;**组织单位**&#x200B;相结合，为用户提供了一个经过筛选的界面视图，并定义了用户对不同功能的访问权限。

Campaign standard还允许您监控与安全相关的信息。 您可以通过&#x200B;**[!UICONTROL Export audits]**&#x200B;屏幕检索有关用户执行的数据导出的信息，并利用&#x200B;**[!UICONTROL Licenses]**&#x200B;屏幕来监控您组织内安装的所有Campaign许可证，以及内部版本号、发行版本和协议条款等不同信息。

阅读更多:

* [用户管理](../../administration/using/users-management.md)
* [组织实体](../../administration/using/organizational-units.md)
* [角色列表](../../administration/using/list-of-roles.md)
* [管理组和用户](../../administration/using/managing-groups-and-users.md)
* [审核导出日志](../../administration/using/auditing-export-logs.md)
* [许可证](../../administration/using/licenses.md)

## 渠道配置 {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

必须正确配置Adobe Campaign中的所有通信渠道，才能有效地发送消息。**[!UICONTROL Channel]**&#x200B;菜单允许您管理链接到不同渠道的技术参数。

配置各种&#x200B;**email**&#x200B;参数：退回、隔离、电子邮件属性和路由参数、类型规则的处理规则。 为&#x200B;**SMS**&#x200B;渠道以及短信编码和格式定义路由配置和属性。

设置&#x200B;**移动应用程序**，以便能够使用Adobe Experience Platform SDK发送应用程序内消息和推送通知。

阅读更多:

* [关于渠道配置](../../administration/using/about-channel-configuration.md)
* [配置电子邮件渠道](../../administration/using/configuring-email-channel.md)
* [配置短信渠道](../../administration/using/configuring-sms-channel.md)
* [配置移动应用程序](../../administration/using/configuring-a-mobile-application.md)

## 应用程序设置 {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard附带了可根据您的需求配置的不同应用程序元素。

设置&#x200B;**外部帐户**，用于将Adobe Campaign连接到外部服务器。 访问Campaign Standard目标映射，并使用&#x200B;**技术工作流**&#x200B;监控您的平台。

为您的组织定义一个或多个&#x200B;**品牌**，并在发生重要系统活动时配置应用程序内发送&#x200B;**实时通知**&#x200B;的操作。

阅读更多:

* [关于 Campaign Standard 设置](../../administration/using/about-campaign-standard-settings.md)
* [外部帐户](../../administration/using/external-accounts.md)
* [Campaign 中的目标映射](../../administration/using/target-mappings-in-campaign.md)
* [技术工作流](../../administration/using/technical-workflows.md)
* [品牌化](../../administration/using/branding.md)
* [发送内部通知](../../administration/using/sending-internal-notifications.md)
