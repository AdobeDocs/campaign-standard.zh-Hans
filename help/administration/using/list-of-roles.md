---
title: 角色列表
seo-title: 角色列表
description: 角色列表
seo-description: 查找可分配给用户的角色列表。
page-status-flag: 从未激活
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: ceaa3c94-9e1a-4271-b443-b00 b4068929 f
context-tags: 角色，概述；角色，main
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# List of roles{#list-of-roles}

默认情况下，Adobe Campaign提供了一组角色，用于定义分配给用户和用户组的统一授权。与组织单位相结合，角色为用户提供了界面的筛选视图，并定义了对不同功能的访问。For more on this, refer to the [Roles and permissions table](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

![](assets/user_management_3.png)

Roles can be managed from the **[!UICONTROL Administration > Users & Security > Roles]** menu.

默认权限为：

* **[!UICONTROL Administration]**：常规管理权限。
* **[!UICONTROL Datamodel]**：运行出版物和创建自定义资源的权利。
* **[!UICONTROL Export]**：导出数据的权利。
* **[!UICONTROL Generic import]**：对数据运行常规导入的权限。For this to work, you need to link the **[!UICONTROL Generic import]** role to the **[!UICONTROL Workflow]** role.
* **[!UICONTROL Prepare deliveries]**：有权创建、编辑、开始交付准备和发送证明。
* **[!UICONTROL Start deliveries]**：用于验证之前准备好的交付的权利。
* **[!UICONTROL Workflow]**：使用工作流程的权利。

>[!CAUTION]
>
>交付功能仅供Adobe管理员内部使用。不能授予用户此权限。

**相关主题：**

* [关于访问管理](../../administration/using/about-access-management.md)
* [管理组和用户](../../administration/using/managing-groups-and-users.md)

