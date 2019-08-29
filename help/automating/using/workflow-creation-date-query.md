---
title: “工作流程使用案例：在配置文件的创建日期创建分发”
seo-title: “工作流程使用案例：在配置文件的创建日期创建分发”
description: “工作流程使用案例：在配置文件的创建日期创建分发”
seo-description: “工作流程使用案例：在配置文件的创建日期创建分发”
page-status-flag: 从未激活
uuid: 396a3de1-6ffa-4385-ac9 f-15fdeae5 a366
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: '执行活动 '
discoiquuid: 377821e6-69f8-41cc-a1 ad-8a2 f5 ed4 d409
context-tags: 工作流，用例，查询
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: f57775ec88925d43046fe4162f2753c189d50c62

---


# 工作流使用案例：在档案的创建日期创建分发 {#creation-date-query}

您可以在客户配置文件创建周年时通过电子邮件发送选件。

1. 在中 **[!UICONTROL Marketing Activities]**，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 工作流类型，然后单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 创建计划程序活动 {#creating-a-scheduler-activity}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Execution]**，拖放a **[!UICONTROL Scheduler activity]**![](assets/scheduler_icon.png)。
1. 双击活动。
1. 配置交付的执行。
1. 在中 **[!UICONTROL Execution frequency]**，选择 **[!UICONTROL Daily]**。
1. 选择工作流的执行 **[!UICONTROL Time]** 和执行 **[!UICONTROL Repetition frequency]** 。
1. 选择 **[!UICONTROL Start]** 日期和 **[!UICONTROL Expiration]** 工作流。

>[!NOTE]
>
>要在特定时区启动工作流，请在&#x200B;**[!UICONTROL Execution options]**&#x200B;选项卡中为您的调度程序设置时区 **[!UICONTROL Time zone]**。

![](assets/time_zone.png)

1. 确认活动并保存工作流程。

## 创建查询活动 {#creating-a-query-activity}

1. 要选择收件人，请拖放一个 **[!UICONTROL Query activity]** 并双击它。
1. 添加 **[!UICONTROL Profiles]****[!UICONTROL no longer contact by email]** 并选择值 **[!UICONTROL no]**。

### 检索在当天的执行当天创建的配置文件 {#retriving-profiles-created-on-the-same-day}

1. 在中 **[!UICONTROL Profile]**，拖放 **[!UICONTROL Created]** 字段。然后单击 **[!UICONTROL Advanced Mode]**。
   ![](assets/advanced_mode.png)
1. 在 **[!UICONTROL list of functions]**&#x200B;中，双击&#x200B;**[!UICONTROL Day]****[!UICONTROL Date]**&#x200B;该节点。
1. 然后，将字段 **[!UICONTROL Created]** 插入为参数。
1. 选择 **[!UICONTROL equals to (=)]** 作为操作符。
1. 对于“值”，从&#x200B;**[!UICONTROL Day]** 中的 **[!UICONTROL Date]** 节点进行选择 **[!UICONTROL List of functions]**。
1. 将&#x200B;**[!UICONTROL GetDate()]**&#x200B;函数插入参数。

您检索了创建天等于当日的配置文件。

您应该最终得到：

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Click **[!UICONTROL Confirm]**.

### 检索在当月与执行当月创建的配置文件{#retriving-profiles-created-on-the-same-month}

1. 在 **[!UICONTROL Query]** 编辑器中，选择第一个查询并复制它。
1. 打开重复项。
1. 替换 **[!UICONTROL Day]** 为 **[!UICONTROL Month]** 查询。
您应该最终做到这一点：

``` Month(@created) = Month(GetDate()) ```

1. Click **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

此时将显示最终查询：

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## 创建电子邮件分发{#creating-an-email-delivery}

1. 拖放电子邮件。
1. 单击活动并选择 ![](assets/edit_darkgrey-24px.png) 编辑。
1. 选择 **[!UICONTROL Recurring email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用字段和链接个性化您的电子邮件。
有关更多信息，请参阅 [设计电子邮件](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. Click **[!UICONTROL Save]**.

**相关主题：**

* [Query](../../automating/using/query.md)
* [调度程序](../../automating/using/scheduler.md)
* [电子邮件发送](../../automating/using/email-delivery.md)
* [电子邮件渠道](../../channels/using/creating-an-email.md)
