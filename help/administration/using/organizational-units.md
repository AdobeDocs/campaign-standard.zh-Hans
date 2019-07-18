---
title: 组织单位
seo-title: 组织单位
description: 组织单位
seo-description: 使用组织单位定义用户的访问级别。
page-status-flag: 从未激活
uuid: 8c82ffea-cf4-4a89-b823-d8 b7 bae1 db4 f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 6f60c653-1d12-4d27-9bc8-ce8 c19 bca466
context-tags: orgUnit，概述；orgUnit，main；GeoIT，概述；GeUnit，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Organizational units{#organizational-units}

## About units {#about-units}

平台的每个对象和用户都链接到组织单位。此单元允许定义层次结构，以便为用户提供筛选视图。用户单位定义不同平台对象的访问级别。

>[!CAUTION]
>
>如果用户未链接到任何单位，则该用户将无法连接到Adobe Campaign。If you would like to restrict access for a particular user or group of users, do not link it to the **[!UICONTROL All]** unit.

用户具有对父组件中所有对象的只读访问权限。他对单位和子单位的所有对象都具有读写权限。用户无权访问并行分支中的对象。

By default, only the **[!UICONTROL All]** units are available.

分配给用户的组织单元时，此单元始终应用于用户创建的对象。

![](assets/user_management_2.png)

>[!NOTE]
>
>当用户在链接到不同单位的几个组中时，将应用某些规则。For more information, refer to the [Managing groups and users](../../administration/using/managing-groups-and-users.md) section.

## Creating and managing units {#creating-and-managing-units}

组织单位允许您根据用户所链接的组织过滤实例。此单元可代表您的地区、国家/地区甚至品牌。

Here, we previously created security groups with different roles to two users: one user is assigned the security groups Administrators and Geometrixx, the other user belongs to the security groups Standard user and Geometrixx Clothes See [Creating a security group and assigning users](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) for the full example.

我们现在需要为Geometrixx服装和Geometrixx安全组创建组织单位：

1. From Adobe campaign advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Users & security]** &gt; **[!UICONTROL Organizational units]**.
1. Click **[!UICONTROL Create]** to start configuring your organizational unit.

   ![](assets/manage_units_1.png)

1. Change the default **[!UICONTROL Label]** and **[!UICONTROL ID]** to Geometrixx.
1. 然后，将此单元链接到父单位。Here, we chose **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Finally, click **[!UICONTROL Create]** to start assigning your new organizational unit to security group.
1. 请按照Geometrixx服装单元的相同步骤操作，但其父单位必须是之前创建的单位Geometrixx。

   ![](assets/manage_units_3.png)

要查看为不同的安全组分配不同单元的影响，分配给Administrator和Geometrixx组的用户将创建两个电子邮件模板，以查看分配给标准用户和Geometrixx服装的其他用户可以或无法访问的其他用户。

1. From the advanced menu, select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery Templates]**.
1. 复制现有模板并根据需要对其进行个性化。For more on this, refer to the [About templates](../../start/using/about-templates.md) section.
1. When the template is created, select the **[!UICONTROL Edit properties]** icon to assign units to your template.

   ![](assets/manage_units_6.png)

1. In the **[!UICONTROL Access authorization]** drop down menu, select the organizational unit.

   在这里，我们将创建一个包含先前创建的组织Geometrixx的模板。

   ![](assets/manage_units_5.png)

1. 按照相同的过程创建分配给先前创建的Geometrixx服装组织单元的第二个模板。

分配给标准用户和Geometrixx服装组的用户将能够看到两个模板。由于组织单位的层次结构，他将有权读写链接到Geometrixx服装单元的模板，并且只读取链接到Geometrixx单位的模板。

![](assets/manage_units_7.png)

由于Geometrixx服装单元是Geometrixx的子单位，因此在用户尝试修改Geometrixx模板时会显示以下消息：

![](assets/manage_units_8.png)

组织单位可以限制对不同功能(如配置文件)的访问。For example, if our Geometrixx Clothes user access the **[!UICONTROL Profiles]** tab, he will be able to fully access and modify the profiles with the Geometrixx Clothes organizational unit.

Whereas the profiles with the Geometrixx organizational unit will be read only, the following error will appear if our user tries to modify one profile: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Partitioning profiles {#partitioning-profiles}

如果您的组织需要隔离每个不同品牌所联系的档案，您可以按组织单位划分档案。

默认情况下，您的配置文件中不提供组织单元字段，并且需要添加单位字段。

用户无法访问没有组织单位的配置文件。

>[!CAUTION]
>
>我们建议在导入任何配置文件之前添加此选项。如果您已经导入了客户数据库，则必须进行更新才能设置已导入配置文件上的组织单位值。

1. From the advanced menu, via the Adobe Campaign logo, select **Administration &gt; Development &gt; Custom resources**.
1. Select **Profile** or create a new custom resource to extend the profiles.
1. Check the **Add access authorization management fields** box to add the organizational units in the **Profile** extension.

   ![](assets/user_management_9.png)

1. Click **[!UICONTROL Save]**.
1. 重新发布自定义资源更新结构。For more information about the publication process, refer to [Updating the structure](../../developing/using/data-model-concepts.md) section.

The organizational unit field is added to your profiles in the **[!UICONTROL Access authorization]** section.

![](assets/user_management_10.png)

**相关主题**：

* [关于单位](../../administration/using/organizational-units.md#about-units)
* [关于访问管理](../../administration/using/about-access-management.md)

