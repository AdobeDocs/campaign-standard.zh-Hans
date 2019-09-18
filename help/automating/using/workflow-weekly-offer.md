---
title: “工作流用例：创建每周交付”
seo-title: “工作流用例：创建每周交付”
description: “工作流用例：创建每周交付”
seo-description: “工作流用例：创建每周交付”
page-status-flag: 从未激活
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: '执行活动 '
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 工作流，用例，查询，传送，调度程序
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4a38b1f3d7d6dbf12fa71c819147bf2d91acb0c4

---


# 工作流用例：每星期二创建电子邮件发送{#creating-email-every-tuesday}

您可以每星期二向所有客户发送电子邮件，以获取优惠。

1. 在中， **[!UICONTROL Marketing Activities]**&#x200B;单击并 **[!UICONTROL Create]** 选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 为工作流类型，然后单击 **[!UICONTROL Next]**。
1. 输入工作流的属性，然后单击 **[!UICONTROL Create]**。

## 创建调度程序活动{#creating-a-scheduler-activity}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**&#x200B;中，拖放 **[!UICONTROL Scheduler activity]**。
1. 双击活动。
1. 配置交付的执行。
1. 在中 **[!UICONTROL Execution frequency]**，选择 **[!UICONTROL Weekly]**。
1. 为您的 **[!UICONTROL Time]** 提交选 **[!UICONTROL Repetition frequency]** 择一个和一个。
1. 在中 **[!UICONTROL Days of the week]**，选择 **[!UICONTROL Tuesday]**。
1. 为工作 **[!UICONTROL Start]** 流指定 **[!UICONTROL Expiration]** 和参数。
1. 确认活动并保存工作流。

![](assets/scheduler_properties.png)

>[!NOTE]
>
>要在特定位置启动工作流，请 **[!UICONTROL Time Zone]**&#x200B;在选项卡的&#x200B;**[!UICONTROL Execution options]**&#x200B;时区字段中为调度程序设置时区。

## 创建查询活动{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**&#x200B;中，要选择收件人，请拖放活动， **[!UICONTROL query]** 然后双击它。
1. 在 **[!UICONTROL Shortcuts]** &gt; **[!UICONTROL Profile]**&#x200B;中，拖放 **[!UICONTROL Email]**。
1. 选择 **[!UICONTROL is not empty]** 作为运算符。
1. 在 **[!UICONTROL Shortcuts]** &gt; **[!UICONTROL General]**&#x200B;中，添加配置文件并 **[!UICONTROL no longer contact by email]** 使用值进行选择 **[!UICONTROL No]**。
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## 创建电子邮件分发{#creating-an-email-delivery}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**&#x200B;中，拖放 **[!UICONTROL Email delivery]**。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 进行编辑。
1. 选择 **[!UICONTROL Recurring email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件布局，请单击 **[!UICONTROL Use Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用字段和链接个性化您的电子邮件。
1. Click **[!UICONTROL Save]**.

有关详细信息，请参阅 [设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

**相关主题：**

* [查询活动](../..//automating/using/query.md)
* [调度程序活动](../..//automating/using/scheduler.md)
* [电子邮件发送](../..//automating/using/email-delivery.md)
* [电子邮件渠道](../..//channels/using/creating-an-email.md)
