---
title: “工作流用例：在个人资料的创建日期创建提交”
seo-title: “工作流用例：在个人资料的创建日期创建提交”
description: “工作流用例：在个人资料的创建日期创建提交”
seo-description: “工作流用例：在个人资料的创建日期创建提交”
page-status-flag: 从未激活
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: '执行活动 '
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 工作流，用例，查询
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4a38b1f3d7d6dbf12fa71c819147bf2d91acb0c4

---


# 工作流用例：在配置文件的创建日期创建分发 {#creation-date-query}

您可以在客户个人资料创建周年时通过电子邮件发送优惠。

1. 在中， **[!UICONTROL Marketing Activities]**&#x200B;单击并 **[!UICONTROL Create]** 选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 为工作流类型，然后单击 **[!UICONTROL Next]**。
1. 输入工作流的属性，然后单击 **[!UICONTROL Create]**。

## 创建调度程序活动 {#creating-a-scheduler-activity}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**&#x200B;中，拖放 **[!UICONTROL Scheduler activity]**。
1. 双击活动。
1. 配置交付的执行。
1. 在中 **[!UICONTROL Execution frequency]**，选择 **[!UICONTROL Daily]**。
1. 为您的工 **[!UICONTROL Time]** 作流选 **[!UICONTROL Repetition frequency]** 择一个和执行的时间。
1. 为您的工 **[!UICONTROL Start]** 作流选择 **[!UICONTROL Expiration]** 日期和日期。
1. 确认活动并保存工作流。

>[!NOTE]
>
>要在特定时区启动工作流，请在选项&#x200B;**[!UICONTROL Execution options]**&#x200B;卡的字段中为调度程序设置时 **[!UICONTROL Time zone]**&#x200B;区。

![](assets/time_zone.png)

## 创建查询活动 {#creating-a-query-activity}

1. 要选择收件人，请拖放并 **[!UICONTROL Query activity]** 双击它。
1. 添 **[!UICONTROL Profiles]** 加并选 **[!UICONTROL no longer contact by email]** 择该值 **[!UICONTROL no]**。

### 检索在执行日期的同一天创建的配置文件 {#retriving-profiles-created-on-the-same-day}

1. 在 **[!UICONTROL Profile]**&#x200B;中，拖放字 **[!UICONTROL Created]** 段。 并单击 **[!UICONTROL Advanced Mode]**。
   ![](assets/advanced_mode.png)
1. 在中， **[!UICONTROL list of functions]**&#x200B;从节点中双&#x200B;**[!UICONTROL Day]** 击鼠标&#x200B;**[!UICONTROL Date]**&#x200B;键。
1. 然后，将字段作为 **[!UICONTROL Created]** 参数插入。
1. 选择 **[!UICONTROL equals to (=)]** 作为运算符。
1. 对于“值”,**[!UICONTROL Day]** 从中 **[!UICONTROL Date]** 的节点中选择 **[!UICONTROL List of functions]**。
1. 将函数&#x200B;**[!UICONTROL GetDate()]**&#x200B;作为参数插入。

您检索了创建日等于当前日的配置文件。

您最终应该有：

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Click **[!UICONTROL Confirm]**.

### 检索在执行月创建的配置文件{#retriving-profiles-created-on-the-same-month}

1. 在编辑 **[!UICONTROL Query]** 器上，选择第一个查询并复制它。
1. 打开副本。
1. 在 **[!UICONTROL Day]** 查询 **[!UICONTROL Month]** 中替换为。
1. Click **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

您最后应该有：

``` Month(@created) = Month(GetDate()) ```

最终查询显示：

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## 创建电子邮件分发{#creating-an-email-delivery}

1. 拖放电子邮件分发。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 进行编辑。
1. 选择 **[!UICONTROL Recurring email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用字段和链接个性化您的电子邮件。
有关详细信息，请参阅 [设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 单击 **[!UICONTROL Preview]** 以检查您的布局。
1. Click **[!UICONTROL Save]**.

**相关主题：**

* [查询](../../automating/using/query.md)
* [调度程序](../../automating/using/scheduler.md)
* [电子邮件发送](../../automa