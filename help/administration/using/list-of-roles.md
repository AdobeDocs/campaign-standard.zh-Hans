---
title: 角色列表
description: 查找可分配给用户的角色列表。
page-status-flag: 从未激活
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参考
topic-tags: 用户和安全性
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: 角色，概述；角色，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 角色列表{#list-of-roles}

默认情况下，Adobe Campaign提供一组角色，允许您定义分配给用户和用户组的统一授权。 角色与组织单位相结合，为用户提供界面的筛选视图并定义他们对不同功能的访问。 有关详细信息，请参阅“角色 [和权限”表](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)。

[![图像](/help/administration/using/assets/user_management_3.png)](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

可以从菜单中管理角 **[!UICONTROL Administration > Users & Security > Roles]** 色。

默认权限为：

* **[!UICONTROL Administration]**:一般管理权限。
* **[!UICONTROL Datamodel]**:有权运行出版物和创建自定义资源。
* **[!UICONTROL Export]**:导出数据的权利。
* **[!UICONTROL Generic import]**:有权对数据运行通用导入。 要使其正常工作，您需要将角 **[!UICONTROL Generic import]** 色链接到角 **[!UICONTROL Workflow]** 色。
* **[!UICONTROL Prepare deliveries]**:有权创建、修改、准备和删除分发。 具有此角色的用户可以准备分发，但不能发送。
* **[!UICONTROL Start deliveries]**:有权创建、修改、准备、发送和删除分发。
* **[!UICONTROL Workflow]**:创建、修改、启动和删除工作流的权限。 具有此角色的用户即使在工作流中也无法发送分发。

>[!CAUTION]
>
>Adobe管 **[!UICONTROL Deliverability]**&#x200B;理员仅 **[!UICONTROL Command execution]**&#x200B;可在内部使 **[!UICONTROL Export]**&#x200B;用、、和 **[!UICONTROL File access]****[!UICONTROL Message Center push]** 角色。 不应将其授予用户。

**相关主题：**

* [关于访问管理](../../administration/using/about-access-management.md)
* [管理组和用户](../../administration/using/managing-groups-and-users.md)

