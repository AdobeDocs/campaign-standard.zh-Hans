---
title: 用户管理
description: 'Adobe Campaign用户具有特定角色。 发现主要用户类型。 '
page-status-flag: never-activated
uuid: 8c4cc74a-815f-4815-af66-a7c21bc754f1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 08c8712a-0066-4b8b-8471-2656b8fb23ed
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# 用户管理{#users-management}

## 关于用户 {#about-users}

Adobe Campaign允许您为用户分配一组角色，以定义他们可以访问的界面的哪个部分。

以下各节详细介绍了特定角色和相应的授权：了 [解角色](../../administration/using/list-of-roles.md)[和授权](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)。

管理员可以通过管理控制台管理用户。 然后，用户会自动与Adobe Campaign同步。 有关详细信息，请参阅 [Admin Console文档](https://helpx.adobe.com/enterprise/using/users.html) 。

要在Adobe Campaign中查看用户，请单击左 **[!UICONTROL Adobe Campaign]** 上角的徽标，然后选择 **[!UICONTROL Administration > Users & Security > Users]**。

要从Adobe Campaign访问用户管理界面，请单击 **[!UICONTROL User administration]**。

![](assets/user_management_5.png)

**相关主题：**

* [管理用户权限](https://helpx.adobe.com/campaign/kt/acs/using/acs-user-access-rights-feature-video-use.html) 视频
* [角色列表](../../administration/using/list-of-roles.md)
* [授权列表](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## 用户类型 {#type-of-users}

此用户细分不是强制的，它仅代表Adobe Campaign最常用的用法。

本节将帮助您了解Adobe Campaign用户的主要类型。 在此，我们不会进入用户可以担任的所有特定角色（开始提交、导出、准备提交等）。 有关角色的详细信息，请参阅角色 [列表和管理](../../administration/using/list-of-roles.md)[组和用户页面](../../administration/using/managing-groups-and-users.md) 。

我们宁愿关注Adobe Campaign中的不同任务是如何被分为三种主要用户类型的：

* [功能管理员](#functional-administrators):在您组织的所有用户中，他们是最具技术性的。
* [高级用户](#advanced-users):他们设置营销人员发送和监控其交付所需的所有元素。
* [基本用户](#basic-users):他们是营销人员，负责个性化、投放和监控营销活动。

>[!NOTE]
>
>功能管理员与Adobe技术管理员不同。 Adobe技术管理员承担Adobe内部角色，客户无法使用。 他们管理实例配置、托管、基础架构监控和监督、技术故障排除。

### 功能管理员 {#functional-administrators}

功能管理员是可以访问界面中技术最为完善的部分的用户。 他们担 **[!UICONTROL Administration]** 任此角色，并确保平台已全部建立，因此营销人员只需专注于提供其营销活动。

功能管理员是Adobe Campaign界面中唯一可以访 **[!UICONTROL Administration]** 问菜单的用户。 由于这些用户需要访问技术资源，因此应为他们分配更高级的角 **[!UICONTROL Administration]** 色， **[!UICONTROL Datamodel]** 如现成的角色。 这些角色将组合在 **[!UICONTROL Administrators]** 现成的安全组中。 For more on this, refer to this [section](../../administration/using/list-of-roles.md).

以下是他们可以执行的主要任务：

* [管理用户和权限](../../administration/using/about-access-management.md):管理对平台（用户、角色、安全组、设备）的访问。
* [配置不同的渠道](../../administration/using/about-channel-configuration.md):建立不同的平台渠道以及类型和检疫管理。
* [配置常规应用程序设置](../../administration/using/external-accounts.md):配置不同的应用程序元素（外部帐户、选项、技术工作流程）。
* [开发新功能以增强开箱即用功能](../../developing/using/data-model-concepts.md):管理您的自定义资源并访问诊断工具。
* [设置实例参数](../../administration/using/branding.md):定义不同品牌并配置其设置（徽标、管理跟踪、URL域以访问登录页面等）。
* [导出和导入数据包](../../automating/using/managing-packages.md):通过结构化XML文件在不同的Adobe Campaign实例之间交换资源。
* [导出日志](../../automating/using/exporting-logs.md) ，并 [定义导入模板](../../automating/using/defining-import-templates.md)。

### 高级用户 {#advanced-users}

高级用户是在Adobe Campaign中执行最技术性使用案例的营销用户。 他们预配置营销人员用于发送和监控其分发的所有元素。

与功能管理员相比，此类用户需要的常规角色更多，但仍应能够执行一些技术操作。 为此，应为其分配(例如， **[!UICONTROL Export]**&#x200B;或 **[!UICONTROL Generic import]****[!UICONTROL Workflow]** 现成角色)。 For more on this, refer to this [section](../../administration/using/list-of-roles.md).

以下是他们可以执行的主要任务：

* [创建和执行复杂的数据管理工作流程](../../automating/using/about-data-management-activities.md):导入、扩充和转换数据以供给数据库，或导出外部文件中需要的数据以在您自己的工具中进行处理。
* [管理模板](../../start/using/marketing-activity-templates.md):管理您的模板，以根据您的需求预配置营销活动的特定参数。
* [创建查询](../../automating/using/editing-queries.md#about-query-editor) , [并管理受众](../../audiences/using/about-audiences.md):使用查询或自动使用专用工作流程手动创建受众。
* [执行高级表达式编辑](../../automating/using/editing-queries.md#about-query-editor):使用高级函数处理用于执行特定查询的值，如日期、字符串、数字字段、排序等。
* [使用现有导](../../automating/using/exporting-lists.md) 入模板导出列表和导入数据 [](../../automating/using/importing-data-with-import-templates.md)。

### 基本用户 {#basic-users}

借助功能管理员和高级用户，营销人员可以个性化、投放和监控其营销活动，而不必担心技术配置。 为此，应分配这些角色，例 **[!UICONTROL Prepare deliveries]**&#x200B;如 **[!UICONTROL Workflow]** , **[!UICONTROL Start deliveries]** 即装即用的角色。 这些角色将组合在 **[!UICONTROL Standard Users]** 现成的安全组中。 For more on this, refer to this [section](../../administration/using/list-of-roles.md).

以下是他们可以执行的主要任务：

* [管理计划和营销活动](../../start/using/programs-and-campaigns.md):创建包括不同类型的活动（电子邮件、短信、推送通知、工作流、登录页面）的营销活动。
* 管理配 [置文件](../../audiences/using/about-profiles.md) 和测 [试配置文件](../../sending/using/managing-test-profiles-and-sending-proofs.md):管理由您的分发定向的已识别和测试收件人。 添加名字、姓、联系信息、订阅、电子邮件等信息。
* [创建和发送消息](../../sending/using/confirming-the-send.md):创建您的信息，选择受众，定义消息内容及其个性化元素，发送校样并向受众发送最终消息。
* [创建和发布登陆页面](../../channels/using/getting-started-with-landing-pages.md):创建并管理您希望为客户提供的一组服务，例如订阅或取消订阅表单。
* [创建和执行营销活动工作流](../../automating/using/building-a-workflow.md):使用工作流程实现营销活动流程自动化。
* 通过可用报告监控您的 [营销活动](../../reporting/using/defining-the-report-period.md)。

## 创建用户 {#creating-a-user}

要将用户添加到您的实例，必须先在Admin Console中创建该用户，然后再在Adobe Campaign standard中管理它。

1. 从高级菜单中，选择并 **[!UICONTROL Administration > Users & Security > Users]** 单击以 **[!UICONTROL User administration]** 访问管理控制台。

   ![](assets/user_management_5.png)

1. 在中， **[!UICONTROL Admin Console]**&#x200B;单击选项卡 **[!UICONTROL Users]** 。

1. Click **[!UICONTROL Add User]**.

   ![](assets/create_user_2.png)

1. 在选项卡 **[!UICONTROL User details]** 中，填写用户的详细信息，如电子邮件地址、姓名和姓氏。

   ![](assets/create_user_3.png)

1. 在选项卡 **[!UICONTROL Assign products]** 中，为用户分配一个或多个安全组。 有关安全组的详细信息，请参阅此 [页](../../administration/using/managing-groups-and-users.md)。

   完成 **[!UICONTROL Save]** 配置后单击。

   ![](assets/create_user_4.png)

您的用户现已创建，并且应会收到一封电子邮件，该电子邮件重定向到以下窗口，在该窗口中，用户必须设置口令，然后接受使用条款协议。 然后，此用户将能够连接到您的Adobe Campaign standard实例。

![](assets/create_user_5.png)

用户登录到您的实例后，将立即同步到Adobe Campaign Standard。

然后，您可以检查用户是否已正确同步到Adobe Campaign:

1. 从高级菜单中，选 **[!UICONTROL Administration > Users & Security > Users]** 择您之前创建的用户。

1. 更新 **[!UICONTROL Mobile]**&#x200B;或 **[!UICONTROL Time zone]** 根 **[!UICONTROL Regional settings]** 据需要。

1. 检查用户的安全组。 在此，您可以看到已为用户分配了安全 **[!UICONTROL Administrators]** 组。

   >[!Note]
   >
   >安全组只能在管理控制台中删除或添加到用户。

   ![](assets/create_user_6.png)

1. 选 **[!UICONTROL Account disabled]** 中是否要取消激活此用户。

1. 在字 **[!UICONTROL Authorized connection zone]** 段中，选择用户将通过哪种方式连接到此实例，如内部网络或VPN。

1. Click **[!UICONTROL Save]**.

您的用户现已准备好使用Adobe Campaign Standard。
