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


# Retargeting workflow sending a new delivery to non-openers{#retargeting-delivery-to-non-openers}

您可以向客户发送电子邮件，然后向未打开邮件的用户发送短信。

1. 在 **[!UICONTROL Marketing Activities]** 中，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 作为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## Creating a query activity{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放[查询](../../automating/using/query.md)活动。
1. 双击该活动。
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL email]** with the operator **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL no longer contact by email]** with the value **[!UICONTROL no ]**.
1. 单击 **[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## 创建电子邮件投放{#creating-an-email-delivery}

1. 将电子邮件投放 [拖放到](../../automating/using/email-delivery.md) 每个区段之后。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 以进行编辑。
1. 选择 **[!UICONTROL Simple email]** 并单击 **[!UICONTROL Next]**。
1. 选择 **[!UICONTROL Add an outbound transition without the population]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Using the Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用特定于每个位置的优惠个性化您的电子邮件。有关详细信息，请参 [阅设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**。

## 在查询活动中定位非打开者{#targeting-non-openers-in-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, drag and drop a [Wait](../../automating/using/wait.md) activity.
1. 在 **[!UICONTROL Duration]**&#x200B;中，单 ![](assets/duration-icon.png) 击并选择一天。
1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放 **[!UICONTROL Query activity]**。
1. 双击该活动。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放 **[!UICONTROL Tracking Logs]** 和使用运算符 **[!UICONTROL exists]**。
1. 在 **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**&#x200B;中，用运算符拖 **[!UICONTROL delivery]** 放，然 **[!UICONTROL is equal to]** 后选择投放作为值。
1. 在 **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**&#x200B;中，拖放 **[!UICONTROL type]** 并检 **[!UICONTROL Open]** 查为值。
1. 在规则之间选择运算符 **[!UICONTROL except]**。
1. 单击 **[!UICONTROL Confirm]**.

## 创建sms投放{#creating-a-sms-delivery}

1. 在每个区段之后拖放一个sms投放。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 以进行编辑。
1. 选择 **[!UICONTROL Simple sms]** 并单击 **[!UICONTROL Next]**。
1. Select an sms template and click **[!UICONTROL Next]**.
1. Enter the sms properties and click **[!UICONTROL Next]**.
1. To create the layout of your sms, click on **[!UICONTROL Email Designer]**.
1. 插入元素或选择现有模板。
1. 利用各个位置特定的优惠个性化您的短信。
有关详细信息，请参 [阅设计sms](../../channels/using/creating-an-sms-message.md) 部分。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**。

![](assets/wf-retargeting-non-openers.png)

**相关主题：**

* [电子邮件渠道](../../channels/using/creating-an-email.md)
