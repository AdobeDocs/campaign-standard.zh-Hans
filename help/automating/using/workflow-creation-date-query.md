---
title: 在投放的创建日期创建用户档案
description: 此用例说明如何在投放的创建日期创建用户档案。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 1%

---


# Creating deliveries on profiles&#39; creation date {#creation-date-query}

您可以在优惠创建周年时通过电子邮件发送用户档案。

1. 在中 **[!UICONTROL Marketing Activities]**，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 创建调度程序活动 {#creating-a-scheduler-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;中，拖放一个 [调度程序](../../automating/using/scheduler.md) 活动。
1. 多次单击活动。
1. 配置投放的执行。
1. 在中 **[!UICONTROL Execution frequency]**，选择 **[!UICONTROL Daily]**。
1. 选择工 **[!UICONTROL Time]** 作流 **[!UICONTROL Repetition frequency]** 的执行和执行。
1. 为您的 **[!UICONTROL Start]** 工作流 **[!UICONTROL Expiration]** 选择日期和日期。
1. 确认您的活动并保存您的工作流。

>[!NOTE]
>
>要在特定时区开始您的工作流，请在&#x200B;**[!UICONTROL Execution options]**&#x200B;选项卡中，在字段中为调度程序设置时 **[!UICONTROL Time zone]**&#x200B;区。 默认情况下，所选时区是在工作流属性中定义的时区(请参 [阅构建工作流](../../automating/using/building-a-workflow.md))。

![](assets/time_zone.png)

## 创建查询活动 {#creating-a-query-activity}

1. 要选择收件人，请拖放 [查询](../../automating/using/query.md) 活动，然后多次单击它。
1. 添加 **[!UICONTROL Profiles]** 并使 **[!UICONTROL no longer contact by email]** 用值进行选择 **[!UICONTROL no]**。

### 检索在执行日创建的用户档案 {#retriving-profiles-created-on-the-same-day}

1. 在 **[!UICONTROL Profile]**&#x200B;中，拖放字 **[!UICONTROL Created]** 段。 并单击 **[!UICONTROL Advanced Mode]**。
   ![](assets/advanced_mode.png)
1. 在中， **[!UICONTROL list of functions]**&#x200B;多次并&#x200B;**[!UICONTROL Day]** 单击节&#x200B;**[!UICONTROL Date]**&#x200B;点。
1. 然后，将字段作 **[!UICONTROL Created]** 为参数插入。
1. 选择 **[!UICONTROL equals to (=)]** 作为运算符。
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
1. 单击活动，然 ![](assets/edit_darkgrey-24px.png) 后选择编辑。
1. 选择 **[!UICONTROL Recurring email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用字段和链接个性化您的电子邮件。
有关详细信息，请参阅 [设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**.

**相关主题：**

* [电子邮件渠道](../../channels/using/creating-an-email.md)
