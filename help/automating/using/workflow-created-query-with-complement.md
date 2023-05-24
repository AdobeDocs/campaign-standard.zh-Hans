---
title: 使用补充创建投放
description: 此使用案例顯示如何使用補充來建立傳送。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,segmentation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5cd71e07-f955-4c15-bdfb-14b0daccec1a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 41%

---

# 使用补充创建投放 {#deliveries-with-complement}

您可以傳送電子郵件給客戶：一個用於不到一年前建立的客戶，另一個用於超過一年前建立的客戶。

1. 在 **[!UICONTROL Marketing Activities]** 中，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 作为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 建立查詢活動 {#create-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放[查询](../../automating/using/query.md)活动。
1. 双击该活动。
1. 在 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 並選取 **[!UICONTROL email]** 使用運運算元 **[!UICONTROL is not empty]**.
1. 在 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 並選取 **[!UICONTROL no longer contact by email]** 包含值 **[!UICONTROL no]**.
1. 单击 **[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## 建立細分活動 {#create-a-segmentation-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**，拖放 [細分](../../automating/using/segmentation.md) 活動並連按兩下。
1. 暫留在區段上，然後按一下 ![](assets/edit_darkgrey-24px.png) ，以定位今年新增到資料庫中的客戶。
1. 拖放 **[!UICONTROL Profiles]** 並選取 **[!UICONTROL Created]** 使用篩選器型別 **[!UICONTROL Relative]**.
1. 變更 **[!UICONTROL Level of precision]** 至 **[!UICONTROL Year]** 並選取 **[!UICONTROL This year]**.
1. 单击 **[!UICONTROL Confirm]** 两次。
1. 在 **[!UICONTROL Advanced Options]**，檢查 **[!UICONTROL Generate complement]** 建立以其他收件者為目標的區段。
1. 单击 **[!UICONTROL Confirm]**。
1. 单击 **[!UICONTROL Save]**。

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>若要觀察規則的結構，請按一下 **[!UICONTROL Advanced Mode]**.

## 创建电子邮件投放 {#create-an-email-delivery}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Channels]**，拖放 [電子郵件傳遞](../../automating/using/email-delivery.md) 活動於每個區段之後。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 以进行编辑。
1. 选择 **[!UICONTROL Single send email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用每個傳遞的特定優惠方案個人化您的電子郵件。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**。

有关更多信息，请参阅[设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

![](assets/wf-deliveries-with-a-complement.png)
