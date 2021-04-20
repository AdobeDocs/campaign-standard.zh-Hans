---
solution: Campaign Standard
product: campaign
title: 管理组和用户
description: 了解创建安全组和管理用户的方法。
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: user,overview;user,main;security,overview;security,main
feature: Access Management
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 88%

---


# 管理组和用户{#managing-groups-and-users}

## 关于安全组{#about-security-groups}

安全组是指组织内共享相同角色和权限的一组用户。

用户必须始终链接到安全组。这样您即可为他们分配特定的角色和组织单位。

有关角色的详细信息，下页中的表显示了根据用户角色可用的可能操作：[Adobe Campaign Standard授权](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)。

默认安全组为：

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

>[!IMPORTANT]
>
>**[!UICONTROL Access to the deliverability parameters (Deliverability)]**&#x200B;和&#x200B;**[!UICONTROL Message Center agents (mcExec)]**&#x200B;安全组仅是Adobe内部组，不应分配给任何用户。

要能够访问Adobe Campaign，必须将每个用户分配给一个安全组。

要限制某个用户的访问，请勿将该用户添加到 Campaign Standard 用户组，因为该组已链接到 **[!UICONTROL All]** 组织单位。

>[!NOTE]
>
>默认情况下，**[!UICONTROL All (all)]** 组织单位被分配给 **[!UICONTROL Administrators]** 安全组。该项为只读项，无法修改。

## 创建安全组并分配用户{#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>请注意，在管理控制台中，安全组被视为用户档案。

如果现成的用户组不足以管理用户，您可以创建自己的安全组。有权访问 Adobe Campaign 管理菜单和管理控制台的管理员，可管理安全组。有关管理控制台的更多信息，请参阅此[文档](https://helpx.adobe.com/cn/enterprise/managing/user-guide.html)。

在此，我们首先需要将两个现成的组“标准用户”和“管理员”分配给我们的用户。这些安全组将限制 Adobe Campaign 的某些功能：例如，标准用户具有访问 Adobe Campaign 的基础权限，而管理员可以访问管理菜单。

请注意，一旦用户登录 Adobe Campaign，对管理控制台上的安全组所做的任何更改都将同步。

然后，我们要创建一系列安全组 Geometrixx 和 Geometrixx Clothes，这些安全组将根据标准用户和管理员的组织单位，限制某些权限。

![](assets/ootb_security_group_1.png)

您首先需要将一个现成的安全组分配给用户：

1. 在管理控制台中，选择您的实例，然后选择 **Users** 选项卡。

   ![](assets/manage_security_group_2.png)

1. 单击 **[!UICONTROL Add user]** 按钮并输入用户的电子邮件地址。
1. 在 **[!UICONTROL Assign Products]** 选项卡的 **[!UICONTROL Administrators]** 下拉列表中选择您的实例，然后选择现成的安全组。这样可让用户有权访问管理菜单并创建下一个安全组。

   ![](assets/ootb_security_group_2.png)

1. 单击 **[!UICONTROL Save]** 并按照相同的步骤进行操作，将 **[!UICONTROL Standard Users]** 这个现成的安全组分配给新用户。

   ![](assets/ootb_security_group_3.png)

将您的两个用户附加到为用户分配角色的 **[!UICONTROL Administrators]** 和 **[!UICONTROL Standard users]** 现成安全组后，管理员用户现在即可创建两个安全组 **Geometrixx** 和 **Geometrixx Clothes**，这两个安全组可以为我们的用户分配除现成安全组以外的组织单位。

1. 在管理控制台中，选择您的实例，然后选择 **Products** 选项卡。
1. 单击 **New Profile** 按钮以创建 **Geometrixx** 安全组。

   ![](assets/create_security_1.png)

1. 按以下精确语法键入 **[!UICONTROL Profile name]**：**[!UICONTROL Campaign Standard- instance name - ID of the security group]** 并单击 **[!UICONTROL Done]**。

   在 Adobe Campaign 中创建安全组时，将使用所选 ID。

   >[!NOTE]
   >
   >如果上述语法不适用于较旧的实例，则需要替换为 **[!UICONTROL Campaign - instance name - ID of the security group]**。

   ![](assets/manage_security_group_1.png)

1. 然后，按照相同的步骤创建 **Geometrixx Clothes** 安全组。
1. 选择 **[!UICONTROL Users]** 选项卡，将您的安全组分配给用户。

   ![](assets/manage_security_group_2.png)

1. 单击您之前创建的用户，然后单击 **[!UICONTROL Products]** 类别中的 ![](assets/managing_security_group_10.png) 图标。

   选择 **[!UICONTROL Edit products assigned directly]** 以开始为用户分配新的安全组。

   ![](assets/manage_security_group_8.png)

1. 在 **[!UICONTROL Assign Products]** 选项卡的下拉列表中选择您的实例，然后选择之前创建的 Geometrixx 安全组，将其分配给管理员用户。

   单击 **[!UICONTROL Save]**。

   ![](assets/manage_security_group_3.png)

   如果某个用户位于多个组中：

   * 则该用户将叠加不同组的角色。在本例中，用户位于两个不同的组中：一个代表角色，另一个代表单位。
   * 单位是所用层次结构中最高的级别（请参阅[组织单位](../../administration/using/organizational-units.md)一节中的示例）。
   * 如果多个单位具有相同的对等级别并且位于层次结构中的并行分支中，则用户将无法再进行连接。

1. 按照相同的步骤将 Geometrixx Clothes 安全组分配给您的标准用户。

   ![](assets/manage_security_group_9.png)

现在，已在管理控制台中生成了新创建的安全组。要使它们完全同步，您还需要在 Adobe Campaign 创建它们。

管理员用户必须创建用于分配组织单位的一系列安全组：Geometrixx 和 Geometrixx Clothes。要了解如何创建组织单位，请参阅[创建和管理单位](../../administration/using/organizational-units.md#creating-and-managing-units)。

1. 单击左上角的 **[!UICONTROL Adobe Campaign]** 徽标，然后选择 **[!UICONTROL Administration > Users & Security > Security groups]**。
1. 创建新的安全组并指定其 **[!UICONTROL Label]** 和 **[!UICONTROL ID]**。

   ID 必须与在管理控制台中选择的 ID 相同。

1. 在 **[!UICONTROL User access]** 字段中，分配组织单位。在本例中，已经为 **[!UICONTROL All]** 组织单位分配了 Geometrixx 安全组。

   >[!NOTE]
   >
   >如果要将现成的安全组分配给用户，则需要重置组织单位。

   ![](assets/manage_security_group_6.png)

1. 您还可以为安全组分配角色。在本例中，由于使用了现成的安全组 **[!UICONTROL Administrators]** 和 **[!UICONTROL Standard users]** 来分配角色，因此无需进行此步骤。
1. 按照相同的步骤创建最后一个安全组 Geometrixx Clothes，并分配 Geometrixx Clothes 组织单位。

   ![](assets/manage_security_group_7.png)

现在，您的用户已分配到了安全组，并可以连接到 Adobe Campaign。

>[!IMPORTANT]
>
>如果从“管理”控制台中的安全组中删除了用户，则这些用户将仍是Adobe Campaign安全组的一部分，将无法再登录Adobe Campaign。 在这种情况下，请删除管理控制台中用户的电子邮件地址，以防止他们接收敏感信息。

