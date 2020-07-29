---
title: 管理组和用户
description: 了解如何创建安全组和管理用户。
page-status-flag: never-activated
uuid: b3a3a2e3-9d69-4231-b724-8f37419f7a61
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 12f896ab-ee79-4d96-976d-cf34643491b4
context-tags: user,overview;user,main;security,overview;security,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 09a6e062be32b78fda6b0eb83a6d11ac249b3168
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 0%

---


# 管理组和用户{#managing-groups-and-users}

## 关于安全组 {#about-security-groups}

安全组是指在您的组织内共享相同角色和权限的一组用户。

用户必须始终链接到安全组。 这将允许您为他们分配特定角色和组织单位。

有关角色的详细信息，下页中的表显示根据用户角色可用的不同操作： [Adobe Campaign Standard授权](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)。

默认安全组为：

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

如果用户未链接到任何安全组，他将无法访问Adobe Campaign。

要限制用户的访问，请不要将用户添加到Campaign Standard用户组，因为这已链接到组 **[!UICONTROL All]** 织单元。

>[!NOTE]
>
>默认情况下， **[!UICONTROL All (all)]** 组织单元被分配给安 **[!UICONTROL Administrators]** 全组。 它是只读的，无法修改。

## 创建安全组并分配用户 {#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>请注意，在管理控制台中，安全组称为用户档案。

如果现成的用户组不足以管理您的用户，您可以创建自己的安全组。 它们可由有权访问Adobe Campaign管理菜单和管理控制台的管理员管理。 有关Admin Console的详细信息，请参阅此 [文档](https://helpx.adobe.com/enterprise/managing/user-guide.html)。

在此，我们首先需要将两个现成的组“标准用户”和“管理员”分配给我们的用户。 这些安全组将限制Adobe Campaign的某些功能： 标准用户具有访问Adobe Campaign的基础知识，而管理员可以访问管理菜单等。

请注意，一旦用户登录Adobe Campaign，对管理控制台上的安全组所做的任何更改都将同步。

然后，我们要创建一组安全组Geometrixx和Geometrixx服，这些安全组将根据我们的标准用户和管理员的组织单位限制某些访问。

![](assets/ootb_security_group_1.png)

您首先需要将现成的安全组分配给您的用户：

1. 在管理控制台中，选择您的实例，然后选择“ **用户** ”选项卡。

   ![](assets/manage_security_group_2.png)

1. 单击按 **[!UICONTROL Add user]** 钮并输入用户的电子邮件地址。
1. 在选 **[!UICONTROL Assign Products]** 项卡中，从下拉列表 **[!UICONTROL Administrators]** 中选择您的实例，然后选择现成的安全组。 这将允许用户访问管理菜单并创建下一个安全组。

   ![](assets/ootb_security_group_2.png)

1. 单 **[!UICONTROL Save]** 击并按照相同的步骤，将 **[!UICONTROL Standard Users]** 现成的安全组分配给新用户。

   ![](assets/ootb_security_group_3.png)

将您的两个用户连接到为我们 **[!UICONTROL Administrators]** 的 **[!UICONTROL Standard users]** 用户分配角色的即装即用安全组后，管理员用户现在可以创建两个安全组 **Geometrixx** 和Geometrixx服装 **** ，除了开箱即用的安全组，它们还会为我们的用户分配组织单位。

1. 在管理控制台中，选择您的实例，然后选择“ **产品** ”选项卡。
1. 单击“ **新建用户档案** ”按钮以创 **建Geometrixx安** 全组。

   ![](assets/create_security_1.png)

1. 按以下 **[!UICONTROL Profile name]** 精确语法键入： **[!UICONTROL Campaign Standard- instance name - ID of the security group]** 并单击 **[!UICONTROL Done]**。

   在Adobe Campaign中创建安全组时，将使用所选ID。

   >[!NOTE]
   >
   >如果上述语法似乎不适用于较旧的实例，则需要用替换 **[!UICONTROL Campaign - instance name - ID of the security group]**。

   ![](assets/manage_security_group_1.png)

1. 然后，按照相同的步骤创建 **Geometrixx服** 。
1. 通过选择选项卡，将您的安全组分配给您 **[!UICONTROL Users]** 的用户。

   ![](assets/manage_security_group_2.png)

1. 单击您之前创建的用户，然 ![](assets/managing_security_group_10.png) 后单击类别中的 **[!UICONTROL Products]** 图标。

   选择 **[!UICONTROL Edit products assigned directly]** 以开始为用户分配新的安全组。

   ![](assets/manage_security_group_8.png)

1. 在选项 **[!UICONTROL Assign Products]** 卡中，选择您的实例，然后从下拉Geometrixx卡中选择之前创建的安全组列表，将其分配给管理员用户。

   单击 **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   如果用户位于多个组中：

   * 将累积不同组的角色。 此处，用户位于两个不同的组中： 一个在部队中扮演角色。
   * 它是层次结构中要使用的最高单位(请参阅“组织单位”部 [分中的](../../administration/using/organizational-units.md) 示例)。
   * 如果单元具有相同的对等级别并且位于层次结构中的并行分支中，则用户将无法再进行连接。

1. 按照相同的步骤将Geometrixx服安全组分配给您的标准用户。

   ![](assets/manage_security_group_9.png)

新创建的安全组现在在管理控制台中创建。 要使它们完全同步，您还需要以Adobe Campaign创建它们。

管理员用户必须创建用于分配组织单位的安全组集： Geometrixx和Geometrixx服。 要了解如何创建组织单位，请参 [阅创建和管理单位](../../administration/using/organizational-units.md#creating-and-managing-units) 。

1. 单击左 **[!UICONTROL Adobe Campaign]** 上角的徽标，然后选择 **[!UICONTROL Administration > Users & Security > Security groups]**。
1. 创建新的安全组并指定其 **[!UICONTROL Label]** 和 **[!UICONTROL ID]**。

   ID必须与在管理控制台中选择的ID相同。

1. 在字段 **[!UICONTROL User access]** 中，分配组织单位。 在此，Geometrixx安全组被分配给组 **[!UICONTROL All]** 织单位。

   >[!NOTE]
   >
   >如果要为用户分配现成的安全组，您需要重置组织单位。

   ![](assets/manage_security_group_6.png)

1. 您还可以向安全组分配角色。 在我们的情况下，由于现成的安全组用于分配角色，因此 **[!UICONTROL Administrators]** 不 **[!UICONTROL Standard users]** 需要此步骤。
1. 按照相同的步骤创建最后一个安全Geometrixx服装，并指定Geometrixx服装组织单位。

   ![](assets/manage_security_group_7.png)

您的用户现已分配到安全组，并可以连接到Adobe Campaign。

>[!IMPORTANT]
>
>如果从管理控制台中的安全组中删除用户，则这些用户仍将是Adobe Campaign安全组的一部分，并且将无法再登录Adobe Campaign。 在这种情况下，请删除管理控制台中用户的电子邮件地址，以阻止他们接收敏感信息。

