---
solution: Campaign Standard
product: campaign
title: 在投放的创建日期创建用户档案
description: 此用例说明如何在投放的创建日期创建用户档案。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 38%

---


# 在用户档案的创建日期创建投放 {#creation-date-query}

您可以在优惠创建周年时通过电子邮件发送用户档案。

1. 在 **[!UICONTROL Marketing Activities]** 中，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 作为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 创建调度程序活动 {#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, drag and drop a [Scheduler](../../automating/using/scheduler.md) activity.
1. 双击该活动。
1. 配置投放的执行方式。
1. 在 **[!UICONTROL Execution frequency]** 中，选择 **[!UICONTROL Daily]**。
1. 选择工 **[!UICONTROL Time]** 作流 **[!UICONTROL Repetition frequency]** 的执行和执行。
1. 为您的 **[!UICONTROL Start]** 工作流 **[!UICONTROL Expiration]** 选择日期和日期。
1. 确认您的活动并保存工作流。

>[!NOTE]
>
>To start your workflow at a specific time zone, in the **[!UICONTROL Execution options]** tab, set up the time zone for your scheduler in the **[!UICONTROL Time zone]** field. 默认情况下，所选时区就是在工作流属性中定义的时区（请参阅[构建工作流](../../automating/using/building-a-workflow.md)）。

![](assets/time_zone.png)

## 创建查询活动{#creating-a-query-activity}

1. To select recipients, drag and drop a [Query](../../automating/using/query.md) activity and double-click it.
1. 添加 **[!UICONTROL Profiles]** 并使 **[!UICONTROL no longer contact by email]** 用值进行选择 **[!UICONTROL no]**。

### 检索在执行日创建的用户档案 {#retriving-profiles-created-on-the-same-day}

1. 在 **[!UICONTROL Profile]**&#x200B;中，拖放字 **[!UICONTROL Created]** 段。 并单击 **[!UICONTROL Advanced Mode]**。
   ![](assets/advanced_mode.png)
1. 在中， **[!UICONTROL list of functions]**&#x200B;多次键并&#x200B;**[!UICONTROL Day]** 单击节&#x200B;**[!UICONTROL Date]**&#x200B;点。
1. 然后，将字段作 **[!UICONTROL Created]** 为参数插入。
1. Select **[!UICONTROL equals to (=)]** as the operator.
1. 对于“值”,**[!UICONTROL Day]** 请从 **[!UICONTROL Date]** 中的节点中选 **[!UICONTROL List of functions]**&#x200B;择。
1. 将函数&#x200B;**[!UICONTROL GetDate()]**&#x200B;作为参数插入。

您检索了创建日等于当前日的用户档案。

您最终应该有：

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

单击 **[!UICONTROL Confirm]**.

### 检索在执行月创建的用户档案{#retriving-profiles-created-on-the-same-month}

1. 在编辑 **[!UICONTROL Query]** 器上，选择第一个查询并重复它。
1. 打开重复。
1. 在 **[!UICONTROL Day]** 查询 **[!UICONTROL Month]** 中替换为。
1. 单击 **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

您最后应该有：

``` Month(@created) = Month(GetDate()) ```

最终查询显示：

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## 创建电子邮件投放{#creating-an-email-delivery}

1. 拖放电子邮件 [投放](../../automating/using/email-delivery.md) 活动。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 以进行编辑。
1. 选择 **[!UICONTROL Recurring email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用字段和链接将电子邮件个性化。有关更多信息，请参阅[设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**。

**相关主题：**

* [电子邮件渠道](../../channels/using/creating-an-email.md)
