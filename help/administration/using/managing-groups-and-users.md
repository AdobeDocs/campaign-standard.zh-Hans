---
title: 管理组和用户
seo-title: 管理组和用户
description: 管理组和用户
seo-description: 了解如何创建安全组和管理用户。
page-status-flag: 从未激活
uuid: b3a3a2e3-9d69-4231-b724-8f37419 f7 a61
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 12f896ab-ee79-4d96-976d-cf34643491 b4
context-tags: 用户，概述；用户，主要；安全性，概述；安全性，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Managing groups and users{#managing-groups-and-users}

## About security groups {#about-security-groups}

安全组是在您的组织内共享相同角色和权限的用户组。

用户必须始终链接到安全组。这将允许您为他们分配特定角色和组织单位。

For more information on roles, the tables in the following page present the different operations available according to a user's role(s): [Adobe Campaign Standard authorizations](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

默认安全组有：

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

如果用户未链接到任何安全组，他将无法访问Adobe Campaign。

To restrict a user's access, do not add the user to the Campaign Standard users group as this is linked to **[!UICONTROL All]** organizational unit.

## Creating a security group and assigning users {#creating-a-security-group-and-assigning-users}

>[!CAUTION]
>
>请注意，在Admin Console中，安全组被称为配置文件。

如果现成用户组不足以管理用户，您可以创建自己的安全组。管理员可以由有权访问Adobe Campaign管理菜单和管理控制台的管理员管理。For more information on the Admin console, refer to this [documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).

这里，我们首先需要为用户分配两个现成的用户组Standard用户和管理员。这些安全组将限制Adobe Campaign的某些功能：Standard用户对Adobe Campaign拥有基本访问权限，而管理员可以访问管理菜单。

请注意，在用户登录Adobe Campaign后，管理控制台上对安全组所做的任何更改都将同步。

然后，我们要创建一组Geometrixx和Geometrixx服装，它们将限制某些访问，具体取决于标准用户和管理员的组织单位。

![](assets/ootb_security_group_1.png)

首先需要为用户分配现成的安全组：

1. In the Admin console, select your instance then the **Users** tab.

   ![](assets/manage_security_group_2.png)

1. Click the **[!UICONTROL Add user]** button and enter your user's email address.
1. In the **[!UICONTROL Assign Products]** tab, select your instance then the **[!UICONTROL Administrators]** out-of-the-box security group from the drop-down list. 这将允许用户访问管理菜单并创建下一个安全组。

   ![](assets/ootb_security_group_2.png)

1. Click **[!UICONTROL Save]** and follow the same procedures to assign the **[!UICONTROL Standard Users]** out-of-the-box security group to your new user.

   ![](assets/ootb_security_group_3.png)

Once your two users are attached to the **[!UICONTROL Administrators]** and **[!UICONTROL Standard users]** out-of-the-box security groups which assign roles to our users, the Administrator user can now create the two security groups **Geometrixx** and **Geometrixx Clothes** that will assign organizational units to our users in addition to the out-of-the-box security groups.

1. In the Admin console, select your instance then the **Products** tab.
1. Click the **New Profile** button to create the **Geometrixx** security group.

   ![](assets/create_security_1.png)

1. Type the **[!UICONTROL Profile name]** by following this exact syntax: **[!UICONTROL Campaign Standard- instance name - ID of the security group]** and click **[!UICONTROL Done]**.

   在Adobe Campaign中创建安全组时，将使用选定的ID。

   >[!NOTE]
   >
   >If the above syntax doesn't seem to work with an older instance, it needs to be replaced by **[!UICONTROL Campaign - instance name - ID of the security group]**.

   ![](assets/manage_security_group_1.png)

1. Then, follow the same procedures to create the **Geometrixx Clothes** security group.
1. Assign your security group to your user by selecting the **[!UICONTROL Users]** tab.

   ![](assets/manage_security_group_2.png)

1. Click your previously created user then the ![](assets/managing_security_group_10.png) icon in the **[!UICONTROL Products]** category.

   Select **[!UICONTROL Edit products assigned directly]** to start assigning new security group to your user.

   ![](assets/manage_security_group_8.png)

1. In the **[!UICONTROL Assign Products]** tab, select your instance then your previously created security groups Geometrixx from the drop-down list to assign it to your Administrator user.

   Click **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   如果用户位于多个用户组中：

   * 将累积不同组的角色。此处，用户位于两个不同的组中：在单元上扮演角色的角色。
   * It is the unit that is the highest in the hierarchy that will be used (see example in the [Organizational units](../../administration/using/organizational-units.md) section).
   * 如果单位具有相同的对等级别并且层次结构中的并行分支，则用户将不再能够连接。

1. 按照相同的过程将Geometrixx服装安全组分配给您的标准用户。

   ![](assets/manage_security_group_9.png)

新创建的安全组现在Admin Console中创建。为使它们完全同步，您还需要在Adobe Campaign中创建它们。

管理员用户必须创建用于分配组织单位的安全组集：Geometrixx和Geometrixx服装。To learn how to create organizational units, see [Creating and managing units](../../administration/using/organizational-units.md#creating-and-managing-units) .

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration > Users & Security > Security groups]**.
1. Create your new security group and specify its **[!UICONTROL Label]** and **[!UICONTROL ID]**.

   ID必须与在Admin Console中所选的ID相同。

1. **[!UICONTROL User access]** 在字段中，分配组织单位。Here, the Geometrixx security group is assigned the **[!UICONTROL All]** organizational unit.

   ![](assets/manage_security_group_6.png)

1. 您还可以为安全组分配角色。In our case, this step is not needed since the out-of-the-box security groups **[!UICONTROL Administrators]** and **[!UICONTROL Standard users]** are used to assign roles.
1. 按照相同的过程创建最后一个安全Geometrixx服装并指定Geometrixx服装单位单位。

   ![](assets/manage_security_group_7.png)

您的用户现在分配给安全组，并且可以连接到Adobe Campaign。

>[!CAUTION]
>
>如果用户从管理控制台中的安全组中删除，他们将仍然属于Adobe Campaign安全组的一部分，并且将无法再登录Adobe Campaign。在这种情况下，请在管理控制台中删除用户的电子邮件地址，以防止他们接收敏感信息。

