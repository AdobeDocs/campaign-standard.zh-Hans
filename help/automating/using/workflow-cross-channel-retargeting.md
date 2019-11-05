---
title: “工作流用例：重新定位非开放者”
description: “工作流用例：重新定位非开放者”
page-status-flag: 从未激活
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 执行活动
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: '工作流，用例，查询，等待，交付 '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 工作流用例：重定向工作流向非打开者发送新分发{#retargeting-delivery-to-non-openers}

您可以向客户发送电子邮件，然后向未打开邮件的用户发送短信。

1. 在中， **[!UICONTROL Marketing Activities]**&#x200B;单击并 **[!UICONTROL Create]** 选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 为工作流类型，然后单击 **[!UICONTROL Next]**。
1. 输入工作流的属性，然后单击 **[!UICONTROL Create]**。

## 创建查询活动{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**&#x200B;中，拖放 **[!UICONTROL Query activity]**![](assets/query.png)。
1. 双击活动。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放并 **[!UICONTROL Profiles]** 使用运 **[!UICONTROL email]** 算符进行选择 **[!UICONTROL is not empty]**。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放并 **[!UICONTROL Profiles]** 使用值 **[!UICONTROL no longer contact by email]** 进行选择 **[!UICONTROL no ]**。
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## 创建电子邮件分发{#creating-an-email-delivery}

1. 在每个区段之 **[!UICONTROL Email delivery]** 后拖放一个。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 进行编辑。
1. 选择 **[!UICONTROL Simple email]** 并单击 **[!UICONTROL Next]**。
1. 选择 **[!UICONTROL Add an outbound transition without the population]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件布局，请单击 **[!UICONTROL Using the Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用特定于每个位置的优惠个性化您的电子邮件。有关详细信息，请参阅 [设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 单击 **[!UICONTROL Preview]** 以检查您的布局。
1. Click **[!UICONTROL Save]**.

## 在查询活动中定位非打开者{#targeting-non-openers-in-a-query-activity}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**&#x200B;中，拖放 **[!UICONTROL Wait activity]**![](assets/wait.png)。
1. 在中 **[!UICONTROL Duration]**，单击并 ![](assets/duration-icon.png) 选择一天。
1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**&#x200B;中，拖放 **[!UICONTROL Query activity]**![](assets/query.png)。
1. 双击活动。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放和 **[!UICONTROL Tracking Logs]** 拖放操作符 **[!UICONTROL exists]**。
1. 在 **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**&#x200B;中，用运算符拖放 **[!UICONTROL delivery]** 并选择 **[!UICONTROL is equal to]** 交付作为值。
1. 在 **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**&#x200B;中，拖放并 **[!UICONTROL type]** 检查 **[!UICONTROL Open]** 为值。
1. 在规则之间选择运算符 **[!UICONTROL except]**。
1. Click **[!UICONTROL Confirm]**.

## 创建短信交付{#creating-a-sms-delivery}

1. 在每个区段之后拖放一个sms交付。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 进行编辑。
1. 选择 **[!UICONTROL Simple sms]** 并单击 **[!UICONTROL Next]**。
1. 选择一个sms模板，然后单击 **[!UICONTROL Next]**。
1. 输入sms属性并单击 **[!UICONTROL Next]**。
1. 要创建sms的布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 利用每个位置特定的推广信息个性化您的短信。
有关详细信息，请参 [阅设计sms](../../channels/using/creating-an-sms-message.md)。
1. 单击 **[!UICONTROL Preview]** 以检查您的布局。
1. Click **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**相关主题：**

* [查询](../../automating/using/query.md)
* [短信投放](../../automating/using/sms-delivery.md)
* [电子邮件投放](../../automating/using/email-delivery.md)
* [电子邮件渠道](../../channels/using/creating-an-email.md)
