---
title: 角色列表
description: 了解可分配给用户的角色列表
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 00714c80-bdaf-4241-bf2f-51498ca1dbef
TQID: 'https://experienceleague.adobe.com/HvLFiLS2GV0iJODsGL3AMMWd-lXbvDXYyLSJ8Mj20-w'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
  - id: efa38731-2723-4334-8d8b-a778af834835
    internal-label: Access management
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 75%
---
# 角色列表{#list-of-roles}

默认情况下，Adobe Campaign 提供了一系列的角色，用于定义分配给用户和用户组的统一授权。

将角色与组织单位相结合，可为用户提供一个经过筛选的界面视图，并定义用户对于各种功能的访问权限。

可使用 **[!UICONTROL Administration > Users & Security > Roles]** 菜单管理角色。

默认权限为：

* **[!UICONTROL Administration]**：一般管理权限。

  >[!NOTE]
  >
  >如果您使用Experience Cloud触发器，则需要&#x200B;**[!UICONTROL Administration]**&#x200B;权限才能访问Experience Cloud触发器菜单。 有关Experience Cloud触发器的更多信息，请参阅此[页面](../../integrating/using/about-adobe-experience-cloud-triggers.md)。

* **[!UICONTROL Datamodel]**：有权运行发布和创建自定义资源。
* **[!UICONTROL Generic import]**：有权执行一般数据导入。 要使此功能正常工作，必须将&#x200B;**[!UICONTROL Generic import]**&#x200B;角色链接到&#x200B;**[!UICONTROL Workflow]**&#x200B;角色。
* **[!UICONTROL Prepare deliveries]**：有权创建、修改、准备和删除投放。 拥有此角色的用户可以准备投放，但不能发送。
* **[!UICONTROL Start deliveries]**：有权创建、修改、准备、发送和删除投放。
* **[!UICONTROL Workflow]**：有权管理工作流执行（开始、停止、暂停等）。 即使在工作流中，此角色的用户也无法发送投放。

有关更多信息，请参阅[角色和权限表格](/help/administration/using/assets/acs_rights.pdf)，其中根据所选授权详细列出了界面中可用的功能。

[![image](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf)

**相关主题：**

* [关于访问管理](../../administration/using/about-access-management.md)
* [管理组和用户](../../administration/using/managing-groups-and-users.md)
