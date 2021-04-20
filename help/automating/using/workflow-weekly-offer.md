---
solution: Campaign Standard
product: campaign
title: 创建每周投放
description: 此用例说明如何创建每周投放。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,delivery,scheduler
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 80%

---


# 每星期二创建一封电子邮件投放{#creating-email-every-tuesday}

您可以在每个星期二向所有客户发送电子邮件以提供特惠信息。

1. 在 **[!UICONTROL Marketing Activities]** 中，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 作为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 创建调度程序活动{#creating-a-scheduler-activity}

1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;中，拖放[调度程序](../../automating/using/scheduler.md)活动。
1. 双击该活动。
1. 配置投放的执行方式。
1. 在 **[!UICONTROL Execution frequency]** 中，选择 **[!UICONTROL Weekly]**。
1. 为您的投放选择 **[!UICONTROL Time]** 和 **[!UICONTROL Repetition frequency]**。
1. 在 **[!UICONTROL Days of the week]** 中，选择 **[!UICONTROL Tuesday]**。
1. 为工作流指定 **[!UICONTROL Start]** 和 **[!UICONTROL Expiration]** 参数。
1. 确认您的活动并保存工作流。

![](assets/scheduler_properties.png)

>[!NOTE]
>
>要在特定的 **[!UICONTROL Time Zone]** 启动工作流，请在 **[!UICONTROL Execution options]** 选项卡的时区字段中为调度程序设置时区。默认情况下，所选时区就是在工作流属性中定义的时区（请参阅[构建工作流](../../automating/using/building-a-workflow.md)）。

## 创建查询活动{#creating-a-query-activity}

1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，要选择收件人，请拖放[查询](../../automating/using/query.md)活动，然后按住多次单击它。
1. 在 **[!UICONTROL Shortcuts]** > **[!UICONTROL Profile]** 中，拖放 **[!UICONTROL Email]**。
1. 选择 **[!UICONTROL is not empty]** 作为运算符。
1. 在 **[!UICONTROL Shortcuts]** > **[!UICONTROL General]** 中，添加用户档案并选择 **[!UICONTROL no longer contact by email]**（其值为 **[!UICONTROL No]**）。
1. 单击 **[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## 创建电子邮件投放{#creating-an-email-delivery}

1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Channels]**&#x200B;中，拖放[电子邮件投放](../../automating/using/email-delivery.md)活动。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 以进行编辑。
1. 选择 **[!UICONTROL Recurring email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Use Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用字段和链接将电子邮件个性化。
1. 单击 **[!UICONTROL Save]**。

有关更多信息，请参阅[设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

**相关主题：**

* [电子邮件渠道](../../channels/using/creating-an-email.md)
