---
title: 审核记录
description: 使用Campaign审核记录监控操作和事件
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: bda6f8d5-3bcf-498c-a7c4-d3c2c79b9510
source-git-commit: 64da7ac09e1b0fbf13ba1e563b6dc7be995b1640
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 3%

---

# 审核记录 {#audit}

通过&#x200B;**[!UICONTROL Audit trail]**，您可以访问实例中所做更改的完整历史记录。

**[!UICONTROL Audit trail]**&#x200B;可实时捕获您的Adobe Campaign Standard实例中发生的操作和事件的全面列表。 它提供了一种访问数据历史的自助方式，可帮助回答以下问题：您的工作流发生了什么情况、自定义资源和选项、上次更新这些资源的人员或者您的用户在实例中做了什么。

![](assets/audit-trail.png)

**[!UICONTROL Audit trail]**&#x200B;由三个组件组成：

* **自定义资源审核跟踪**：检查自定义资源的活动和上次修改。

  有关&#x200B;**[!UICONTROL Custom resources]**&#x200B;的详细信息，请参阅此[页面](../../developing/using/key-steps-to-add-a-resource.md)。

* **工作流审核跟踪**：检查活动和上次对工作流进行的修改，以及工作流的状态，例如：

   * 已创建
   * 修改时间
   * 已删除
   * 工作流开始
   * 工作流暂停
   * 工作流停止
   * 工作流重新启动
   * 工作流清理
   * 工作流模拟
   * 工作流唤醒
   * 工作流立即停止
   * 与同一用户一起重新启动工作流
   * 工作流重新启动未知命令

  有关&#x200B;**[!UICONTROL Workflows]**&#x200B;的详细信息，请参阅此[页面](../../automating/using/get-started-workflows.md)。

* **选项审核跟踪**：检查活动和上次对选项进行的修改。

  有关&#x200B;**[!UICONTROL Options]**&#x200B;的详细信息，请参阅此[页面](../../administration/using/about-campaign-standard-settings.md)。

请注意，默认情况下，保留期为30天。

## 访问审核记录 {#audit-access}

要访问实例的审核记录，请执行以下操作：

1. 在Adobe Campaign Standard中，从高级菜单中选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Audit trail]**。

   ![](assets/audit-trail.png)

1. 此时将打开&#x200B;**[!UICONTROL Audit trail]**&#x200B;窗口，其中包含您的实体列表。 Adobe Campaign Standard将审核工作流、选项和自定义资源的创建、编辑和删除操作。

   从&#x200B;**[!UICONTROL Search]**&#x200B;菜单中，您可以按以下项筛选您的实体：

   * **[!UICONTROL Start date]**
   * **[!UICONTROL End date]**
   * **[!UICONTROL Type]**：实体类型介于“全部”、“工作流”、“自定义资源”和“选项”之间。
   * **[!UICONTROL Entity name]**：工作流、选项或自定义资源的ID

   ![](assets/audit-trail_2.png)

1. 选择其中一个实体以了解有关上次修改的更多信息。

1. “审计实体”窗口提供有关所选实体的更多详细信息，例如：

   * **[!UICONTROL Entity]**：工作流、选项或自定义资源的ID。
   * **[!UICONTROL Action]**：对此实体执行的最后一个操作。
   * **[!UICONTROL Changed by]**：上次修改此实体的人员的用户名。
   * **[!UICONTROL Changed date]**：对此实体执行的上次操作的日期。
   * **[!UICONTROL Content]**：代码块，它为您提供了有关实体中确切更改内容的更多信息。

   在本例中，我们可以看到此实例的业务管理员已于8月26日启动工作流WKF110。

   ![](assets/audit-trail_3.png)

## 启用/禁用审核跟踪 {#enable-disable-audit}

>[!NOTE]
>
> 只有功能管理员可以启用或禁用审核跟踪。 有关详细信息，请参见此 [ 页面](../../administration/using/users-management.md#functional-administrators)。

可以轻松地为特定活动激活或停用审核跟踪。

为实现此操作，请执行以下步骤：

1. 在Adobe Campaign Standard中，从高级菜单中选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**。

   ![](assets/audit-trail_4.png)

1. 根据要禁用的实体选择以下选项之一：

   * 用于管理工作流审核跟踪的&#x200B;**[!UICONTROL XtkAudit_Workflows]**&#x200B;选项。
   * 用于管理选项审核跟踪的&#x200B;**[!UICONTROL XtkAudit_Option]**&#x200B;选项。
   * 用于管理自定义资源的审核跟踪的&#x200B;**[!UICONTROL XtkAudit_CusResource]**&#x200B;选项。
   * 用于管理每个实体的审核跟踪的&#x200B;**[!UICONTROL XtkAudit_Enable_All]**&#x200B;选项。

     >[!NOTE]
     >
     >如果&#x200B;**[!UICONTROL XtkAudit_Enable_All]**&#x200B;选项设置为0，则&#x200B;**[!UICONTROL Audit trail]**&#x200B;功能将完全禁用，而不考虑其他单个选项值。

   ![](assets/audit-trail_5.png)

1. 如果要禁用&#x200B;**[!UICONTROL Audit trail]**，请在&#x200B;**[!UICONTROL Options]**&#x200B;页面中将&#x200B;**[!UICONTROL Value (integer)]**&#x200B;设置为0，或将其设置为1以启用它。

   ![](assets/audit-trail_6.png)

1. 单击 **[!UICONTROL Save]**。
