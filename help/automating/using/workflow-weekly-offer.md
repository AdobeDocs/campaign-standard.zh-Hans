---
title: 创建每周投放
description: 此用例说明如何创建每周投放。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,delivery,scheduler
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 3%

---


# 每周二创建电子邮件投放{#creating-email-every-tuesday}

您可以每周二向特殊优惠的所有客户发送电子邮件。

1. 在中 **[!UICONTROL Marketing Activities]**，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 创建调度程序活动{#creating-a-scheduler-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;中，拖放一个 [调度程序](../../automating/using/scheduler.md) 活动。
1. 多次单击活动。
1. 配置投放的执行。
1. 在中 **[!UICONTROL Execution frequency]**，选择 **[!UICONTROL Weekly]**。
1. 为您的 **[!UICONTROL Time]** 投放 **[!UICONTROL Repetition frequency]** 选择一个和一个。
1. 在中 **[!UICONTROL Days of the week]**，选择 **[!UICONTROL Tuesday]**。
1. 为工作 **[!UICONTROL Start]** 流指定 **[!UICONTROL Expiration]** 一个和一个参数。
1. 确认您的活动并保存您的工作流。

![](assets/scheduler_properties.png)

>[!NOTE]
>
>要在特定的开始工作 **[!UICONTROL Time Zone]**&#x200B;流，**[!UICONTROL Execution options]**&#x200B;请在选项卡的时区字段中为调度程序设置时区。 默认情况下，所选时区是在工作流属性中定义的时区(请参 [阅构建工作流](../../automating/using/building-a-workflow.md))。

## 创建查询活动{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，要选择收件人，请拖放 [查询](../../automating/using/query.md) 活动，然后多次单击它。
1. 在 **[!UICONTROL Shortcuts]** > **[!UICONTROL Profile]**&#x200B;中，拖放 **[!UICONTROL Email]**。
1. 选择 **[!UICONTROL is not empty]** 为运算符。
1. 在 **[!UICONTROL Shortcuts]** > **[!UICONTROL General]**&#x200B;中，添加用户档案，然 **[!UICONTROL no longer contact by email]** 后使用值进行选 **[!UICONTROL No]**&#x200B;择。
1. 单击 **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## 创建电子邮件投放{#creating-an-email-delivery}

1. 在> **[!UICONTROL Activities]** 中 **[!UICONTROL Channels]**，拖放电子邮件 [投放活动](../../automating/using/email-delivery.md) 。
1. 单击活动，然 ![](assets/edit_darkgrey-24px.png) 后选择编辑。
1. 选择 **[!UICONTROL Recurring email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Use Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用字段和链接个性化您的电子邮件。
1. 单击 **[!UICONTROL Save]**.

有关详细信息，请参阅 [设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

**相关主题：**

* [电子邮件渠道](../../channels/using/creating-an-email.md)
