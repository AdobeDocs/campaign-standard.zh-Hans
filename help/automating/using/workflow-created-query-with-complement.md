---
title: 使用补充创建投放
description: 此用例说明如何使用补充创建投放。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,segmentation
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 5%

---


# 使用补充创建投放 {#deliveries-with-complement}

您可以向客户发送电子邮件： 一款面向不到一年前创建的客户，一款面向一年多前创建的客户。

1. 在中 **[!UICONTROL Marketing Activities]**，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 创建查询活动 {#create-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放一个 [查询](../../automating/using/query.md) 活动。
1. 多次单击活动。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放并 **[!UICONTROL Profiles]** 使用运 **[!UICONTROL email]** 算符进行选择 **[!UICONTROL is not empty]**。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放并 **[!UICONTROL Profiles]** 使用值 **[!UICONTROL no longer contact by email]** 进行选择 **[!UICONTROL no]**。
1. 单击 **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## 创建分段活动 {#create-a-segmentation-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放分段 [活动](../../automating/using/segmentation.md) ，然后多次单击它。
1. 将鼠标悬停在区段上，然后单 ![](assets/edit_darkgrey-24px.png) 击以目标今年在数据库中添加的客户。
1. 拖放并 **[!UICONTROL Profiles]** 使用筛 **[!UICONTROL Created]** 选器类型进行选择 **[!UICONTROL Relative]**。
1. 将更改 **[!UICONTROL Level of precision]** 为并 **[!UICONTROL Year]** 选择 **[!UICONTROL This year]**。
1. 单击 **[!UICONTROL Confirm]** 两次。
1. 在中 **[!UICONTROL Advanced Options]**，选 **[!UICONTROL Generate complement]** 中以创建定位其余收件人的区段。
1. 单击 **[!UICONTROL Confirm]**.
1. 单击 **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>要观察规则的结构，请单击 **[!UICONTROL Advanced Mode]**。

## 创建电子邮件投放 {#create-an-email-delivery}

1. 在> **[!UICONTROL Activities]** 中 **[!UICONTROL Channels]**，将电子邮件投放 [](../../automating/using/email-delivery.md) 活动拖放到每个区段之后。
1. 单击活动，然 ![](assets/edit_darkgrey-24px.png) 后选择编辑。
1. 选择 **[!UICONTROL Single send email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用特定于每个优惠的投放个性化您的电子邮件。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**.

有关详细信息，请参阅 [设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

![](assets/wf-deliveries-with-a-complement.png)
