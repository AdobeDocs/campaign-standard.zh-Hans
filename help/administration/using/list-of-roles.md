---
solution: Campaign Standard
product: campaign
title: 角色列表
description: 了解可分配给用户的角色列表。
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: role,overview;role,main
translation-type: tm+mt
source-git-commit: ae2b6587d71f0915da05e53bf45c67c7a37a42c8
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 85%

---


# 角色列表{#list-of-roles}

默认情况下，Adobe Campaign 提供了一系列的角色，用于定义分配给用户和用户组的统一授权。

将角色与组织单位相结合，可为用户提供一个经过筛选的界面视图，并定义用户对于各种功能的访问权限。

可使用 **[!UICONTROL Administration > Users & Security > Roles]** 菜单管理角色。

默认权限为：

* **[!UICONTROL Administration]**：一般管理权限。

   >[!NOTE]
   >
   >如果您需要使用Experience Cloud触发器，您需要&#x200B;**[!UICONTROL Administration]**&#x200B;权限才能访问Experience Cloud触发器菜单。 有关Experience Cloud触发器的详细信息，请参阅此[页面](../../integrating/using/about-adobe-experience-cloud-triggers.md)。

* **[!UICONTROL Datamodel]**：有权运行发布和创建自定义资源。
* **[!UICONTROL Generic import]**：有权执行一般数据导入。要使其生效，您需要将 **[!UICONTROL Generic import]** 角色链接到 **[!UICONTROL Workflow]** 角色。
* **[!UICONTROL Prepare deliveries]**：有权创建、修改、准备和删除投放。拥有此角色的用户可以准备投放，但不能发送。
* **[!UICONTROL Start deliveries]**：有权创建、修改、准备、发送和删除投放。
* **[!UICONTROL Workflow]**：有权管理工作流执行（开始、停止、暂停等）。即使在工作流中，此角色的用户也无法发送投放。

有关更多信息，请参阅[角色和权限表格](/help/administration/using/assets/acs_rights.pdf)，其中根据所选授权详细列出了界面中可用的功能。

[![图像](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)

**相关主题：**

* [关于访问管理](../../administration/using/about-access-management.md)
* [管理组和用户](../../administration/using/managing-groups-and-users.md)
