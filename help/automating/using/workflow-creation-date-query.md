---
title: 在用户档案的创建日期创建投放
description: 此用例展示了如何在用户档案的创建日期创建投放。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: f611e023-f74c-476e-83b9-aff451f68c81
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 33%

---

# 在轮廓的创建日期创建投放 {#creation-date-query}

您可以在客户用户档案创建周年纪念日通过电子邮件发送选件。

1. 在 **[!UICONTROL Marketing Activities]** 中，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 作为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 创建调度程序活动 {#creating-a-scheduler-activity}

1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;中，拖放[调度程序](../../automating/using/scheduler.md)活动。
1. 双击该活动。
1. 配置投放的执行方式。
1. 在 **[!UICONTROL Execution frequency]** 中，选择 **[!UICONTROL Daily]**。
1. 选择工作流的&#x200B;**[!UICONTROL Time]**&#x200B;和执行的&#x200B;**[!UICONTROL Repetition frequency]**。
1. 为您的工作流选择&#x200B;**[!UICONTROL Start]**&#x200B;日期和&#x200B;**[!UICONTROL Expiration]**。
1. 确认您的活动并保存工作流。

>[!NOTE]
>
>要在特定时区启动工作流，请在&#x200B;**[!UICONTROL Execution options]**&#x200B;选项卡的&#x200B;**[!UICONTROL Time zone]**&#x200B;字段中为调度程序设置时区。 默认情况下，所选时区就是在工作流属性中定义的时区（请参阅[构建工作流](../../automating/using/building-a-workflow.md)）。

![](assets/time_zone.png)

## 创建查询活动 {#creating-a-query-activity}

1. 要选择收件人，请拖放[查询](../../automating/using/query.md)活动并双击该活动。
1. 添加&#x200B;**[!UICONTROL Profiles]**&#x200B;并选择值为&#x200B;**[!UICONTROL no longer contact by email]**&#x200B;的&#x200B;**[!UICONTROL no]**。

### 检索在执行日期的同一天创建的用户档案 {#retrieving-profiles-created-on-the-same-day}

1. 在&#x200B;**[!UICONTROL Profile]**&#x200B;中，拖放&#x200B;**[!UICONTROL Created]**&#x200B;字段。 并单击&#x200B;**[!UICONTROL Advanced Mode]**。
   ![](assets/advanced_mode.png)
1. 在&#x200B;**[!UICONTROL list of functions]**&#x200B;中，双击&#x200B;**[!UICONTROL Day]**&#x200B;节点中的&#x200B;**[!UICONTROL Date]**。
1. 然后，插入字段&#x200B;**[!UICONTROL Created]**&#x200B;作为参数。
1. 选择&#x200B;**[!UICONTROL equals to (=)]**&#x200B;作为运算符。
1. 对于值，从&#x200B;**[!UICONTROL Day]**&#x200B;中的&#x200B;**[!UICONTROL Date]**&#x200B;节点中选择&#x200B;**[!UICONTROL List of functions]**。
1. 将&#x200B;**[!UICONTROL GetDate()]**&#x200B;函数作为参数插入。

您检索了创建日期等于当天的用户档案。

您最终应会得到：

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

单击 **[!UICONTROL Confirm]**。

### 检索在执行当月同一月创建的用户档案{#retrieving-profiles-created-on-the-same-month}

1. 在&#x200B;**[!UICONTROL Query]**&#x200B;编辑器上，选择第一个查询并复制它。
1. 打开副本。
1. 在查询中用&#x200B;**[!UICONTROL Day]**&#x200B;替换&#x200B;**[!UICONTROL Month]**。
1. 单击 **[!UICONTROL Confirm]**。

![](assets/month_rule.png)

您最终应会得到以下结果：

``` Month(@created) = Month(GetDate()) ```

将显示最终查询：

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## 创建电子邮件投放{#creating-an-email-delivery}

1. 拖放[电子邮件投放](../../automating/using/email-delivery.md)活动。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 以进行编辑。
1. 选择 **[!UICONTROL Recurring email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用字段和链接个性化电子邮件。
有关更多信息，请参阅[设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**。

**相关主题：**

* [电子邮件渠道](../../channels/using/creating-an-email.md)
