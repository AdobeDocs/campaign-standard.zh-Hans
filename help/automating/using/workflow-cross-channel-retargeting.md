---
title: 重新定位未打开者
description: 此用例展示了如何重新定位非打开者。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: cba4e5c6-8acd-47a1-824e-14415e90d451
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 38%

---

# 重定向工作流 — 向未打开者发送新投放{#retargeting-delivery-to-non-openers}

您可以向客户发送电子邮件，然后向未打开邮件的用户发送短信。

1. 在 **[!UICONTROL Marketing Activities]** 中，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 作为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 创建查询活动{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放[查询](../../automating/using/query.md)活动。
1. 双击该活动。
1. In **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 并选择 **[!UICONTROL email]** 带有运算符 **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 并选择 **[!UICONTROL no longer contact by email]** 具有值 **[!UICONTROL no ]**.
1. 单击 **[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## 创建电子邮件投放{#creating-an-email-delivery}

1. 拖放 [电子邮件投放](../../automating/using/email-delivery.md) 在每个区段之后。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 以进行编辑。
1. 选择 **[!UICONTROL Simple email]** 并单击 **[!UICONTROL Next]**。
1. 选择 **[!UICONTROL Add an outbound transition without the population]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Using the Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用特定于每个位置的优惠来个性化您的电子邮件。有关更多信息，请参阅 [设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**。

## 在查询活动中定位非打开者{#targeting-non-openers-in-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**，拖放 [等待](../../automating/using/wait.md) 活动。
1. In **[!UICONTROL Duration]**，单击 ![](assets/duration-icon.png) 并选择一天。
1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放 **[!UICONTROL Query activity]**。
1. 双击该活动。
1. In **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Tracking Logs]** 和运算符 **[!UICONTROL exists]**.
1. In **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**，拖放 **[!UICONTROL delivery]** 带有运算符 **[!UICONTROL is equal to]** 并选择投放作为值。
1. In **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**，拖放 **[!UICONTROL type]** 和检查 **[!UICONTROL Open]** 作为值。
1. 选择规则之间的运算符为 **[!UICONTROL except]**.
1. 单击 **[!UICONTROL Confirm]**。

## 创建短信投放{#creating-a-sms-delivery}

1. 在每个区段后拖放短信投放。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 以进行编辑。
1. 选择 **[!UICONTROL Simple sms]** 并单击 **[!UICONTROL Next]**。
1. 选择短信模板并单击 **[!UICONTROL Next]**.
1. 输入短信属性并单击 **[!UICONTROL Next]**.
1. 要创建短信的布局，请单击 **[!UICONTROL Email Designer]**.
1. 插入元素或选择现有模板。
1. 使用特定于每个位置的优惠，个性化您的短信。
欲了解更多信息，请参见 [设计短信](../../channels/using/creating-an-sms-message.md) 部分。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**。

![](assets/wf-retargeting-non-openers.png)

**相关主题：**

* [电子邮件渠道](../../channels/using/creating-an-email.md)
