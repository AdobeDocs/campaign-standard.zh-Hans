---
solution: Campaign Standard
product: campaign
title: 组织单位
description: 使用组织单位定义用户的访问级别。
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
feature: 访问管理
role: 管理员
level: 富有经验
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 4%

---


# 组织单位{#organizational-units}

## 关于单位{#about-units}

平台的每个对象和用户都链接到组织单元。 该单元允许定义分层结构，以便向用户提供过滤的视图。 用户单元为不同的平台对象定义其访问级别。

>[!IMPORTANT]
>
>如果用户未链接到任何设备，则该用户将无法连接到Adobe Campaign。 如果您希望限制特定用户或用户组的访问，请不要将其链接到&#x200B;**[!UICONTROL All]**&#x200B;设备。 我们建议在导入任何用户档案之前添加选项&#x200B;**访问授权管理字段**。 有关更多信息，请参阅此](../../administration/using/organizational-units.md#partitioning-profiles)章节[。
>
>默认情况下，**[!UICONTROL All (all)]** 组织单位被分配给 **[!UICONTROL Administrators]** 安全组。该项为只读项，无法修改。

用户对父单元中的所有对象具有只读访问权限。 他对单位和儿童单位的所有物品都有读写权限。 用户无权访问并行分支中的对象。

默认情况下，只有&#x200B;**[!UICONTROL All]**&#x200B;单位可用。

为用户分配组织单位后，此单位将始终应用于用户创建的对象。

![](assets/user_management_2.png)

>[!NOTE]
>
>当用户处于多个与不同设备链接的组中时，会应用某些规则。 有关详细信息，请参阅[管理组和用户](../../administration/using/managing-groups-and-users.md)部分。

## 创建和管理单元{#creating-and-managing-units}

组织单位允许您根据用户所链接到的组织来筛选实例。 此单位可以代表您实例中的区域、国家或甚至品牌。

在此，我们以前为两个用户创建了具有不同角色的安全组：为一个用户分配了安全组管理员和Geometrixx，而另一个用户属于安全组标准用户和Geometrixx服装请参阅[创建安全组和为完整示例分配用户](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users)。

我们现在需要为Geometrixx服装和Geometrixx安全组创建组织单位：

1. 从Adobe活动高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**。
1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;以开始配置您的组织单位。

   ![](assets/manage_units_1.png)

1. 将默认&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL ID]**&#x200B;更改为Geometrixx。
1. 然后，将此单元链接到父单元。 这里，我们选择了&#x200B;**[!UICONTROL All]**。

   ![](assets/manage_units_2.png)

1. 最后，单击&#x200B;**[!UICONTROL Create]**&#x200B;以开始将新的组织单元分配给安全组。
1. 对“Geometrixx服装”单元执行相同的步骤，但其父单元必须是先前创建的单元“Geometrixx”。

   ![](assets/manage_units_3.png)

要了解将不同设备分配给不同安全组的影响，分配给管理员和Geometrixx组的用户将创建两个电子邮件模板，以查看分配给标准用户和Geometrixx服装的其他用户可以访问或无法访问的内容。

1. 从高级菜单中，选择&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**。
1. 重复现有模板，并根据需要对其进行个性化。 有关详细信息，请参阅[关于模板](../../start/using/marketing-activity-templates.md)部分。
1. 创建模板后，选择&#x200B;**[!UICONTROL Edit properties]**&#x200B;图标以将设备分配给模板。

   ![](assets/manage_units_6.png)

1. 在&#x200B;**[!UICONTROL Access authorization]**&#x200B;下拉菜单中，选择组织单位。

   在此，我们将使用先前创建的组织单位Geometrixx创建一个模板。

   ![](assets/manage_units_5.png)

1. 按照相同的步骤创建分配给先前创建的Geometrixx服装组织单位的第二个模板。

分配给“标准用户”和“Geometrixx服装”组的用户将能够看到这两个模板。 由于组织单位的分层结构，他将具有对链接到Geometrixx服装单元的模板的读写权限，以及对链接到Geometrixx单元的模板的只读访问权限。

![](assets/manage_units_7.png)

由于Geometrixx服装单元是Geometrixx的子单元，当用户尝试修改Geometrixx模板时，将显示以下消息：

![](assets/manage_units_8.png)

组织单位可以限制对不同功能(如用户档案)的访问。 例如，如果我们的Geometrixx服装用户访问&#x200B;**[!UICONTROL Profiles]**&#x200B;选项卡，他将能够完全访问和修改Geometrixx服装组织单位的用户档案。

虽然Geometrixx组织单位的用户档案将为只读，但如果用户尝试修改一个用户档案，则会出现以下错误：**[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**。

![](assets/manage_units_10.png)

## 分区用户档案{#partitioning-profiles}

>[!IMPORTANT]
>
>我们建议在导入任何用户档案之前添加此选项，因为用户无法访问没有组织单位的用户档案。
>
>如果您已导入客户用户档案库，则需要进行更新，以便在已导入的客户上设置组织单位值。

如果您的组织需要隔离每个不同品牌所联系的用户档案，您可以按其组织单位划分用户档案。

默认情况下，您的用户档案上不提供组织单位字段，需要添加这些字段。

1. 从高级菜单中，通过Adobe Campaign徽标选择&#x200B;**“管理”>“开发”>“自定义资源”**。
1. 选择&#x200B;**用户档案**&#x200B;或创建新的自定义资源以扩展用户档案。 有关如何扩展用户档案的详细信息，请参阅此[页面](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource)。
1. 选中&#x200B;**添加访问授权管理字段**&#x200B;框，以添加&#x200B;**用户档案**&#x200B;扩展中的组织单元。

   ![](assets/user_management_9.png)

1. 单击 **[!UICONTROL Save]**.
1. 通过重新发布自定义资源更新结构。 有关发布过程的详细信息，请参阅[更新结构](../../developing/using/updating-the-database-structure.md)部分。

组织单位字段将添加到&#x200B;**[!UICONTROL Access authorization]**&#x200B;部分的用户档案中。

![](assets/user_management_10.png)

**相关主题**：

* [关于单位](../../administration/using/organizational-units.md#about-units)
* [关于访问管理](../../administration/using/about-access-management.md)

