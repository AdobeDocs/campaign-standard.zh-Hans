---
title: 管理组和用户
description: 了解如何创建安全组和管理用户。
page-status-flag: 从未激活
uuid: b3a3a2e3-9d69-4231-b724-8f37419f7a61
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参考
topic-tags: 用户和安全性
discoiquuid: 12f896ab-ee79-4d96-976d-cf34643491b4
context-tags: 用户，概述；用户，主要；安全性，概述；安全性，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 管理组和用户{#managing-groups-and-users}

## 关于安全组 {#about-security-groups}

安全组是指在您的组织内共享相同角色和权限的一组用户。

用户必须始终链接到安全组。 这允许您为他们分配特定的角色和组织单位。

有关角色的详细信息，下一页中的表显示了根据用户角色提供的不同操作：Adobe [Campaign standard授权](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)。

默认安全组为：

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

如果用户未关联到任何安全组，他将无法访问Adobe Campaign。

要限制用户的访问，请勿将用户添加到Campaign standard用户组，因为该用户组已链接到组 **[!UICONTROL All]** 织单元。

## 创建安全组并分配用户 {#creating-a-security-group-and-assigning-users}

>[!CAUTION]
>
>请注意，在Admin Console中，安全组称为配置文件。

如果现成的用户组不足以管理您的用户，您可以创建自己的安全组。 管理员可以对Adobe Campaign管理菜单和管理控制台进行管理。 有关Admin Console的详细信息，请参阅此 [文档](https://helpx.adobe.com/enterprise/managing/user-guide.html)。

首先，我们需要将两个现成的用户组Standard用户和管理员分配给我们的用户。 这些安全组将限制Adobe Campaign的某些功能：标准用户对Adobe Campaign具有基本访问权限，而管理员可以访问管理菜单等。

请注意，一旦用户登录Adobe Campaign，对管理控制台上的安全组所做的任何更改都将同步。

然后，我们要创建一组安全组Geometrixx和Geometrixx Chastes，它们将根据我们的标准用户和管理员的组织单位限制某些访问。

![](assets/ootb_security_group_1.png)

您首先需要为用户分配一个现成的安全组：

1. 在“管理控制台”中，选择您的实例，然后选择“用 **户** ”选项卡。

   ![](assets/manage_security_group_2.png)

1. 单击该 **[!UICONTROL Add user]** 按钮并输入用户的电子邮件地址。
1. 在选 **[!UICONTROL Assign Products]** 项卡中，从下拉列表 **[!UICONTROL Administrators]** 中选择您的实例，然后选择现成的安全组。 这将允许用户访问管理菜单并创建下一个安全组。

   ![](assets/ootb_security_group_2.png)

1. 单 **[!UICONTROL Save]** 击并按照相同的步骤将开箱 **[!UICONTROL Standard Users]** 即用的安全组分配给新用户。

   ![](assets/ootb_security_group_3.png)

在您的两个用户连接到为我们的用户分配角色的即装即用安全组后，管理员用户现在可以创建两个安全组 **[!UICONTROL Administrators]** Geometrixx **[!UICONTROL Standard users]** 和 **Geometrixx Chastes****** ，这两个安全组除了现成的安全组，还将为我们的用户分配组织单位。

1. 在“管理控制台”中，选择您的实例，然后选择“产 **品** ”选项卡。
1. 单击“ **新建配置文件** ”按钮以创 **建Geometrixx** 安全组。

   ![](assets/create_security_1.png)

1. 按照以下 **[!UICONTROL Profile name]** 精确语法键入：并 **[!UICONTROL Campaign Standard- instance name - ID of the security group]** 单击 **[!UICONTROL Done]**。

   然后，在Adobe Campaign中创建安全组时将使用所选的ID。

   >[!NOTE]
   >
   >如果上述语法似乎不适用于较旧的实例，则需要将其替换为 **[!UICONTROL Campaign - instance name - ID of the security group]**。

   ![](assets/manage_security_group_1.png)

1. 然后，按照相同的步骤创建 **Geometrixx Chastes** security组。
1. 通过选择选项卡，将您的安全组分配给您的 **[!UICONTROL Users]** 用户。

   ![](assets/manage_security_group_2.png)

1. 单击您之前创建的用户，然 ![](assets/managing_security_group_10.png) 后单击类别中的 **[!UICONTROL Products]** 图标。

   选择 **[!UICONTROL Edit products assigned directly]** 以开始为用户分配新的安全组。

   ![](assets/manage_security_group_8.png)

1. 在选项 **[!UICONTROL Assign Products]** 卡中，选择您的实例，然后从下拉列表中选择之前创建的安全组Geometrixx，以将其分配给您的管理员用户。

   Click **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   如果用户位于多个组中：

   * 将累积不同组的角色。 此处，用户分为两个不同的组：一个将在单位扮演角色。
   * 它是层次中要使用的最高单位(请参阅“组织单位”部 [分的示例](../../administration/using/organizational-units.md) )。
   * 如果单元具有相同的对等级别并且位于层次结构中的并行分支中，则用户将无法再连接。

1. 按照相同的步骤将Geometrixx Chastes安全组分配给您的标准用户。

   ![](assets/manage_security_group_9.png)

新创建的安全组现在在管理控制台中创建。 要使它们完全同步，您还需要在Adobe Campaign中创建它们。

管理员用户必须创建用于分配组织单位的一组安全组：Geometrixx和Geometrixx Chastes。 要了解如何创建组织单位，请参阅创 [建和管理单位](../../administration/using/organizational-units.md#creating-and-managing-units) 。

1. 单击左 **[!UICONTROL Adobe Campaign]** 上角的徽标，然后选择 **[!UICONTROL Administration > Users & Security > Security groups]**。
1. 创建新的安全组并指定其 **[!UICONTROL Label]** 和 **[!UICONTROL ID]**。

   ID必须与在管理控制台中选择的ID相同。

1. 在现场 **[!UICONTROL User access]** 中，分配组织单位。 此处，Geometrixx安全组被分配给组 **[!UICONTROL All]** 织单元。

   ![](assets/manage_security_group_6.png)

1. 您还可以为安全组分配角色。 在我们的情况下，由于现成的安全组用于分配角色，因此不 **[!UICONTROL Administrators]** 需 **[!UICONTROL Standard users]** 要执行此步骤。
1. 按照相同的步骤创建最后一个安全的Geometrixx Chastes并分配Geometrixx Chastes组织单元。

   ![](assets/manage_security_group_7.png)

您的用户现在已分配到安全组，并可以连接到Adobe Campaign。

>[!CAUTION]
>
>如果用户从管理控制台中的安全组中删除，他们将保留在Adobe Campaign安全组的一部分，并且将无法再登录Adobe Campaign。 在这种情况下，请删除管理控制台中用户的电子邮件地址，以阻止他们接收敏感信息。

