---
title: 角色列表
description: 了解可分配给用户的角色的列表。
page-status-flag: never-activated
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: role,overview;role,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 18db1b8cade7d88294ef2609dd4fad95c55fbd37

---


# 角色列表{#list-of-roles}

默认情况下，Adobe Campaign优惠一组角色，允许您定义分配给用户和用户组的统一授权。

角色与组织单位相结合，为用户提供了筛选的界面视图，并定义他们对不同功能的访问。

有关详细信息，请参阅角色 [和权限表](/help/administration/using/assets/acs_rights.pdf)，该表根据所选的授权详细说明了界面中可用的功能。

![](assets/user_management_3.png)

可以从菜单中管理角 **[!UICONTROL Administration > Users & Security > Roles]** 色。

默认权限为：

* **[!UICONTROL Administration]**:一般管理权限。
* **[!UICONTROL Datamodel]**:有权运行出版物和创建自定义资源。
* **[!UICONTROL Generic import]**:有权对数据运行通用导入。 要使其正常工作，您需要将角 **[!UICONTROL Generic import]** 色链接到角 **[!UICONTROL Workflow]** 色。
* **[!UICONTROL Prepare deliveries]**:有权创建、修改、准备和删除投放。 具有此角色的用户可以准备投放，但不能发送。
* **[!UICONTROL Start deliveries]**:有权创建、修改、准备、发送和删除投放。
* **[!UICONTROL Workflow]**:管理工作流执行(开始、停止、暂停等)的权利。 具有此角色的用户即使在工作流中也无法发送投放。

**相关主题：**

* [关于访问管理](../../administration/using/about-access-management.md)
* [管理组和用户](../../administration/using/managing-groups-and-users.md)
