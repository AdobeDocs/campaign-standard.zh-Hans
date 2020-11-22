---
solution: Campaign Standard
product: campaign
title: Campaign Standard 管理快速入门
description: 发现用户和权限管理、监视指南、特定于渠道的配置和应用程序设置指南。
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 16%

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

## “管理”菜单 {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

单击左上角的Adobe Campaign徽标时， **[!UICONTROL Administration]** 可通过可访问的菜单执行不同的Adobe Campaign管理操作。 此部分界面只能由平台的功能管理员访问。

可用的不同菜单有：

* [用户和安全](../../administration/using/about-access-management.md):此菜单允许您管理对平台（用户、角色、安全组、设备）的访问。
* [渠道](../../administration/using/about-channel-configuration.md):此菜单重新分组链接到不同平台渠道（电子邮件、移动设备）的技术参数，以及类型和隔离管理。
* [应用程序设置](../../administration/using/external-accounts.md):此菜单允许您配置不同的应用程序元素(外部帐户、选项、技术工作流)。
* [开发](../../developing/using/data-model-concepts.md):此菜单允许您管理自定义资源并访问诊断工具。
* [实例设置](../../administration/using/branding.md):此菜单用于定义不同品牌并配置其设置(徽标、管理跟踪、URL域以访问登陆页等)。
* [部署](../../automating/using/managing-packages.md):此菜单重新分组包导入和导出选项。
* [客户指标](../../audiences/using/active-profiles.md):Adobe Campaign提供一个报告，其中显示活动用户档案的数量。 此报告仅提供信息，对计费没有直接影响。
* [隐私工具](https://docs.campaign.adobe.com/doc/standard/getting_started/cn/ACS_GDPR.html):此菜单允许您创建GDPR访问和删除请求并跟踪其演变。

## 用户和安全性 {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

邀请用户访问应用程序并管 **理安全组**，这些组是在您的组织内共享相同角色和权限的一组用户。 By default, Adobe Campaign offers a set of **roles** which allows you to define unitary authorizations assigned to users and user groups. Combined with **organizational units**, roles give users a filtered view of the interface and define their access to the different features.

活动标准还允许您监视与安全相关的信息。 您可以通过屏幕检索有关用户执行的活动导出 **[!UICONTROL Export audits]** 的信息，并利用屏幕来监 **[!UICONTROL Licenses]** 视组织内所有已安装的许可证，以及内部版本号、发行版本和协议条款等不同信息。

阅读更多:

* [用户管理](../../administration/using/users-management.md)
* [组织单位](../../administration/using/organizational-units.md)
* [角色列表](../../administration/using/list-of-roles.md)
* [管理组和用户](../../administration/using/managing-groups-and-users.md)
* [审核导出日志](../../administration/using/auditing-export-logs.md)
* [许可证](../../administration/using/licenses.md)

## 渠道配置 {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

必须正确配置Adobe Campaign中的所有通信渠道，以便能够有效地发送消息。 **[!UICONTROL Channel]** 菜单允许您管理链接到不同渠道的技术参数。

配置各种电 **子邮件** 参数：跳出、隔离、电子邮件属性和路由参数的处理规则、typoly规则。 为SMS路由定义渠道配 **置和属性** ，以及SMS编码和格式。

设置移 **动应用** ，以便能够使用Adobe Experience PlatformSDK发送应用程序内消息和推送通知，并通过创建和 **设置事件来** 配置事务消息。

阅读更多:

* [关于渠道配置](../../administration/using/about-channel-configuration.md)
* [配置电子邮件渠道](../../administration/using/configuring-email-channel.md)
* [配置短信渠道](../../administration/using/configuring-sms-channel.md)
* [配置移动应用程序](../../administration/using/configuring-a-mobile-application.md)
* [配置事务型消息传递](../../administration/using/configuring-transactional-messaging.md)

## 应用程序设置 {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard附带不同的应用程序元素，这些元素可以配置为满足您的需求。

设置 **外部帐户**，用于将Adobe Campaign连接到外部服务器。 访问Campaign Standard目标映射，并使用技术工作流监 **视平台**。

为组织定 **义一个** 或多个品牌，并在应用程 **序内配置实时通知的发送** ，以防出现重要的系统活动。

阅读更多:

* [关于 Campaign Standard 设置](../../administration/using/about-campaign-standard-settings.md)
* [外部帐户](../../administration/using/external-accounts.md)
* [Campaign 中的目标映射](../../administration/using/target-mappings-in-campaign.md)
* [技术工作流](../../administration/using/technical-workflows.md)
* [品牌策略](../../administration/using/branding.md)
* [发送内部通知](../../administration/using/sending-internal-notifications.md)

## 其他资源

* [管理用户访问权限（视频）](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/managing-user-access-rights.html)
* [控制面板文档](https://docs.adobe.com/content/help/zh-Hans/control-panel/using/control-panel-home.html)
