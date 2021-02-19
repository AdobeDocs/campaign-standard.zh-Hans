---
solution: Campaign Standard
product: campaign
title: 重新定位未打开者
description: 此用例说明如何重新定位非打开者。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 38%

---


# 将新投放发送给非打开者的重定向工作流{#retargeting-delivery-to-non-openers}

您可以向客户发送电子邮件，然后向未打开邮件的用户发送短信。

1. 在 **[!UICONTROL Marketing Activities]** 中，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 作为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 创建查询活动{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放[查询](../../automating/using/query.md)活动。
1. 双击该活动。
1. 在&#x200B;**[!UICONTROL Shortcuts]**&#x200B;中，拖放&#x200B;**[!UICONTROL Profiles]**&#x200B;并使用运算符&#x200B;**[!UICONTROL is not empty]**&#x200B;选择&#x200B;**[!UICONTROL email]**。
1. 在&#x200B;**[!UICONTROL Shortcuts]**&#x200B;中，拖放&#x200B;**[!UICONTROL Profiles]**&#x200B;并选择值为&#x200B;**[!UICONTROL no ]**&#x200B;的&#x200B;**[!UICONTROL no longer contact by email]**。
1. 单击 **[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## 创建电子邮件投放{#creating-an-email-delivery}

1. 在每个区段之后拖放[电子邮件投放](../../automating/using/email-delivery.md)。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 以进行编辑。
1. 选择 **[!UICONTROL Simple email]** 并单击 **[!UICONTROL Next]**。
1. 选择 **[!UICONTROL Add an outbound transition without the population]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Using the Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用特定于每个位置的优惠个性化您的电子邮件。有关详细信息，请参阅[设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**。

## 在查询活动{#targeting-non-openers-in-a-query-activity}中定位非打开者

1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;中，拖放[等待](../../automating/using/wait.md)活动。
1. 在&#x200B;**[!UICONTROL Duration]**&#x200B;中，单击![](assets/duration-icon.png)并选择一天。
1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放 **[!UICONTROL Query activity]**。
1. 双击该活动。
1. 在&#x200B;**[!UICONTROL Shortcuts]**&#x200B;中，拖放&#x200B;**[!UICONTROL Tracking Logs]**&#x200B;并使用运算符&#x200B;**[!UICONTROL exists]**。
1. 在&#x200B;**[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**&#x200B;中，用运算符&#x200B;**[!UICONTROL is equal to]**&#x200B;拖放&#x200B;**[!UICONTROL delivery]**&#x200B;并选择投放作为值。
1. 在&#x200B;**[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**&#x200B;中，拖放&#x200B;**[!UICONTROL type]**&#x200B;并将&#x200B;**[!UICONTROL Open]**&#x200B;作为值进行检查。
1. 在规则之间选择运算符&#x200B;**[!UICONTROL except]**。
1. 单击 **[!UICONTROL Confirm]**.

## 创建sms投放{#creating-a-sms-delivery}

1. 在每个区段后拖放一个sms投放。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 以进行编辑。
1. 选择 **[!UICONTROL Simple sms]** 并单击 **[!UICONTROL Next]**。
1. 选择一个sms模板，然后单击&#x200B;**[!UICONTROL Next]**。
1. 输入sms属性，然后单击&#x200B;**[!UICONTROL Next]**。
1. 要创建sms的布局，请单击&#x200B;**[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用特定于每个位置的优惠个性化您的短信。
有关详细信息，请参阅[设计sms](../../channels/using/creating-an-sms-message.md)部分。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**。

![](assets/wf-retargeting-non-openers.png)

**相关主题：**

* [电子邮件渠道](../../channels/using/creating-an-email.md)
