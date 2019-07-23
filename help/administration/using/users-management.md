---
title: 用户管理
seo-title: 用户管理
description: 用户管理
seo-description: 'Adobe Campaign用户保留特定角色。发现主要用户类型。 '
page-status-flag: 从未激活
uuid: 8c4cc74a-815f-4815-af66-a7 c21 bc754 f1
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 08c8712a-0066-4b8b-8471-2656b8fb23eded
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 4d95fe00c1958399ff4d22d5f0e7762f895b4032

---


# Users management{#users-management}

## About users {#about-users}

Adobe Campaign允许您为用户分配一组角色，以定义他们可以访问的界面的哪一部分。

The specific roles and the corresponding authorizations are detailed in the following sections: [understanding roles](../../administration/using/list-of-roles.md) and [authorizations](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

管理员可以从Admin Console管理用户。然后，用户会自动与Adobe Campaign同步。For more on this, refer to the [Admin console](https://helpx.adobe.com/enterprise/using/users.html) documentation.

To view the users in Adobe Campaign, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration > Users & Security > Users]**.

To access the user management interface from Adobe Campaign, click **[!UICONTROL User administration]**.

![](assets/user_management_5.png)

**相关主题：**

* [管理用户权限](https://helpx.adobe.com/campaign/kt/acs/using/acs-user-access-rights-feature-video-use.html) 视频
* [角色列表](../../administration/using/list-of-roles.md)
* [授权列表](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## Type of users {#type-of-users}

此用户细分不是强制性的，它仅代表Adobe Campaign最常用的用途。

本节将帮助您了解Adobe Campaign用户的主要类型。此处，我们不会进入用户可以存放的所有特定角色(开始提交、导出、准备交付等)。For more information on roles, refer to [List of roles](../../administration/using/list-of-roles.md) and [Managing groups and users](../../administration/using/managing-groups-and-users.md) pages.

我们希望重点介绍Adobe Campaign中的不同任务划分到三种主要用户类型之间的情况：

* [职能管理员](../../administration/using/users-management.md#functional-administrators)：在您组织的所有用户中，他们是最懂技术的用户。
* [高级用户](../../administration/using/users-management.md#advanced-users)：它们设置营销人员发送和监控其交付所需的所有元素。
* [基本用户](../../administration/using/users-management.md#basic-users)：他们是个性化、投放和监控营销活动的营销人员。

>[!NOTE]
>
>职能管理员与Adobe技术管理员不同。Adobe技术管理员持有Adobe内部角色，不可使用任何客户。他们管理实例供应、托管、基础结构监控和监督、技术故障排除。

### Functional administrators {#functional-administrators}

职能管理员是能够访问界面技术部分的用户。They hold the **[!UICONTROL Administration]** role and make sure that the platform is all set up so that marketers only have to focus on delivering their campaigns.

Functional administrators are the only users who can access the **[!UICONTROL Administration]** menu, in the Adobe Campaign interface. Since these users need to access technical resources, more advanced roles should be assigned to them, such as the **[!UICONTROL Administration]** and **[!UICONTROL Datamodel]** out-of-the-box roles. These roles are combined in the **[!UICONTROL Administrators]** out-of-the-box security group. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

以下是他们可以执行的主要任务：

* [管理用户和权限](../../administration/using/about-access-management.md)：管理对平台的访问(用户、角色、安全组、单位)。
* [配置不同的渠道](../../administration/using/about-channel-configuration.md)：设置不同的平台渠道以及打字和检疫管理。
* [配置常规应用程序设置](../../administration/using/external-accounts.md)：配置不同的应用程序元素(外部帐户、选项、技术工作流)。
* [开发新功能以增强开箱即用的功能](../../developing/using/data-model-concepts.md)：管理自定义资源并访问诊断工具。
* [设置实例参数](../../administration/using/branding.md)：定义不同品牌并配置其设置(徽标、管理跟踪、URL域访问登陆页面等)。
* [导出和导入数据包](../../automating/using/managing-packages.md)：通过结构化XML文件在不同的Adobe Campaign实例之间交换资源。
* [导出日志](../../automating/using/exporting-logs.md) 并 [定义导入模板](../../automating/using/defining-import-templates.md)。

### Advanced users {#advanced-users}

高级用户是在Adobe Campaign中执行最多技术使用案例的营销用户。他们预配置营销人员用于发送和监控其交付的所有元素。

此类型的用户需要的角色比功能管理员更多，但仍能执行一些技术操作。To do so, they should be assigned, for example, the **[!UICONTROL Export]**, **[!UICONTROL Generic import]** or **[!UICONTROL Workflow]** out-of-the-box roles. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

以下是他们可以执行的主要任务：

* [创建和执行复杂的数据管理工作流程](../../automating/using/about-data-management-activities.md)：导入、丰富和转换数据以传送数据库，或导出外部文件中需要的数据以在自己的工具中处理它。
* [管理模板](../../start/using/about-templates.md)：管理模板，根据您的需求预配置营销活动的特定参数。
* [创建查询](../../automating/using/editing-queries.md#about-query-editor) 和 [管理受众](../../audiences/using/about-audiences.md)：使用查询或使用专用工作流程自动创建受众。
* [执行高级表达式编辑](../../automating/using/editing-queries.md#about-query-editor)：使用高级函数处理用于执行特定查询(如日期、字符串、数字字段、排序等)的值。
* [导出列表](../../automating/using/exporting-lists.md) 并 [使用现有导入模板导入数据](../../automating/using/importing-data-with-import-templates.md)。

### Basic users {#basic-users}

多亏功能管理员和高级用户，营销人员无需担心技术配置即可个性化、交付和监控营销活动。To do so, they should be assigned, for example, the **[!UICONTROL Prepare deliveries]**, **[!UICONTROL Workflow]** and **[!UICONTROL Start deliveries]** out-of-the-box roles. These roles are combined in the **[!UICONTROL Standard Users]** out-of-the-box security group. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

以下是他们可以执行的主要任务：

* [管理计划和营销活动](../../start/using/programs-and-campaigns.md)：创建营销活动，包括不同类型的活动(电子邮件、SMS消息、推送通知、工作流、登陆页面)。
* Manage [profiles](../../audiences/using/about-profiles.md) and [test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md): manage the identified and test recipients that will be targeted by your deliveries. 添加名字、姓氏、联系信息、订阅、电子邮件等信息。
* [创建和发送消息](../../sending/using/confirming-the-send.md)：创建消息、选择受众、定义消息内容及其个性化元素、发送证明并向受众发送最终消息。
* [创建和发布登陆页面](../../channels/using/about-landing-pages.md)：创建和管理您希望为客户提供的一组服务，例如订阅或取消订阅表单。
* [创建和执行营销活动工作流程](../../automating/using/building-a-workflow.md)：使用工作流程自动化营销活动流程。
* Monitor your marketing activities through the [available reports](../../reporting/using/defining-the-report-period.md).

## Creating a user {#creating-a-user}

要将用户添加到实例，必须先在Admin Console中创建该用户，然后再在Adobe Campaign Standard中管理它。

1. From the advanced menu, select **[!UICONTROL Administration > Users & Security > Users]** and click **[!UICONTROL User administration]** to access the admin console.

   ![](assets/user_management_5.png)

1. In the **[!UICONTROL Admin Console]**, click on the **[!UICONTROL Users]** tab.

1. Click **[!UICONTROL Add User]**.

   ![](assets/create_user_2.png)

1. From the **[!UICONTROL User details]** tab, fill in the user's details such as email address, name and surname.

   ![](assets/create_user_3.png)

1. From the **[!UICONTROL Assign products]** tab, assign one or multiple security group to your user. For more information on security groups, refer to this [page](../../administration/using/managing-groups-and-users.md).

   Click **[!UICONTROL Save]** when done configuring.

   ![](assets/create_user_4.png)

您的用户现在已创建，并且应接收到指向以下窗口的电子邮件重定向到以下窗口，用户必须先设置口令才能使用。此用户随后将能够连接到您的Adobe Campaign Standard实例。

![](assets/create_user_5.png)

用户登录您的实例后，将与Adobe Campaign Standard同步。

然后，您可以检查用户是否已与Adobe Campaign正确同步：

1. From the advanced menu **[!UICONTROL Administration > Users & Security > Users]** select your previously created user.

1. Update the **[!UICONTROL Mobile]**, **[!UICONTROL Time zone]** or **[!UICONTROL Regional settings]** if needed.

1. 检查用户的安全组。Here, you can see that the user has been assigned the **[!UICONTROL Administrators]** security group.

   >[!Nte]
   >
   >只能在Admin Console中将安全组删除或添加到用户。

   ![](assets/create_user_6.png)

1. Check **[!UICONTROL Account disabled]** if you want to deactivate this user.

1. **[!UICONTROL Authorized connection zone]** 在字段中，选择用户将连接到此实例的方式，例如内部网络或VPN。

1. Click **[!UICONTROL Save]**.
