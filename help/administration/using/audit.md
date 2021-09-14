---
title: 审核记录
description: 使用促销活动审核跟踪监控操作和事件
audience: administration
content-type: reference
topic-tags: users-and-security
feature: Access Management
role: Admin
level: Experienced
exl-id: 4a4c14da-d842-4f65-821a-ca9e73a94adc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 1%

---

# 审核跟踪 {#audit}

通过&#x200B;**[!UICONTROL Audit trail]**，您可以访问实例中所做更改的完整历史记录。

**[!UICONTROL Audit trail]** 可实时捕获在Adobe Campaign Standard实例内发生的操作和事件的完整列表。它包括一种访问数据历史的自助方式，可帮助回答以下问题：工作流、自定义资源和选项发生的事件、上次更新这些事件的人员或用户在实例中的操作。

![](assets/audit-trail.png)

**[!UICONTROL Audit trail]** 包含三个组件：

* **自定义资源审核跟踪**:检查活动和上次对自定义资源所做的修改。

   有关&#x200B;**[!UICONTROL Custom resources]**&#x200B;的详细信息，请参阅此[页面](../../developing/using/key-steps-to-add-a-resource.md)。

* **工作流审核跟踪**:检查活动和对工作流的上次修改，以及工作流的状态，例如：

   * 已创建
   * 已修改
   * 已删除
   * 工作流开始
   * 工作流暂停
   * 工作流停止
   * 工作流重新启动
   * 工作流清理
   * 工作流模拟
   * 工作流唤醒
   * 工作流立即停止
   * 工作流重新启动同一用户
   * 工作流重新启动未知命令

   有关&#x200B;**[!UICONTROL Workflows]**&#x200B;的详细信息，请参阅此[页面](../../automating/using/get-started-workflows.md)。

* **选项审核跟踪**:检查活动和上次对选项进行的修改。

   有关&#x200B;**[!UICONTROL Options]**&#x200B;的详细信息，请参阅此[页面](../../administration/using/about-campaign-standard-settings.md)。

请注意，默认情况下，保留期为30天。

## 访问审核跟踪 {#audit-access}

要访问实例的审核跟踪，请执行以下操作：

1. 在Adobe Campaign Standard的高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Audit trail]**。

   ![](assets/audit-trail.png)

1. 将打开&#x200B;**[!UICONTROL Audit trail]**&#x200B;窗口，其中包含实体列表。 Adobe Campaign Standard将审核工作流、选项和自定义资源的创建、编辑和删除操作。

   从&#x200B;**[!UICONTROL Search]**&#x200B;菜单中，您可以按以下方式筛选实体：

   * **[!UICONTROL Start date]**
   * **[!UICONTROL End date]**
   * **[!UICONTROL Type]**:“全部”、“工作流”、“自定义资源”和“选项”之间的实体类型。
   * **[!UICONTROL Entity name]**:工作流、选项或自定义资源的ID

   ![](assets/audit-trail_2.png)

1. 选择一个实体，以了解有关上次修改的更多信息。

1. “审核实体”(Audit entity)窗口提供有关所选实体的更详细信息，例如：

   * **[!UICONTROL Entity]**:工作流、选项或自定义资源的ID。
   * **[!UICONTROL Action]**:对此实体执行的上次操作。
   * **[!UICONTROL Changed by]**:上次修改此实体的最后一个人员的用户名。
   * **[!UICONTROL Changed date]**:对此实体执行最后一次操作的日期。
   * **[!UICONTROL Content]**:代码块，用于提供有关实体中确切更改了哪些内容的更多信息。

   在本例中，我们可以看到此实例的业务管理员已于8月26日启动工作流WKF110。

   ![](assets/audit-trail_3.png)

## 启用/禁用审核跟踪 {#enable-disable-audit}

可以轻松激活或停用特定活动的审核跟踪。

为实现此操作，请执行以下步骤：

1. 在Adobe Campaign Standard的高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**。

   ![](assets/audit-trail_4.png)

1. 根据要禁用的实体选择以下选项之一：

   * **[!UICONTROL XtkAudit_Workflows]** 选项来管理工作流的审核跟踪。
   * **[!UICONTROL XtkAudit_Option]** 选项来管理选项的审核跟踪。
   * **[!UICONTROL XtkAudit_CusResource]** 用于管理自定义资源的审核跟踪的选项。
   * **[!UICONTROL XtkAudit_Enable_All]** 选项来管理每个实体的审核跟踪。

      >[!NOTE]
      >
      >如果将&#x200B;**[!UICONTROL XtkAudit_Enable_All]**&#x200B;选项设置为0，则无论其他各个选项值如何，**[!UICONTROL Audit trail]**&#x200B;功能都将被完全禁用。
   ![](assets/audit-trail_5.png)

1. 如果要禁用&#x200B;**[!UICONTROL Audit trail]**，请在&#x200B;**[!UICONTROL Options]**&#x200B;页面中将&#x200B;**[!UICONTROL Value (integer)]**&#x200B;设置为0，或将设置为1。

   ![](assets/audit-trail_6.png)

1. 单击 **[!UICONTROL Save]**。