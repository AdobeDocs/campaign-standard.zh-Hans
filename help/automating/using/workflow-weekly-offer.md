---
title: “工作流程使用案例：创建每周交付”
seo-title: “工作流程使用案例：创建每周交付”
description: “工作流程使用案例：创建每周交付”
seo-description: “工作流程使用案例：创建每周交付”
page-status-flag: 从未激活
uuid: 396a3de1-6ffa-4385-ac9 f-15fdeae5 a366
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: '执行活动 '
discoiquuid: 377821e6-69f8-41cc-a1 ad-8a2 f5 ed4 d409
context-tags: 工作流，用例，查询，交付，调度程序
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 035726bbd3112058b9a89525a861521bc3b9867e

---


# Worflow使用案例：在星期二创建电子邮件{#creating-email-every-tuesday}

您可以在星期二向所有客户发送有关特殊优惠的电子邮件。

1. 在中 **[!UICONTROL Marketing Activities]**，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 工作流类型，然后单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 创建计划程序活动{#creating-a-scheduler-activity}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Execution]**，拖放a **[!UICONTROL Scheduler activity]**![](assets/scheduler_icon.png)。
1. 双击活动。
1. 配置交付的执行。
1. 在中 **[!UICONTROL Execution frequency]**，选择 **[!UICONTROL Weekly]**。
1. 为您的交付选择a **[!UICONTROL Time]** 和a。**[!UICONTROL Repetition frequency]**
1. 在中 **[!UICONTROL Days of the week]**，选择 **[!UICONTROL Tuesday]**。
1. 为工作流指定一个 **[!UICONTROL Start]** 和 **[!UICONTROL Expiration]** 参数。
1. 确认活动并保存工作流程。

![](assets/scheduler_properties.png)

>[!NOTE]
>
>要在特定 **[!UICONTROL Time Zone]**&#x200B;位置启动工作流，请在&#x200B;**[!UICONTROL Execution options]**“时区”字段中为您的调度程序设置时区。

## 创建查询活动{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Targeting]**，要选择收件人，请拖放 **[!UICONTROL query]** 活动并双击它。
1. 在 **[!UICONTROL Shortcuts]** &gt;中 **[!UICONTROL Profile]**，拖放 **[!UICONTROL Email]**。
1. 选择 **[!UICONTROL is not empty]** 作为操作符。
1. 在 **[!UICONTROL Shortcuts]** &gt;中 **[!UICONTROL General]**，添加配置文件并使用 **[!UICONTROL no longer contact by email]** 该值进行选择 **[!UICONTROL No]**。
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## 创建电子邮件分发{#creating-an-email-delivery}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Channels]**，拖放一 **[!UICONTROL Email delivery]**&#x200B;个。
1. 单击活动并选择 ![](assets/edit_darkgrey-24px.png) 编辑。
1. 选择 **[!UICONTROL Recurring email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Use Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用字段和链接个性化您的电子邮件。
1. Click **[!UICONTROL Save]**.

有关更多信息，请参阅 [设计电子邮件](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)。

**相关主题：**

* [查询活动](../..//automating/using/query.md)
* [调度程序活动](../..//automating/using/scheduler.md)
* [电子邮件发送](../..//automating/using/email-delivery.md)
* [电子邮件渠道](../..//channels/using/creating-an-email.md)
