---
title: 角色列表
description: 了解可分配给用户的角色列表
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 00714c80-bdaf-4241-bf2f-51498ca1dbef
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 72%

---

# 角色列表{#list-of-roles}

默认情况下，Adobe Campaign 提供了一系列的角色，用于定义分配给用户和用户组的统一授权。

将角色与组织单位相结合，可为用户提供一个经过筛选的界面视图，并定义用户对于各种功能的访问权限。

可使用 **[!UICONTROL Administration > Users & Security > Roles]** 菜单管理角色。

默认权限为：

* **[!UICONTROL Administration]**：一般管理权限。

   >[!NOTE]
   >
   >如果您使用Experience Cloud触发器，则需要 **[!UICONTROL Administration]** 有权访问Experience Cloud触发器菜单。 有关Experience Cloud触发器的详细信息，请参阅此 [页面](../../integrating/using/about-adobe-experience-cloud-triggers.md).

* **[!UICONTROL Datamodel]**：有权运行发布和创建自定义资源。
* **[!UICONTROL Generic import]**：有权执行一般数据导入。要使此功能正常工作，您必须链接 **[!UICONTROL Generic import]** 角色到 **[!UICONTROL Workflow]** 角色。
* **[!UICONTROL Prepare deliveries]**：有权创建、修改、准备和删除投放。拥有此角色的用户可以准备投放，但不能发送。
* **[!UICONTROL Start deliveries]**：有权创建、修改、准备、发送和删除投放。
* **[!UICONTROL Workflow]**：有权管理工作流执行（开始、停止、暂停等）。即使在工作流中，此角色的用户也无法发送投放。

有关更多信息，请参阅[角色和权限表格](/help/administration/using/assets/acs_rights.pdf)，其中根据所选授权详细列出了界面中可用的功能。

[![图像](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf)

**相关主题：**

* [关于访问管理](../../administration/using/about-access-management.md)
* [管理组和用户](../../administration/using/managing-groups-and-users.md)
