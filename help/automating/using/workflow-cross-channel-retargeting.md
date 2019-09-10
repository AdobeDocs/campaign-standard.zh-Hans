---
title: “工作流程使用案例：重定向非Openers”
seo-title: “工作流程使用案例：重定向非Openers”
description: “工作流程使用案例：重定向非Openers”
seo-description: “工作流程使用案例：重定向非Openers”
page-status-flag: 从未激活
uuid: 396a3de1-6ffa-4385-ac9 f-15fdeae5 a366
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 执行活动
discoiquuid: 377821e6-69f8-41cc-a1 ad-8a2 f5 ed4 d409
context-tags: '工作流，用例，查询，等待，交付 '
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 035726bbd3112058b9a89525a861521bc3b9867e

---


# 工作流使用案例：重定向向非Opener发送新交付的工作流{#retargeting-delivery-to-non-openers}

您可以向客户发送电子邮件，然后发送给未打开邮件的用户。

1. 在中 **[!UICONTROL Marketing Activities]**，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 工作流类型，然后单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 创建查询活动{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Targeting]**，拖放a **[!UICONTROL Query activity]**![](assets/query.png)。
1. 双击活动。
1. 在中 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 并 **[!UICONTROL email]** 与操作符进行选择 **[!UICONTROL is not empty]**。
1. 在中 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 并使用 **[!UICONTROL no longer contact by email]** 该值进行选择 **[!UICONTROL no ]**。
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## 创建电子邮件分发{#creating-an-email-delivery}

1. 在每个区段之后拖放一个****[!UICONTROL Email delivery]电子邮件。
1. 单击活动并选择 ![](assets/edit_darkgrey-24px.png) 编辑。
1. 选择 **[!UICONTROL Simple email]** 并单击 **[!UICONTROL Next]**。
1. 选择 **[!UICONTROL Add an outbound transition without the population]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Using the Email Designer]**。
1. 插入元素或选择现有模板。
1. 通过特定于每个位置的选件个性化您的电子邮件。有关详细信息，请参阅 [设计电子邮件](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. Click **[!UICONTROL Save]**.

## 在查询活动中定位非Opener{#targeting-non-openers-in-a-query-activity}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Execution]**，拖放a **[!UICONTROL Wait activity]**![](assets/wait.png)。
1. 在中 **[!UICONTROL Duration]**，单击 ![](assets/duration-icon.png) 并选择一天。
1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Targeting]**，拖放a **[!UICONTROL Query activity]**![](assets/query.png)。
1. 双击活动。
1. In **[!UICONTROL Shortcuts]**、拖放和with **[!UICONTROL Tracking Logs]** the运算符 **[!UICONTROL exists]**。
1. 在 **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**&#x200B;中， **[!UICONTROL delivery]** 与运算符 **[!UICONTROL is equal to]** 拖放，并选择传递作为值。
1. 在 **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**&#x200B;中，拖放 **[!UICONTROL type]** 并检查 **[!UICONTROL Open]** 值。
1. 选择规则之间的运算符 **[!UICONTROL except]**。
1. Click **[!UICONTROL Confirm]**.

## 创建sms交付{#creating-a-sms-delivery}

1. 在每个区段之后拖放一个sms交付。
1. 单击活动并选择 ![](assets/edit_darkgrey-24px.png) 编辑。
1. 选择 **[!UICONTROL Simple sms]** 并单击 **[!UICONTROL Next]**。
1. 选择sms模板并单击 **[!UICONTROL Next]**。
1. 输入sms属性并单击 **[!UICONTROL Next]**。
1. 要创建sms的布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 通过特定于每个位置的优惠，个性化您的sms。
有关更多信息，请参阅 [设计sms](../../channels/using/creating-an-sms-message.md)。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. Click **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**相关主题：**

* [Query](../../automating/using/query.md)
* [SMS交付](../../automating/using/sms-delivery.md)
* [电子邮件发送](../../automating/using/email-delivery.md)
* [电子邮件渠道](../../channels/using/creating-an-email.md)
